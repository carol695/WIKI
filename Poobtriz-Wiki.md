# Poobtriz



Tetris es un juego de puzzle muy popular que fue creado en 1984 por el programador ruso, Alexey Pajitnov. El objetivo del juego es colocar piezas de diferentes formas llamadas "tetrominos" en una matriz de juego y completar líneas horizontales sin espacios vacíos. A medida que se completan las líneas, se eliminan del juego y se otorgan puntos al jugador.

Por otra parte, se desarrolló un programa que permite jugar una versión alternativa al tetris tradicional, con la posibilidad de jugar en línea, donde se puede jugar a través de Internet en un navegador web. En POOBTriz se usarán bloques de diferentes formas, en el cual los tetrónimos pueden ser de diferentes tipos y son reconocidos por su reborde, es decir: 

- Si el tetronimo tiene el borde de color **negro**, no se generá ninguna acción especial. 
- Si se completa una línea con un bloque donde los tetronimos tegan borde **plateado**, la línea no desaparecerá. 
- Si el borde el **dorado**, se transforman en en el mejor bloque para el lugar donde se ubican.
- Cuando el bloque se fije y el tetronimo tenga borde **rojo** se autodestruirá y destruirán los bloques que este
toque.

De igual manera, en este programa el jugador tendrá la posibilidad de  seleccionar una velocidad inicial para que el juego transcurra con esta misma velocidad. 



## Integrantes

- Carol Cely Rodriguez
- Juan Pablo Fonseca
- Santiago Cardenas Amaya

## Antecedentes

El código hace parte de un desarrollo realizado en la materia POOB. De esa lógica solo se hará uso del back.

Inicialmente viene con problemas de sincronización para el modo multijugador, puesto que el tema de concurrencia y paralelismo no fue implementado de forma adecuada

## Necesidad

![image.png](/.attachments/image-8b59abe4-e7b1-45fa-8d82-38b49fc8f953.png)