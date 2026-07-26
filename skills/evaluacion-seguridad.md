# Skill — Evaluación de Seguridad

## Principio base

> La seguridad no es un feature extra — es parte del entregable.
> Todo proyecto debe tener al menos una revisión de seguridad antes de salir a producción.

---

## Checklist de seguridad universal

### Credenciales
- [ ] Ninguna credencial hardcodeada en nodos — todo en el sistema de Credentials de n8n
- [ ] Credenciales con el menor privilegio necesario (no usar admin si con lector basta)
- [ ] Credenciales de producción separadas de credenciales de prueba
- [ ] El cliente tiene acceso a sus propias credenciales (no solo tú)
- [ ] Documentar qué credenciales se crearon y con qué propósito

### Webhooks expuestos
- [ ] Todo webhook público tiene autenticación (Header Auth, Basic Auth, o verificación de firma)
- [ ] No exponer IDs internos, claves, ni datos sensibles en las URLs de webhook
- [ ] Validar el origen del request (whitelist de IPs si es posible)
- [ ] Limitar rate: ¿puede alguien hacer flood de requests y colapsar el workflow?

### Datos del cliente
- [ ] ¿El workflow maneja datos personales? → Aplica consideraciones de privacidad
- [ ] ¿Los datos se guardan en n8n o se pasan y descartan? → Preferir descartar
- [ ] Logs de ejecución: configurar retención limitada (no indefinida)
- [ ] ¿Hay datos de tarjetas, contraseñas, documentos de identidad? → Nunca almacenar en texto plano

### Acceso a n8n
- [ ] n8n no está expuesto al internet sin autenticación
- [ ] Si self-hosted: servidor con firewall configurado
- [ ] API Key de n8n no compartida con el cliente si no es necesario

---

## Riesgos por tipo de integración

### Alto riesgo
| Integración | Riesgo principal | Mitigación |
|---|---|---|
| Webhooks públicos | Cualquiera puede enviar data falsa | Validar firma / token secreto |
| Bases de datos directas | SQL injection si se construyen queries dinámicas | Usar parámetros, nunca concatenar strings |
| APIs de pago | Exposición de claves de producción | Credenciales separadas, logs sin datos de tarjeta |
| Email con adjuntos | Procesamiento de archivos maliciosos | Validar tipo/tamaño, no ejecutar adjuntos |
| Automatizaciones de login | Captura de credenciales del cliente | Siempre OAuth, nunca guardar passwords |

### Medio riesgo
| Integración | Riesgo principal | Mitigación |
|---|---|---|
| Google Workspace | Token OAuth con demasiados permisos | Solicitar solo los scopes necesarios |
| CRMs | Sobreescribir datos de clientes reales en pruebas | Usar sandbox o datos ficticios en testing |
| Redes sociales | Publicaciones no deseadas en pruebas | Desactivar webhook en ambiente de prueba |
| WhatsApp Business | Envío masivo accidental | Throttling + confirmación antes de envío masivo |

### Bajo riesgo (pero no ignorar)
| Integración | Consideración |
|---|---|
| Google Sheets | No usar como base de datos de producción si hay datos sensibles |
| Slack/Discord | Cuidado con mensajes que incluyen datos privados de clientes |
| Placid/Canva | No incluir datos sensibles en imágenes generadas |

---

## Niveles de seguridad por tipo de cliente

### Nivel básico (micro/pequeña empresa, datos no sensibles)
- Credenciales en sistema n8n ✓
- Webhook con token básico ✓
- Logs con retención de 7 días ✓

### Nivel medio (empresa mediana, datos de clientes)
- Todo lo anterior +
- IP whitelist donde sea posible
- Auditoría de accesos cada 3 meses
- NDA firmado antes de recibir accesos
- Credenciales con rotación semestral

### Nivel alto (sector salud, financiero, legal, datos muy sensibles)
- Todo lo anterior +
- n8n self-hosted en servidor del cliente (no en tu infraestructura)
- Cifrado de datos en tránsito y en reposo
- Logs de auditoría completos
- Revisión de seguridad formal antes de go-live
- Contrato con cláusulas de protección de datos (RGPD/Habeas Data Colombia)

---

## Consideraciones legales Colombia

### Ley 1581 de 2012 — Protección de Datos Personales
- Si el workflow procesa datos personales de colombianos → el cliente debe tener política de privacidad
- Como proveedor, puedes ser considerado "encargado del tratamiento"
- Recomendado: incluir cláusula de tratamiento de datos en el contrato de servicios

### Lo que debes hacer como proveedor
- Eliminar o devolver los datos del cliente al terminar el proyecto
- No compartir datos del cliente con terceros
- Documentar qué datos procesas y con qué propósito
- Tener contrato firmado antes de recibir datos sensibles

---

## Frases para comunicar seguridad al cliente

**Si preguntan sobre sus datos:**
> "Trabajo con tus accesos únicamente durante el proyecto. Al finalizar, los elimino de mi sistema o te los transfiero. Nunca comparto información de mis clientes con terceros."

**Si tienen datos muy sensibles:**
> "Para este tipo de datos recomiendo que n8n corra en tu propio servidor — así los datos nunca salen de tu infraestructura. Puedo ayudarte a configurarlo."

**Si son una empresa mediana o grande:**
> "Antes de iniciar necesitamos firmar un acuerdo de confidencialidad. ¿Tienen modelo de NDA propio o uso el mío?"
