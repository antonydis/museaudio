# MuseAudio

Audioguía independiente, gratuita y multilingüe para recorrer exposiciones de arte desde el teléfono.

**Demo:** https://antonydis.github.io/museaudio/

## Estado (noviembre de 2026)

- **La colección Torlonia** se conserva como demostración funcional, aunque la exposición del MBAM terminó el 19 de julio de 2026.
- **Anne Kahane : Structures** abre al público el 19 de noviembre de 2026 (avant-première para miembros: 17 y 18 de noviembre). El recorrido de MuseAudio está **en preparación**, sin obras ni audios publicados.
- **Hors socle**, **Chiharu Shiota** y **Allison Katz** aparecen en el catálogo como recorridos en preparación.
- El modo offline, la suscripción por correo y la música ambiente están ocultos hasta contar con implementaciones completas. No se debe prometer reproducción sin conexión.

Fuentes: [Exposiciones del MBAM](https://www.mbam.qc.ca/fr/expositions/) · [Anne Kahane](https://www.mbam.qc.ca/fr/expositions/13639/).

## Uso y desarrollo

Proyecto web estático: `index.html`, `manifest.json`, `sw.js` y `legal.html`. No necesita compilación ni framework.

1. Abrir `index.html` mediante un servidor HTTP local, por ejemplo `python -m http.server 8000`. Los service workers no funcionan desde `file://`.
2. Elegir idioma, museo y exposición; la demostración Torlonia tiene 38 obras y una introducción.
3. Para añadir una exposición, crear su ficha en `window.MA.expos`, incluir su identificador en `window.MA.museums[0].expos` y añadir su lista en `window.MA.works`. No publicar títulos de obras ni audios no verificados.
4. Para añadir audio real, publicar archivos MP3 bajo `<AUDIO_BASE>/<museumId>/<expoId>/<workId>_<lang>.mp3`. El navegador puede usar voz sintética como alternativa, con limitaciones al bloquear la pantalla.

El progreso y las preferencias se guardan localmente en el dispositivo. Las duraciones estimadas se calculan a partir del texto y no equivalen necesariamente a la duración de los MP3.

## Pruebas recomendadas

- Reproducir, pausar, avanzar y volver a una obra.
- Salir de la exposición y regresar; comprobar que no se superponen narraciones.
- Buscar por título, cambiar idioma y reordenar la lista completa.
- Probar «Continuar» tras recargar la página.
- Probar teclado y lector de pantalla, especialmente la ficha de obra y el reproductor.
- Verificar iOS Safari, Android Chrome y la reproducción con pantalla bloqueada.
- Confirmar que offline y suscripción no se ofrecen como funciones activas.

## Independencia

MuseAudio es un proyecto independiente y no está afiliado, aprobado ni patrocinado por el Musée des beaux-arts de Montréal (MBAM). Los contenidos son propios y pueden contener errores. Consulta [avisos legales](legal.html).

## Licencia

No se ha especificado una licencia de uso o reutilización del código ni de las narraciones. Debe definirse antes de admitir reutilizaciones por terceros.
