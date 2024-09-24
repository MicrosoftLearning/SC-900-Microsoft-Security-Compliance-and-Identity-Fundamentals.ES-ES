<!---
---
Demo: Título: "Etiquetas de confidencialidad en Microsoft Purview" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Priva y Microsoft Purview; Módulo 2: Descripción de las soluciones de seguridad de datos de Microsoft Purview; Unidad 4: Descripción de las etiquetas y directivas de confidencialidad en Microsoft Purview Information Protection"
---
--->

# Demo: Etiquetas de confidencialidad en Microsoft Purview

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Priva y Microsoft Purview
- Módulo: Descripción de las soluciones de seguridad de datos de Microsoft Purview
- Unidad: Descripción de las etiquetas y directivas de confidencialidad en Microsoft Purview Information Protection

## Supuesto de demostración

En esta demo hará una demostración de las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad existentes creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.  **NOTA**: La primera vez que use Word online con el inquilino de Microsoft 365, la opción Confidencialidad puede tardar 15 minutos en aparecer en la cinta de opciones.  Los moderadores deben ejecutar la segunda parte de la demostración antes de la clase para que la opción tenga el tiempo suficiente para aparecer.

### Demo, parte 1

En esta demo mostrarás la configuración de una etiqueta de confidencialidad existente y la directiva correspondiente para publicarla.

1. Abre una nueva pestaña de explorador Microsoft Edge y, en la barra de direcciones, escribe **https://purview.microsoft.com**. Para acceder al nuevo portal de Microsoft Purview, selecciona el cuadro situado junto a donde dice, **Acepto las condiciones de divulgación del flujo de datos y las Declaraciones de privacidad** y, después, selecciona **Introducción**.  

1. En la página de aterrizaje del nuevo portal de Microsoft Purview, selecciona el icono **Ver todas las soluciones** y, después, selecciona el icono **Información del administrador**. Como alternativa, selecciona **Soluciones** en el panel de navegación izquierdo y, después, selecciona **Information Protection**.

1. Llegarás a la página de información general. En el panel de navegación izquierdo, selecciona **Etiquetas de confidencialidad**.

1. Algunas etiquetas se han preconfigurado en el inquilino de laboratorio de Microsoft 365, para su comodidad. Selecciona la etiqueta denominada **Confidential-Finance**.  Se abrirá una ventana que proporciona información sobre esta etiqueta.  Fíjate en la configuración de esta etiqueta.  Selecciona **Editar etiqueta** (también puede mostrarse como un icono de lápiz) en la parte superior de la página para ver algunos de los valores de configuración básicos. Si no ves esta opción, selecciona los puntos suspensivos.
    1. El primer paso para completar la configuración es dar un nombre y una descripción a la etiqueta.  No hagas ningún cambio.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa el ámbito de esta etiqueta. No hagas ningún cambio.  Selecciona **Siguiente** en la parte inferior de la página.
    1. La siguiente pantalla es donde puedes elegir la configuración de protección para los elementos etiquetados. Esta etiqueta está configurada para admitir el marcado de contenido. No hagas ningún cambio.  Selecciona **Siguiente** en la parte inferior de la página.
        1. En la página Marcados de contenido, toma nota del cuadro de información de la parte superior de la página.  No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Ahora te encuentras en la ventana Etiquetado automático de archivos y correos.  Lee la descripción del etiquetado automático en la parte superior de la página y el cuadro de información que aparece debajo.  Toma nota también de que esta etiqueta está configurada en Etiquetado automático para determinadas condiciones específicas. No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. La siguiente ventana define la configuración de protección de los equipos, grupos y sitios a los que se les ha aplicado esta etiqueta. Esta opción no está habilitada. Selecciona **Siguiente** en la parte inferior de la página.
    1. Esta ventana es una característica en vista previa para aplicar automáticamente esta etiqueta a los recursos de datos esquematizados en el Mapa de datos de Microsoft Purview (como SQL, Synapse, etc.) que contienen los tipos de información confidencial que elija.  Esta característica no está habilitada. Selecciona **Cancelar** en la parte inferior de la página para salir del asistente de configuración de etiquetas y volver a la página Information Protection.

1. En el panel de navegación izquierdo, selecciona **Directivas** y, después, selecciona **Publicación de directivas**.  Las etiquetas de confidencialidad se pueden publicar mediante directivas de etiquetas.  El inquilino de Microsoft 365 se ha configurado con algunas directivas de etiqueta para su comodidad.

1. Selecciona **Confidential-Fianance Polic**.  Se abrirá una ventana que proporciona información sobre la directiva. Selecciona **Editar directiva** en la parte superior de la ventana.  Aquí podrás ver la configuración sin cambiar nada.
    1. Revisa la descripción de "Elegir etiquetas de confidencialidad para publicar".  Observa la etiqueta que aparece en la lista.  No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa la descripción de "Asignar unidades de administración". Las unidades de administración se establecen en el directorio completo, no cambies ninguna configuración. Selecciona **Siguiente**.  
    1. Revisa la descripción de "Publicar para usuarios y grupos".  Observa que esta etiqueta está disponible para todos los usuarios.  No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa la configuración de la directiva. No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa la descripción de "Aplicar una etiqueta predeterminada a los documentos". No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa la descripción de "Aplicar una etiqueta predeterminada a los correos electrónicos" y "Heredar etiqueta de los datos adjuntos". No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa la descripción de "Aplicar una etiqueta predeterminada las reuniones y eventos de calendario". No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa la descripción de "Aplicar una etiqueta predeterminada al contenido de Power BI". No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. La última opción de la configuración te permite dar un nombre a su directiva.  Puesto que estás editando la directiva, el campo de nombre está atenuado. Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa la configuración de la directiva. Selecciona **Cancelar** para descartar los cambios y volver a la página Directivas de etiqueta.

1. En el panel de navegación izquierdo, en Information Protection, selecciona Etiquetado automático. Revisa la descripción. Ten en cuenta que creas directivas de etiquetado automático para aplicar automáticamente etiquetas de confidencialidad a mensajes de correo electrónico o archivos de OneDrive y SharePoint que contienen información confidencial. Si hay directivas de etiquetado automático configuradas, selecciona una y revisa la información de la directiva en el panel de detalles.  Si no aparece ninguna directiva, puedes realizar los pasos para crear una, si el tiempo lo permite.

1. En el panel de navegación izquierdo, selecciona Inicio para volver al portal de Microsoft Purview.

1. Mantén abierta esta pestaña del explorador.

### Demo, parte 2

En este paso, harás una demostración del proceso de aplicar una etiqueta desde la perspectiva del usuario (en este caso el usuario es el administrador).  Para ver el impacto de aplicar la etiqueta, seleccionarás la etiqueta Confidential - Finance porque esta etiqueta aplica una marca de agua.

1. En la página principal del portal de cumplimiento de Microsoft Purview, selecciona el **icono del iniciador de aplicaciones**, junto a donde dice Microsoft Purview (en la parte superior del icono de inicio). Selecciona el **icono de Word**.  

1. Selecciona **Documento en blanco** y escribe algún texto en la página.  En la barra azul de la parte superior de la página, seleccione la flecha hacia abajo que hay junto a las palabras DocumentoXX: Guardado y, en el cuadro Nombre de archivo, escriba **Etiqueta:Prueba** y pulse la tecla **Entrar** en el teclado.

1. En el extremo derecho de la barra de menú superior (también denominada cinta) hay una flecha hacia abajo, selecciónela y después seleccione **Cinta clásica**.  Esto facilitará la identificación del icono de confidencialidad. Seleccione **Confidencialidad**, situado junto al icono de micrófono. En el menú desplegable, seleccione **Confidential-Finance**.  

1. En la barra de menús de la parte superior, seleccione **Vista** y luego **Vista de lectura**.

1. Observe que el documento incluye la marca de agua.  

1. Cierre las pestañas de Microsoft Word que hay abiertas en su explorador para salir de Word.

1. Mantenga abierta la pestaña del explorador Microsoft Purview para la siguiente demostración.

### Revisar

En esta demostración, mostró la configuración que se puede configurar para las etiquetas de confidencialidad y la configuración de las directivas para publicar etiquetas de confidencialidad. También mostró cómo aplicar una etiqueta.
