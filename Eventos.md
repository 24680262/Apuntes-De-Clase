# 1.2 Tipos de Eventos
Un evento es una notificación que el framework envía a tu código cuando algo sucede en la interfaz de usuario. En la arquitectura de Flet, estos eventos viajan desde el cliente (el navegador o la app) hacia tu script de Python.

Los podemos clasificar en cuatro categorías principales según su origen y comportamiento:

## 1. Eventos de Entrada de Usuario (Input Events)
Son los más comunes y ocurren cuando el usuario interactúa directamente con un control específico.

>```on_click```: Se dispara al presionar botones (```ElevatedButton```, ```IconButton```) o elementos cliqueables.

>```on_change```: Crucial para formularios. Se activa cada vez que el contenido de un ```TextField```, ```Checkbox```, ```Slider``` o ```Dropdown``` cambia.

>```on_submit```: Específico de los campos de texto; se activa cuando el usuario presiona "Enter".

## 2. Eventos de Teclado (Keyboard Events)
Flet permite capturar pulsaciones de teclas de forma global en la aplicación, no solo dentro de un cuadro de texto. Esto es ideal para crear atajos (ej. ```Ctrl + S``` para guardar).

>```on_keyboard_event```: Captura la tecla presionada (```key```), si se usó Shift, Control o Alt, y el tipo de acción (presionar o soltar).

## 3. Eventos de la Ventana y Ciclo de Vida (Lifecycle Events)
Estos eventos pertenecen al objeto Page y afectan a toda la aplicación.

>```on_resize```: Se dispara cuando el usuario cambia el tamaño de la ventana. Permite crear interfaces responsivas que se adaptan en tiempo real.

>```on_connect``` / ```on_disconnect```: Detectan cuando un usuario abre la aplicación o cierra la pestaña (muy útil en aplicaciones web multiusuario).

>```on_route_change```: Esencial para aplicaciones de varias páginas; detecta cuando la URL o la ruta de navegación cambia.

## 4. Eventos de Arrastrar y Soltar (Drrag & Drop)
Flet tiene soporte nativo para gestos complejos que permiten mover elementos.

```on_pan_update```: Detecta el movimiento de un dedo o mouse sobre un control.

```on_accept```: Se dispara cuando un objeto arrastrado es soltado sobre un área válida (```DragTarget```).

## Estructura de un Evento (```ControlEvent```)
Cuando un evento se dispara, Flet pasa un objeto de clase ```ControlEvent``` a tu función. Este objeto contiene información vital:

>```target```: El ID del control que originó el evento.

>```name```: El nombre del evento (ej. "click").

>```data```: El valor asociado (ej. el texto nuevo en un ```TextField``` o las coordenadas del mouse).

## Bibliografia
Introduccion - Flet. (s. f.-b). Flet. https://docs.flet.dev/
