# 🎬 CineStream

**CineStream** es una aplicación de streaming para Android que permite ver Películas, Series, TV en Vivo y Eventos deportivos en directo, con soporte para móviles, tablets y dispositivos Android TV / emuladores.

---

## ✨ Características

- 🎬 **Películas** — Catálogo completo con filtros por género, año y buscador. Paginación de 30 en 30.
- 📺 **Series** — Lista de series con selector de episodios y múltiples calidades.
- 📡 **TV en Vivo** — Canales en directo con mini-player fijo + lista de canales. Favoritos con ⭐.
- ▶ **Continuar** — Historial de reproducción con progreso guardado automáticamente.
- 📅 **Eventos** — Agenda de eventos deportivos en vivo cargada en tiempo real. Compatible con móvil y TV.

---

## 🆕 Novedades por versión

### v1.0.5 — Eventos en Vivo
- ✅ Nueva sección **Eventos** reemplaza al botón Transmitir en la barra de navegación
- ✅ Carga en tiempo real desde agenda JSON con anti-caché automático
- ✅ Agrupación por categoría (Fútbol, etc.) con contador de eventos
- ✅ Badge **EN VIVO** para eventos activos
- ✅ Búsqueda por título o categoría
- ✅ Compatible con interfaz **móvil** (bottom nav) y **TV/emulador** (top nav con D-pad)
- ✅ Al tocar un evento abre el player directamente con el stream

### v1.0.4
- ✨ Navegación de episodios: botones Anterior, Episodios y Siguiente
- ✨ Selector de episodios con lista completa
- ✨ Badge con episodio actual (ej: 3/25)
- ⚡ Botones de episodios en la parte superior (no interfiere con la barra de tiempo)
- ⚡ Se ocultan automáticamente a los 3 segundos
- ⚡ Protección del código con ProGuard + ofuscación Dart
- 🐛 Soporte de múltiples calidades en películas y episodios

### v1.0.3
- ✨ Interfaz adaptativa TV / Móvil
- ✨ Mini-player fijo en TV en Vivo
- ✨ Favoritos en canales
- ⚡ Historial con progreso de reproducción

### v1.0.2
- ✨ Player híbrido: Chewie (películas/series) + media_kit FFmpeg (TV en vivo)
- ✨ Intro animada al iniciar la app

### v1.0.1
- 🚀 Lanzamiento inicial

---

## 📲 Instalación

1. Descarga el APK desde [Releases](../../releases/latest)
2. En tu Android: **Ajustes → Seguridad → Instalar apps de fuentes desconocidas**
3. Instala el APK descargado

---

## 🖥️ Compatibilidad

| Plataforma | Soporte |
|---|---|
| Android (móvil/tablet) | ✅ Completo |
| Android TV / Google TV | ✅ Completo (D-pad) |
| Emuladores (BlueStacks, etc.) | ✅ Completo |
| Mínimo SDK | Android 5.0 (API 21) |

---

## 🛠️ Tecnologías

- [Flutter](https://flutter.dev) 3.x
- [media_kit](https://pub.dev/packages/media_kit) — Reproducción FFmpeg para TV en Vivo
- [chewie](https://pub.dev/packages/chewie) + [video_player](https://pub.dev/packages/video_player) — Player para películas y series
- [cached_network_image](https://pub.dev/packages/cached_network_image) — Imágenes con caché
- [provider](https://pub.dev/packages/provider) — Gestión de estado
- [http](https://pub.dev/packages/http) — Consumo de APIs JSON

---

## ⚠️ Aviso Legal

Esta aplicación es un reproductor multimedia. No almacena, distribuye ni aloja ningún contenido. Todo el contenido es provisto por fuentes externas de terceros. El uso de esta aplicación es responsabilidad exclusiva del usuario.
