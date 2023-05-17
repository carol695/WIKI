
# :desktop_computer: POOBTRIZ

Tetris es un juego de puzzle muy popular que fue creado en 1984 por el programador ruso, Alexey Pajitnov. El objetivo del juego es colocar piezas de diferentes formas llamadas "tetrominos" en una matriz de juego y completar líneas horizontales sin espacios vacíos. A medida que se completan las líneas, se eliminan del juego y se otorgan puntos al jugador.

---------------

## Indice

* [Descripción del proyecto](#Descripción-del-proyecto)

    * [ Buffos](#Buffos)
    * [ Rebordes](#Rebordes)

* [Marco Metodológico](#Marco-metodológico)
 
    * [ Scrum](#Scrum)
    * [ DoR](#Definition-of-ready)
    * [ DoD](#Defintion-of-done)
    
* [Marco de Arquitectura](#Marco-de-arquitectura)

    * [ Criterios de calidad](#Criterios-de-calidad)
    * [ Modelo de arquitectura cloud](#Modelo-de-arquitectura-cloud)
    * [ Diagrama de componentes](#Diagrama-de-componentes)
    * [ Diagrama de despliegue](#Diagrama-de-despliegue)
    * [ Diagrama de secuencia](#Diagrama-de-secuencia)

* [Bitácora](#Bitácora)

   * [Sprint Concept](#Sprint-concept)

* [Sprint 1](#Sprint-1)

   * [Sprint Planning](#Sprint-planning)
   * [Sprint Review](#Sprint-review)
   * [Sprint Retrospective ](#Sprint-retrospective)

* [Sprint 2](#Sprint-2)

   * [Sprint Planning](#Sprint-planning)
   * [Sprint Review](#Sprint-review)
   * [Sprint Retrospective ](#Sprint-retrospective)

* [Personas](#Personas-desarrolladores)

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

## Marco metodológico 

### Scrum 
Se implementó Scrum en el proyecto de la siguiente manera: 

1. Definición del equipo: Se seleccionó el equipo en cual se encargó de desarrollar el proyecto. 
2. Se definión un product Owner: El producto Owner seleccionado fue Juan Pablo Fonseca, responsable de definir los objetviso del proyecto y de crear una lista priorizar todas las caracterisitcas, funcionalidades y requisitos del proyecto. 
3. Se planificaron los sprints: Para este caso, se contó con un sprint concept y dos sprint. 
4. Realización de revisiones: Al finalizar cada sprint, se realizó una revisión del sprint, donde cada persona presentó el trabajo que había realizado y completado al product owner, se recibieron comentarios y se planeó el siguienye sprint. 
5. Realización de retrospectivas: Al final de cada spritn, también se realizó una restrospectiva, donde el equipo reflexionó sobre el sprint, se miraron las tareas faltantes y se discutió las formas de mejorar el proceso de trabajo. 

### Definition of ready 

- Historias de usuario bien definidas
- Cristerios de aceptación de historias de usuario definida.
- Identificación de la persona que aceptará las diferentes historias de usuario 

*Independent* 

- La historia de usuario se puede desarrollar independientemente de otras historias. 

*Negotiable*

- La historia de usuarió se discutió con el equipo y se entendió lo que se debía hacer 
- Se definieron los criterios de aceptación 

*Valuable*

- El equipo entiende el por qué se hace esto y el impacto esperado.

*Small*

- Las historias de usuario son pequeñas


### Definition of done 

- Análisis de código

![image](https://github.com/carol695/WIKI/assets/63822072/c932956e-8374-45ed-bde8-35dcc0d9a350)
![image](https://github.com/carol695/WIKI/assets/63822072/771d9b72-7a4a-4b00-9804-d1a005cd73cf)

*DeepScan*

![image](https://github.com/carol695/WIKI/assets/63822072/310414a6-e769-4ff5-9b92-6c720a2060d2)
![image](https://github.com/carol695/WIKI/assets/63822072/699a7c87-ab2a-447d-8a56-0bacdd2daf02)

- Criterios de aceptación cumplidos 
- No se cumplieron todas las historias de usuario 

## Marco de arquitectura 

### Criterios de calidad

**1. Testeabilidad :** El proyecto tiene diferentes test, en el cual se pueden ejecutar facilmente y además se puedene llegar a implementar otras pruebas con el fin de que se detecte algún defecto dentro del programa. 

![image](https://github.com/carol695/WIKI/assets/63822072/4f6e7f3c-e8f5-4af8-a9a5-b5a0f31918b9)

**2. Escalabilidad:** El proyecto es escalable debido a que hace uso de tecnología como la computación en la nube, ya que en azure, por medio de appservices se despliega la acplicación, llegando a tener los dos tipos de escalabilidad. Tanto escalabilidad vertical, como escalabilidad horizontal. 

**3. Modificabilidad:** El proyecto se encuentra diseñado por componentes, esto hace que se pueda modificar de manera individual sin afectar el funcionamiento de otros componentes. Además, cuenta con pruebas, lo que ayuda a indentificar errores en el código y faciliatr la identificación de las partes que necesitan ser modificables. 

![image](https://github.com/carol695/WIKI/assets/63822072/4b9cc4b8-fb75-406b-8ff0-84a74b664901)

### Modelo de arquitectura cloud 

#### Backend 

![49576bd5-f6ce-4b0b-8877-13bcd99130e9](https://github.com/carol695/WIKI/assets/63822072/a72b880e-4a5e-4dc0-b86a-889dc502af29)

Desde el browser en internet se comunica con el BackEnd de la aplicación, luego este es desplegado
en una app Service y en este se encuentra un app Service plan. Para el desarrollo de esto, se trabajará
con un resource Group

#### Front-end

![4a06db48-9eab-44de-9612-6d425b6be5a8](https://github.com/carol695/WIKI/assets/63822072/3b5d8f61-ce69-45a1-9598-01ca899282fc)

Desde el browser en internet se comunica con el FrontEnd de la aplicación, luego este es
desplegado en una app service web App y en este se encuentra un app Service plan. Para el
desarrollo de esto, se trabajará con un resource Group. 

### Diagrama de componentes 

![Imagen2](https://github.com/carol695/WIKI/assets/63822072/bcc5b26e-5d04-4f33-8a71-f22ce2d430fa)

### Diagrama de despliegue

![image](https://github.com/carol695/WIKI/assets/63822072/2e22bc5b-9589-4b66-b08f-54a4d263e377)

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

### Caso de uso 

 ![Imagen1](https://github.com/carol695/WIKI/assets/63822072/aae11fb7-0d16-4d73-84c9-15e1f5857348)

## Bitácora 

### Sprint Concept 

**Duración del Sprint:** Se decide que cada sprint tendrá una duración de seis semanas.

**Planificación del Sprint:** Al inicio de cada sprint, el equipo se reunió para realizar una reunión de planificación del sprint. Durante esta reunión, el Product Owner presentó los elementos e historias de usuarios que se iban a desarrollar durante cada sprint, el equipo de seleccionó las tareas que se comprometián completar durante el sprint.

**Desarrollo del Sprint:** Durante el sprint, el equipo trabajó en las tareas seleccionadas del Sprint. Se intentó llevar a cabo  las prácticas de desarrollo ágil, como el desarrollo de  pruebas automatizadas y revisión de código.

**Revisión del Sprint:** Al finalizar cada sprint, se realizó una reunión de revisión del sprint, donde el equipo presentaó el incremento funcional desarrollado durante el sprint al Product Owner. Durante estas reuniones, se mostraron lo que cada persona trabajó y se recibieron comentarios y sugerencias para futuras mejoras.

**Retrospectiva del Sprint:** Después de la reunión de revisión del sprint, el equipo realizó una retrospectiva del sprint. Durante esta reunión, el equipo reflexionó sobre el sprint que acaba de terminar y discutió qué funcionó bien, qué se puede mejorar y qué acciones tomar en el siguiente sprint para aumentar la eficiencia y la calidad del trabajo.

### Sprint 1

#### Sprint planning 

Durante el Sprint 1, el equipo llevó a cabo una reunión de preparación en la que se generaron las historias de usuario y se definieron las tareas correspondientes a cada una. Durante esta reunión, cada miembro del equipo asumió compromisos individuales para completar las diversas historias de usuario.

Las historias definidas para el sprint 1 fueron: 

**HISTORIAS DE USUARIOS SPRINT 1**

![image](https://github.com/carol695/WIKI/assets/63822072/eb066ffb-6eb0-4740-9357-76378237203f)

*Tareas de cada historia de usuario*

![image](https://github.com/carol695/WIKI/assets/63822072/87fee513-9eb8-4cfa-9d2e-af4487902e71)

![image](https://github.com/carol695/WIKI/assets/63822072/b736ff6a-aa06-4e91-b66f-a73f6b69ce56)


#### Sprint review

**Incremento**

![Picture1](https://github.com/carol695/WIKI/assets/63822072/00ef2705-2b92-449d-873f-d977f7763f8d)

![Picture2](https://github.com/carol695/WIKI/assets/63822072/00072d65-de26-4274-95da-b4213fbd4b4c)


#### Sprint retrospective




### Sprint 2

#### Sprint planning 

Durante el Sprint 2, el equipo también llevó a cabo una reunión de preparación en la que se generaron las historias de usuario y se definieron las tareas correspondientes a cada una. Durante esta reunión, cada miembro del equipo asumió compromisos individuales para completar las diversas historias de usuario.

Las historias definidas para el sprint 2 fueron: 

**HISTORIAS DE USUARIOS SPRINT 2**

![image](https://github.com/carol695/WIKI/assets/63822072/3ec582e6-bf15-4c17-babe-b86b39536a88)

*Tareas de cada historia de usuario*

![image](https://github.com/carol695/WIKI/assets/63822072/3e7a313e-1900-40a3-bed7-232a2d9cef24)

![image](https://github.com/carol695/WIKI/assets/63822072/65a016a0-3f71-4fa7-9079-76c608f45502)

#### Sprint review

*Incremento*

![image](https://github.com/carol695/WIKI/assets/63822072/b7c81665-4820-43fb-a168-a764a98afe83)

![image](https://github.com/carol695/WIKI/assets/63822072/85adb45c-0e56-4744-b810-e58218f247ba)

#### Sprint retrospective




## Personas desarrolladores

- Juan Pablo Fonseca
- Santiago Cardenas Amaya
- Carol Cely Rodriguez

## Conclusión 

El desarrollo de este proyecto fue una experiencia muy enriquecedora para cada uno de los integrantes del grupo, ya que se pudo aprender muchas habilidades nuevas y enfrentar desafíos interesantes. En particular, el aprendizaje de Angular, esto fue muy valioso, ya que Angular es un marco de trabajo popular y ampliamente utilizado para el desarrollo de aplicaciones web.

Durante el desarrollo de este proyecto, fue común enfrentarse a problemas y desafíos técnicos que  requerieron una solución creativa. Estos problemas incluían problemas con la lógica del juego, la gestión de los recursos, la interacción de los usuarios, el desempeño del juego, entre otros. Para resolver estos problemas se requirió  habilidades de resolución de problemas, pensamiento crítico y capacidad de investigación.

Otro aspecto importante que se genero durante la elaboración de este prouecto fue la colaboración y el trabajo en equipo. En muchos casos, se  requirió la colaboración entre todo el equipo para lograr un resultado exitoso. Esto generó habilidades de comunicación efectiva, capacidad de trabajo en equipo y habilidades de liderazgo.

En conclusión, POOBTRIZ fue una experiencia muy enriquecedora y desafiante para cada uno de nosotros. Se pudieron aprender habilidades nuevas, enfrentarse a problemas y desafíos técnicos interesantes, y mejorar habilidades de comunicación y trabajo en equipo.
