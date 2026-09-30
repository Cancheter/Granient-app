# Grainient Studio

Configurador visual de fondos animados con grano (WebGL2), pensado para exportar directo a Webflow.

**Demo:** _(https://cancheter.github.io/Granient-app/)_

## Qué hace

- Tres formas: **Banda**, **Círculo** (con elipse y puntas de estrella) y **Lava** (metaballs).
- Rampa de hasta 8 colores con posición, ancho y grano independiente por color.
- Color de fondo propio, resplandor, giro, pulso y deformación de flujo.
- Presets: veta con corazón blanco, sol naciente, estrella, lava, aurora.
- Exporta un snippet autocontenido (sin dependencias) y la configuración en JSON.

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
