
# POOBTRIZ




Tetris es un juego de puzzle muy popular que fue creado en 1984 por el programador ruso, Alexey Pajitnov. El objetivo del juego es colocar piezas de diferentes formas llamadas "tetrominos" en una matriz de juego y completar líneas horizontales sin espacios vacíos. A medida que se completan las líneas, se eliminan del juego y se otorgan puntos al jugador.

---------------

## Indice

* [Descripción del proyecto](#Descripción-del-proyecto)

    * [ Buffos](#Buffos)
    * [ Rebordes](#Rebordes)

* [Antecedentes](#Antecedentes)

* [Problema a resolver](#Problema-a-resolver)

* [Diagramación](#Diagramas-del-proyecto)

* [Criterios de calidad](#Criterios-de-calidad)

* [Características de la aplicación y demostración](#Características-de-la-aplicación-y-demostración)

* [Acceso al proyecto](#Acceso-proyecto)

* [Tecnologías utilizadas](#Tecnologías-utilizadas)

* [Personas-Desarrolladores del Proyecto](#Personas-desarrolladores)

* [Conclusión](#Conclusión)

## Descripción del proyecto

![image](https://github.com/carol695/WIKI/assets/63822072/18694fd9-3bfb-42b4-914c-9e81c0a86eec)

Se desarrolló un programa que permite jugar una versión alternativa al tetris tradicional, con la posibilidad de jugar en línea y con multijugador, donde se puede jugar a través de Internet en un navegador web. En POOBTriz se usarán bloques de diferentes formas, en el cual los tetrónimos pueden ser de diferentes tipos y son reconocidos por su reborde, es decir: 

- Si el tetronimo tiene el borde de color **negro**, no se generá ninguna acción especial. 
- Si se completa una línea con un bloque donde los tetronimos tegan borde **plateado**, la línea no desaparecerá. 
- Si el borde el **dorado**, se transforman en en el mejor bloque para el lugar donde se ubican.
- Cuando el bloque se fije y el tetronimo tenga borde **rojo** se autodestruirá y destruirán los bloques que este
toque.

De igual manera, en este programa el jugador se tendrá la posibilidad de visualizar los "buffos". Los buffos aparecerán cada cierto tiempo en un espacio especial de la zona de juego de manera aleatoria para que los jugadores en ningún momento conozcan cada cuánto aparecerá un buffo ni de qué tipo será.


### Buffos
Un buffo es un atributo del juego que le aparecerá a varios jugadores. Estos aparecen cada 10 segundos y se reconocen porque no tienen un color plano.

Para simplificar, se considera invocador aquel que activa un buffo

| Buffo          | Descripción                                                  |
| -------------- | ------------------------------------------------------------ |
| SlowScore| La puntuación que consigan los jugadores se verá disminuida en un 50% por 10 segundos a excepción del invocador. |
| StopDiece      | Se detienen los bloques de los jugadores a excepción del invocador, hasta que se presione la tecla de bajar. |
| Slow           | Los jugadores caerán el doble de lento a excepción del invocador |
| 2x             | El jugador que lo coja bajará el doble de rápido.            |



### Rebordes
Se refiere al contorno del tetrómino. Según el color de este, la ficha se comportará de distintas maneras al momento de hacer contacto con cuadros del tablero que no permitan bajar más:

| Reborde    | Color | Descripción                                                  |
| -------------- | ------------------------------------------------------------ | ------------------------------------------------------------ |
| Classic | Negro | Borde normal. |
| Useless | Plateado | Si se completa una línea con este bloque, la línea no desaparecerá |
| Winner     | Dorado | Se transforman en el mejor bloque para el lugar donde se ubican. |
| Bomb          | Rojo      | Cuando el bloque se fije se autodestruiré y destruirán los bloques que este toque |

## Antecedentes 

El código hace parte de un desarrollo realizado en la materia POOB. De esa lógica solo se hará uso del back.

Inicialmente viene con problemas de sincronización para el modo multijugador, puesto que el tema de concurrencia y paralelismo no fue implementado de forma adecuada


## Problema a resolver 

Los problemas identificados que se pueden resolver a tener un tetris en lineal son los siguientes: 

1. Accesibilidad: un Tetris en línea debería ser jugado por cualquier persona con acceso a Internet y un navegador web, lo que significa que el juego puede ser disfrutado por una audiencia mucho más amplia.

2. Interacción social: una versión en línea del Tetris debería permitir a los jugadores interactuar entre sí. Esto puede llegar a generar una experiencia social y una sensación de comunidad para los jugadores.

3. Variedad: una versión en línea del Tetris debería ofrecer una amplia variedad de opciones y características, como modos de juego adicionales, opciones de personalización, diferentes escenarios en cuanto a piezas, variedad de funcionalidades y gráficos mejorados. Esto puede mantener el juego fresco e interesante para los jugadores. 

## Diagramas del proyecto 

### Caso de uso 
 ![Imagen1](https://github.com/carol695/WIKI/assets/63822072/aae11fb7-0d16-4d73-84c9-15e1f5857348)
### Diagrama de secuencia 
### Diagrama de componentes 
### Diagrama de despliegue 
## Criterios de ![Imagen1](https://github.com/carol695/WIKI/assets/63822072/aae11fb7-0d16-4d73-84c9-15e1f5857348)
calidad
## Características de la aplicación y demostración
## Acceso proyecto
## Tecnologías utilizadas
## Personas desarrolladores

- Carol Cely Rodriguez
- Juan Pablo Fonseca
- Santiago Cardenas Amaya

## Conclusión 





