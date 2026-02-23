# 1.3 Manejo de eventos
El manejo de eventos en Flet es el proceso de vincular una acción del usuario con un bloque de código específico en Python. Flet utiliza un modelo de programación asíncrona y basada en callbacks.

## 1. El Mecanismo de "Callback"
Un callback es simplemente una función que pasas como argumento a un control. No la llamas tú; Flet la llama cuando ocurre el evento.

Definición: Creas una función que acepte un argumento (comúnmente llamado ```e```).

Asignación: Pasas esa función a la propiedad del control (ej. ```on_click=mi_funcion```).

## 2. El Objeto ```ControlEvent```
Cada vez que se dispara un evento, Flet envía un objeto de la clase ```ft.ControlEvent``` a tu función manejadora. Este objeto es una "caja" que contiene:

```e.control```: El objeto exacto que disparó el evento (puedes cambiar su color, texto, etc., directamente desde aquí).

```e.page```: Una referencia a la página principal.

```e.data```: Información adicional (como las coordenadas de un clic o el texto de un campo).

## 3. Sincronización de la Interfaz (```page.update()```)
Este es el concepto más importante en el manejo de eventos de Flet. A diferencia de otros frameworks, los cambios en el código no se reflejan automáticamente en la pantalla. Cuando tu manejador de eventos cambia una propiedad (como ```boton.text = "Enviado"```), el cambio ocurre en la memoria de Python. Para que el usuario lo vea, debes llamar a:

```page.update()```: Actualiza toda la página.

```control.update()```: Actualiza solo un componente específico (más eficiente).

## 4. Manejo de Eventos con Parámetros (Lambdas)
A veces necesitas pasar datos extra a tu manejador de eventos que no están en el objeto e. Para esto se utilizan las funciones Lambda:
```python
ft.ElevatedButton("Eliminar", on_click=lambda e: borrar_item(e, item_id=5))
```

## Arquitectura de Comunicación
Flet maneja los eventos a través de un Socket (una conexión abierta). Cuando el usuario hace clic, el navegador envía un mensaje JSON al servidor de Python, Python ejecuta tu función y devuelve otro JSON con las instrucciones de actualización.

## Biliografia
Introduccion - Flet. (s. f.-b). Flet. https://docs.flet.dev/
