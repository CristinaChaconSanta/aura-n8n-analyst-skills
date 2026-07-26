# Skill — Checklist de Accesos por Cliente

## Regla fundamental

> **No inicies construcción sin tener el 100% de los accesos confirmados.**
> Un acceso faltante puede paralizar el proyecto por días.
> Incluye este checklist en la propuesta y pide confirmación antes de agendar inicio.

---

## Accesos universales (todo proyecto)

- [ ] Acceso a la instancia de n8n donde se desplegará (URL + API Key, o credenciales de acceso)
- [ ] Decisión: ¿n8n Cloud o self-hosted? Si self-hosted: ¿quién administra el servidor?
- [ ] Email de contacto técnico del cliente (para dudas durante construcción)
- [ ] Ventana de pruebas acordada (horario en que se puede probar sin afectar operación)

---

## Por tipo de integración

### Google Workspace (Gmail, Sheets, Drive, Calendar, Docs)
- [ ] Cuenta de Google con los permisos necesarios
- [ ] Autorización OAuth en n8n (el cliente debe aprobar el consentimiento)
- [ ] Confirmar: ¿es cuenta personal o Google Workspace empresarial?
- [ ] Si Workspace: ¿el admin permite apps de terceros?

### WhatsApp Business
- [ ] Número de WhatsApp Business verificado
- [ ] Acceso a Meta Business Suite
- [ ] WhatsApp Business API configurada (Cloud API o BSP como Twilio/360dialog)
- [ ] Token de acceso permanente generado
- [ ] Webhook URL aprobado en el panel de Meta

### Telegram
- [ ] Bot token (creado via BotFather)
- [ ] Chat ID del grupo o canal destino (si aplica)
- [ ] Confirmar si es bot nuevo o existente

### CRM (HubSpot, Pipedrive, Salesforce, Zoho, etc.)
- [ ] API Key o credenciales OAuth del CRM
- [ ] Acceso a sandbox/ambiente de pruebas (ideal)
- [ ] Lista de propiedades/campos personalizados que se usarán
- [ ] Confirmar versión del CRM (algunas APIs varían por versión/plan)

### Email marketing (Mailchimp, ActiveCampaign, Brevo, etc.)
- [ ] API Key de la plataforma
- [ ] IDs de listas/audiencias que se usarán
- [ ] Confirmar límites del plan (algunos tienen rate limits bajos)

### E-commerce (Shopify, WooCommerce, Tiendanube)
- [ ] API Key + API Secret (Shopify) o Consumer Key/Secret (WooCommerce)
- [ ] URL de la tienda
- [ ] Webhooks habilitados en la plataforma
- [ ] Confirmar si es tienda de pruebas o producción

### Bases de datos (PostgreSQL, MySQL, MongoDB, Supabase, Airtable)
- [ ] Host, puerto, nombre de la base de datos
- [ ] Usuario y contraseña con permisos de lectura/escritura
- [ ] IP de n8n en whitelist del servidor (si hay firewall)
- [ ] Schema o estructura de tablas relevantes

### Facturación / ERP (Siigo, Alegra, SAP, Odoo)
- [ ] API Key o credenciales de integración
- [ ] Documentación de la API (especialmente si es sistema colombiano)
- [ ] Ambiente de pruebas disponible
- [ ] NIT de la empresa para pruebas de facturación

### Pagos (Wompi, PayU, Stripe, MercadoPago)
- [ ] API Keys de prueba (sandbox) + producción por separado
- [ ] Webhook secret para validación de firmas
- [ ] Confirmar monedas y países configurados

### Redes sociales (Instagram, Facebook, LinkedIn, TikTok)
- [ ] Acceso a Meta Business Suite / cuenta de desarrollador
- [ ] App ID y App Secret
- [ ] Token de acceso de página (no personal)
- [ ] Confirmar permisos necesarios según el uso (publish_pages, etc.)

### Almacenamiento (Dropbox, OneDrive, S3, Google Drive)
- [ ] Credenciales OAuth o API Keys
- [ ] Confirmar estructura de carpetas que se usará
- [ ] Permisos de lectura y escritura en las carpetas destino

### Notificaciones (Slack, Discord, Teams)
- [ ] Webhook URL del canal destino
- [ ] Si se necesita leer mensajes: Bot Token con permisos adecuados
- [ ] Canal o workspace donde se instala el bot

---

## Preguntas de contexto que siempre debes hacer

1. **¿Tienen equipo técnico interno?** → Define quién gestiona credenciales y servidor
2. **¿Tienen ambientes de prueba?** → Evita modificar datos reales en testing
3. **¿Cuál es el volumen esperado?** → Determina si necesitan plan de pago en n8n
4. **¿Hay datos sensibles involucrados?** → Determina nivel de seguridad requerido
5. **¿Quién aprueba los accesos en la empresa?** → No perder tiempo con la persona equivocada

---

## Plantilla de solicitud de accesos (para enviar al cliente)

```
Hola [Nombre],

Para iniciar la construcción de tu automatización necesito los siguientes accesos.
Por favor confirma cada uno antes de la fecha de inicio:

ACCESOS REQUERIDOS:
□ [Acceso 1] — [instrucciones de cómo obtenerlo]
□ [Acceso 2] — [instrucciones de cómo obtenerlo]
□ [Acceso 3] — [instrucciones de cómo obtenerlo]

IMPORTANTE:
- Los accesos deben ser de un usuario/cuenta específica para la integración,
  no de tu cuenta personal principal
- Guardaré los accesos de forma segura y los eliminaré al finalizar el proyecto
  (o los transferiré a tu nombre si así lo prefieres)
- El tiempo del proyecto empieza a correr desde que confirmes todos los accesos

¿Tienes alguna duda sobre cómo obtener alguno de estos accesos?

[Tu nombre]
```
