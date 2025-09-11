---
lab:
  title: "Explorar las etiquetas de confidencialidad en Microsoft\_Purview"
  module: Describe the data security solutions of Microsoft Purview
---

# Laboratorio: Explorar las etiquetas de confidencialidad en Microsoft Purview

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Priva y Microsoft Purview
- Módulo: Descripción de las soluciones de seguridad de datos de Microsoft Purview
- Unidad: Descripción de las etiquetas y directivas de confidencialidad en Microsoft Purview Information Protection

## Escenario del laboratorio

En este laboratorio explorarás las funcionalidades de las etiquetas de confidencialidad.  Realizarás un recorrido por la configuración de las etiquetas de confidencialidad existentes creadas previamente y por la directiva correspondiente para publicar la etiqueta. Después aprenderás a aplicar una etiqueta y comprobarás el impacto que tiene esta desde la perspectiva de un usuario.

**Tiempo estimado**: 45 minutos

### Tarea 1

En esta tarea obtendrás información de lo que pueden hacer las etiquetas de confidencialidad. Para ello, realizarás un recorrido por el proceso de crear una etiqueta nueva y una directiva para publicarla.

1. Abre la pestaña del explorador para la página principal de Microsoft Purview.  Si la habías cerrado, abre otra y escribe **`https://admin.microsoft.com`** . Inicia sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Microsoft Purview**.  Se abrirá una nueva página del explorador con la página principal del Portal de Microsoft Purview.

1. En el panel de navegación izquierdo, selecciona **Soluciones** e **Information Protection**.  Estás en la página de información general. Desplázate hacia abajo para ver la información disponible.

1. En el panel de navegación izquierdo, selecciona **Etiquetas de confidencialidad**.
1. Verás un banner amarillo que indica que tu organización no ha activado la posibilidad de procesar el contenido de los archivos en línea de Office a los que se les ha aplicado etiquetas de confidencialidad cifradas y que se han almacenado en OneDrive y SharePoint.  Seleccione **Activar ahora**.

1. Algunas etiquetas se han preconfigurado en el inquilino de laboratorio de Microsoft 365, para su comodidad. Expanda la etiqueta denominada **Extremadamente confidencial** y, a continuación, seleccione **Todos los empleados**.  Se abrirá una ventana que proporciona información sobre esta etiqueta.  Fíjate en la configuración de esta etiqueta.  Selecciona **Editar etiqueta**. Si no ves esta opción, selecciona los puntos suspensivos.
    1. La configuración comienza por proporcionar detalles básicos para la etiqueta.  No hagas ningún cambio.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa el ámbito de esta etiqueta. No hagas ningún cambio.  Selecciona **Siguiente** en la parte inferior de la página.
    1. La siguiente pantalla es donde puedes elegir la configuración de protección para los elementos etiquetados. Esta etiqueta controla quién puede acceder a los elementos etiquetados y verlos y también aplica el marcado de contenido.  Seleccione **Siguiente** para ver los detalles.
        1. Control de acceso: revise la configuración actual, pero no cambie nada.  Seleccione **Siguiente**.
        1. Marcado de contenido: observe que la etiqueta aplica un pie de página.  Después, seleccione **Siguiente**.
        1. Etiquetado automático de archivos y correos electrónicos: Lea la descripción del etiquetado automático en la parte superior de la página y el cuadro de información que aparece debajo.  observe también que esta etiqueta está establecida para el etiquetado automático cuando se detectan números de tarjeta de crédito. No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Defina la configuración de protección para grupos y sitios: revise las opciones de configuración de protección y de aplicación automática.  No se ha configurado nada en esta ventana.  No hagas ningún cambio. Selecciona **Siguiente** en la parte inferior de la página.
    1. Revise la configuración y finalice: Revise la configuración.  Como no se ha cambiado nada, seleccione **Cancelar**.

1. En el panel de navegación izquierdo, expanda **Directivas** y, después, seleccione **Directivas de publicación de etiquetas**.  Las etiquetas de confidencialidad se pueden publicar mediante directivas de etiquetas.  El inquilino de Microsoft 365 se ha configurado con algunas directivas de etiqueta para su comodidad. Seleccione **Directiva extremadamente confidencial**.  Se abrirá una ventana que proporciona información sobre la directiva. Selecciona **Editar directiva** en la parte superior de la ventana.  Aquí podrás ver la configuración sin cambiar nada.
    1. Elija etiquetas de confidencialidad para publicar:  Observe las etiquetas enumeradas.  No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Asigne unidades de administración: Las unidades de Administración se establecen en el directorio completo, no cambie ninguna configuración. Seleccione **Siguiente**.  
    1. Publique en usuarios y grupos:  Observe que esta etiqueta está disponible para todos los usuarios.  No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Configuración de directivas: Tenga en cuenta las opciones disponibles. No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Configuración predeterminada para documentos: No cambie la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Configuración predeterminada para correos electrónicos: revise las opciones y tenga en cuenta que los correos electrónicos pueden heredar una etiqueta de un archivo adjunto con mayor prioridad, si está configurado para ello. Seleccione **Siguiente**.
    1. Configuración predeterminada para reuniones y eventos de calendario: revise las opciones y observe la opción para aplicar herencia entre la reunión de Teams y los artefactos. No cambies la configuración.  Seleccione **Siguiente**.
    1. Configuración predeterminada para el contenido de Fabric y Power BI: No cambie la configuración.  Seleccione **Siguiente**.
    1. Escriba un nombre para la directiva: como está editando la directiva, el campo de nombre está atenuado.  Seleccione **Siguiente**.
    1. Revise y finalice: como no se cambió nada, seleccione **Cancelar**.

1. En el panel de navegación izquierdo, en Protección de la información, seleccione **Directivas de etiquetado automático**. Revisa la descripción. Ten en cuenta que creas directivas de etiquetado automático para aplicar automáticamente etiquetas de confidencialidad a mensajes de correo electrónico o archivos de OneDrive y SharePoint que contienen información confidencial. No se han preconfigurado directivas de etiqueta automática en nuestro inquilino. Para crear una nueva directiva, selecciona **Crear directiva de etiquetado automático**.  Aquí, recorrerá los pasos necesarios para crear una nueva directiva.
    1. Para empezar, elige la información a la que deseas aplicar esta etiqueta.  Fíjate en las opciones disponibles.  Seleccione **Medicina y salud** y, a continuación, seleccione una de las normativas disponibles que servirán como plantilla.  Seleccione **Siguiente**.
    1. Puedes asignar un nombre a la directiva de etiqueta automática o usar el nombre predeterminado.  Seleccione **Siguiente**.
    1. A continuación, elija una etiqueta para aplicarla automáticamente.  Seleccione **+Elegir una etiqueta**.  Seleccione una etiqueta de la lista y, a continuación, seleccione **Agregar**.
    1. Puedes asignar las unidades de administración a las que se aplica esta directiva.  Deje la configuración predeterminada como directorio completo y seleccione **Siguiente**.
    1. Elija ubicaciones en las que quiera aplicar la etiqueta.  Revise la información que proporcione y las ubicaciones disponibles que puede seleccionar. Para este ejercicio, seleccione el cuadro situado junto a **Correo electrónico de Exchange** y, a continuación, seleccione **Siguiente**.
    1. Puede configurar reglas comunes o avanzadas que definen a qué contenido se aplica la etiqueta.  Deje la configuración predeterminada como reglas comunes y seleccione **Siguiente**.
    1. Puede definir reglas para el contenido en todas las ubicaciones.  La etiqueta se aplicará al contenido que coincida con las reglas definidas en esta página.  Para la plantilla seleccionada, debería ver un elemento de línea. Expándalo para ver las condiciones que se aplican.  Deje la configuración predeterminada y seleccione **Siguiente**.
    1. Se pueden configurar opciones adicionales para el correo electrónico. Deje los valores predeterminados y seleccione **Siguiente**.
    1. Puede decidir probar la directiva ahora o más tarde.  Seleccione **Dejar la directiva desactivada** y, a continuación, seleccione **Siguiente**.
    1. Revise la configuración. Para los fines de este ejercicio, puede anular sin crear la directiva. Seleccione **Cancelar**.

1. En el panel de navegación izquierdo, selecciona **Inicio** para volver al portal de Microsoft Purview.

1. Deje esta página abierta. La utilizará en la siguiente tarea.

### Tarea 2

En esta tarea, recorrerá el proceso de aplicar una etiqueta de confidencialidad a un documento de Microsoft Word y, a continuación, verá el marcado de contenido (pie de página) generado por la etiqueta. NOTA: Cuando use Microsoft Word online, puede experimentar algo de retraso antes de que aparezca la opción para seleccionar Etiquetas de confidencialidad en la cinta de opciones de la parte superior.  Le recomendamos que complete todos los laboratorios restantes y que vuelva más tarde a esta tarea.

1. Deberías encontrarte en la página principal del portal de Microsoft Purview. 
1. En el portal de Microsoft Purview selecciona el **icono del iniciador de aplicaciones**, junto a donde dice Microsoft Purview. Seleccione el **icono de Word**.  

1. En Crear nuevo, seleccione **Documento en blanco** y escriba algún texto en la página.  En la parte superior de la página, junto al icono de Word, selecciona donde dice **Documento**, cambia el nombre del archivo por **Test-label** y luego pulsa **Entrar** en el teclado.

1. En el extremo derecho de la barra de menú superior (también denominada cinta) hay una flecha hacia abajo, selecciónela y después seleccione **Cinta clásica**.  Esto facilitará la identificación del icono de confidencialidad. Seleccione **Confidencialidad**, situado junto al icono de micrófono. En el menú desplegable, seleccione **Extremadamente confidencial** y, a continuación, seleccione **Todos los empleados**.  

1. En la barra de menús de la parte superior, seleccione **Vista** y luego **Vista de lectura**.

1. Observe cómo el documento incluye el pie de página, "Clasificado como extremadamente confidencial".  

1. Cierre las pestañas de Microsoft Word que están abiertas en el explorador para salir de Word, pero mantenga abierta la pestaña del explorador en la página principal de Microsoft Purview.

### Revisar

En este laboratorio, ha explorado las funcionalidades de las etiquetas de confidencialidad.  Ha explorado la configuración de una etiqueta de confidencialidad existente y la directiva correspondiente para publicar la etiqueta.  Ha aplicado la etiqueta y, dado que la etiqueta incluía marcas de contenido, ha podido ver esa marca en el documento al que aplicó la etiqueta.
