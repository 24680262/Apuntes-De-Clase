# 1.1 Interfaz grafica de usuario

La creación de una GUI en Flet no se trata de colocar píxeles en coordenadas X e Y. Se trata de definir qué elementos quieres y cómo se relacionan entre sí.
El Concepto de "Control" en Flet, todo es un Control. Un botón es un control, un texto es un control, e incluso la ventana misma es un control raíz llamado
```Page```. Estos se organizan en una estructura jerárquica:

## El Contenedor Raiz (```Page```):
Es la instancia que representa la ventana de la aplicación (o la pestaña del navegador). Aquí configuras el título, el tema (oscuro/claro) y el alineamiento.

## Layout Controls (Contenedores):
Son invisibles pero determinan la posición.

```Column```: Apila elementos de arriba hacia abajo.

```Row```: Alinea elementos de izquierda a derecha.

```Container```: Permite añadir bordes, márgenes y colores de fondo a otros controles.

## Leaf Controls (Controles finales): 
Son los que el usuario ve y toca (```Text```, ```ElevatedButton```, ```TextField```).

## El Flujo de Construcción
Para crear la interfaz, sigues este flujo lógico:

Importas el framework: Generalmente como ```import flet as ft```.

Defines la función ```main```: Es donde vive la lógica de tu interfaz.

Instancias controles: Creas los objetos (ej. ```txt = ft.Text(value="Hola")```).

Agregas a la página: Usas ```page.add(txt)``` o ```page.controls.append(txt)``` seguido de ```page.update()```.

## Diferencia técnica: Imperativo vs. Declarativo
A diferencia del modelo imperativo (donde das instrucciones paso a paso para dibujar), Flet es declarativo: tú describes el estado deseado de la interfaz ("Quiero una columna con dos botones") y el framework se encarga de renderizarlo eficientemente usando Flutter en el fondo.

## Bibliografia
Introduccion - Flet. (s. f.). Flet. https://flet.dev/docs/guides/python/how-it-works
