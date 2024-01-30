<!---
---
Laboratorio: Título: "Exploración de las etiquetas de confidencialidad en Microsoft Purview" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft; Módulo 3: Descripción de la protección de la información y la administración del ciclo de vida de los datos en Microsoft Purview; Unidad 4: Descripción de las etiquetas de confidencialidad"
---
--->

# Laboratorio: Explorar las etiquetas de confidencialidad en Microsoft Purview

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de la protección de la información y la administración del ciclo de vida de los datos en Microsoft Purview
- Unidad: Descripción de las etiquetas de confidencialidad

## Escenario del laboratorio

En este laboratorio explorará las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad existentes creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.

**Tiempo estimado**: 20-25 minutos

### Tarea 1

En esta tarea descubrirá las posibilidades que ofrecen las etiquetas de confidencialidad. Para ello, realizará un recorrido por el proceso de crear una etiqueta nueva y una directiva para publicarla.

1. Abra la pestaña del explorador para la página principal de Microsoft Purview.  Si la había cerrado, abra otra y escriba **https://admin.microsoft.com** . Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.

1. En el panel de navegación izquierdo, debajo de Soluciones, expanda **Information Protection** y luego seleccione **Información general**. Fíjese en la advertencia de la parte superior de la página y desplácese hacia abajo para ver la información disponible.
   1. En la página Información general, podrá ver un cuadro de información amarillo que indica que su organización no ha activado la capacidad de procesar el contenido de los archivos en línea de Office a los que se les ha aplicado etiquetas de confidencialidad cifradas y que se han almacenado en OneDrive y SharePoint.  Seleccione **Activar ahora**.  Una vez hecho esto, puede haber un retraso para que la configuración se propague a través del sistema y hay pasos adicionales que deben completarse para proteger Teams, sitios de SharePoint y Grupos de Microsoft 365.

1. En el panel de navegación izquierdo, seleccione **Etiquetas**.
   1. En la página Etiquetas, podrá ver un cuadro de información amarillo que indica que su organización no ha activado la capacidad de procesar el contenido de los archivos en línea de Office a los que se les ha aplicado etiquetas de confidencialidad cifradas y que se han almacenado en OneDrive y SharePoint.  Seleccione **Activar ahora**.  Una vez hecho esto, puede haber un retraso para que la configuración se propague a través del sistema y hay pasos adicionales que deben completarse para proteger Teams, sitios de SharePoint y Grupos de Microsoft 365.

1. Algunas etiquetas se han preconfigurado en el inquilino de laboratorio de Microsoft 365, para su comodidad. Seleccione la etiqueta denominada **Confidential-Finance**.  Se abrirá una ventana que proporciona información sobre esta etiqueta.  Fíjese en la configuración de esta etiqueta.  Seleccione **Editar etiqueta** (también puede mostrarse como un icono de lápiz) en la parte superior de la página para ver algunos de los valores de configuración básicos. Si no ve esta opción, seleccione los puntos suspensivos.
    1. El primer paso para completar la configuración es dar un nombre y una descripción a su etiqueta.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise el ámbito de esta etiqueta. No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.
    1. La siguiente pantalla es donde puede elegir la configuración de protección para los elementos etiquetados. Esta etiqueta está configurada para admitir el marcado de contenido. No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.
        1. En la página Marcados de contenido, tome nota del cuadro de información de la parte superior de la página.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Ahora se encuentra en la ventana Etiquetado automático de archivos y correos.  Lea la descripción del etiquetado automático en la parte superior de la página y el cuadro de información que aparece debajo.  Tome nota también de que esta etiqueta está configurada en Etiquetado automático para determinadas condiciones específicas. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. La siguiente ventana define la configuración de protección de los equipos, grupos y sitios a los que se les ha aplicado esta etiqueta. Esta opción no está habilitada. Seleccione **Siguiente** en la parte inferior de la página.
    1. Esta ventana es una característica en vista previa para aplicar automáticamente esta etiqueta a los recursos de datos esquematizados en el Mapa de datos de Microsoft Purview (como SQL, Synapse, etc.) que contienen los tipos de información confidencial que elija.  Esta característica no está habilitada. Seleccione **Cancelar** en la parte inferior de la página para salir del asistente de configuración de etiquetas y volver a la página Information Protection.

1. En el panel de navegación izquierdo, seleccione **Directivas de etiquetas**.  Las etiquetas de confidencialidad se pueden publicar mediante directivas de etiquetas.  El inquilino de Microsoft 365 se ha configurado con algunas directivas de etiqueta para su comodidad.

1. Seleccione **Confidential-Fianance Policy (Directiva confidencial/finanzas)**.  Se abrirá una ventana que proporciona información sobre la directiva. Seleccione **Editar** directiva en la parte superior de la ventana.  Aquí podrá ver la configuración sin cambiar nada.
    1. Revise la descripción de "Elegir etiquetas de confidencialidad para publicar".  Observe la etiqueta que aparece en la lista.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Asignar unidades de administración". Las unidades de administración se establecen en el directorio completo, no cambie ninguna configuración. Seleccione **Siguiente**.  
    1. Revise la descripción de "Publicar para usuarios y grupos".  Observe que esta etiqueta está disponible para todos los usuarios.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la configuración de la directiva. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Aplicar una etiqueta predeterminada a los documentos". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Aplicar una etiqueta predeterminada a los correos electrónicos" y "Heredar etiqueta de los datos adjuntos". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Aplicar una etiqueta predeterminada las reuniones y eventos de calendario". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Aplicar una etiqueta predeterminada al contenido de Power BI". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. La última opción de la configuración le permite dar un nombre a su directiva.  Puesto que está editando la directiva, el campo de nombre está atenuado. Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la configuración de la directiva. Seleccione **Cancelar** para descartar los cambios y volver a la página Directivas de etiqueta.

1. En el panel de navegación izquierdo, en Information Protection, seleccione Etiquetado automático. Revise la descripción. Tenga en cuenta que crea directivas de etiquetado automático para aplicar automáticamente etiquetas de confidencialidad a mensajes de correo electrónico o archivos de OneDrive y SharePoint que contienen información confidencial. No se han preconfigurado directivas de etiqueta automática en nuestro inquilino. Para crear una nueva directiva, seleccione **Crear directiva de etiquetado automático**.  Aquí verá los pasos para crear una nueva directiva.
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
