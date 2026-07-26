# Skill — Integraciones: Ecosistema Empresarial

## Principio

Antes de proponer qué construir, preguntar qué ya tienen.
El objetivo no es reemplazar herramientas que funcionan — es conectarlas,
automatizar el flujo entre ellas y eliminar el trabajo manual que vive
en los huecos entre sistemas.

---

## CRMs

### Los más comunes en el mercado

| CRM | Perfil de cliente | Qué puede automatizarse |
|---|---|---|
| **HubSpot** | Mediana empresa, marketing-driven | Crear/actualizar contactos, mover deals en pipeline, enviar emails automáticos, reportes, alertas |
| **Salesforce** | Grande / enterprise | Todo — API muy completa. Mayor complejidad de implementación |
| **Pipedrive** | Equipos comerciales small/mid | Actualizar deals, notificaciones, reportes de pipeline, sync con email |
| **Zoho CRM** | Presupuesto limitado, PYME | Similar a HubSpot, API funcional |
| **Monday CRM** | Equipos que ya usan Monday para proyectos | Sync de proyectos y clientes, notificaciones, reportes |
| **Notion como CRM** | Agencias, empresas creativas | Base de datos flexible, automatización con webhooks, reportes |
| **Google Sheets como CRM** | Micro/pequeña empresa en Colombia | El más común — totalmente automatizable, gratuito, el equipo ya lo conoce |
| **Excel en OneDrive/SharePoint** | Empresas con Microsoft 365 | Automatizable si está en la nube. Si está en PC local: no es automatizable directamente |

### Nota importante sobre Excel local
> Si el archivo de Excel está guardado en el computador de alguien (no en OneDrive ni SharePoint),
> no es accesible para automatización. La solución más simple: moverlo a Google Sheets o OneDrive.
> Es una migración de una sola vez que no cambia el flujo de trabajo del equipo.

---

## CMS (Gestión de contenido web)

| CMS | Perfil | Posibilidades de automatización |
|---|---|---|
| **WordPress** | La mayoría de webs colombianas | Publicar posts, actualizar páginas, sincronizar catálogos, gestionar medios — API REST completa |
| **Webflow** | Agencias de diseño, marcas premium | CMS collections via API — crear, actualizar, publicar entradas; automatizar blog y portafolio |
| **Contentful** | Proyectos headless modernos | API-first — muy automatizable, ideal para equipos con developer |
| **Strapi** | Open source, control total | API personalizable, self-hosted, sin costo de licencia |
| **Sanity.io** | Contenido estructurado, equipos de contenido | API potente, queries tipo GraphQL |
| **Shopify** | E-commerce | Pedidos, inventario, notificaciones, reportes, clientes — API completa |
| **Ghost** | Medios, newsletters, blogs | Publicación automática, sync de suscriptores, API limpia |
| **Notion** | Bases de conocimiento, webs simples | Sync de contenido, actualización de páginas, base de datos de recursos |

---

## Comunicación corporativa

### WhatsApp

| Tipo | Qué permite | Notas importantes |
|---|---|---|
| **WhatsApp Business API (oficial)** | Mensajes masivos, respuestas automáticas, notificaciones, chatbot | Requiere número de teléfono dedicado + proveedor autorizado |
| **Proveedores recomendados** | 360Dialog, Twilio, Gupshup, MessageBird | Cada uno tiene costos distintos — el cliente elige según volumen |
| **WhatsApp personal** | No automatizable | Términos de servicio de Meta lo prohíben — riesgo de bloqueo |

**Cómo presentarlo:**
> "Implementamos mensajería automática por WhatsApp usando la API oficial de Meta —
> con número propio del cliente, sin riesgo de bloqueo y con cumplimiento de sus políticas."

**Casos de uso frecuentes:** notificaciones de estado de pedido, confirmaciones de cita,
alertas internas de equipo, respuesta automática a consultas frecuentes, recordatorios.

### Telegram

| Aspecto | Detalle |
|---|---|
| API | Completamente abierta y gratuita |
| Nivel de automatización | Muy alto — sin restricciones de volumen |
| Mejor para | Notificaciones internas, reportes de equipo, alertas, bots de consulta |
| Adopción en Colombia | Creciente, especialmente en equipos tech y creativos |

**Ideal cuando:** el equipo ya usa Telegram internamente, o cuando se necesita un canal de
notificaciones sin costo de mensajería.

### Slack

| Aspecto | Detalle |
|---|---|
| API | Robusta, bien documentada |
| Nivel de automatización | Muy alto — mensajes, alertas, aprobaciones, bots |
| Mejor para | Equipos de agencias, startups, empresas con cultura digital |
| Casos de uso | Notificaciones de pipeline, alertas de mención de marca, reportes automáticos, aprobaciones de contenido |

### Microsoft Teams

| Aspecto | Detalle |
|---|---|
| API | Microsoft Graph API — bien documentada |
| Nivel de automatización | Alto |
| Mejor para | Empresas con Microsoft 365 — se integra al ecosistema que ya usan |

### Email

| Servicio | Cuándo usarlo |
|---|---|
| Gmail API / Outlook | Envío con cuenta del cliente, respuestas automáticas, clasificación de inbox |
| SendGrid | Envío masivo transaccional — confirmaciones, notificaciones, reportes |
| Mailchimp / Brevo (ex-Sendinblue) | Email marketing — newsletters, secuencias, segmentación |
| Amazon SES | Volumen alto con costo muy bajo — para proyectos con envíos masivos |

### SMS

| Servicio | Cuándo usarlo |
|---|---|
| Twilio | Alertas críticas, confirmaciones, autenticación 2FA |
| AWS SNS | Volumen alto, integrado con infraestructura AWS |
| Mensajes Colombia (operadores locales) | Si el cliente requiere facturación local en COP |

---

## Herramientas internas de gestión

### Gestión de proyectos y tareas

| Herramienta | Nivel de automatización | Notas |
|---|---|---|
| **Notion** | Muy alto | Bases de datos, páginas, bloques — API flexible. Muy usado en agencias |
| **Airtable** | Muy alto | Bases de datos visuales con automatización nativa + API externa |
| **ClickUp** | Alto | Tareas, proyectos, reportes, notificaciones |
| **Monday.com** | Alto | Boards, automatizaciones, reportes, integraciones |
| **Asana** | Alto | Tareas, proyectos, notificaciones, reportes de avance |
| **Jira** | Alto | Equipos de software — tickets, sprints, releases |
| **Trello** | Medio | Tableros Kanban, bueno para equipos pequeños |

**Regla:** preguntar siempre qué usa el cliente antes de proponer. El objetivo es automatizar
dentro de la herramienta que ya conocen — no obligarlos a aprender una nueva.

### Google Workspace

Prácticamente toda la suite es automatizable:
- **Google Sheets:** base de datos, reportes, pipelines
- **Google Docs:** generación de documentos desde templates
- **Google Drive:** organización automática, notificaciones, permisos
- **Google Calendar:** agendamiento, recordatorios, sincronización
- **Gmail:** clasificación, respuestas, notificaciones
- **Google Forms:** trigger de workflows al recibir respuesta

### Microsoft 365

Equivalente a Google Workspace para empresas con ecosistema Microsoft:
- Excel (OneDrive), Word, Teams, Outlook, SharePoint — todos tienen API via Microsoft Graph.

---

## Almacenamiento y gestión de archivos

| Servicio | Cuándo usarlo |
|---|---|
| Google Drive | Cliente en Google Workspace |
| OneDrive / SharePoint | Cliente en Microsoft 365 |
| Dropbox | Equipos creativos, manejo de archivos pesados |
| AWS S3 | Proyectos con alto volumen de archivos, imágenes, videos |
| Cloudinary | Optimización automática de imágenes para web |

---

## Preguntas clave antes de proponer integraciones

1. ¿Qué herramientas usa el equipo hoy? (listar todas — CRM, email, mensajería, gestión de proyectos, almacenamiento)
2. ¿Cuáles usan bien y cuáles casi no usan?
3. ¿Hay herramientas que están pagando pero no aprovechando? (HubSpot sin usar es el más común)
4. ¿El equipo usa WhatsApp para trabajo interno? ¿o Slack / Teams?
5. ¿Dónde viven los archivos hoy? (Drive, OneDrive, computadores locales)
6. ¿Quién del equipo tiene acceso técnico a las herramientas? (para saber quién proveerá los accesos)

---

## Cómo nombrar las integraciones al cliente

**No decir:** "Conectamos con la API de HubSpot y hacemos un webhook que escucha nuevos deals"

**Sí decir:**
> "Conectamos directamente con el HubSpot que ya tienen — cuando un negocio avanza en el pipeline,
> el sistema actúa automáticamente sin que nadie tenga que hacer nada."

La integración siempre se presenta como una extensión de lo que el cliente ya usa,
no como una pieza técnica nueva que tienen que entender.
