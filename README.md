# 🤖 GitHub Issues Bot con IA

Automatización inteligente de issues de GitHub usando N8N y Google Gemini.

## 📋 Descripción

Este proyecto automatiza el análisis y gestión de issues de GitHub usando inteligencia artificial. Cada vez que se crea un nuevo issue, el flujo lo analiza automáticamente y realiza múltiples acciones sin intervención humana.

## ⚙️ ¿Cómo funciona?

1. **GitHub Trigger** detecta cuando se crea un nuevo issue
2. **Google Gemini (IA)** analiza el título y descripción del issue y genera:
   - Título descriptivo
   - Categoría (Bug, Feature Request, Documentación, Pregunta)
   - Prioridad del 1 al 10
   - Resumen del problema y posible solución
3. **Labels automáticos** se agregan al issue según la categoría y prioridad
4. **Comentario automático** con el análisis completo se publica en el issue
5. **Notificación en Telegram** llega instantáneamente con dos niveles:
   - 🔴 URGENTE para prioridad 8-10
   - 🔵 Normal para prioridad 1-7

## 🛠️ Tecnologías utilizadas

- [N8N](https://n8n.io) — Automatización de flujos de trabajo
- [Google Gemini](https://aistudio.google.com) — Modelo de IA para análisis
- [GitHub API](https://docs.github.com/en/rest) — Gestión de issues y labels
- [Telegram Bot API](https://core.telegram.org/bots/api) — Notificaciones

## 🔄 Flujo del proyecto
GitHub (nuevo issue)
→ Google Gemini (analiza con IA)
→ Code (limpia y procesa JSON)
→ HTTP Request (agrega label de categoría)
→ IF (prioridad >= 8?)
→ HTTP Request (label Urgente/Prioridad Media)
→ IF (urgencia)
→ Telegram (mensaje urgente 🔴 o normal 🔵)
→ GitHub Comment (comentario con análisis)

## 📦 Instalación

### Requisitos previos
- Cuenta en [N8N](https://n8n.io)
- API Key de [Google Gemini](https://aistudio.google.com)
- Bot de Telegram (via @BotFather)
- Token de GitHub

### Pasos
1. Importa el archivo `workflow.json` en N8N
2. Configura las credenciales:
   - GitHub API Token
   - Google Gemini API Key
   - Telegram Bot Token y Chat ID
3. Activa el flujo
4. ¡Listo! Crea un issue en tu repositorio para probarlo

## 📸 Ejemplo de notificación en Telegram

🔴 URGENTE - Prioridad 9/10

📌 Título: Sistema caído en producción
🏷️ Categoría: Bug  
📝 Resumen: El servidor principal no responde...
⚠️ Este issue requiere atención inmediata!

## 👤 Autor

- GitHub: [@Alanmv12](https://github.com/Alanmv12)
