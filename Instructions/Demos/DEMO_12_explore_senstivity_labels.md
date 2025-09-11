<!---
---
Demo: Título: "Etiquetas de confidencialidad en Microsoft Purview" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Priva y Microsoft Purview; Módulo 2: Descripción de las soluciones de seguridad de datos de Microsoft Purview; Unidad 4: Descripción de las etiquetas y directivas de confidencialidad en Microsoft Purview Information Protection"
---
--->

# Demo: Etiquetas de confidencialidad en Microsoft Purview

Esta demo está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Priva y Microsoft Purview
- Módulo: Descripción de las soluciones de seguridad de datos de Microsoft Purview
- Unidad: Descripción de las etiquetas y directivas de confidencialidad en Microsoft Purview Information Protection

## Supuesto de demostración

En esta demo mostrará las funcionalidades de las etiquetas de confidencialidad.  Realizarás un recorrido por la configuración de las etiquetas de confidencialidad existentes creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderás a aplicar una etiqueta y comprobarás el impacto que tiene esta desde la perspectiva de un usuario.

**NOTA**: La primera vez que use Word en línea con el inquilino de Microsoft 365, el icono de Confidencialidad puede tardar 15 minutos en aparecer en la cinta de opciones. Se recomienda que los moderadores abran Word en línea (como se muestra en la parte 3 de la demostración) antes de iniciar la demostración completa para garantizar el tiempo suficiente para que aparezca la opción.

### Demo, parte 1 (opcional)

Si es la primera vez que hace una demostración de las soluciones de Microsoft Purview, se recomienda dedicar un par de minutos a introducir el portal de Microsoft Purview antes de meterse de lleno en las etiquetas de confidencialidad.

1. Abra Microsoft Edge y, en la barra de direcciones, escriba **https://purview.microsoft.com**, inicie sesión con las credenciales proporcionadas por el anfitrión del laboratorio autorizado y, a continuación, seleccione **Comenzar**.  

1. Antes de meterse de lleno en las etiquetas de confidencialidad, dedique unos minutos a explorar el portal de Microsoft Purview.

1. Selecciona el icono **Ver todas las soluciones** para ver la agrupación de las soluciones de Microsoft Purview.

1. En el panel de navegación izquierdo verás las opciones Soluciones, Learn, Configuración y soluciones seleccionadas recientemente.
    1. **Soluciones**. Se abrirá un nuevo panel con todas las soluciones y los portales relacionados.
    1. **Learn** para ver vínculos a documentos, vídeos y blogs.
    1. **Configuración**. Explora estas opciones tanto como desees. Desde aquí puedes configurar roles y ámbitos, el conector de datos y todas las configuraciones de solución.

1. Vuelve a la página principal seleccionando **Inicio** en el panel de navegación izquierdo.

### Demo, parte 2

En esta demo mostrarás la configuración de una etiqueta de confidencialidad existente y la directiva correspondiente para publicarla.

1. Debe estar en la página de aterrizaje del portal de Microsoft Purview.  Si no es así, abra una pestaña del explorador en Microsoft Edge, escriba **`https://puriview.microsoft.com`** e inicie sesión con las credenciales proporcionadas por el anfitrión del laboratorio autorizado.

1. En la página de aterrizaje del nuevo Microsoft Purview portal, seleccione el icono **Ver todas las soluciones** y, a continuación, seleccione el icono **Information Protection**. Como alternativa, selecciona **Soluciones** en el panel de navegación izquierdo y, después, selecciona **Information Protection**.

1. Llegarás a la página de información general. En el panel de navegación izquierdo, selecciona **Etiquetas de confidencialidad**. Si ve un mensaje amarillo que indica que su organización no ha activado la capacidad de procesar contenido en archivos en línea de Office que tienen aplicadas etiquetas de confidencialidad cifradas y se almacenan en OneDrive y SharePoint,  seleccione **Activar ahora**.

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
    1. Configuración predeterminada para reuniones y eventos de calendario: revise las opciones y anote la opción para aplicar herencia entre la reunión de Teams y los artefactos. No cambies la configuración.  Seleccione **Siguiente**.
    1. Configuración predeterminada para el contenido de Fabric y Power BI: No cambie la configuración.  Seleccione **Siguiente**.
    1. Escriba un nombre para la directiva: como está editando la directiva, el campo de nombre está atenuado.  Seleccione **Siguiente**.
    1. Revise y finalice: como no se cambió nada, seleccione **Cancelar**.

1. En el panel de navegación izquierdo, en Information Protection, selecciona Etiquetado automático. Revisa la descripción. Ten en cuenta que creas directivas de etiquetado automático para aplicar automáticamente etiquetas de confidencialidad a mensajes de correo electrónico o archivos de OneDrive y SharePoint que contienen información confidencial. Si hay directivas de etiquetado automático configuradas, selecciona una y revisa la información de la directiva en el panel de detalles.  Si no aparece ninguna directiva, puedes realizar los pasos para crear una, si el tiempo lo permite.

1. En el panel de navegación izquierdo, selecciona Inicio para volver al portal de Microsoft Purview.

1. Mantén abierta esta pestaña del explorador.

### Demo, parte 3

En este paso, recorrerá el proceso de aplicar una etiqueta de confidencialidad a un documento de Microsoft Word y, a continuación, verá el marcado de contenido (pie de página) generado por la etiqueta. NOTA: Cuando use Microsoft Word online, puede experimentar algo de retraso antes de que aparezca la opción para seleccionar Etiquetas de confidencialidad en la cinta de opciones de la parte superior.  Le recomendamos que complete todos los laboratorios restantes y que vuelva más tarde a esta tarea.

1. Deberías encontrarte en la página principal del portal de Microsoft Purview. 
1. En el portal de Microsoft Purview selecciona el **icono del iniciador de aplicaciones**, junto a donde dice Microsoft Purview. Seleccione el **icono de Word**.  

1. En Crear nuevo, seleccione **Documento en blanco** y escriba algún texto en la página.  En la parte superior de la página, junto al icono de Word, selecciona donde dice **Documento**, cambia el nombre del archivo por **Test-label** y luego pulsa **Entrar** en el teclado.

1. En el extremo derecho de la barra de menú superior (también denominada cinta) hay una flecha hacia abajo, selecciónela y después seleccione **Cinta clásica**.  Esto facilitará la identificación del icono de confidencialidad. Seleccione **Confidencialidad**, situado junto al icono de micrófono. En el menú desplegable, seleccione **Extremadamente confidencial** y, a continuación, seleccione **Todos los empleados**.  

1. En la barra de menús de la parte superior, seleccione **Vista** y luego **Vista de lectura**.

1. Observe cómo el documento incluye el pie de página, "Clasificado como extremadamente confidencial".  

1. Cierre las pestañas de Microsoft Word que están abiertas en el explorador para salir de Word, pero mantenga abierta la pestaña del explorador en la página principal de Microsoft Purview.

### Revisar

En esta demostración, mostró la configuración que se puede configurar para las etiquetas de confidencialidad y la configuración de las directivas para publicar etiquetas de confidencialidad. También mostró cómo aplicar una etiqueta.
