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

## Con anteojos de realidad virtual (probado en Meta Quest 2)

1. Abre la página en el navegador del visor y toca el botón **VR** (abajo a la derecha).
2. El juego empieza solo después de una cuenta de 3 segundos.
3. Hay un bate en cada mano (izquierda y derecha): **batea moviendo el brazo**, sin apretar botones. Si el swing es fuerte, es jonrón. El control vibra al golpear.
4. Al perder, empieza una nueva partida en 10 segundos (o al tiro con el gatillo).

## Explosiones en el aire

Si un meteorito bateado pasa cerca de uno que va cayendo, chocan y explotan los dos: chispas, una onda de luz y +2 puntos.

## Cómo está hecho

- **A-Frame 1.5**: escena, cámara con look-controls y el bate como hijo de la cámara.
- **Componente `estrellas`**: genera 900 estrellas al azar en una cúpula.
- **Componente `juego`**: crea los meteoritos con Three.js, los mueve en cada `tick`, detecta el golpe (distancia y ángulo respecto a la mirada) y anima el swing del bate.
- **Controles de VR** (WebXR de Three.js, `renderer.xr.getControllerGrip`): cada control lleva un bate; se mide la velocidad de la punta y se revisa si el segmento del bate toca algún meteorito (`THREE.Line3`).
- **Explosiones**: partículas (chispas) que salen en direcciones al azar y se apagan en 1 segundo.
- **Web Audio API**: sonido del golpe y del choque generados con ruido filtrado.
