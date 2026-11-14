# Re-Bio · prototipo móvil (v0.2)

App de prueba para la comunidad ESPOL: comprar, donar e intercambiar materiales reutilizables.
No usa servidor: los datos se guardan solo en el teléfono donde se instala.

- Cuenta de prueba: `demo@espol.edu.ec` · contraseña `rebio123`
- Código de verificación al crear cuenta: `123456`

---

## Opción A · APK de Android sin instalar nada (recomendada)

GitHub compila el APK gratis en sus servidores.

1. Crea una cuenta en https://github.com (si no tienes).
2. Pulsa **+ → New repository**. Nombre: `re-bio`. Elige **Public** (necesario para la Opción C gratis) y pulsa **Create repository**.
3. En el repositorio vacío pulsa **uploading an existing file**.
4. Descomprime `Re-Bio-proyecto.zip` en tu computador y **arrastra todo el contenido de la carpeta** (incluida la carpeta `.github`) a la página. Pulsa **Commit changes**.
   - Si tu explorador oculta la carpeta `.github`, actívala en "Ver → Elementos ocultos" (Windows) o con Cmd+Shift+. (Mac).
5. Abre la pestaña **Actions**. Verás "Compilar APK de Android" en marcha (tarda unos 5–8 minutos).
6. Cuando tenga ✔ verde, entra en la ejecución y descarga **Re-Bio-APK** (abajo, en *Artifacts*). Es un .zip que contiene `Re-Bio.apk`.

### Instalar en el celular Android
1. Pasa `Re-Bio.apk` al teléfono (WhatsApp a ti mismo, Drive, cable USB…).
2. Ábrelo. Android pedirá permitir **"Instalar apps desconocidas"** para esa aplicación (Archivos, Chrome, Drive): actívalo.
3. Pulsa **Instalar**. Play Protect puede advertir que la app es desconocida: elige **Instalar de todas formas**. Es normal en apps de prueba sin publicar.

Requiere Android 7.0 o superior.

## Opción B · APK con Android Studio (en tu computador)
1. Instala Node.js 22 y Android Studio.
2. En la carpeta del proyecto: `npm install` y luego `npx cap sync android`.
3. Abre la carpeta `android` en Android Studio → **Build → Build App Bundle(s) / APK(s) → Build APK(s)**.

## Opción C · iPhone (sin App Store)
Apple no permite instalar archivos de app (IPA) sin firmarlos con una cuenta de desarrollador (USD 99/año) desde una Mac.
Para probar en iPhone se instala como app web, que funciona sin conexión y aparece con su ícono:

1. En tu repositorio de GitHub: **Settings → Pages → Source: GitHub Actions**.
2. Pestaña **Actions** → "Publicar versión web" → **Run workflow** (si no se ejecutó sola).
3. Tu app quedará en `https://TU-USUARIO.github.io/re-bio/`.
4. En el iPhone abre ese enlace en **Safari** → botón **Compartir** → **Agregar a pantalla de inicio**.

Ese mismo enlace también funciona en Android (Chrome → menú ⋮ → **Instalar app**).

---

## Qué hay en el proyecto
- `www/` — la app (un solo `index.html`, íconos, manifiesto y modo sin conexión).
- `android/` — proyecto Android nativo generado con Capacitor 8 (id `ec.espol.rebio`).
- `assets/` — ícono y pantalla de inicio de origen.
- `.github/workflows/` — compilación automática del APK y publicación web.

Para cambiar la app solo se edita `www/index.html` y se vuelve a subir: GitHub recompila todo.
