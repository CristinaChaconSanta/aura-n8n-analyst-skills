# Skill — Social Listening e Inteligencia Digital

## Qué es social listening (para explicarlo sin jerga)

Social listening es monitorear automáticamente lo que se dice sobre una marca,
un competidor o una industria en internet — en redes sociales, prensa, foros,
blogs y medios especializados — y convertir eso en información útil para tomar
decisiones.

El resultado puede ser:
- Alertas en tiempo real cuando mencionan la marca
- Reportes semanales de sentimiento (positivo / negativo / neutro)
- Análisis de competidores
- Monitoreo de tendencias de industria
- Detección de crisis reputacionales antes de que escalen

---

## Fuentes de información por tipo de necesidad

### Redes sociales
| Fuente | Qué entrega | Acceso |
|---|---|---|
| Instagram Graph API | Posts, comentarios, métricas de cuenta propia + menciones | Requiere cuenta Business + token |
| TikTok API | Videos públicos, tendencias, hashtags | API oficial limitada; datos públicos disponibles |
| YouTube Data API | Videos, comentarios, estadísticas de canal | API de Google, gratuita con límites |
| Reddit API | Conversaciones en subreddits, menciones, sentimiento | Gratuita con registro |
| X / Twitter API | Menciones, hashtags, tendencias, sentimiento | Pago desde 2023 — evaluar caso por caso |
| Facebook | Datos muy limitados por privacidad desde Cambridge Analytica | Solo páginas propias del cliente |

### Noticias y prensa
| Fuente | Qué entrega |
|---|---|
| NewsAPI | Noticias de +80,000 fuentes globales en tiempo real |
| GDELT Project | Monitoreo masivo de prensa global, gratuito |
| Mediastack | Noticias por país, idioma, categoría — incluye Colombia/Latam |
| Google News RSS | Alertas por término de búsqueda, gratuito |
| RSS de medios especializados | Suscripción directa a El Tiempo, Portafolio, La República, Semana, etc. |

### Industria creativa, publicidad y marketing
| Fuente | Qué entrega |
|---|---|
| Cannes Lions Archive | Casos ganadores por año, categoría, marca, país |
| Effie Worldwide | Casos de efectividad publicitaria con resultados de negocio |
| WARC | Investigación de marketing, effectiveness data, trends |
| Ad Age / Campaign Brief / LIA | Noticias de industria, rankings, tendencias creativas |
| Kantar / Nielsen | Datos de audiencia y consumo de medios (acceso de pago) |

### Analytics propios del cliente
| Fuente | Qué entrega | Requiere |
|---|---|---|
| Google Analytics 4 API | Tráfico web, comportamiento, conversiones | Acceso a la propiedad GA4 |
| Meta Business Suite API | Alcance, engagement, demografía de Facebook/Instagram | Cuenta Business + permisos |
| LinkedIn Analytics API | Métricas de página de empresa, alcance de posts | Admin de página |
| Google Search Console | Visibilidad en búsquedas, palabras clave, clics | Acceso verificado al sitio |

---

## Qué puede construir Aura en esta área

### Monitoreo de marca
Un sistema que rastrea menciones de la marca en redes y prensa, clasifica el
sentimiento automáticamente y envía un resumen diario o semanal al equipo.
No requiere que nadie busque manualmente — la información llega sola.

### Inteligencia competitiva
Monitoreo de los competidores: qué publican, cómo les va, qué dice la prensa
sobre ellos, qué campañas están corriendo. Reporte periódico con comparativo.

### Diagnóstico de marca para propuestas
Para agencias que hacen diagnósticos como parte de su proceso comercial o
de onboarding: sistema que, dado el nombre de una marca, recopila automáticamente
sus mensajes clave en redes, cobertura de prensa reciente, actividad de competidores
y tendencias de su industria — y entrega un brief estructurado.

### Reporte de lanzamiento / relanzamiento
Después de un lanzamiento de marca: sistema que monitorea el impacto en medios
digitales, cuantifica menciones, sentimiento y alcance, y genera un informe de
resultados con KPIs.

### Tendencias de industria
Rastreo semanal de medios especializados, Cannes Lions, WARC y publicaciones
de referencia para entregar un resumen de tendencias relevantes para el cliente.

---

## Lo que NO es automatizable completamente

- **Interpretación estratégica del dato:** una máquina puede decir "el sentimiento
  bajó 12 puntos esta semana" — qué hacer con eso sigue siendo decisión humana.
- **Análisis cualitativo profundo:** los matices culturales, el humor, la ironía
  en comentarios requieren lectura humana para interpretación real.
- **Datos de plataformas cerradas:** WhatsApp, DMs de Instagram, conversaciones
  privadas — no son accesibles. Solo contenido público.
- **Scraping de LinkedIn:** LinkedIn prohíbe el rastreo automatizado. Alternativa
  legal para datos de contacto: Apollo.io, Hunter.io.

---

## Cómo presentar esta capacidad al cliente

**No decir:** "Conectamos la API de NewsAPI y hacemos análisis de sentimientos con IA"

**Sí decir:**
> "Desarrollamos un sistema de inteligencia de marca que monitorea automáticamente
> lo que se dice sobre su marca y su industria en medios digitales, redes sociales
> y prensa especializada. El equipo recibe un reporte estructurado con la frecuencia
> que definan — sin tener que buscar nada manualmente."

**Para diagnósticos de cliente:**
> "Construimos un módulo de diagnóstico que, con el nombre de la marca, recopila
> automáticamente su presencia digital, cobertura de prensa, actividad competitiva
> y tendencias de industria — y lo entrega en un brief listo para trabajar."

---

## Preguntas clave antes de proponer esta solución

1. ¿Qué marcas o términos necesitan monitorear? (marca propia, competidores, industria)
2. ¿Con qué frecuencia necesitan el reporte? (tiempo real, diario, semanal)
3. ¿Dónde quieren recibir la información? (email, Slack, dashboard, documento)
4. ¿Ya tienen alguna herramienta de monitoreo activa?
5. ¿Los datos son para uso interno o para presentar a clientes finales?
6. ¿En qué países o idiomas opera la marca?
