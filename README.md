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

## Cómo está hecho

- **A-Frame 1.5**: escena, cámara con look-controls y el bate como hijo de la cámara.
- **Componente `estrellas`**: genera 900 estrellas al azar en una cúpula.
- **Componente `juego`**: crea los meteoritos con Three.js, los mueve en cada `tick`, detecta el golpe (distancia y ángulo respecto a la mirada) y anima el swing del bate.
- **Web Audio API**: sonido del golpe y del choque generados con ruido filtrado.
