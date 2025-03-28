# bimestral_1

## Explicacion line a linea

- import pygame: quiere decir que se importó una librería para desarrollar el juego.

- from random import randint: permite generar números aleatorios.

- pygame.init(): inicializa pygame para que funcione correctamente.

- ANCHURA_VENTANA = 600: define el ancho de la ventana.

- ALTURA_VENTANA = 600: define el alto de la ventana.

- COLOR_FONDO = (255, 255, 250): establece un color de fondo (blanco).

- PANTALLA = pygame.display.set_mode(...): crea la ventana del juego.

- PARAR_JUEGO = False: indica que el juego está en ejecución.

- XX_COHETE:coordenada (x) iniciales del cohete.

- YY_COHETE:coordenada (y) inicial del cohete.

- ALTURA_COHETE:Define el alto del cohete

- ANCHURA_COHETE: Define el ancho del cohete

- MOVIMIENTO_XX_COHETE = 0: variable para el movimiento horizontal.

- XX_PLANETA = randint(30, 130): el planeta aparece en una posición aleatoria.

- YY_PLANETA = 20: altura inicial del planeta.

- VELOCIDAD_PLANETAS = 2: controla la velocidad de caída.

- PUNTOS = 0: almacena la puntuación.

- FUENTE = pygame.font.Font(None, 24): define el tamaño y tipo del texto puntos.

- MARCADOR: crea el texto de la puntuación.

- pygame.image.load( ): carga las imágenes del cohete y planetas.

- pygame.display.set_caption( ): establece el título de la ventana.

- while not PARAR_JUEGO:: mantiene el juego en ejecución.

- for event in pygame.event.get():por cada evento en pygame.event.get( ) se estara comprobando las siguientes condiciones

- if event.type == pygame.KEYDOWN:verifica si se esta presionando una tecla si es asi pasara a la siguiente linea

-  if event.key == pygame.K_ESCAPE: 
        PARAR_JUEGO = True --->  si la tecla espacio se encuentra presionada el juego se detendra  

- if event.key == pygame.K_RIGHT:
        MOVIMIENTO_XX_COHETE = 4 ----> si la tecla derecha se presina le sumara 4 a la posicion (x) generando movimiento

- elif event.type == pygame.KEYUP:
         MOVIMIENTO_XX_COHETE = -4 ---> si la cualquier tecla se preiona se le restara 4 a al eje (x) generando movimiento 

-   if XX_COHETE < -10 or XX_COHETE>ALTURA_VENTANA:
            PARAR_JUEGO = True ----> si el eje (x) del cohete es menor que -10 o el eje (x) es del cohete es mayor que la altura de la ventana se detendra el juego

- PANTALLA.fill(COLOR_FONDO): se establecera elcolor del fondo teniendo en cuenta la constante (COLOR_FONTO)

- PANTALLA.blit(IMG_PLANETA_IZQUIERDO, (XX_PLANETA, YY_PLANETA)): sobrepondra la imagen del planeta izquierdo sobre el fondo en las coordenadas indicadas

- PANTALLA.blit(IMG_PLANETA_DERECHO, (XX_PLANETA + XX_ENTRE_PLANETAS, YY_PLANETA + YY_ENTRE_PLANETA)): sobrepondra la imagen del planeta derecho sobre el fondo en las coordenadas indicadas

- YY_PLANETA = YY_PLANETA + VELOCIDAD_PLANETAS: dara el movimiendo vertical de los planetas

- if YY_PLANETA > ANCHURA_VENTANA: se comprueba si el eje (y) es mayor que la anchura de la ventana

- XX_PLANETA = randint(55, 150): el eje (x) del planeta tendra un valor aletario entre 55 y 150

- YY_PLANETA = 25: el eje (y) del planeta sera 25

- PUNTOS = PUNTOS + 1: se le sumara un punto a los puntos

- MARCADOR = FUENTE.render(str(PUNTOS) + " puntos", 1, (255, 0, 0)): se rendizara el texto marcador (los puntos) en la ventana del juego

- PUNTO_INFERIOR_DERECHO_PRIMER_PLANETA_X = XX_PLANETA + ALTURA_PLANETA: se establece que el punto inferior derecho del planeta sera igual a la suma de del eje (x) del planeta y la altura del mismo

- PUNTO_INFERIOR_DERECHO_PRIMER_PLANETA_Y = YY_PLANETA + ANCHURA_PLANETA: se establece que el punto inferior derecho del primer planeta sera igual a la suma de del eje (y) del planeta y la anchura del mismo

- if PUNTO_INFERIOR_DERECHO_PRIMER_PLANETA_X > XX_COHETE: comprueba si se esta cumpliendo que el punto inferior derecho del primer planeta en el eje (x) es mayor que el eje (x) del cohete si es cierto pasara a la siguiente linea

- if PUNTO_INFERIOR_DERECHO_PRIMER_PLANETA_Y > YY_COHETE:comprueba si se esta cumpliendo que el punto inferior derecho del primer planeta en el eje (y) es mayor que el eje (y) del cohete si es cierto pasara a la siguiente linea

- if PUNTO_INFERIOR_DERECHO_PRIMER_PLANETA_Y < YY_COHETE + ANCHURA_COHETE: comprueba que si el punto inferior derecho del primer planeta en el eje  es menor que la suma del eje (y) del cohete y la anchura de si mismo

- PARAR_JUEGO = True: si las 3 condiciones anteriores fueron verdaderas en juego se detendra

- PUNTO_INFERIOR_IZQUIERDO_SEGUNDO_PLANETA_X = XX_PLANETA + XX_ENTRE_PLANETAS: se establece que el punto inferior izquiero del segundo planeta sera igual a la suma de del eje (x) del planeta y la anchura del mismo
                
- UNTO_INFERIOR_IZQUIERDO_SEGUNDO_PLANETA_Y = YY_PLANET+ YY_ENTRE_PLANETA + ANCHURA_PLANETA: se establece que el punto inferior izquiero del segundo planeta sera igual a la suma de del eje (y) del planeta y la anchura del mismo

- if XX_COHETE + ALTURA_COHETE > PUNTO_INFERIOR_IZQUIERDO_SEGUNDO_PLANETA_X: comprueba si se esta cumpliendo que el eje (x) mas la altura del cohete es mayor que el punto inferior izquiedo del segundo planata en el eje (x)

- if XX_COHETE < PUNTO_INFERIOR_IZQUIERDO_SEGUNDO_PLANETA_Y: comprueba que el eje (x) del cohete sea menor que el punto inferior izquiedo del segundo planata en el eje (y) 

- if XX_COHETE + ANCHURA_COHETE > PUNTO_INFERIOR_IZQUIERDO_SEGUNDO_PLANETA_Y: comprueba que si al sumar el eje (x) del cohete más la anchura del mismo sea mayor que el punto inferior izquiedo del segundo planata en el eje (y) 

- PARAR_JUEGO = True: se detendra el juego

- XX_COHETE = XX_COHETE + MOVIMIENTO_XX_COHETE: define que el eje (x) del cohete sera igual a la suma de su eje (x) más su movimiento en el eje (x) del cohete

- PANTALLA.blit(MARCADOR, (20, 580)): se sobre pondra el marcador en las coordenadas indicadas

- PANTALLA.blit(IMG_COHETE, (XX_COHETE, YY_COHETE)): se cargara la imagen del cohete en la ventana sobre las coordenadas del eje (x) y (y) del cohete

- pygame.display.update(): se actulizara la pantalla 

![diagrama de flujo](diagrama.png "diagrama de flujo")