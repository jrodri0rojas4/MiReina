# Para vos — sitio de aniversario

Sitio 100 % estático (HTML + CSS + JS), sin servidor ni dependencias. Funciona gratis en GitHub Pages y también abriendo `index.html` con doble clic.

## Qué tiene

| Sección | Qué hace |
|---|---|
| Puerta | Un sobre que se abre si ella escribe la fecha en que empezaron (si falla 3 veces, se la muestra). Solo la primera vez. |
| Inicio | Contador en vivo: años, meses, días y segundos juntos. |
| Cartitas | 9 cartas cortas "abrir cuando…". Se marcan como leídas. Botón "sorprendeme". |
| Álbum | Fotos tipo polaroid que se dan vuelta y muestran una nota. Incluye el video. |
| Razones | Una razón por clic, sin repetir. |
| Juegos | Memoria con sus fotos, atrapá los corazones, rompecabezas, quiz, ruleta de planes y tres en raya. Guardan récords. |
| Cupones | Cupones rascables. Al canjear se abre WhatsApp con el mensaje armado. |
| Cápsula del tiempo | Una carta que solo se abre el día del próximo aniversario. |
| Final | La pregunta con el botón "No" que se escapa. |
| Ahora te toca a vos | Ella te escribe y le llega a tu WhatsApp. |
| Secreto | Si toca 7 veces el corazón del pie de página, aparece una carta escondida. |

El cielo del fondo pasa de atardecer a noche mientras se hace scroll.

## Lo primero que tenés que editar

Todo está en **`js/config.js`**. Abrilo y revisá:

1. `fechaInicio` — formato `AAAA-MM-DD`. Está en `2016-11-24`, la única fecha que muestra el sitio.
2. `ella` — cómo la llamás (sale en el título).
3. `whatsapp` — tu número con código de país, sin `+` (ej. `595981123456`). Si queda vacío, WhatsApp le deja elegir el contacto.
4. Los textos de `cartas`, `fotos`, `razones`, `cupones`, `capsula`, `secreta` y `final`. Están escritos como borrador: cambialos por tus palabras.
5. En `quiz`, las preguntas sobre las fotos usan `ok: N` (posición de la respuesta correcta, empezando en 0).

## Cambiar o agregar fotos

1. Copiá la foto a `img/` y una versión chica (unos 720 px de ancho) a `img/thumbs/`.
2. Agregá un bloque en `fotos` dentro de `config.js` con `src`, `thumb`, `titulo` y `nota`.

El juego de memoria usa las primeras 4 fotos. El rompecabezas usa `img/thumbs/puzzle.jpg` (cuadrada); reemplazala por otra cuadrada si querés.

## Música (opcional)

Subí un `.mp3` (por ejemplo `audio/cancion.mp3`) y poné la ruta en `musica`. Aparece un botón ♪ en una esquina.

## Subirlo a GitHub Pages (gratis, sin dominio)

1. Creá un repositorio en GitHub y subí **el contenido** de esta carpeta (que `index.html` quede en la raíz).
2. En el repo: **Settings → Pages**.
3. En *Source* elegí **Deploy from a branch**, rama `main`, carpeta `/ (root)`, y guardá.
4. En un par de minutos queda en `https://TU-USUARIO.github.io/NOMBRE-DEL-REPO/`. Ese es el link para ella.

Importante: el archivo tiene que llamarse `index.html` en minúsculas. GitHub distingue mayúsculas, y `Index.html` no se abre como página principal.

## Probar y privacidad

- Agregá `?preview=1` al final de la URL para saltarte la puerta y abrir la cápsula (sirve para revisar todo).
- Para volver a ver la puerta, borrá los datos del sitio en el navegador.
- Un repositorio público también es público el contenido: cualquiera con el link puede ver el sitio. El sitio le dice a los buscadores que no lo indexen, pero no lo protege. Si querés más privacidad, usá un nombre de repo difícil de adivinar y no compartas el link.

## Estructura

```
index.html
manifest.webmanifest   (permite "agregar a pantalla de inicio")
sw.js                  (versión sin conexión)
css/style.css
js/config.js           (editás acá)
js/utils.js            (confeti, fechas, utilidades)
js/games.js            (juegos y cupones)
js/app.js              (puerta, secciones, navegación)
img/                   (fotos, video, íconos)
```
