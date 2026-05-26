# Guía Paso a Paso: Obtener credenciales de Google OAuth 2.0

Sigue estos pasos exactamente para configurar tu proyecto en Google y obtener el `Client ID` que necesitamos para que el inicio de sesión funcione.

### Paso 1: Crear el Proyecto en Google Cloud
1. Ve a [Google Cloud Console](https://console.cloud.google.com/).
2. Inicia sesión con tu cuenta de Google.
3. Arriba a la izquierda (junto al logo de Google Cloud), haz clic en el **selector de proyectos** y selecciona **"Nuevo Proyecto"**.
4. Nombra tu proyecto (ej. `Physis Reloaded`) y haz clic en **Crear**. (Espera unos segundos a que se cree y luego asegúrate de tenerlo seleccionado).

### Paso 2: Configurar la Pantalla de Consentimiento
1. En el menú de la izquierda (el menú de hamburguesa ☰), ve a **"API y Servicios"** > **"Pantalla de consentimiento de OAuth"**.
2. En *Tipo de usuario*, selecciona **Externo** (para que cualquier persona con Gmail pueda entrar) y dale a **Crear**.
3. Rellena la información obligatoria:
   - **Nombre de la aplicación**: Physis
   - **Correo electrónico de asistencia al usuario**: (tu correo)
   - **Datos de contacto del desarrollador**: (tu correo)
   - *Nota: Puedes dejar el logo y dominios en blanco por ahora.*
4. Haz clic en **Guardar y Continuar**.
5. En la sección de **Permisos (Scopes)**, dale a **Añadir o Quitar Permisos**. Selecciona los tres primeros (`.../auth/userinfo.email`, `.../auth/userinfo.profile`, y `openid`).
6. Dale a **Guardar y Continuar** en las pantallas restantes hasta volver al Panel.
7. De vuelta en el Panel, pulsa el botón **Publicar aplicación** (bajo el apartado "Estado de publicación") para que pase de "En pruebas" a "Producción" y no te pida añadir correos de prueba uno a uno.

### Paso 3: Crear el Client ID (Credenciales)
1. En el menú izquierdo, ve a **"Credenciales"**.
2. Haz clic en el botón superior **"+ CREAR CREDENCIALES"** y elige **"ID de cliente de OAuth"**.
3. En **Tipo de aplicación**, selecciona **"Aplicación web"**.
4. Ponle un nombre (ej. `Physis Web Frontend`).
5. **¡MUY IMPORTANTE!** En la sección **Orígenes de JavaScript autorizados**, haz clic en "+ AÑADIR URI" y pega exactamente esto:
   `http://localhost:5173`
   *(Asegúrate de que no haya una barra `/` al final)*.
6. En la sección **URI de redireccionamiento autorizados** puedes dejarlo en blanco (porque usaremos el flujo moderno que no redirige, sino que devuelve el token en un popup).
7. Haz clic en **Crear**.

### Paso 4: Copiar las Credenciales
Te aparecerá un popup con tu **ID de cliente** y tu **Secreto de cliente**. 

Copia el **ID de cliente** (`GOOGLE_CLIENT_ID`) y añádelo a tus archivos `.env`:

**En el `.env` del Frontend (`Physis_FrontEnd/.env`):**
```env
VITE_GOOGLE_CLIENT_ID=tu_id_de_cliente_aqui.apps.googleusercontent.com
```

**En el `.env` del Backend (`Physis_BackEnd/.env`):**
```env
GOOGLE_CLIENT_ID=tu_id_de_cliente_aqui.apps.googleusercontent.com
```

¡Eso es todo! Cuando lo hayas hecho, el sistema estará listo para conectarse con Google.
