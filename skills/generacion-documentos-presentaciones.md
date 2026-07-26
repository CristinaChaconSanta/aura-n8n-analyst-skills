# Skill — Generación de Documentos, Presentaciones y Contenido Visual

## El universo de posibilidades (más allá de PPT y Google Slides)

La generación automática de documentos y presentaciones es uno de los casos de uso
más demandados. Existe un ecosistema amplio — conocerlo permite proponer la solución
correcta según el diseño, el flujo de trabajo del cliente y el nivel de personalización
que necesita.

---

## Presentaciones

### Por caso de uso

| Herramienta | Cuándo es la mejor opción | Control de diseño |
|---|---|---|
| **Google Slides API** | Cliente en Google Workspace, necesita editar después | Alto — diseño custom por slide |
| **PowerPoint (.pptx programático)** | Cliente en Microsoft 365 o usa Keynote | Alto — abre en Keynote sin pérdida de formato |
| **Canva API** | Cliente tiene templates en Canva, quiere automatizar su llenado | Muy alto si tiene templates propios |
| **Gamma.app** | Quiere que la IA genere estructura visual sola, velocidad > control | Medio — estética automática |
| **Pitch.com** | Startups, equipo comercial que colabora en tiempo real | Medio |
| **HTML → PDF / slides** | Control total de diseño, no necesita editar después | Total — diseño exacto en código |
| **Slidev** | Presentaciones técnicas, desarrolladores | Alto, basado en Markdown |

### Sobre Keynote
Keynote no tiene API pública. No es automatizable directamente.
**Solución real:** generar el archivo como .pptx → el cliente lo abre en Keynote.
El formato, fuentes y diseño se mantienen en un 95%+.
Esto no es una limitación — es un paso invisible para el cliente final.

**Cómo decirlo:**
> "El output es un archivo de presentación que el equipo puede abrir directamente
> en Keynote o en PowerPoint — el diseño de su plantilla se mantiene intacto."

---

## PDFs y documentos formales

| Necesidad | Solución | Nivel de personalización |
|---|---|---|
| PDF de propuesta con diseño de marca | PDFMonkey — templates HTML/CSS con variables dinámicas | Muy alto |
| PDF desde diseño exacto en HTML | Puppeteer o Playwright (headless browser) | Total |
| Documentos Word (.docx) con variables | Carbone.io — reemplaza variables en templates Word/Excel | Alto |
| Contratos, informes, brand guidelines | Carbone.io o PDFMonkey según complejidad | Alto |
| PDF simple desde texto estructurado | DocRaptor, WeasyPrint | Medio |
| Cotizaciones y facturas automatizadas | Carbone.io + template .docx del cliente | Alto |

### Cómo funciona el pipeline de documentos
```
Template (diseñado una vez por el cliente)
+ Datos dinámicos (del formulario / CRM / base de datos)
= Documento final generado automáticamente
```
El cliente mantiene el control del diseño — Aura construye el sistema que lo llena.

---

## Imágenes

### Desde templates con contenido dinámico (recomendado para producción)
| Herramienta | Cuándo usarla |
|---|---|
| **Placid** | Templates visuales con texto e imagen variables — piezas de carrusel, posts, banners |
| **Bannerbear** | Similar a Placid, buena API, templates de marketing |
| **Canva API** | Cliente ya diseña en Canva, quiere automatizar variaciones |
| **HTML → imagen (Puppeteer)** | Control total de diseño, variaciones masivas |

### Generación con IA (imágenes creativas, mockups, conceptos)
| Herramienta | Caso de uso | Nivel de calidad actual |
|---|---|---|
| DALL-E API (OpenAI) | Conceptos visuales, ilustraciones, mockups rápidos | Muy alto |
| Stable Diffusion (via Replicate) | Control de estilo, open source, más personalizable | Alto con configuración |
| Adobe Firefly API | Imágenes con licencia comercial segura, coherentes con Adobe | Alto |
| Midjourney | Calidad artística máxima | Sin API oficial — proceso manual |

**Límite importante:** la IA genera imágenes conceptuales — no reemplaza fotografía de producto
ni dirección de arte creativa. Es ideal para referencias, mockups preliminares, variaciones rápidas.

---

## Video

### Videos con templates editables (producción automatizada)
| Herramienta | Cuándo usarla |
|---|---|
| **Creatomate** | Videos de marca, reels, anuncios — template + variables = video final. API robusta |
| **Shotstack** | Edición de video programática — cortes, texto, audio, transiciones |
| **Lumen5** | Video desde texto / blog posts — orientado a contenido de redes |

### Videos con IA generativa
| Herramienta | Tipo de contenido |
|---|---|
| **Runway ML** | Video generativo, motion, efectos — estado del arte actual |
| **HeyGen API** | Avatar presentando con voz sintetizada — presentaciones, demos |
| **Sora (OpenAI)** | Próximamente — mayor realismo, aún en acceso limitado |

**Lo que es viable automatizar:** videos de marca con template fijo, variaciones de anuncio,
resúmenes de reporte en formato video, presentaciones con avatar.

**Lo que no:** producción audiovisual creativa, storytelling de alto nivel — eso requiere criterio humano.

---

## Animación de logos y motion

| Tipo de animación | Herramienta | Realismo |
|---|---|---|
| Logo con movimiento predefinido | **Lottie** — JSON animado, reproducible en web y apps | Alto para movimientos gráficos |
| Animación interactiva | **Rive** — animación en tiempo real, estados interactivos | Muy alto |
| Video animado programático | **Remotion** — React + código = video exportable | Total |
| After Effects → exportar animación | **Lottie** (plugin Bodymovin) | Depende del diseño |

**Límite honesto sobre animación de logos:**
Aura puede automatizar la **producción** de una animación definida — es decir, si el cliente
define el movimiento que quiere (o ya tiene un motion designer que lo diseñó), Aura construye
el sistema que lo genera y lo entrega. Lo que no puede automatizarse es la **dirección creativa**
del motion: decidir cómo debe moverse el logo, con qué ritmo, qué transmite. Eso es criterio de
un director de arte o motion designer.

**Cómo decirlo:**
> "Podemos automatizar la producción de la animación — necesitamos que el equipo defina
> primero cómo quieren que se mueva el logo, o trabajamos con el motion designer que ya tienen."

---

## Brand guidelines y toolkits

La automatización de brand guidelines tiene dos niveles:

### Nivel 1 — Estructura automatizada (viable hoy)
El cliente sube la presentación de identidad de marca → el sistema extrae los elementos clave
(paleta, tipografías, tono de voz, reglas de uso) y genera un documento estructurado base.
El equipo de diseño revisa y ajusta.

**Reducción real de tiempo:** de 8-12 horas de armado manual a 1-2 horas de revisión y ajuste.

### Nivel 2 — Generación completa (viable con inputs claros)
Si existe un template de brand guidelines con la estructura fija de la agencia, el sistema
puede llenar todas las secciones con los datos del cliente específico.

**Herramientas para el output:** Carbone.io (.docx), PDFMonkey (PDF), Canva API (visual).

---

## Casos de éxito (piezas para web o presentación)

Pipeline automatizable:
```
Información del proyecto (cliente, resultados, equipo)
→ IA redacta el texto del caso (contexto, desafío, solución, resultado)
→ Template visual del caso (diseñado una vez)
→ Sistema llena el template con texto e imágenes
→ Output: pieza lista para web o presentación
```

**Formatos de output:** imágenes (Placid/Bannerbear), PDF (PDFMonkey), slide (Google Slides API).

---

## Preguntas clave antes de proponer generación de documentos

1. ¿El cliente tiene una plantilla de diseño actual? (si sí → se replica; si no → se diseña una)
2. ¿El output necesita ser editable después de generarse? (define PPT vs PDF)
3. ¿Qué programa usa el cliente para presentaciones? (define el formato de entrega)
4. ¿Cuántas variaciones necesitan generar? (define si vale la pena automatizar)
5. ¿Los documentos incluyen datos de sistemas externos? (CRM, formulario, base de datos)
6. ¿Hay elementos visuales variables? (imágenes, logos de clientes, gráficos de datos)
