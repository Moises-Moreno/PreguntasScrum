# Sprint de preguntas: eventos y artefactos de Scrum

Juego didáctico de 12 preguntas sobre los eventos y artefactos de Scrum (basado en la Guía de Scrum 2020). Cada persona tiene **una sola oportunidad**.

Es un único archivo (`index.html`), sin dependencias ni proceso de compilación.

## Publicarlo en línea con GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo `scrum-juego`), público.
2. Sube `index.html`, `README.md`, `GUIA-RANKING.md` y la carpeta `apps-script` a la rama `main` (botón **Add file → Upload files**).
3. Ve a **Settings → Pages**.
4. En **Build and deployment**, elige **Deploy from a branch**, rama `main` y carpeta `/ (root)`. Guarda.
5. Espera uno o dos minutos. El juego quedará en `https://TU-USUARIO.github.io/scrum-juego/`.

Comparte ese enlace con tu público.

## Cómo funciona el intento único

El intento se guarda en el `localStorage` del navegador:

- Al comenzar se registra el nombre y, después de cada respuesta, el avance y el puntaje.
- Si la persona recarga la página, continúa en la siguiente pregunta sin poder repetir la anterior.
- Al terminar ya no hay botón para jugar de nuevo.

Por sí solo, GitHub Pages no tiene servidor, así que sin backend esta restricción vale solo por navegador. Para un **ranking y control por nombre único**, sigue `GUIA-RANKING.md` (Google Sheets + Apps Script, gratis). El ranking en vivo se proyecta con `?ranking=1`.

## Probarlo como presentador

Abre la página con `?reset=1` al final de la dirección (por ejemplo `.../scrum-juego/?reset=1`) para borrar tu intento y volver a jugar.

## Personalizar las preguntas

Edita el arreglo `Q` dentro de `index.html`. Cada pregunta tiene:

- `t`: categoría que se muestra arriba.
- `q`: el enunciado.
- `o`: las opciones. **La primera siempre es la correcta**; el juego las mezcla al mostrarlas.
- `e`: la explicación que aparece después de responder.
