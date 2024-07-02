# IISSI-2 IS: Examen de laboratorio

## Proyecto base suministrado

Este repositorio incluye el backend completo (carpeta `DeliverUS-Backend`) y el frontend de `owner` (carpeta `DeliverUS-Frontend-Owner`). Servirá como base para realizar el examen de laboratorio de la asignatura.

## Preparación del entorno

### a) Windows

* Abra un terminal y ejecute el comando `npm run install:all:win`.

### b) Linux/MacOS

* Abra un terminal y ejecute el comando `npm run install:all:bash`.

## Ejecución

### Backend

* Para **rehacer las migraciones y seeders**, abra un terminal y ejecute el comando

    ```Bash
    npm run migrate:backend
    ```

* Para **ejecutarlo**, abra un terminal y ejecute el comando

    ```Bash
    npm run start:backend
    ```

### Frontend

* Para **ejecutar la aplicación frontend de `owner`**, abra un nuevo terminal y ejecute el comando

    ```Bash
    npm run start:frontend:owner
    ```

## Depuración

* Para **depurar el backend**, asegúrese de que **NO** existe una instancia en ejecución, pulse en el botón `Run and Debug` de la barra lateral, seleccione `Debug Backend` en la lista desplegable, y pulse el botón de *Play*.

* Para **depurar el frontend**, asegúrese de que **EXISTE** una instancia en ejecución del frontend que desee depurar, pulse en el botón `Run and Debug` de la barra lateral, seleccione `Debug Frontend` en la lista desplegable, y pulse el botón de *Play*.


## Test

* Para comprobar el correcto funcionamiento de backend puede ejecutar el conjunto de tests incluido a tal efecto. Para ello ejecute el siguiente comando:

    ```Bash
    npm run test:backend
    ```
**Advertencia: Los tests no pueden ser modificados.**

## Problemas con los puertos

En ocasiones, los procesos de backend o frontend, con o sin depuración, pueden quedarse bloqueados sin liberar los puertos utilizados, impidiendo que puedan ejecutarse otros procesos. Se recomienda cerrar y volver a iniciar VSC para cerrar dichos procesos.


## Procedimiento de entrega

1. Borrar las carpetas **node_modules** de backend y frontend y **.expo** del frontend.
1. Crear un ZIP que incluya todo el proyecto. **Importante: Comprueba que el ZIP no es el mismo que te has descargado e incluye tu solución**
1. Avisa al profesor antes de entregar.
1. Cuando el profesor te dé el visto bueno, puedes subir el ZIP a la plataforma de Enseñanza Virtual. **Es muy importante esperar a que la plataforma te muestre un enlace al ZIP antes de pulsar el botón de enviar**. Se recomienda descargar ese ZIP para comprobar lo que se ha subido. Un vez realizada la comprobación, puedes enviar el examen.
  
Si no se siguen estos pasos de manera escrupulosa, cabe la posibilidad de que no se entregue nada o que el ZIP contenga cualquier cosa. 

## Enunciado
La empresa ha decidido ofrecer a los propietarios la posibilidad de asociar un descuento (entero entre 0 y 100, por ejemplo: 10) a sus restaurantes, para que posteriormente el sistema muestre y aplique el descuento especificado a sus productos. Los propietarios podrán establecer un porcentaje de descuento diferente para cada uno de sus restaurantes y que después se aplicarían a los productos de cada restaurante.

Sin embargo, algunos propietarios han indicado que no todos los productos de sus catálogos se promocionan habitualmente. Por ello, la empresa ha decidido, además de permitir al restaurante indicar el porcentaje de descuento sobre el precio original, dar la posibilidad de indicar en cada producto si será promocionado o no.

Todos los productos promocionados de un restaurante serán promocionados con el mismo porcentaje de descuento que el propietario indique en las propiedades de sus restaurantes. Tenga en cuenta que un producto puede estar promocionado pero, si el porcentaje de descuento indicado en el restaurante es 0%, no tendrá ningún efecto. Sólo los propietarios de un restaurante podrán activar y desactivar los productos promocionados así como indicar el descuento promocional.

Por defecto, los restaurantes no tendrán ningún porcentaje de descuento (es decir, el porcentaje de descuento será 0).

Recuerde validar en el backend que, al promocionar/despromocionar un producto, el restaurante asociado tenga un porcentaje de descuento superior a 0. En caso contrario, no podrá ser promocionado.

Por lo tanto, las vistas de edición y creación de los restaurantes deben incorporar un campo nuevo en el formulario (InputItem) para cambiar el porcentaje de descuento, permitiendo al propietario ajustar el valor de la propiedad. Recuerde validar en frontend (y backend) que el valor de ese nuevo campo es compatible con el tipo de dato y las restricciones mencionadas.

Para que el propietario pueda determinar a qué productos se les aplica el descuento del restaurante, modifique la vista de detalle del restaurante, donde se muestra el listado de sus productos, para que incluya un botón que permita al propietario activar o desactivar la promoción para ese producto. En caso de que el restaurante no tenga un descuento mayor que 0, no se mostrará este botón.

Las vistas de creación y edición de producto no incluirán la opción de aplicar o no aplicar el descuento.

El sistema debería mostrar los restaurantes con el descuento aplicado y la opción de promocionarlos o quitarles la promoción tal y como se muestra en la siguiente captura de pantalla:

Image2

Como ejemplo ilustrativo, el propietario de un restaurante podría aplicar un descuento del 10% al restaurante1, y otro descuento del 20% al restaurante2.

Image3

Recuerda que:

El descuento está en el intervalo [0,100].
Si un restaurante activa el descuento promocional, los productos pueden estar promocionados o no.
Implemente los cambios necesarios en Backend y Frontend para incluir esta funcionalidad.
