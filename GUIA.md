# AMEBGAMES con cuentas de Google — guía de publicación

Tiempo: unos 15 minutos. Todo es gratis con el plan Spark de Firebase.

## 1. Crear el proyecto
1. Entra en https://console.firebase.google.com con tu cuenta de Google.
2. «Crear un proyecto» → nombre: `amebgames` → puedes desactivar Google Analytics → Crear.

## 2. Registrar la web y copiar la configuración
1. En la página del proyecto, pulsa el icono **`</>`** (Web).
2. Apodo: `amebgames` → marca **«Configurar también Firebase Hosting»** → Registrar.
3. Te enseña un bloque `const firebaseConfig = { ... }`. Copia los valores.
4. Abre `public/config.js` y sustituye los valores de ejemplo por los tuyos (apiKey, authDomain, projectId, etc.).

## 3. Activar «Entrar con Google»
1. Menú izquierdo → **Compilación → Authentication** → «Comenzar».
2. Pestaña «Método de inicio de sesión» → **Google** → Habilitar → elige tu correo de asistencia → Guardar.

## 4. Crear la base de datos
1. Menú → **Compilación → Firestore Database** → «Crear base de datos».
2. Ubicación: `eur3 (europe-west)` → modo **producción** → Crear.
3. Pestaña **Reglas** → borra lo que hay, pega el contenido de `firestore.rules` → Publicar.

## 5. Publicar la web (desde el ordenador)
1. Instala Node.js (versión LTS) desde https://nodejs.org
2. Abre una terminal en la carpeta `amebgames-firebase` y ejecuta:
   ```
   npm install -g firebase-tools
   firebase login
   firebase use --add        (elige tu proyecto amebgames, alias: default)
   firebase deploy
   ```
3. Al terminar te da la dirección: `https://amebgames.web.app` (o parecida). ¡Ese es tu enlace!

## 6. Comprobar
- Abre el enlace en el móvil → sale la pantalla de inicio → «Continuar con Google».
- Juega un reto, cierra, ábrelo en otro dispositivo con la misma cuenta: el progreso debe estar ahí.
- En Firebase → Firestore verás una colección `users` con un documento por jugador.

## Para actualizar la web más adelante
Sustituye los archivos de `public/` por la versión nueva y vuelve a ejecutar `firebase deploy`.

## Notas
- El código de creador y los demás códigos funcionan igual que antes.
- Los grupos siguen funcionando con enlaces/QR; el siguiente paso sería pasarlos a la base de datos para que se actualicen solos.
- Si «Continuar con Google» no abre la ventana en el móvil, la web usa automáticamente el modo de redirección.
