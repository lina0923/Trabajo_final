

# Sistema de Gestión de Paquetería

Este es un sistema en Python orientado a objetos que permite gestionar clientes y envíos de paquetes, incluyendo el registro, seguimiento, precios y almacenamiento en archivos JSON.



## Características

* Registro de clientes con dirección.
* Gestión de paquetes estándar y express.
* Creación de envíos asociados a clientes.
* Cálculo automático del precio de los paquetes.
* Cambios en el estado del envío (`pendiente`, `en tránsito`, `entregado`).
* Reportes de ventas por tipo de paquete.
* Guardado y carga de datos en archivos JSON.



## Cómo usarlo

### 1. Ejecuta el programa:

```bash
python nombre_del_archivo.py
```

### 2. Menú interactivo:

```
--- Menú Sistema de Gestión de Paquetería ---
1. Registrar cliente
2. Crear envío
3. Cambiar estado de paquete
4. Mostrar envíos
5. Mostrar totales de ventas
6. Guardar datos
7. Cargar datos
0. Salir
```

---

## Estructura de Clases

* `Direccion`: Representa la dirección del cliente (calle, ciudad, código postal).
* `Cliente`: Contiene el nombre del cliente y su dirección.
* `Paquete` (abstracto): Clase base con atributos como peso, precio base y estado.

  * `PaqueteEstandar`: Hereda de `Paquete`.
  * `PaqueteExpress`: Añade un recargo sobre el precio base.
* `Envio`: Asocia un cliente con un paquete.
* `SistemaEnvios`: Controlador principal que gestiona clientes, envíos y persistencia.



## Guardado y carga de datos

Los datos se guardan automáticamente en `envios.json` usando el formato JSON.

```python
sistema.guardar_archivo("envios.json")
sistema.cargar_archivo("envios.json")
```



## Validaciones

* Clientes no pueden tener nombres vacíos.
* No se permite registrar clientes duplicados.
* El peso del paquete debe ser positivo.
* El precio base no puede ser negativo.
* El estado del paquete debe ser uno de los tres permitidos.



## Requisitos

* Python 3.x
* No se requieren librerías externas (solo `json`).



## Notas

* El programa está diseñado para ejecutarse desde consola.
* En caso de no existir `envios.json`, se inicia con datos vacíos.
* Los recargos en paquetes express están definidos por defecto en 50%.



## Autor

Desarrollado como ejercicio educativo de programación orientada a objetos con persistencia en archivos.

