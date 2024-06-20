# Object Options Panel

El Object Options Panel es un componente central que administra las funcionalidades de los objetos en el inventario. A diferencia de estar limitado a un módulo específico, puede ser accedido desde diversas áreas como el módulo de navegación, pools y al ejecutar queries, entre otros puntos de acceso.

| ![Object Options Panel](images/object_dashboard.png) |
| :--: |
| ***Figure 1**. Object Options Panel.*|

La Figura 1 muestra los componentes que conforman el Object Options Panel. A continuación, se explicará cada uno de ellos detalladamente.

## Show More Information Button

Al dar click en el botón `Show More Information` mostrado en la parte superior de la Figura 1, se abre una ventana emergente como la mostrada en la Figura 2, la cual contiene información básica del objeto del inventario seleccionado:

* **Object Id**. Es el identificador del objeto en la base de datos.  Resulta útil para solucionar problemas. Suele utilizarse en el **Query Manager** para crear queries.
* **Class Name**. La clase a la que pertenece el objeto del inventario.
* **Containment Path**. Indicates the complete containment structure of the object.

| ![Object Options Panel Information](images/show_more_information.png) |
| :--: |
| ***Figure 2**. Object Information.*|

## Object Properties

Muestra los valores de los atributos de un objeto del inventario. Estos atributos coinciden con los atributos visibles definidos en el Gestor de Contención. Todos los cambios se introducen automáticamente en la base de datos al pulsar la tecla Intro.

| ![Object Properties](images/object_properties.png) |
| :--: |
| ***Figure 3**. Object Properties.*|

Existen diferentes tipos de atributos.

* **Solo lectura**. Estos son atributos que no pueden ser modificados. En la Figura 3, se puede observar que el atributo creationDate está en color gris, lo que indica que su valor no es modificable.
* Únicos. Estos son atributos cuyo valor debe ser único en el inventario y se indican con color morado.
  | ![Unique attribute](images/unique_att.png) |
  | :--: |
  | ***Figure 3**. Unique attribute.*|
* Obligatorios.Estos son atributos cuyo valor debe ser definido obligatoriamente. Los atributos obligatorios se indican con color rojo, como se muestra en la figura a continuación.
  | ![Mandatory attribute](images/mandatory_att.png) |
  | :--: |
  | ***Figure 3**. Mandatory attribute.*|
  
* **List Type Items**. Son atributos que su valor debe ser definido por los valores establecidos en una lista de un tipo especifico.

## Basic Actions

Las acciones básicas de cada objeto del inventario se muestran en la Figura 4 y son descritas a continuación.

| ![Basic Actions](images/basic_actions.png) |
| :--: |
| ***Figure 4**. Basic Actions.*|

* **New Object.** Crea un único objeto como hijo de Root utilizando la jerarquía de contención estándar.

  | ![Create Object](images/create_object_action.png) |
  | :--: |
  | ***Figure 5**. Create Object.*|

* **New Multiple Objects.** Crea un número definido de objetos a la vez utilizando un patrón de nombres dado.
  
  | ![Create multiple Objects](images/create_multiple_objects_action.png) |
  | :--: |
  | ***Figure 6**. Create Multiple Objects.*|

* **New Object from Template.** Crea un objeto (y posiblemente una estructura de contención compleja bajo él) a partir de una plantilla definida previamente. Ver más detalles en el capítulo **Administrador de plantillas**.
  
* **New Special Object.** Crea un objeto en la Jerarquía de Contención Especial (véase Administrador de Contención).

  | ![Create Special Object](images/create_special_object_action.png) |
  | :--: |
  | ***Figure 7**. Create Special Object.*|

* **New Multiple Special Objects.** Crea varios objetos de la jerarquía de contención especial utilizando un patrón.
  
  | ![Create Multiple Special Objects](images/create_multiple_special_objects_action.png) |
  | :--: |
  | ***Figure 8**. Create Multiple Special Objects.*|

* **New Special Object from Template.** Crea un objeto de jerarquía de contención especial a partir de una Plantilla definida en el **Administrador de Plantillas**.
  
* **Copy to.** A plain copy operation.

  | ![Copy Object](images/copy_action.png) |
  | :--: |
  | ***Figure 9**. Copy Object to another Object.*|

* **Move to.** Mueve el objeto respetando la jerarquía de contención.

  | ![Move Object](images/move_object_action.png) |
  | :--: |
  | ***Figure 10**. Move Object to another Object.*|

* **Copy as Special to.** Copia el objeto respetando la jerarquía de contención especial.

  | ![Copy as Special Action](images/copy_special_action.png) |
  | :--: |
  | ***Figure 11**. Copy as Special Object to another Object.*|
  
* **Move as Special to.** Mueve el objeto respetando la jerarquía de contención especial.
  
  | ![Move as Special Action](images/move_special_action.png) |
  | :--: |
  | ***Figure 12**. Move as Special Object to another Object.* |

* **Manage Attachments.** Gestiona los archivos adjuntos relacionados directamente con el objeto, así como los archivos adjuntos asociados a los elementos de tipo lista vinculados al objeto. En la Figura 13, se muestra cómo se pueden visualizar, agregar, eliminar o descargar los archivos adjuntos directamente relacionados con el objeto. En este caso, un MPLS Router tiene un archivo adjunto directamente relacionado al objeto.

  | ![Manage Direct Attachments](images/manage_attachments_action.png) |
  | :--: |
  | ***Figure 13**. Manage Direct Attachments.* |

  Por otro lado, en la Figura 14, se observa que los archivos adjuntos relacionados indirectamente con el objeto solo pueden ser visualizados y descargados, mas no modificados. En este caso, el MPLS Router tiene un archivo adjunto relacionado indirectamente con el objeto.

  | ![Manage other Attachments](images/manage_other_attachments_action.png) |
  | :--: |
  | ***Figure 14**. Manage other Attachments.* |
  
* **Manage Special Relationships.** Permite crear relaciones arbitrarias entre objetos.
  > Nota: Esta acción debe manejarse con total precaución, ya que puede provocar daños en el modelo.

* **Reports.** Los reportes asociados a los objetos de esta clase. En este caso, Rack tiene tres informes asociados, como se muestra en la Figura 17.
Al seleccionar un reporte especifico se abre una nueva ventana HTML con el resultado de la ejecución del reporte.
Esta sección se explica detalladamente en el capitulo **Reports**.

  | ![Reports](images/reports_action.png) |
  | :--: |
  | ***Figure 17**. Reports.*|
  
* **Copy to Pool.** Copiar el objeto de inventario en un pool que contenga elementos del mismo tipo que el objeto a copiar. Ver más detalles en [Pools](../../pools/README.MD).
  
* **Move to Pool.** Mover el objeto de inventario a un pool que contenga elementos del mismo tipo que el objeto de interés. Para más detalles revise el capitulo [Pools](../../pools/README.MD).
  
* **Add to Folder.** Todos los objetos de inventario pueden añadirse a una Carpeta de Favoritos existente. Ver más detalles en el capítulo **Favoritos**.
  
* **Delete Object.** Elimina el objeto. Esto fallará si el objeto tiene una relación entrante, por ejemplo, un Puerto conectado a un cable.

## Advanced Actions

Las acciones avanzadas de los objetos del inventario difieren del tipo de objeto de interés. Son inyectadas por otros módulos en donde serán detalladas.

| ![Advanced actions](images/advanced_actions.png) |
| :--: |
| ***Figure 18**. Advanced Actions.*|

## Views

| ![Views](images/views.png) |
| :--: |
| ***Figure 19**. Views.*|

* **Object View.** Una vista es una representación gráfica de lo que hay dentro de un objeto. Todas las instancias (objetos) de subclases de `ViewableObject` tienen una Vista de Objeto que muestra los hijos directos del nodo seleccionado.
La mayoría de los objetos, excepto los activos lógicos y administrativos y unos pocos físicos como ranuras y puertos, son subclases de `ViewableObject`.
Un ejemplo de la vista de objeto se muestra en la Figura 20, en donde el objeto seleccionado es un país y en la vista de objeto se encuentran las ciudades y estados que son hijos directos del país seleccionado.

  | ![Object View](images/object_view.png) |
  | :--: |
  | ***Figure 20**. Object View.*|

  En la Figura 21 se encuentra la barra de herramientas que aparece en la parte superior de la Figura 20.

  | ![Object View Toolbar](images/object_view_toolbar.png) |
  | :--: |
  | ***Figure 21**. Object View Toolbar.*|

  En la parte superior izquierda de la Figura 21 aparece un buscador, en donde se puede busca un objeto especifico que sea hijo directo del objeto seleccionado.

  |Icon| Description |
  | :--:|:--:|
  | ![download icon](images/icons/download_icon.png)| Save view|
  | ![refresh](images/icons/refresh_view_icon.png)| Update view|
  | ![refresh](images/icons/connect_icon.png)| Conecta dos nodos (See Physical Connections for more details on how to use it)|
  | ![background](images/icons/background_icon.png)| Add a background image|
  | ![hide labels](images/icons/labels_icon.png)| Hide/show the labels next to the connections|
  | ![labels color](images/icons/labels_color_icon.png)| falta|
  | ![labels color](images/icons/export_icon.png)| Export as image |

* **Rack View.** Esta vista sólo funciona con objetos de la clase Rack o sus subclases. Muestra cómo están organizados los elementos contenidos en el objeto seleccionado, en función de su posición y del número de unidades de rack utilizadas.
  
  | ![Explorer Special Children](images/rack_view.png) |
  | :--: |
  | ***Figure 25**. Rack View.*|

  > Para que esta vista se construya correctamente, deben cumplirse tres condiciones:
  >
  > * El rack debe tener su atributo `rackUnits` establecido en un valor entero válido. Este atributo almacena el número total de unidades de rack que admite el rack. Los valores típicos son 20, 28, 34, 40 o 45.
  > * El atributo `rackUnitsNumberingDescending` debe existir, si no se ha establecido el orden de las unidades de rack se asume una numeración ascendente. Este atributo indica a la vista que muestre las unidades de rack en orden ascendente (si es falso) o descendente (si es verdadero).
  > * Los atributos `rackUnits` y `position` deben existir y tener valores válidos en los elementos contenidos dentro del rack. `rackUnits` en este caso, hace referencia al número de unidades de rack ocupadas por el elemento contenido, mientras que `position` es la posición inicial del elemento contenido, basada en 1, numerada de arriba a abajo. El proveedor de su equipo suele proporcionar este valor. Si el valor de `rackUnits` es 0, el elemento no será desplegado en la vista.

    | ![Rack Properties](images/rack_properties_valid.png) |
  | :--: |
  | ***Figure 26**. Rack Properties.*|
  
  | ![Children Rack Properties](images/rack_child_valid_properties.png) |
  | :--: |
  | ***Figure 27**. Rack Children Properties.*|
  
  En la parte superior de la Figura 25 se observa un menú.

  | ![Rack View Menu](images/rack_view_menu.png) |
  | :--: |
  | ***Figure 28**. Rack View Menu.*|

  * El botón `Show/Hide Help` le brinda al usuario una pequeña guía para el uso de la herramienta, como se muestra en la Figura 29.

    | ![Rack View Help](images/rack_view_help.png) |
    | :--: |
    | ***Figure 29**. Rack View Help.*|

  * La herramienta ofrece una vista más detallada del rack y sus componentes, haciendo click en la opción `Show Detailed View` como se muestra a continuación.

    | ![Detailed View](images/detailed_rack_view.png) |
    | :--: |
    | ***Figure 29**. Detailed Rack View.*|

  * El icono ![detailed port](images/icons/port_icon.png) abre una nueva ventana con los dispositivos conectados y su estado, como se muestra en la Figura 30.

    | ![Detailed View](images/port_summary.png) |
    | :--: |
    | ***Figure 30**. Device Summary.*|

  * El icono ![connection list](images/icons/connection_list.png) abre una ventana con las conexiones entre los dispositivos, como muestra la Figura 31.

    | ![Connection List](images/connection_list.png) |
    | :--: |
    | ***Figure 31**. Connections List.*|
  
  * El icono ![edit properties](images/icons/rack_edit_properties.png) es usado para editar los atributos del rack seleccionado, como muestra la Figura 32.

    | ![Edit Rack Properties](images/edit_rack_properties.png) |
    | :--: |
    | ***Figure 32**. Rack Properties.*|

  Por ultimo, en la Figura 25, en la parte izquierda de la vista, se observan dos opciones que aparecen al lado de cada uno de los dispositivos, las cuales son:

  * El icono ![Port Summary By Device icon](images/icons/port_summary_by_device.png) abre una nueva ventana con la información de los puertos de cada dispositivo, como indica la Figura 33.
  
    | ![Port Summary By Device](images/port_summary_by_device.png) |
    | :--: |
    | ***Figure 33**. Port summary by device.*|

  * El icono ![Port Summary By Device](images/icons/move_device_icon.png) permite mover el dispositivo a una posicion diferente dentro del rack.
  
    | ![Move Device](images/move_device.png) |
    | :--: |
    | ***Figure 34**. Move Device in the Rack.*|

* **Physical Path View.**
* **Physical Tree View.**
* **Fiber Splitter View.**
* **Splice Box View.**
  
## Explorers

Este componente, como su nombre lo indica, explora las estructuras de un modelo, incluyendo relaciones, anexos y jerarquías de contención. En el módulo de navegación, se encuentran tres subcomponentes, los cuales se explican a continuación.

| ![Explorer Special Children](images/explorer_actions.png) |
| :--: |
| ***Figure 24**. Explorers.*|

* **Special Children.** Los hijos especiales son elementos que, aunque siguen el concepto de jerarquía de contención, se utilizan en modelos específicos de dominio. Esto les confiere un comportamiento particular según la situación. No pueden ser tratados como simples objetos en el árbol de navegación ya que, por ejemplo, su eliminación puede requerir tareas adicionales más allá de simplemente eliminarlos de la base de datos, debido a que forman parte de un flujo de trabajo complejo. Estos hijos respetan la jerarquía de contención especial detallada en el capítulo de Jerarquía de contención especial.
Como se muestra en la Figura 22, al seleccionar un objeto aparece una ventana emergente con sus hijos especiales. Si se selecciona alguno de estos hijos especiales, se mostrarán sus propios hijos especiales, si los tiene. Al seleccionar cualquier hijo especial, la información del objeto correspondiente aparece en el panel de opciones del objeto (Object Options Panel) en la parte derecha de la pantalla.

  | ![Explorer Special Children](images/explorer_special_children.png) |
  | :--: |
  | ***Figure 22**. Special Children Explorer.*|

* **Relationships.** Permite ver las relaciones especiales del objeto seleccionado. Cuando un objeto forma parte de un modelo de dominio específico (como SDH, Conexiones Físicas, MPLS, Servicios, etc.), existen vínculos especiales con otros objetos llamados **relaciones**. Estas relaciones, con nombres documentados según el modelo, se pueden visualizar utilizando este explorador.
En la Figura 23 se muestran las relaciones de un Optical Link, donde se observan tres tipos de relaciones. La relación parent, que es común a todos los objetos de inventario y se utiliza para navegar hacia arriba en la estructura de contención, y las relaciones endpointA y endpointB, que se utilizan en el modelo de Conexiones Físicas. Al seleccionar cualquiera de estas dos últimas relaciones, se expande el árbol mostrado, indicando el objeto con el cual existe la relación y, a su vez, mostrando las relaciones de dicho objeto.
En la parte derecha de la Figura 23 se encuentra el Object Options Panel, que muestra información y acciones relacionadas con el objeto específico seleccionado.

  | ![Explorer Relationships](images/relationships_action.png) |
  | :--: |
  | ***Figure 23**. Relationships Explorer.*|

* **Audit Trail.** Es una secuencia de registros que documenta los cambios en los objetos del inventario. Para mas detalles, ver el capitulo [Audit Trail][auditTrail].

[auditTrail]: ../../auditTrail/README.md
