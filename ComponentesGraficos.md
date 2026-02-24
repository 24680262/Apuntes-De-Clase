# 1.4 Manejo de Componentes Gráficos de Control
En la arquitectura de Flet, los componentes (llamados Controls) no son solo dibujos; son objetos de Python con propiedades que puedes manipular en tiempo real.

## 1. El Estado de un Control (Properties)
Cada componente tiene un conjunto de atributos que definen su apariencia y comportamiento. Manejar un control implica modificar estas propiedades:

>Visuales: ```bgcolor``` (color de fondo), ```width```, ```height```, ```visible```, ```opacity```.

>De Contenido: ```value``` (para el texto de un ```TextField``` o un ```Text```), ```src``` (para una ```Image```).

>De Estado: ```disabled``` (para habilitar o deshabilitar botones), ```selected``` (para checkboxes).

## 2. Uso de Referencias (```Ref```)
Cuando una aplicación crece, tener docenas de variables globales para cada botón o cuadro de texto se vuelve un caos. Flet introduce el concepto de ```Ref``` (Referencias).

>Permite crear una "etiqueta" para un control antes de que este sea renderizado.

>Facilita el acceso a los valores del control desde cualquier parte del código sin perder la estructura limpia.

## 3. Contenedores y Layout (Estructura de Control)
Manejar componentes no solo es cambiar su color, sino decidir dónde viven. Flet utiliza un sistema de Flexbox (similar a CSS):

>```ResponsiveRow```: Un componente avanzado que permite que los controles cambien de tamaño o se reacomoden según el dispositivo (móvil, tablet o PC).

>```ListView``` y ```GridView```: Controles especializados para manejar grandes cantidades de datos de forma eficiente (haciendo "scroll" solo de lo necesario).

## 4. Animaciones de Control
Flet permite manejar transiciones visuales de forma sencilla mediante la propiedad ```animate```. Puedes animar cambios de tamaño, posición o rotación simplemente cambiando el valor de la propiedad y llamando a ```update()```.

## Tipos de Controles Principales

Tipo de Control             Función Principal	                                                        Propiedad Clave
                        
Input Controls:	            Recibir datos (```TextField```, ```Dropdown```):	                        ```value```
                        
Selection Controls:	        Opciones (```Checkbox```, ```Switch```, ```Radio```):	                    ```value```(booleano)
                        
Information Controls:	      Mostrar datos (```Text```, ```Icon```, ```Image```):                     	```value``` / ```src```
                        
Action Controls:	            Ejecutar tareas (```ElevatedButton```,```FloatingActionButton```):	      ```on_click```
