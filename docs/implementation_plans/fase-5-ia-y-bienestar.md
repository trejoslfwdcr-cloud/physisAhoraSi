# Fase 5: Inteligencia Artificial (Coach) y Gestor de Bienestar Diario

## Objetivo
Potenciar el ecosistema Physis integrando un asistente virtual propulsado por la IA de Google Gemini para actuar como Coach personalizado y, a nivel de administración/recursos humanos, un Gestor de Clima Laboral basado en sentimientos (Daily Pulse).

## Tareas Implementadas

### 1. IA Coach Widget (Frontend)
- **Componente Flotante:** Desarrollo de `IACoachWidget.jsx`, un botón flotante y draggable gracias a `framer-motion` ubicado en la esquina inferior derecha.
- **Chat Interactivo:** Al hacer clic, despliega una interfaz de chat que consume el historial de la conversación conectándose a `/api/ai/conversaciones/chat`.
- **Personalización:** El Coach conoce quién le habla usando el nombre real de la base de datos para generar rapport.

### 2. Backend y Conexión Gemini AI
- **Controlador (`AiController.js`):** Uso directo de la librería oficial `@google/generative-ai`. Se configura y carga la API key desde `.env`.
- **Contexto (System Prompt):** Se inyectan reglas e información de las tareas y metas del usuario para que la IA brinde consejos de productividad específicos, alineados a la plataforma Physis y responda dudas del usuario.

### 3. Daily Pulse (Encuesta de Bienestar)
- **Modal y Registro Diaro:** Componente `DailyPulseModal.jsx` (Frontend) diseñado para abrirse 1 vez al día de forma automática (o al presionar un botón) con el fin de consultar el estado de ánimo (5 niveles de emoción) y el factor de influencia actual.
- **Base de Datos:** Migración y modelo Sequelize `daily_pulses`.

### 4. Dashboard de Clima Laboral y Sentimiento (Admin)
- **Análisis de Sentimiento IA:** Si el empleado incluye texto en su estado de ánimo, la API del Backend se comunica brevemente con Gemini para puntuar el sentimiento e identificar alertas de "Burnout" o desmotivación.
- **Visualización (Admin):** Nueva página `WellnessDashboard.jsx` (protegida exclusivamente para administradores/dueños). Muestra datos agregados con gráficos interactivos (`recharts`), priorizando a los empleados en riesgo mediante una lista generada a partir de los puntajes de sentimiento de la IA.
