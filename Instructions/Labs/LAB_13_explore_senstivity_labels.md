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

En este laboratorio explorará las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad existentes creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.

**Tiempo estimado**: 45 minutos

### Tarea 1

En esta tarea obtendrás información de lo que pueden hacer las etiquetas de confidencialidad. Para ello, realizarás un recorrido por el proceso de crear una etiqueta nueva y una directiva para publicarla.

1. Abra la pestaña del explorador para la página principal de Microsoft Purview.  Si la había cerrado, abra otra y escriba **https://admin.microsoft.com** . Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). Si has iniciado sesión anteriormente como administrador, se te pedirá que completes una autenticación secundaria, como parte de MFA. Si no has iniciado sesión anteriormente como administrador, se te pedirá que completes el proceso de registro de MFA. Sigue las indicaciones en la pantalla para configurar MFA.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de Microsoft Purview.

1. En el panel de navegación izquierdo, selecciona **Soluciones** e **Information Protection**.  Estás en la página de información general. Desplázate hacia abajo para ver la información disponible.

1. En el panel de navegación izquierdo, selecciona **Etiquetas de confidencialidad**.

1. Algunas etiquetas se han preconfigurado en el inquilino de laboratorio de Microsoft 365, para su comodidad. Selecciona la etiqueta denominada **Confidential-Finance**.  Se abrirá una ventana que proporciona información sobre esta etiqueta.  Fíjate en la configuración de esta etiqueta.  Selecciona **Editar etiqueta**. Si no ves esta opción, selecciona los puntos suspensivos.
    1. La configuración comienza por proporcionar detalles básicos para la etiqueta.  No hagas ningún cambio.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Revisa el ámbito de esta etiqueta. No hagas ningún cambio.  Selecciona **Siguiente** en la parte inferior de la página.
    1. La siguiente pantalla es donde puedes elegir la configuración de protección para los elementos etiquetados. Esta etiqueta está configurada para admitir el marcado de contenido. No hagas ningún cambio.  Selecciona **Siguiente** en la parte inferior de la página.
        1. En la página Marcados de contenido, toma nota del cuadro de información de la parte superior de la página.  No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Ahora te encuentras en la ventana Etiquetado automático de archivos y correos.  Lee la descripción del etiquetado automático en la parte superior de la página y el cuadro de información que aparece debajo.  Toma nota también de que esta etiqueta está configurada en Etiquetado automático para determinadas condiciones específicas. No cambies la configuración.  Selecciona **Siguiente** en la parte inferior de la página.
    1. Esta ventana define la configuración de protección de los grupos y sitios a los que se les ha aplicado esta etiqueta. Esta opción no está habilitada. Selecciona **Siguiente** en la parte inferior de la página.
    1. Esta ventana es una característica en vista previa para aplicar automáticamente esta etiqueta a los recursos de datos esquematizados en el Mapa de datos de Microsoft Purview (como SQL, Synapse, etc.) que contienen los tipos de información confidencial que elija.  Esta característica no está habilitada. Selecciona **Cancelar** en la parte inferior de la página para salir del asistente de configuración de etiquetas y volver a la página Information Protection.

1. En el panel de navegación izquierdo, expande **Directivas** y, después, selecciona **Publicación de directivas**.  Las etiquetas de confidencialidad se pueden publicar mediante directivas de etiquetas.  El inquilino de Microsoft 365 se ha configurado con algunas directivas de etiqueta para su comodidad.

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

1. En el panel de navegación izquierdo, en Information Protection, selecciona Etiquetado automático. Revisa la descripción. Tenga en cuenta que crea directivas de etiquetado automático para aplicar automáticamente etiquetas de confidencialidad a mensajes de correo electrónico o archivos de OneDrive y SharePoint que contienen información confidencial. No se han preconfigurado directivas de etiqueta automática en nuestro inquilino. Para crear una nueva directiva, seleccione **Crear directiva de etiquetado automático**.  Aquí verá los pasos para crear una nueva directiva.
    1. Para empezar, elija la información a la que desea aplicar esta etiqueta.  Fíjese en las opciones disponibles.  Seleccione **Medicina y salud** y, a continuación, seleccione una de las plantillas disponibles.  Seleccione **Siguiente**.
    1. Puede asignar un nombre a la directiva de etiqueta automática o usar el nombre predeterminado.  Seleccione **Siguiente**.
    1. Puede asignar las unidades de administración a las que se aplica esta directiva.  Deje la configuración predeterminada como directorio completo y seleccione **Siguiente**.
    1. Fíjese en las ubicaciones disponibles en las que desea aplicar la etiqueta.  Deje los valores predeterminados y seleccione **Siguiente**.
    1. Puede configurar reglas comunes o avanzadas que definen a qué contenido se aplica la etiqueta.  Deje la configuración predeterminada como reglas comunes y seleccione **Siguiente**.
    1. Puede definir reglas para el contenido en todas las ubicaciones.  La etiqueta se aplicará al contenido que coincida con las reglas definidas en esta página.  Para la plantilla seleccionada, debería ver un elemento de línea. Expándalo para ver las condiciones que se aplican.  Deje la configuración predeterminada y seleccione **Siguiente**.
    1. Elija una etiqueta para aplicarla automáticamente, para ello, seleccione **Elegir una etiqueta**.  Elija una etiqueta y, a continuación, seleccione **Agregar**. Seleccione **Siguiente**.
    1. Se pueden configurar opciones adicionales para el correo electrónico. Deje los valores predeterminados y seleccione **Siguiente**.
    1. Puede decidir probar la directiva ahora o más tarde.  Seleccione **Dejar la directiva desactivada** y, a continuación, seleccione **Siguiente**.
    1. Revise la configuración y seleccione **Crear directiva**, luego seleccione **Listo**.

1. En el panel de navegación izquierdo, seleccione **Inicio** para volver al portal de cumplimiento de Microsoft Purview.

1. Deje esta página abierta. La utilizará en la siguiente tarea.

### Tarea 2

En esta tarea, verá el proceso de aplicar una etiqueta de confidencialidad a un documento de Microsoft Word y, a continuación, verá el marcado de contenido (marca de agua) que genera la etiqueta. NOTA: Cuando use Microsoft Word online, puede experimentar algo de retraso antes de que aparezca la opción para seleccionar Etiquetas de confidencialidad en la cinta de opciones de la parte superior.  Le recomendamos que complete todos los laboratorios restantes y que vuelva más tarde a esta tarea.

1. En la página principal del Portal de cumplimiento de Microsoft Purview, seleccione el **icono del iniciador de aplicaciones**, junto a Contoso Electronics. Seleccione el **icono de Word**.  

1. En Crear nuevo, seleccione **Documento en blanco** y escriba algún texto en la página.  En la parte superior de la página, seleccione la flecha hacia abajo que hay junto a las palabras DocumentoXX: Guardado y, en el cuadro Nombre de archivo, escriba **Etiqueta:Prueba** y pulse **Entrar** en el teclado.

1. En el extremo derecho de la barra de menú superior (también denominada cinta) hay una flecha hacia abajo, selecciónela y después seleccione **Cinta clásica**.  Esto facilitará la identificación del icono de confidencialidad. Seleccione **Confidencialidad**, situado junto al icono de micrófono. En el menú desplegable, seleccione **Confidential-Finance**.  

1. En la barra de menús de la parte superior, seleccione **Vista** y luego **Vista de lectura**.

1. Observe que el documento incluye la marca de agua "Confidential FINANCIAL DATA".  

1. Cierre las pestañas de Microsoft Word que están abiertas en el explorador para salir de Word, pero mantenga abierta la pestaña del explorador en la página principal de Microsoft Purview.

### Revisar

En este laboratorio explorará las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad existentes que se crearon previamente y por la directiva correspondiente para publicar la etiqueta.   A continuación, verá cómo aplicar una etiqueta.
