# Grainient Studio

Configurador visual de fondos animados con grano (WebGL2), pensado para exportar directo a Webflow.

**Demo:** _(agregá acá el link de GitHub Pages)_

## Qué hace

- Cuatro formas: **Banda**, **Círculo** (con elipse y puntas de estrella), **Lava** (metaballs) y **Rayos** (luz que entra desde fuera de pantalla, con cono, rayos irregulares y animación de luz).
- **Texturas de fondo**: degradé, viñeta, nubes, papel, tramado de puntos y líneas, con color secundario.
- **Estilos de movimiento** y **estilos de luz** de un clic, ajustables después.
- Rampa de hasta 8 colores con posición, ancho (zona sólida), fusión con los vecinos y grano, independientes por color.
- Color de fondo propio, resplandor, giro, pulso y deformación de flujo.
- Presets: veta con corazón blanco, sol naciente, estrella, lava, aurora, luz entrante cálida y fría.
- Exporta un snippet autocontenido (sin dependencias) y la configuración en JSON.
- **Copiar ajustes / Copiar link / Pegar ajustes** para pasar un set entre personas.
- **Deshacer / rehacer** (⌘Z / ⇧⌘Z, o Ctrl+Z / Ctrl+Y).
- **Reubicar colores** arrastrando la manija ⋮⋮ (con vista previa de dónde cae) o con las flechas de cada color.
- **Invertir rampa** (cambia el resultado) e **Invertir lista** (solo cambia el orden en el panel).
- La **posición** de cada color queda acotada entre sus vecinos: nunca cambia de lugar por accidente.
- **Favoritos** guardados en el navegador (renombrables con el lápiz o doble clic), con opción de copiarlos todos y pasarlos a otra persona.

## Compartir un set con otra persona

- **Copiar link** (solo en la URL publicada): genera un link que abre el studio con esos ajustes exactos.
- **Copiar ajustes**: copia el JSON. La otra persona lo pega con **Pegar ajustes**.
- **Copiar todos los favoritos**: copia tu colección. Al pegarla con **Pegar ajustes**, se suman a los favoritos de la otra persona.

Los favoritos viven en el `localStorage` de cada navegador: no se sincronizan solos entre personas ni dispositivos.

## Usar el snippet en Webflow

1. **Exportar a Webflow** → copiar el snippet.
2. Pegarlo en *Page Settings › Custom Code › Before `</body>`*.
3. En la sección: `position: relative` y `overflow: hidden`.
4. Agregar un Div vacío con el atributo `data-grainient`.
5. Al contenido de la sección: `position: relative; z-index: 1`.

Opcional: `data-grainient='{"timeSpeed":0.15}'` sobreescribe valores solo para ese Div.

El Designer no ejecuta scripts: el fondo se ve en Preview o en el sitio publicado.

## Estructura

Todo vive en `index.html`: interfaz, motor de render (`<script id="engine">`) y shader GLSL. El snippet exportado reutiliza ese mismo motor.

## Créditos

Basado en el componente **Grainient** de [React Bits](https://reactbits.dev) (David Haz). Revisá la licencia vigente en el [repositorio de React Bits](https://github.com/DavidHDev/react-bits) antes de uso comercial.
