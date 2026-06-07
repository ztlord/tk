# URL Viewer APK

App Android en Kotlin que te permite ingresar una URL y visualizarla en **modo fullscreen** usando WebView nativo.

## Funcionalidades

- ✅ Pantalla de inicio para ingresar cualquier URL
- ✅ Auto-completa `https://` si no lo escribes
- ✅ Validación de URL antes de abrir
- ✅ WebView en pantalla completa (sin barra de estado ni navegación)
- ✅ Botones flotantes: **Cerrar**, **Atrás**, **Recargar**
- ✅ Los controles se ocultan al tocar y reaparecen con otro toque
- ✅ Barra de progreso de carga
- ✅ Pantalla de error con opción de reintentar
- ✅ JavaScript habilitado, DOM storage, zoom
- ✅ Compatible con Android 5.0+ (API 21+)

---

## Cómo compilar en Android Studio

### Requisitos previos
- [Android Studio Hedgehog o superior](https://developer.android.com/studio)
- JDK 8 o superior (incluido con Android Studio)
- SDK Android 34 instalado (Tools → SDK Manager → API 34)

### Pasos

1. **Abre el proyecto**
   - Abre Android Studio
   - `File → Open` → selecciona la carpeta `UrlViewer`
   - Espera a que sincronice Gradle (puede tardar 1-2 minutos la primera vez)

2. **Instala en tu teléfono (más rápido)**
   - Conecta tu Android por USB con **Depuración USB** activada
   - Presiona el botón ▶ (Run) o `Shift+F10`

3. **Generar APK para instalar manualmente**
   - Menú: `Build → Build Bundle(s) / APK(s) → Build APK(s)`
   - El APK se genera en:
     ```
     app/build/outputs/apk/debug/app-debug.apk
     ```
   - Cópialo a tu teléfono e instálalo (necesitas permitir "Instalar apps de fuentes desconocidas")

4. **Generar APK firmado (para distribución)**
   - `Build → Generate Signed Bundle / APK`
   - Elige APK y sigue el asistente para crear o usar una keystore

---

## Estructura del proyecto

```
UrlViewer/
├── app/
│   └── src/main/
│       ├── java/com/urlviewer/
│       │   ├── MainActivity.kt       ← Pantalla de ingreso de URL
│       │   └── WebViewActivity.kt    ← WebView fullscreen
│       ├── res/
│       │   ├── layout/
│       │   │   ├── activity_main.xml
│       │   │   └── activity_webview.xml
│       │   ├── drawable/             ← Íconos vectoriales
│       │   └── values/
│       │       ├── strings.xml
│       │       ├── colors.xml
│       │       └── themes.xml
│       └── AndroidManifest.xml
├── build.gradle
└── settings.gradle
```

---

## Permisos requeridos

- `INTERNET` — para cargar páginas web
- `usesCleartextTraffic="true"` — para permitir URLs HTTP (no solo HTTPS)
