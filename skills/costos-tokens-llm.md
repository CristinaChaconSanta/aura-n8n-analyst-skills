# Skill — Costos de Tokens y Modelos de IA

## Cómo funciona el cobro de LLMs

Los modelos de lenguaje cobran por **tokens** — fragmentos de texto de
aproximadamente 4 caracteres o 0.75 palabras en inglés (en español son
ligeramente más tokens por la longitud de las palabras).

El costo tiene dos componentes:
- **Tokens de entrada (input):** lo que se le envía al modelo (instrucciones + datos)
- **Tokens de salida (output):** lo que el modelo genera como respuesta

El output siempre es más caro que el input. La mayoría de automatizaciones
generan más input que output, lo que favorece el costo real.

**Referencia rápida:** 1,000 tokens ≈ 750 palabras en inglés / ≈ 600 palabras en español

**Conversión USD a COP:** 1 USD ≈ $4.200 – $4.400 COP (verificar antes de cotizar)

---

## Precios por modelo — referencia 2026

> ⚠️ Los precios de LLMs cambian con frecuencia. Verificar antes de cotizar en:
> - Anthropic: https://anthropic.com/pricing
> - OpenAI: https://openai.com/api/pricing
> - Google: https://ai.google.dev/pricing
> - Groq: https://console.groq.com/docs/openai

### Anthropic Claude (recomendado por Aura)

| Modelo | Input / 1M tokens | Output / 1M tokens | Ideal para |
|---|---|---|---|
| Claude Opus 4.6 | $15 USD | $75 USD | Análisis estratégico complejo, razonamiento profundo |
| Claude Sonnet 4.6 | $3 USD | $15 USD | Workflows de producción, propuestas, análisis |
| Claude Haiku 4.5 | $0.80 USD | $4 USD | Clasificación, resúmenes, tareas repetitivas |

### OpenAI GPT

| Modelo | Input / 1M tokens | Output / 1M tokens | Ideal para |
|---|---|---|---|
| GPT-4o | $2.50 USD | $10 USD | Propósito general, multimodal (texto + imagen) |
| GPT-4o mini | $0.15 USD | $0.60 USD | Tareas simples, clasificación, extracción de datos |
| GPT-4.1 | $2 USD | $8 USD | Balance costo/calidad para producción |
| o3-mini | $1.10 USD | $4.40 USD | Razonamiento y lógica compleja |

### Google Gemini

| Modelo | Input / 1M tokens | Output / 1M tokens | Ideal para |
|---|---|---|---|
| Gemini 2.5 Pro | $1.25 USD | $10 USD | Contexto largo (hasta 1M tokens), documentos extensos |
| Gemini 2.0 Flash | $0.10 USD | $0.40 USD | Velocidad + bajo costo, producción liviana |
| Gemini 1.5 Flash | $0.075 USD | $0.30 USD | El más económico para tareas sencillas |

### Modelos open source vía proveedores (Groq, Together.ai)

| Modelo | Costo aprox / 1M tokens | Ideal para |
|---|---|---|
| Llama 3.3 70B (Groq) | ~$0.59 input / $0.79 output | Tareas generales sin costo de marca |
| Llama 3.1 405B (Together.ai) | ~$3.50 / $3.50 | Alto rendimiento sin licencia OpenAI/Anthropic |
| Mixtral 8x7B (Groq) | ~$0.24 / $0.24 | Muy económico para clasificación y extracción |

### Perplexity API (para búsqueda en tiempo real + IA)

| Modelo | Costo | Notas |
|---|---|---|
| sonar | $1 / $1 por 1M tokens + $5 por 1.000 búsquedas | Noticias y web en tiempo real |
| sonar-pro | $3 / $15 por 1M tokens + $5 por 1.000 búsquedas | Más profundidad en la búsqueda |

---

## Generación de imágenes

| Herramienta | Costo por imagen | Notas |
|---|---|---|
| DALL-E 3 (OpenAI) — estándar | $0.040 USD (~$170 COP) | 1024×1024 |
| DALL-E 3 (OpenAI) — HD | $0.080 USD (~$340 COP) | Mayor detalle |
| Stable Diffusion XL (Replicate) | ~$0.002 USD (~$9 COP) | Open source, muy económico |
| Flux Pro (Replicate) | ~$0.055 USD (~$230 COP) | Alta calidad fotorrealista |
| Flux Schnell (Replicate) | ~$0.003 USD (~$13 COP) | Rápido y económico |
| Placid / Bannerbear | Plan mensual fijo | Templates — sin costo por imagen de IA |

> Para generación de piezas de marca (carruseles, posts) con templates:
> Placid o Bannerbear son más predecibles en costo y calidad que la IA generativa.
> IA generativa recomendada para conceptos, mockups y contenido creativo.

---

## Audio y voz

| Servicio | Costo | Notas |
|---|---|---|
| OpenAI Whisper (transcripción) | $0.006 USD/minuto | 1 hora de audio ≈ $0.36 USD |
| OpenAI TTS-1 (voz sintética) | $15 USD / 1M caracteres | Calidad estándar |
| OpenAI TTS-1-HD | $30 USD / 1M caracteres | Alta calidad |
| ElevenLabs | Desde $0.30 USD / 1.000 caracteres (plan pago) | Voces muy realistas, clonación de voz |

---

## Video generativo

| Servicio | Costo | Notas |
|---|---|---|
| Runway ML Gen-3 | ~$0.05 USD/segundo de video | 10 seg de video ≈ $0.50 USD |
| Creatomate (template-based) | Desde $29 USD/mes (500 renders) | Más predecible, ideal para producción |
| Shotstack | Desde $29 USD/mes | Edición programática de video |

---

## Costo real por tipo de workflow — estimaciones prácticas

Estas son las estimaciones más útiles para cotizar. Los costos de IA en
producción suelen sorprender al cliente por lo bajos que son.

### Agente de email (clasificación + respuestas automáticas)
```
100 emails/día = 3.000 emails/mes
Promedio por email: ~500 tokens entrada + 200 tokens salida
Total mensual: ~2,1M tokens
Con Claude Haiku:  ~$2,5 USD/mes   → ~$10.500 COP/mes
Con GPT-4o mini:   ~$0,5 USD/mes   → ~$2.100 COP/mes
```

### Agente de prospección semanal
```
4 ejecuciones/mes
Por ejecución: analiza 30 empresas × 2.000 tokens + reporte 3.000 tokens
Total mensual: ~0,3M tokens entrada + 0,05M tokens salida
Con Claude Sonnet: ~$1,5 USD/mes  → ~$6.300 COP/mes
Con GPT-4o mini:   ~$0,05 USD/mes → ~$210 COP/mes
```

### Generador de propuestas comerciales
```
20 propuestas/mes
Por propuesta: brief + contexto ~5.000 tokens + propuesta generada ~4.000 tokens
Total mensual: ~0,18M tokens
Con Claude Sonnet: ~$1,1 USD/mes  → ~$4.600 COP/mes
Con GPT-4o:        ~$0,6 USD/mes  → ~$2.500 COP/mes
```

### Social listening con resumen semanal
```
4 resúmenes/mes
Por ejecución: procesa 50 artículos × 1.500 tokens + resumen 2.000 tokens
Total mensual: ~0,32M tokens
Con Gemini Flash:  ~$0,03 USD/mes  → ~$126 COP/mes   ← casi gratuito
Con Claude Haiku:  ~$0,30 USD/mes  → ~$1.260 COP/mes
```

### Pipeline comercial + reporte semanal
```
~200 actualizaciones/mes + 4 reportes
Por operación: ~300 tokens entrada + 200 tokens salida
Total mensual: ~0,1M tokens
Con cualquier modelo económico: < $0,10 USD/mes → < $420 COP/mes
```

### Generación de imágenes — carrusel semanal
```
2 publicaciones/semana × 6 imágenes = 48 imágenes/mes
Con Placid (templates):  costo fijo del plan, no por imagen
Con DALL-E 3 estándar:   48 × $0,04 = $1,92 USD/mes → ~$8.000 COP/mes
Con Flux Schnell:        48 × $0,003 = $0,14 USD/mes → ~$600 COP/mes
```

---

## Conclusión clave para cotizaciones

**El costo de IA en producción es sorprendentemente bajo.**
En la mayoría de automatizaciones para agencias y PYMEs, el costo mensual
de tokens oscila entre $1 y $30 USD/mes ($4.000 – $125.000 COP/mes).

Lo que hace caro un proyecto no son los tokens — es la construcción,
la arquitectura y el mantenimiento.

**Cómo presentarlo al cliente:**
> "El costo de operación del sistema depende del volumen de uso.
> Para el flujo que están manejando hoy, la estimación es entre
> $X y $Y USD/mes en costos de IA — aproximadamente $[COP] al mes.
> Eso va incluido en el mantenimiento o lo maneja el cliente directamente
> según prefieran."

**Para proyectos con volumen alto o incierto:**
Incluir un rango en la propuesta y aclarar que se ajusta según uso real.
No fijar un número que luego no corresponda — genera desconfianza.

---

## Elección del modelo según caso de uso

| Prioridad | Modelo recomendado |
|---|---|
| Máxima calidad / análisis estratégico | Claude Sonnet 4.6 o GPT-4o |
| Balance costo/calidad para producción | Claude Haiku 4.5 o GPT-4o mini |
| Contexto muy largo (documentos, PDFs) | Gemini 2.5 Pro |
| Búsqueda web en tiempo real + IA | Perplexity sonar |
| Mínimo costo para tareas simples | Gemini Flash o GPT-4o mini |
| Sin dependencia de proveedor US | Llama vía Groq o Together.ai |
