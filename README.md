# 📺 CineStream For TV

App Flutter para Android TV con diseño estilo Netflix. Consume el repositorio JSON de CineStream para mostrar canales de TV en vivo, películas y series.

---

## 🚀 Requisitos

| Herramienta | Versión mínima |
|-------------|---------------|
| Flutter     | 3.16+         |
| Dart        | 3.0+          |
| Android SDK | API 21+       |
| Gradle      | 8.3           |
| Java        | 11+           |

---

## 📦 Instalación

### 1. Clonar / Descomprimir el proyecto

```bash
cd cinestream_tv
```

### 2. Obtener dependencias

```bash
flutter pub get
```

### 3. Preparar icono de la app (opcional pero recomendado)

Reemplaza los archivos en:
```
android/app/src/main/res/mipmap-*/ic_launcher.png
```
Con el ícono de tu app en los tamaños correctos.

### 4. Compilar para Android TV

#### Debug (para pruebas)
```bash
flutter build apk --debug
```

#### Release
```bash
flutter build apk --release
```

El APK se genera en:
```
build/app/outputs/flutter-apk/app-release.apk
```

---

## 📲 Instalación en dispositivo Android TV

### Via ADB (modo desarrollador activado)
```bash
# Conectar al TV por red
adb connect <IP_DEL_TV>:5555

# Instalar la app
adb install build/app/outputs/flutter-apk/app-release.apk

# Lanzar directamente
adb shell am start -n com.cinestream.tv/.MainActivity
```

### Via USB
```bash
adb install -r build/app/outputs/flutter-apk/app-release.apk
```

### En dispositivos Fire TV (Amazon)
```bash
# Mismo proceso pero con el ADB de Fire TV
adb connect <IP>:5555
adb install app-release.apk
```

---

## 🎮 Controles del Control Remoto

| Botón | Acción |
|-------|--------|
| ▲ Arriba | Mover foco arriba / Subir volumen (en reproductor) |
| ▼ Abajo | Mover foco abajo / Bajar volumen (en reproductor) |
| ◀ Izquierda | Mover foco izquierda / Retroceder 10s (en reproductor) |
| ▶ Derecha | Mover foco derecha / Adelantar 10s (en reproductor) |
| OK / Enter | Seleccionar / Pausar-Reproducir |
| Atrás / Back | Volver a pantalla anterior |
| Play/Pause | Pausar/Reproducir (en reproductor) |

---

## 🗂 Estructura del Proyecto

```
lib/
├── main.dart                    # Punto de entrada
├── theme/
│   └── app_theme.dart           # Colores, estilos TV
├── models/
│   └── media_item.dart          # Modelo de datos universal
├── services/
│   ├── api_service.dart         # Carga JSON del repositorio
│   └── storage_service.dart    # Guarda progreso localmente
├── providers/
│   └── app_provider.dart        # Estado global de la app
├── screens/
│   ├── home_screen.dart         # Pantalla principal Netflix-style
│   └── player_screen.dart       # Reproductor de video TV
└── widgets/
    ├── tv_focus_widget.dart     # Indicador de foco con glow
    ├── hero_banner.dart         # Banner destacado superior
    ├── content_row.dart         # Filas horizontales desplazables
    └── media_card.dart          # Tarjetas de contenido
```

---

## 🎨 Características de UI

- ✅ Fondo oscuro estilo Netflix
- ✅ Hero banner con imagen destacada
- ✅ Filas horizontales desplazables por categoría
- ✅ Indicador de foco con brillo/glow blanco
- ✅ Animación de escala al cambiar foco
- ✅ Tarjetas grandes con imagen, título, calificación, año, categoría
- ✅ Sección "Continuar viendo" persistente
- ✅ Badges EN VIVO / PELÍCULA / SERIE
- ✅ Barra de progreso en tarjetas

---

## 📡 Reproductor de Video

Compatible con:
- HLS / M3U8 (`.m3u8`)
- MPEG-TS (`.ts`)
- MP4 (`.mp4`)
- Streams directos HTTP/HTTPS
- URLs de streaming tipo `http://live.btv.mx:2424/stream/...`

Controles TV:
- Barra de progreso grande
- Controles adaptados al control remoto
- Indicador de volumen
- Pantalla completa automática
- Guarda posición de reproducción

---

## ⚙️ Configuración de HTTP Streams

La app permite tráfico HTTP (no solo HTTPS) para compatibilidad con streams IPTV. Esto está configurado en:
```
android/app/src/main/res/xml/network_security_config.xml
```

---

## 🔧 Personalización

### Cambiar el repositorio JSON
En `lib/services/api_service.dart`:
```dart
static const String _jsonUrl = 'TU_URL_AQUI';
```

### Cambiar colores
En `lib/theme/app_theme.dart`:
```dart
static const Color accent = Color(0xFFE50914); // Cambia el color principal
```

### Cambiar el Application ID
En `android/app/build.gradle`:
```gradle
applicationId "com.tuempresa.tuapp"
```
Y en `android/app/src/main/AndroidManifest.xml`:
```xml
package="com.tuempresa.tuapp"
```

---

## 📱 Dispositivos Compatibles

| Dispositivo | Compatible |
|-------------|-----------|
| Android TV (Sony, TCL, Philips) | ✅ |
| Google TV (Chromecast 4K) | ✅ |
| NVIDIA Shield TV | ✅ |
| Amazon Fire TV | ✅ (via ADB) |
| Mi TV Box | ✅ |
| TiVo Stream 4K | ✅ |
| Mecool Box | ✅ |

---

## 🐛 Solución de Problemas

### El stream no reproduce
1. Verifica que el URL del stream sea válido
2. Prueba el stream en VLC primero
3. Revisa que `usesCleartextTraffic="true"` esté en el Manifest

### Error de foco/navegación
- Asegúrate de que `FocusTraversalGroup` esté envolviendo las filas
- El primer elemento de cada fila debe tener `autofocus: true` en la primera fila

### La app no aparece en el launcher del TV
- Verifica que el `LEANBACK_LAUNCHER` intent-filter esté en el Manifest
- El `android:banner` debe apuntar a un drawable válido

---

## 📄 Licencia

MIT License - CineStream For TV
