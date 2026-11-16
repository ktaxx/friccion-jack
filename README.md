# FRICCIÓN

Juego de carreras de bloques en lenguaje Jack, ejecutado sobre la arquitectura Hack.

## Integrantes

- Sofia Rojo 
- Catalina Zuluaga

## Concepto

Un bloque se desliza sobre cuatro cintas transportadoras que avanzan a distintas velocidades. Cada cinta tiene una superficie (hielo, arena o caucho) con un coeficiente de fricción diferente. El jugador debe frenar el bloque dentro de una zona de meta y mantenerlo ahí un tiempo para anotar, antes de que se agote el tiempo del intento o de que la cinta lo saque de la pantalla.

## Factor diferenciador

La dificultad nace de la fricción y no de enemigos ni obstáculos. Un mismo impulso produce resultados distintos según la superficie: en el hielo el bloque casi no frena, en la arena frena a un ritmo intermedio y en el caucho frena con fuerza. El jugador debe aprender cómo se comporta cada superficie para planear su trayectoria.

[Completar: comparación breve con otros juegos de Jack encontrados en la web, para demostrar que no es un juego repetido.]

## Controles

| Tecla | Acción |
|---|---|
| ← / → | Aplica impulso horizontal al bloque |
| ↑ / ↓ | Cambia de carril |
| Q | Sale del juego |

## Mecánicas

- **Fricción por superficie:** en cada ciclo, la velocidad del bloque se reduce según la superficie del carril donde está. El hielo tiene la fricción más baja, la arena una intermedia y el caucho la más alta.
- **Arrastre de la cinta:** cada cinta arrastra al bloque a su propia velocidad.
- **Conservación de la velocidad:** al cambiar de carril, el bloque conserva su velocidad horizontal.
- **Zona de meta:** la zona está delimitada por dos barras verticales. Si el bloque permanece dentro un tiempo suficiente, suma 1 punto y se reinicia en la posición inicial.
- **Tiempo por intento:** cada intento tiene 600 ciclos. La barra "TIEMPO" muestra cuánto queda. Si se agota, el jugador pierde una vida.
- **Rotación de superficies:** cada cierto tiempo, las superficies cambian de carril. Antes del cambio, las marcas de las cintas parpadean como aviso.
- **Vidas:** el jugador tiene 3 vidas. Se pierde una al salir por la izquierda, pasarse de la zona o agotar el tiempo. Al llegar a 0, aparece "GAME OVER".
- **Puntaje:** 1 punto por cada meta alcanzada, visible en la parte superior.

## Arquitectura

El proyecto está organizado en cuatro clases:

- `Main`: punto de entrada. Crea el juego y lo ejecuta.
- `Game`: ciclo principal del juego. Lee el teclado, aplica las reglas (vidas, tiempo, meta), dibuja la pantalla y el marcador, y gestiona la rotación de superficies.
- `Block`: el bloque del jugador. Guarda su posición en 1/8 de píxel y su velocidad, y calcula la fricción y el arrastre en cada ciclo.
- `Belt`: una cinta transportadora. Guarda su velocidad, su superficie (fricción y textura) y dibuja el fondo móvil.

El teclado se lee con `Keyboard.keyPressed()`, sin detener el ciclo del juego.

## Cómo ejecutarlo

1. Descarga o clona este repositorio.
2. Abre el emulador VM de Hack y carga la carpeta del proyecto.
3. Ejecuta el programa. Si se trata de la primera vez, compila los archivos `.jack` antes.
4. Usa las flechas para jugar y Q para salir.

## Video

[Enlace a YouTube]
