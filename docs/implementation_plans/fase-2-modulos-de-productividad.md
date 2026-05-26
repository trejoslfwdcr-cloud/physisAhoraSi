# Fase 2: Core de Funcionalidad Básica y Módulos de Productividad

## Objetivo
Implementar los módulos esenciales para mantener el enfoque del usuario durante la ejecución de sus tareas y gestionar su tiempo de forma eficaz, manteniendo la estética premium y dinámica requerida por el proyecto.

## Tareas Implementadas

### 1. Calendario de Eventos Mensual
- **Propósito:** Permitir al usuario visualizar tareas y metas programadas a lo largo del mes.
- **Implementación Técnica:** Integración de la librería `react-big-calendar` apoyada en `date-fns` para un manejo de fechas óptimo.
- **Diseño:** Adaptación completa del calendario al *Dark Theme* y *Glassmorphism* general del proyecto. Se incluyeron detalles sutiles como destacar el día actual utilizando `physis-primary/10` y bordes translúcidos.

### 2. Timer Pomodoro
- **Propósito:** Ofrecer una herramienta para usar la técnica de concentración en bloques de tiempo (Pomodoro).
- **Implementación Técnica:** Uso de `react-circular-progressbar` para renderizar el progreso de tiempo circularmente. Implementación de lógicas en React para pausar, reiniciar y alternar tiempos.
- **Diseño:** Estilo inmersivo aplicando resplandor ambiental (*Ambient Glow*) tras el reloj (`blur-[100px]`). Los botones para los modos (Pomodoro, Short Break, Long Break) son animados con `framer-motion`.

### 3. Sistema de Notificaciones
- **Propósito:** Centro de alertas visuales en la plataforma para retroalimentación.
- **Implementación Técnica:** Sistema de estado global y componente flotante que usa `AnimatePresence` de `framer-motion` para que las tarjetas desaparezcan suavemente sin saltos visuales.
- **Diseño:** Las notificaciones están categorizadas (`success`, `warning`, `info`) con íconos de `lucide-react` acordes. Integración en el menú lateral.
