# Skill — Stack de Herramientas N8N

## Principio

> Siempre usar el nodo nativo de n8n antes que HTTP Request genérico.
> Los nodos nativos manejan autenticación, paginación y errores automáticamente.

---

## Por caso de uso

### Comunicación y notificaciones

| Necesidad | Nodo recomendado | Notas |
|---|---|---|
| Enviar email | Gmail / Outlook / SMTP | Gmail para G Workspace, SMTP para servidores propios |
| WhatsApp | WhatsApp Business Cloud | Requiere Meta Business API |
| Telegram | Telegram | Bot API, muy confiable y fácil |
| Slack | Slack | Webhook o Bot según si necesitas leer mensajes |
| SMS | Twilio | Nodo nativo disponible |
| Notificación interna | Slack / Discord / Teams | Según lo que use el cliente |

### Almacenamiento de datos

| Necesidad | Nodo recomendado | Cuándo usarlo |
|---|---|---|
| Hoja de cálculo simple | Google Sheets | Hasta ~10.000 filas, no para producción crítica |
| Base de datos relacional | PostgreSQL / MySQL | Datos estructurados, volumen alto |
| Base de datos flexible | MongoDB | Datos variables o anidados |
| Base de datos serverless | Supabase | Si el cliente no quiere administrar servidor |
| Almacenamiento de archivos | Google Drive / S3 / Dropbox | Según lo que ya use el cliente |
| Base de datos simple en nube | Airtable | Pequeñas empresas, fácil de gestionar sin técnico |

### Procesamiento de datos

| Necesidad | Nodo recomendado | Notas |
|---|---|---|
| Transformar/limpiar datos | Set / Edit Fields | Para mapeos simples |
| Lógica condicional | IF / Switch | IF para 2 caminos, Switch para múltiples |
| Iterar sobre arrays | SplitInBatches / Loop | SplitInBatches para volumen alto |
| Código personalizado | Code (JavaScript) | Cuando los nodos no alcanzan |
| Parsear JSON/XML | n8n nativo | Set + expresiones `{{$json}}` |
| Esperar entre pasos | Wait | Útil para polling o delays |
| Combinar flujos | Merge | Para unir ramas paralelas |

### Inteligencia Artificial

| Necesidad | Nodo recomendado | Modelo sugerido |
|---|---|---|
| Generar texto / analizar | OpenRouter (HTTP) | `anthropic/claude-3.5-sonnet` |
| Agente conversacional | AI Agent (LangChain) | Claude o GPT-4o según presupuesto |
| Clasificar / categorizar | OpenRouter (HTTP) | `anthropic/claude-haiku` (más barato) |
| Extraer datos de texto | OpenRouter (HTTP) | Claude 3.5 Sonnet |
| Embeddings / búsqueda semántica | OpenAI Embeddings | Con Pinecone o Supabase pgvector |
| Generar imágenes | Placid | Para imágenes templated/consistentes |

### CRM e integraciones de ventas

| Sistema | Nodo | Notas |
|---|---|---|
| HubSpot | HubSpot (nativo) | Contactos, deals, pipelines |
| Pipedrive | Pipedrive (nativo) | Deals y actividades |
| Salesforce | Salesforce (nativo) | Enterprise, más complejo |
| Zoho | Zoho CRM (nativo) | Alternativa económica |
| Sin CRM | Google Sheets + n8n | Para clientes muy pequeños |

### E-commerce

| Sistema | Nodo | Notas |
|---|---|---|
| Shopify | Shopify (nativo) | Órdenes, productos, clientes |
| WooCommerce | WooCommerce (nativo) | WordPress-based |
| Tiendanube | HTTP Request | No tiene nodo nativo — usar API REST |
| MercadoLibre | HTTP Request | API REST documentada |

### Facturación Colombia

| Sistema | Nodo | Notas |
|---|---|---|
| Siigo | HTTP Request | API REST, bien documentada |
| Alegra | HTTP Request | API REST, fácil de integrar |
| Factus | HTTP Request | DIAN electrónica |
| Helisa | Consultar | APIs limitadas, evaluar caso a caso |

### Pagos

| Sistema | Nodo | Notas |
|---|---|---|
| Stripe | Stripe (nativo) | Internacional, mejor documentado |
| PayU Colombia | HTTP Request | Nodo nativo no disponible |
| Wompi (Bancolombia) | HTTP Request | Webhook para confirmaciones |
| MercadoPago | HTTP Request | Latam, bien documentado |

---

## Decisiones arquitecturales comunes

### ¿Cuándo usar sub-workflows?
- Cuando la misma lógica se repite en 2+ workflows → extraer a sub-workflow
- Cuando un workflow supera ~25 nodos → dividir en módulos
- Para separar responsabilidades (extracción / procesamiento / envío)

### ¿Cuándo usar Code node vs nodos nativos?
**Usar nodos nativos si:**
- Existe un nodo para lo que necesitas
- La transformación es simple (mapear campos, filtrar)

**Usar Code node si:**
- Necesitas lógica compleja (loops anidados, recursión)
- Procesamiento de texto avanzado
- Operaciones matemáticas complejas
- El nodo nativo no tiene la operación específica

### ¿Cuándo n8n Cloud vs self-hosted?
| Criterio | Cloud | Self-hosted |
|---|---|---|
| El cliente no tiene equipo técnico | ✓ | |
| Presupuesto limitado (corto plazo) | ✓ | |
| Datos muy sensibles | | ✓ |
| Alto volumen de ejecuciones (>10k/mes) | | ✓ (más barato) |
| Control total sobre la infraestructura | | ✓ |
| Inicio rápido sin configuración | ✓ | |

**Precios n8n Cloud (referencia):**
- Starter: $20 USD/mes — 2.500 ejecuciones, 5 workflows activos
- Pro: $50 USD/mes — 10.000 ejecuciones, workflows ilimitados
- Enterprise: cotizar

**Self-hosted costos:**
- VPS básico (DigitalOcean/Hetzner): $5-15 USD/mes
- n8n: gratuito (open source)
- Total: $5-15 USD/mes vs $20-50 USD/mes en cloud

---

## Nodos que siempre deberían estar en workflows de producción

1. **Error Trigger** → captura errores y notifica por Telegram/email
2. **IF** antes de operaciones críticas → validar que los datos son correctos
3. **Set** para limpiar y normalizar datos → no pasar datos sucios a las siguientes etapas
4. **Wait** en loops que llaman APIs externas → respetar rate limits
