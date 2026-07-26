# Skill — Estimación de Tiempos

## Regla de oro

> Estima el tiempo técnico real, luego suma **30% de buffer** para pruebas, ajustes e imprevistos.
> Nunca prometas entrega sin tener los accesos del cliente confirmados.

---

## Tiempos por fase

| Fase | % del proyecto | Descripción |
|---|---|---|
| Análisis y diseño | 15% | Entender el proceso, diseñar el flujo, mapear datos |
| Construcción | 55% | Construir nodos, conectar integraciones, lógica |
| Pruebas | 20% | Pruebas unitarias, pruebas de integración, casos borde |
| Ajustes y entrega | 10% | Correcciones del cliente, documentación, handoff |

---

## Tiempos base por complejidad

### Automatización simple
**Características:** 1-5 nodos, trigger claro, sin APIs externas, datos simples
**Ejemplos:** Notificación por email cuando llega un form, copiar datos entre dos Google Sheets

| Fase | Tiempo |
|---|---|
| Análisis | 1-2h |
| Construcción | 2-4h |
| Pruebas | 1h |
| Ajustes | 1h |
| **Total real** | **5-8 horas** |
| **Con buffer (30%)** | **6-10 horas** |
| **Días calendario** | **1-2 días** |

---

### Automatización media
**Características:** 6-15 nodos, 1-2 APIs externas, transformación de datos, lógica condicional básica
**Ejemplos:** CRM sync, pipeline de leads, notificaciones multicanal, reportes automatizados

| Fase | Tiempo |
|---|---|
| Análisis | 2-4h |
| Construcción | 8-15h |
| Pruebas | 3-4h |
| Ajustes | 2-3h |
| **Total real** | **15-26 horas** |
| **Con buffer (30%)** | **20-34 horas** |
| **Días calendario** | **3-5 días** |

---

### Automatización compleja
**Características:** 16-30 nodos, múltiples APIs, lógica condicional avanzada, manejo de errores robusto
**Ejemplos:** Sistema de facturación automatizado, onboarding de clientes completo, sincronización entre 3+ sistemas

| Fase | Tiempo |
|---|---|
| Análisis | 4-8h |
| Construcción | 20-35h |
| Pruebas | 6-10h |
| Ajustes | 4-6h |
| **Total real** | **34-59 horas** |
| **Con buffer (30%)** | **44-77 horas** |
| **Días calendario** | **5-10 días hábiles** |

---

### Automatización con agente de IA
**Características:** LLM integrado, procesamiento de lenguaje natural, decisiones dinámicas
**Ejemplos:** Agente de atención al cliente, clasificador de emails, generador de contenido automatizado

| Fase | Tiempo |
|---|---|
| Análisis | 4-6h |
| Diseño del prompt/agente | 3-6h |
| Construcción | 15-25h |
| Pruebas (requiere más iteración) | 8-12h |
| Ajustes y fine-tuning | 5-8h |
| **Total real** | **35-57 horas** |
| **Con buffer (30%)** | **45-74 horas** |
| **Días calendario** | **7-12 días hábiles** |

---

## Factores que aumentan el tiempo

| Factor | Tiempo adicional |
|---|---|
| API sin documentación clara | +4-8h |
| Sistema legacy o propietario | +6-12h |
| Cliente tarda en dar accesos | Detiene el proyecto |
| Cambios de alcance en mitad del proyecto | +30-50% |
| Datos sucios que necesitan limpieza | +4-10h |
| Autenticación OAuth compleja | +2-4h |
| Webhooks que no tienen sandbox/test | +2-6h |

---

## Factores que reducen el tiempo

| Factor | Ahorro |
|---|---|
| Template de n8n existente y adaptable | -30-40% |
| Cliente con API bien documentada | -20% |
| Proceso muy similar a uno ya construido | -40-50% |
| Credenciales listas desde el día 1 | -15% del total |

---

## Comunicación de tiempos al cliente

**Nunca digas:** "lo tengo listo en 2 días"
**Di:** "el tiempo estimado es de 3-5 días hábiles, contando desde que tenga todos los accesos confirmados"

**Siempre aclara:**
- El tiempo empieza a correr cuando llegan los accesos
- Los cambios de alcance generan un nuevo estimado
- Las pruebas requieren participación del cliente (al menos 2-3h de su tiempo)
