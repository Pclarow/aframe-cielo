# Meteoritos en Atacama · Pedro Claro

Módulo 03 de la Unidad 3 (Taller de Diseño de Interfaces, UAI): escena 3D hecha con **A-Frame**.

**Jugar:** https://pclarow.github.io/aframe-cielo/

## De qué se trata

Estás de noche en el desierto de Atacama, con cielo estrellado, cerros y un observatorio. Desde el cielo caen meteoritos encendidos y tienes un bate en la mano: hay que batearlos antes de que se estrellen.

- **Mirar:** arrastra el mouse (o mueve el celular).
- **Batear:** clic, toque o barra espaciadora cuando el meteorito esté cerca y frente a ti.
- Golpe normal: +1. Golpe al centro: ¡jonrón! +3.
- Si un meteorito toca el suelo deja un cráter y pierdes una vida (hay 3).
- Cada golpe sube la dificultad: caen más rápido y más seguido.

## Con anteojos de realidad virtual

1. Abre la página en el navegador del visor (por ejemplo Meta Quest) y toca el botón **VR** de abajo a la derecha.
2. Aprieta el **gatillo** de un control para empezar.
3. Cada control tiene un bate: **batea moviendo el brazo** de verdad. El golpe cuenta si el bate toca el meteorito con un swing; si es fuerte, es jonrón. El control vibra al golpear.
4. Los meteoritos pasan a la altura del pecho, al alcance del bate.

## Cómo está hecho

- **A-Frame 1.5**: escena, cámara con look-controls y el bate como hijo de la cámara.
- **Componente `estrellas`**: genera 900 estrellas al azar en una cúpula.
- **Componente `juego`**: crea los meteoritos con Three.js, los mueve en cada `tick`, detecta el golpe (distancia y ángulo respecto a la mirada) y anima el swing del bate.
- **Controles de VR** (`meta-touch-controls`, `vive-controls`, `windows-motion-controls`): el bate es un segmento desde el control hasta la punta; se mide la velocidad de la punta y se revisa si toca algún meteorito (`THREE.Line3`).
- **Web Audio API**: sonido del golpe y del choque generados con ruido filtrado.
