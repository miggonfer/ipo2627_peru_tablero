# Proyecto Tablero

El proyecto consiste en una aplicación que implementa un juego de fichas dispuestas en un tablero.

# Objetivos

El proyecto será una aplicación web usando HTML, CSS y JS nativos, sin bibliotecas ni frameworks auxiliares.

Los objetivos del proyecto son: 
- Composición apoyándada en Flexbox & Grid
- Interacción mediante la API `Drag & Drop` (y `dataTransfer`) para el movimiento de fichas. 
- Selección desde JS de elementos HTML mediante atributos `data-*`
- Posicionamiento `position` para el diseño de la asistencia al usuario


# Descripción

El sistema interactúa con un único actor que es el usuario encargado de jugar al juego. 

El tablero donde se practica el juego es una estructura cuadrada NxN con N>=3. En cada celda del tablero se muestra una única ficha, teniendo en cuenta que existen 3 tipos de fichas distinguibles por su forma y color. 

El sistema permitirá al jugador realizar las siguientes acciones:
- Comenzar una nueva partida (tablero inicial)
- Cambiar la dimensión N (con N>=3) del tablero NxN 
- Cambiar el tamaño de las fichas, admitiendo tres magnitudes: pequeña, mediana y grande.
- Modificar el aspecto - forma y color - de las fichas. Por ejemplo: las fichas podrían ser círculos, cuadrados, triángulos, etc.
- Obtener información sobre la mecánica del juego. 


La modificación de las características del tablero o las fichas supondrá la creación de un nuevo tablero de partida. 

La mecánica del juego es la siguiente:
- Comienzo: el tablero de partida consiste en una distribución de fichas aleatorias teniendo en cuenta que las fichas seleccionadas permita que el juego pueda concluir.
- Movimiento: el jugador podrá intercambiar las fichas situadas en dos celdas. 
- Fin: el tablero se completa cuando cada una de las filas del tablero contiene fichas del mismo tipo.


# Diseño

- La aplicación deberá estar implementada siguiendo un patrón MVC (_Model-View-Controller_) con objeto de clarificar y diferenciar las distintas responsabilidades. 
- Tanto la distribución del código de los ficheros como la propia organización de los ficheros incluidos en la carpeta del proyecto deberán facilitar la comprensión y el mantenimiento de la solución aportada. 


## Interacción 

La implementación de la interacción estará guiada para favorecer la usabilidad de la aplicación.

# Buenas prácticas HTML/CSS/JS

- Vinculación moderna de los componentes HTML, CSS y JS
- Etiquetado HTML semántico y moderno. 
- Estrategia de selectores CSS mantenible.
- Selección de composiciones apropiadas (unidimensional, bidmiensional)
- Aplicación justificada del posicionamiento. 
- Separación clara y organizada de los distintos aspectos estilísticos considerados: diseño cromático, tipográfico y espacial. Y cada uno estará cimentado en una sólida estrategia:
  - diseño cromático: monocromático, triádico, complementario, etc.
  - diseño tipográfico: dos fuentes contrastadas, una única fuente con niveles distintos de realce, etc.
  - diseño espacial: selección de unidades de medida y contenedores, principios de diseño `Gestalt`, etc. 



# Organización del proyecto

Se mantiene **una sola aplicación**, con punto de entrada en `index.html` y
separación mediante el patrón MVC. No se necesitan dependencias ni frameworks.

```text
ipo2627_peru_tablero/
├── index.html                 # Estructura semántica de la aplicación
├── README.md                  # Enunciado, estructura y ejecución
├── css/
│   ├── base.css               # Colores, tipografía y estilos base
│   ├── layout.css             # Distribución Flexbox/Grid
│   └── components.css         # Tablero, fichas, formulario y diálogo
└── js/
    ├── main.js               # Inicio de la aplicación
    ├── model/
    │   ├── Configuracion.js   # Reglas de configuración
    │   └── Tablero.js         # Datos y reglas del juego
    ├── view/
    │   └── TableroView.js     # Interfaz y eventos del DOM
    └── controller/
        └── JuegoController.js # Coordina vista y modelo
```

## Ejecutar la aplicación

1. Abrir esta carpeta en Visual Studio Code.
2. Iniciar **Live Server** sobre `index.html` o abrir una terminal en esta
   carpeta y ejecutar `python -m http.server 8000`.
3. Si se usa Python, visitar `http://localhost:8000/` en el navegador.

**Nota:** los módulos JavaScript deben servirse a través de HTTP. No abrir
`index.html` directamente mediante `file://`.

## Qué se conserva y qué se elimina

Esta versión incluye solo los archivos empleados por la aplicación. No se
incluye la versión antigua `tablero.html` ni el directorio `.git` (historial y
metadatos de Git). El ZIP está pensado como copia limpia del código fuente;
para seguir trabajando con el repositorio Git original, copiar sus archivos
a la carpeta de trabajo existente sin borrar su `.git`.
