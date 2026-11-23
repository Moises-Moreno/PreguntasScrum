# Activar el ranking (Google Sheets + Apps Script, gratis)

Los resultados se guardan en una hoja de cálculo tuya. Ahí ves el ranking completo y los contactos para entregar los premios.

## Pasos (unos 10 minutos)

1. Crea una hoja nueva en Google Sheets, por ejemplo "Ranking Scrum".
2. Ve a **Extensiones → Apps Script**, borra el contenido y pega todo el archivo `apps-script/Code.gs`. Guarda.
3. Pulsa **Implementar → Nueva implementación**, tipo **Aplicación web**:
   - Ejecutar como: **Yo**
   - Quién tiene acceso: **Cualquier persona**
4. Autoriza los permisos. Si aparece "Google no ha verificado esta aplicación", elige **Avanzado → Ir a (tu proyecto)**.
5. Copia la URL que termina en `/exec`.
6. En `index.html`, pega esa URL en la línea `const API="";` y sube el cambio a GitHub.
7. Prueba: abre `TU-URL/exec?action=top` en el navegador. Debe mostrar algo como `{"total":0,"top":[]}`.

La hoja `Resultados` se crea sola con el primer registro.

## Cómo usarlo el día de la exposición

- **Ranking en vivo para proyectar:** abre `https://TU-USUARIO.github.io/scrum-juego/?ranking=1`. Se actualiza solo cada 15 segundos.
- **Premios:** en la hoja `Resultados`, ordena por Puntaje (mayor a menor) y luego por Segundos (menor a mayor). El desempate es el tiempo. El contacto está en la columna C.
- **Pruebas:** abre el juego con `?reset=1` para borrar tu intento local. Después borra tu fila de prueba en la hoja, porque el nombre queda registrado.

## Cómo se controla el intento único

- El nombre debe ser único: si ya participó, no deja empezar (aunque la persona cambie de navegador o borre datos).
- Si recarga a mitad del juego, continúa donde se quedó.

## Límites que conviene conocer

- El puntaje lo calcula el navegador, así que alguien con conocimientos técnicos podría enviar uno falso. Antes de premiar, revisa la hoja y desconfía de tiempos imposibles (por ejemplo, menos de 20 segundos para 12 preguntas).
- Alguien podría usar un nombre distinto para jugar dos veces. Si el premio es importante, valida la identidad con el contacto.
- El ranking público muestra nombre, puntaje y tiempo. Los contactos solo se ven en tu hoja. Avisa a los participantes que sus datos se usarán solo para entregar premios.
- Si modificas `Code.gs` después, usa **Implementar → Administrar implementaciones → Editar → Nueva versión** para conservar la misma URL.
