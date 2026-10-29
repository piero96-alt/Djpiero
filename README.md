# 🎵 Melodía

App de música de código abierto para **Android e iPhone** (React Native + Expo), con lo mejor de Spotify (descubrir, playlists, favoritas) y Apple Music (diseño limpio, biblioteca propia). **Sin anuncios, sin cuentas, sin suscripción.**

## Qué hace
- 🔎 Busca y reproduce música libre y legal de **Jamendo** (miles de artistas independientes).
- 📁 Reproduce **tus propios archivos** de música del teléfono (mp3, m4a, etc.).
- 📚 Biblioteca: playlists propias, favoritas, archivos locales.
- ⬇️ **Importa playlists de Spotify y Apple Music** (ver abajo).
- ▶️ Reproducción en segundo plano, mini-reproductor y pantalla completa.

## Importante sobre Spotify / Apple Music
Las canciones de Spotify y Apple Music están protegidas con DRM: ninguna app puede reproducirlas sin anuncios fuera de sus apps oficiales (y hacerlo violaría sus términos). Por eso Melodía **importa tus listas** (título + artista) y busca cada canción en catálogos abiertos y en tus archivos. Las que no se encuentren se muestran al final del import.

### Cómo importar
- **Spotify:** entra a https://exportify.net, inicia sesión y exporta tu playlist a CSV. En Melodía → *Importar* → *Elegir archivo CSV*.
- **Apple Music:** exporta tu playlist a CSV con TuneMyMusic o Soundiiz, o pega líneas con el formato `Artista - Título`.

## Probarla ya (5 min)
```bash
npm install
npx expo start
```
Instala **Expo Go** en tu Android/iPhone y escanea el QR. Funciona en ambos.

## Generar el instalable
### Android (.apk)
```bash
npm install -g eas-cli
eas login            # cuenta gratuita en expo.dev
eas build -p android --profile preview
```
Al terminar te da un enlace para descargar el `.apk` e instalarlo.

### iPhone (.ipa)
```bash
eas build -p ios --profile preview
```
Apple exige firmar las apps: necesitas una cuenta **Apple Developer (99 USD/año)** para instalar en un iPhone real o publicar en TestFlight. Alternativa gratuita para pruebas: Expo Go (arriba).

## Cambiar la clave de Jamendo
Edita `src/config.js` y pon tu propio `client_id` gratuito de https://devportal.jamendo.com.

## Estructura
```
App.js            navegación (Inicio / Biblioteca / Importar)
src/store.js      estado global + motor de audio
src/api.js        API de Jamendo y emparejamiento de canciones
src/importers.js  lector de CSV / texto de playlists
src/screens.js    pantallas y reproductor
```

Licencia: MIT. Úsala, modifícala y compártela libremente.
