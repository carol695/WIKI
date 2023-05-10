
# :desktop_computer: POOBTRIZ




Tetris es un juego de puzzle muy popular que fue creado en 1984 por el programador ruso, Alexey Pajitnov. El objetivo del juego es colocar piezas de diferentes formas llamadas "tetrominos" en una matriz de juego y completar líneas horizontales sin espacios vacíos. A medida que se completan las líneas, se eliminan del juego y se otorgan puntos al jugador.

---------------

## :bookmark_tabs: Indice

* [Descripción del proyecto](#Descripción-del-proyecto)

    * [ Buffos](#Buffos)
    * [ Rebordes](#Rebordes)

* [Antecedentes](#Antecedentes)

* [Problema a resolver](#Problema-a-resolver)

* [Diagramación](#Diagramas-del-proyecto)

* [Criterios de calidad](#Criterios-de-calidad)

* [Demostración](#Demostración)

* [Acceso al proyecto](#Acceso-proyecto)

* [Tecnologías utilizadas](#Tecnologías-utilizadas)

* [Personas-Desarrolladores del Proyecto](#Personas-desarrolladores)

* [Conclusión](#Conclusión)

## :books: Descripción del proyecto

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

## :briefcase: Antecedentes 

El código hace parte de un desarrollo realizado en la materia POOB. De esa lógica solo se hará uso del back.

Inicialmente viene con problemas de sincronización para el modo multijugador, puesto que el tema de concurrencia y paralelismo no fue implementado de forma adecuada


## :nazar_amulet: Problema a resolver 

Los problemas identificados que se pueden resolver a tener un tetris en lineal son los siguientes: 

1. Accesibilidad: un Tetris en línea debería ser jugado por cualquier persona con acceso a Internet y un navegador web, lo que significa que el juego puede ser disfrutado por una audiencia mucho más amplia.

2. Interacción social: una versión en línea del Tetris debería permitir a los jugadores interactuar entre sí. Esto puede llegar a generar una experiencia social y una sensación de comunidad para los jugadores.

3. Variedad: una versión en línea del Tetris debería ofrecer una amplia variedad de opciones y características, como modos de juego adicionales, opciones de personalización, diferentes escenarios en cuanto a piezas, variedad de funcionalidades y gráficos mejorados. Esto puede mantener el juego fresco e interesante para los jugadores. 

## :chart_with_upwards_trend: Diagramas del proyecto 

### Caso de uso 

 ![Imagen1](https://github.com/carol695/WIKI/assets/63822072/aae11fb7-0d16-4d73-84c9-15e1f5857348)
 
### Diagrama de secuencia 


![c90a3847-4519-4857-a271-04ccdbe5fed6](https://github.com/carol695/WIKI/assets/63822072/616fd90a-6877-42f8-af67-d98c4655a11f)

Este diagrama representa la interacción entre el componente del lobby que permita añadir
un usuario, obtener un lobby, y comunicarse en una sala virtual. Además, el cliente podría enviar
mensajes al servidor, como solicitudes para unirse a otras salas. El servidor podría enviar mensajes
a todos los clientes conectados en la sala del lobby para informarles sobre las acciones realizadas
por otros usuarios.

![image](https://github.com/carol695/WIKI/assets/63822072/63c88143-eb8e-485d-8f15-f093513bfcd4)

Este diagrama representa la interacción entre el componente del lobby que permite crear un lobby,
donde si es administrador se crea un lobby y se empieza a jugar. 

*Nota:* Estos son dos ejemplos de diagramas de secuencias, sin embargo, en el portal de azure DevOps se encuentran más diagramas de este tipo en las diferentes historias de usuarios de los sprints realizados.  

### Diagrama de componentes 

![Imagen2](https://github.com/carol695/WIKI/assets/63822072/bcc5b26e-5d04-4f33-8a71-f22ce2d430fa)

### Diagrama de despliegue 

#### Despliegue de back-end

![49576bd5-f6ce-4b0b-8877-13bcd99130e9](https://github.com/carol695/WIKI/assets/63822072/a72b880e-4a5e-4dc0-b86a-889dc502af29)

Desde el browser en internet se comunica con el BackEnd de la aplicación, luego este es desplegado
en una app Service y en este se encuentra un app Service plan. Para el desarrollo de esto, se trabajará
con un resource Group

#### Despliegue de Front-end

![4a06db48-9eab-44de-9612-6d425b6be5a8](https://github.com/carol695/WIKI/assets/63822072/3b5d8f61-ce69-45a1-9598-01ca899282fc)

Desde el browser en internet se comunica con el FrontEnd de la aplicación, luego este es
desplegado en una app service web App y en este se encuentra un app Service plan. Para el
desarrollo de esto, se trabajará con un resource Group. 

## :bar_chart: Criterios de calidad


## :mag_right: Demostración

## :bulb: Acceso proyecto

P
## :computer: Tecnologías utilizadas
## :technologist: Personas desarrolladores

- Carol Cely Rodriguez
- Juan Pablo Fonseca
- Santiago Cardenas Amaya

## :brain: Conclusión 





