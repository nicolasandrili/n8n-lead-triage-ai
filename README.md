# 🤖 Sistema de Triaje y Automatización de Leads con n8n y GPT-4o-mini

Este proyecto implementa un flujo de trabajo automatizado en n8n para la recepción, calificación, almacenamiento y notificación interna de clientes potenciales (leads) recibidos por correo electrónico.

## 🔗 Links del Proyecto
* **Airtable Shared View (Modo Lectura):** https://airtable.com/appMsYM93OLYPxvZe/shrNYHE1bObBcM8OK
* **Repositorio GitHub:** https://github.com/nicolasandrili/n8n-lead-triage-ai

## 🛠️ Arquitectura de la Solución
El flujo se compone de los siguientes nodos en n8n:
1. **Gmail Trigger:** Escucha correos entrantes con consultas comerciales.
2. **If Filter:** Filtra correos no deseados, automáticos o spam.
3. **Airtable Create Record:** Registra inmediatamente el lead en estado `Pendiente`.
4. **OpenAI Node (GPT-4o-mini):** Genera resumen, puntaje (Score IA) y borrador de propuesta en JSON.
5. **Send a Message (Gmail):** Envía notificación interna de revisión (Human-in-the-Loop) al equipo.
6. **Airtable Update Record:** Actualiza el registro con el análisis de la IA asociado por `Record ID`.

## 📄 Archivos del Repositorio
* `workflow.json`: Exportación completa del flujo en n8n.
* `documentacion_proyecto.pdf`: Documentación técnica detallada (Arquitectura, Costos, Seguridad y KPIs).
* `/evidencias`: Capturas de pantalla comprobatorias de la ejecución end-to-end.
