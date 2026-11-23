# Cielo de Atacama en A-Frame

**Ejercicio Módulo 03 · Realidad Virtual y Entornos Inmersivos**
Taller de Diseño de Interfaces, Universidad Adolfo Ibáñez, 2026 · Pedro Claro

▶️ **Probar:** https://pclarow.github.io/aframe-cielo/

Escena 3D de una noche en el desierto, con cielo estrellado, cerros y la cúpula de un observatorio. Tiene **hotspots** que se activan con la mirada (cursor *gaze* con *fuse* de 1,5 s) o con clic: al activarlos se encienden, suenan y muestran un texto.

## Uso
- **Computador:** arrastrar con el mouse para mirar alrededor; apuntar al centro de una esfera o hacer clic.
- **Celular:** mover el teléfono para mirar; mantener la mira sobre una esfera 1,5 s.

## Tecnologías
- **A-Frame 1.5** (arquitectura Entity-Component)
- Componentes propios: `estrellas` (genera 900 estrellas) y `hotspot` (interacción, texto y sonido con Web Audio)
- Cursor con `fuse` y `raycaster`
- GitHub Pages
