# Fase 3: Landing Page y Bento Grid Interactivo

## Objetivo
Rediseñar la página pública de inicio (`LandingPage.jsx`) añadiendo una sección asimétrica y moderna (Bento Grid) que exponga claramente el valor de Physis a nuevos usuarios de manera atractiva, interactiva y premium.

## Tareas Implementadas

### 1. Diseño Estructural "Bento Grid"
- **Maquetación:** Implementación de un diseño moderno y asimétrico de 3 columnas que organiza de forma visualmente atractiva el contenido (Video, Misión/Visión y Noticias).
- **Video Nativo Automático:** Integración de `samplePhysis.mp4` directamente en el grid de manera auto-reproducible y en silencio (`muted autoplay loop`) ocupando una sección principal para capturar la atención inmediatamente.

### 2. Tarjeta Interactiva de Misión y Visión
- **Diseño:** Tarjeta animada implementando la técnica de *glassmorphism* que transmite rápidamente el propósito de la aplicación, reaccionando al cursor y brindando feedback táctil y visual al interactuar.

### 3. Productivity Feed (Consumo de API Real)
- **Desarrollo:** Creación de un "Feed de Productividad" que no usa datos estáticos, sino que realiza un *fetch* dinámico a la API pública de **dev.to**.
- **Valor agregado:** Se filtran los artículos usando etiquetas de productividad (`tag=productivity`) para dotar a la landing page de contenido fresco y real en cada visita.

### 4. Seguridad de Navegación Inicial
- **Protección de Rutas:** Aseguramiento de los enlaces del header (Navbar público) para que redirijan a la Landing Page e impidan el acceso a secciones privadas a visitantes no autenticados.
