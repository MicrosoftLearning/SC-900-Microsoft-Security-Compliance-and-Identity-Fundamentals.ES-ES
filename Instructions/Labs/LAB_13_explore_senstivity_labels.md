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

En esta tarea descubrirá las posibilidades que ofrecen las etiquetas de confidencialidad. Para ello, realizará un recorrido por las opciones de configuración de una etiqueta de confidencialidad existente creada previamente y la directiva correspondiente para publicarla.

1. Abra la pestaña del explorador para la página principal de Microsoft Purview.  Si la había cerrado, abra otra y escriba **https://admin.microsoft.com** . Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.   

1. En el panel de navegación izquierdo, en Soluciones, expanda **Information Protection** y, a continuación, seleccione **Información general**. Anote la advertencia en la parte superior de la página y desplácese hacia abajo para ver la información disponible.
   1. En la página de Información general, puede ver un cuadro de información amarillo que indica que su organización no ha activado la capacidad de procesar el contenido de los archivos en línea de Office a los que se les ha aplicado etiquetas de confidencialidad cifradas y que se han almacenado en OneDrive y SharePoint.  Seleccione **Activar ahora**.  Una vez hecho esto, puede haber un retraso para que la configuración se propague a través del sistema, y hay pasos adicionales que deben completarse para proteger Teams, sitios de SharePoint y Grupos de Microsoft 365.

1. En el panel de navegación izquierdo, seleccione **Etiquetas**.
   1. En la página de Etiquetas, puede ver un cuadro de información amarillo que indica que su organización no ha activado la capacidad de procesar el contenido de los archivos en línea de Office a los que se les ha aplicado etiquetas de confidencialidad cifradas y que se han almacenado en OneDrive y SharePoint.  Seleccione **Activar ahora**.  Una vez hecho esto, puede haber un retraso para que la configuración se propague a través del sistema, y hay pasos adicionales que deben completarse para proteger Teams, sitios de SharePoint y Grupos de Microsoft 365.
1. Algunas etiquetas se han preconfigurado en el inquilino de laboratorio de Microsoft 365, para su comodidad. Expanda la etiqueta denominada **Extremadamente confidencial** seleccionando **>** y, a continuación, seleccione **Todos los empleados**.  Se abrirá una ventana que proporciona información sobre esta etiqueta.  Observe que esta etiqueta está configurada para admitir tanto el cifrado como el marcado de contenido.  Seleccione el **icono de lápiz** de la parte superior de la página para ver algunas de las opciones de configuración básicas. Si no ve el icono de lápiz, seleccione los puntos suspensivos.
    1. El primer paso para completar la configuración es dar un nombre y una descripción a su etiqueta.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Anote el ámbito de esta etiqueta.  El ámbito se establece en Archivos y correos electrónicos.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Esta siguiente pantalla es donde puede elegir la configuración de protección para los elementos etiquetados. Observe que esta etiqueta está configurada para admitir el cifrado y el marcado de contenido. No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.
        1. La ventana Cifrado muestra la configuración de las opciones de cifrado. Revise la configuración actual, pero no cambie nada. Observe cómo el acceso del usuario al contenido está establecido en nunca expirar y permitir siempre el acceso sin conexión.  También puede asignar permisos a usuarios y grupos específicos para que solo ellos puedan interactuar con el contenido al que se ha aplicado esta etiqueta.  Debajo de Usuarios y grupos, la cuenta empresarial está definida para que todos los usuarios de su cuenta puedan ver el contenido etiquetado con esta etiqueta.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
        1. En la página Marcados de contenido, tome nota del cuadro de información de la parte superior de la página.  Los marcados de contenido se aplicarán a los documentos, pero a los correos solo se les aplicarán los encabezados y los pies de página. En otras palabras, las marcas de agua no se aplicarán a los correos.  El marcado de contenido asociado a esta etiqueta es un pie de página.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Ahora se encuentra en la ventana Etiquetado automático de archivos y correos.  Lea la descripción del etiquetado automático en la parte superior de la página y el cuadro de información que aparece debajo.  Tome nota también de que esta etiqueta está configurada en Etiquetado automático para determinadas condiciones específicas. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. La siguiente ventana define la configuración de protección de los equipos, grupos y sitios a los que se les ha aplicado esta etiqueta. Esta opción no está habilitada. Seleccione **Siguiente** en la parte inferior de la página.
    1. La siguiente ventana es una característica en vista previa para aplicar automáticamente esta etiqueta a activos de datos esquematizados en el Mapa de datos de Microsoft Purview (como SQL, Synapse, etc.) que contienen los tipos de información confidencial que ha elegido.  Esta característica no está habilitada. Seleccione **Cancelar** en la parte inferior de la página para salir del asistente de configuración de etiquetas y volver a la página Information Protection.

1. En el panel de navegación izquierdo, seleccione **Directivas de etiquetas**.  Las etiquetas de confidencialidad se pueden publicar mediante directivas de etiquetas.  El inquilino de Microsoft 365 se ha configurado con algunas directivas de etiqueta para su comodidad.

1. En este caso, seleccione **Directiva de etiqueta de confidencialidad global**.  Se abrirá una ventana que proporciona información sobre la directiva.  Tenga en cuenta la descripción: esta directiva de etiqueta se ha configurado para que actúe como directiva de etiqueta de confidencialidad predeterminada para todos los usuarios y grupos. Esta directiva sirve para publicar la mayoría de las etiquetas preconfiguradas para este inquilino de laboratorio de Microsoft 365 y se muestran en la pestaña etiquetas.  

1. Seleccione **Editar directiva** en la parte superior de la ventana.
    1. Revise la descripción de "Elija etiquetas de confidencialidad para publicar".  Observe las etiquetas que aparecen.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Asignar unidades de administración". Las unidades de Administración se establecen en el directorio completo, no cambie ninguna configuración. Seleccione **Next** (Siguiente).  
    1. Revise la descripción de "Publicar para usuarios y grupos".  Observe que esta etiqueta está disponible para todos los usuarios.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la configuración de la directiva. Seleccione **Requerir a los usuarios que apliquen una etiqueta a sus correos electrónicos y documentos** y revise la descripción proporcionada. Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Aplicar una etiqueta predeterminada a los documentos". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Aplicar una etiqueta predeterminada a los correos electrónicos" y "Heredar etiqueta de los datos adjuntos". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Aplicar una etiqueta predeterminada a reuniones y eventos de calendario". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la descripción de "Aplicar una etiqueta predeterminada a contenido de Power BI". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. La última opción de la configuración le permite dar un nombre a su directiva.  Puesto que está editando la directiva, el campo de nombre está atenuado.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la configuración de la directiva. Seleccione **Cancelar** para descartar los cambios y volver a la página Directivas de etiqueta.

1. En la página Information protection, seleccione Etiquetado automático. Revise la descripción. Tenga en cuenta que crea directivas de etiquetado automático para aplicar automáticamente etiquetas de confidencialidad a los mensajes de correo electrónico o a los archivos de OneDrive y SharePoint que contienen información confidencial. No se han configurado previamente directivas de etiqueta automática en nuestro inquilino. Para crear una nueva directiva de etiqueta automática, seleccione **Crear directiva de etiqueta automática**.  Aquí se le guiará por los pasos para crear una nueva directiva.
    1. Para empezar, elija la información a la que desea aplicar esta etiqueta.  Tenga en cuenta las opciones disponibles.  Seleccione **Médico y salud** y, a continuación, seleccione una de las plantillas disponibles.  Seleccione **Next** (Siguiente).
    1. Puede asignar un nombre a la directiva de etiqueta automática o usar el nombre predeterminado.  Seleccione **Next** (Siguiente).
    1. Puede asignar las unidades de administración a las que se aplica esta directiva.  Deje el valor predeterminado establecido en directorio completo y seleccione **Siguiente**.
    1. Anote las ubicaciones disponibles en las que desea aplicar la etiqueta.  Deje los valores predeterminados y seleccione **Siguiente**.
    1. Puede configurar reglas comunes o avanzadas que definen el contenido al que se aplica la etiqueta.  Deje el valor predeterminado establecido en Reglas comunes y seleccione **Siguiente**.
    1. Puede definir reglas para el contenido en todas las ubicaciones.  La etiqueta se aplicará al contenido que coincida con las reglas definidas en esta página.  Debería ver un elemento de línea para la plantilla seleccionada. Expándalo para ver las condiciones que se aplican.  Deje la configuración predeterminada y seleccione **Siguiente**.
    1. Elija una etiqueta para aplicarla automáticamente; para ello, seleccione **Elegir una etiqueta**.  Elija una etiqueta y, a continuación, seleccione **Agregar**. Seleccione **Next** (Siguiente).
    1. Se pueden configurar opciones adicionales para el correo electrónico. Deje los valores predeterminados y seleccione **Siguiente**.
    1. Puede decidir probar la directiva ahora o posterior.  Seleccione **Dejar la directiva desactivada** y, a continuación, seleccione **Siguiente**.
    1. Revise la configuración y seleccione **Crear directiva** y, a continuación, **Listo**.

1. En el panel de navegación izquierdo, seleccione **Inicio** para volver al Portal de cumplimiento de Microsoft Purview.

1. Deje esta página abierta. La utilizará en la siguiente tarea.

### Tarea 2

En esta tarea, recorrerá el proceso de aplicar una etiqueta de confidencialidad a un documento de Microsoft Word y, a continuación, verá el marcado de contenido (marca de agua) generado por la etiqueta. NOTA: Al usar Microsoft Word en línea, puede experimentar un retraso antes de que la opción para seleccionar Etiquetas de confidencialidad aparezca en la cinta de opciones superior.  Se recomienda completar todos los laboratorios restantes y volver a esta tarea.

1. En la página principal del Portal de cumplimiento de Microsoft Purview, seleccione el **icono del iniciador de aplicaciones**, junto a Contoso Electronics. Seleccione el **icono de Word**.  

1. En Crear nuevo, seleccione **Documento en blanco** y escriba algún texto en la página.  En la parte superior de la página, seleccione la flecha hacia abajo que hay junto a las palabras DocumentoXX: Guardado y, en el cuadro Nombre de archivo, escriba **Etiqueta:Prueba** y pulse **Entrar** en el teclado.

1. En la barra de menús superior, seleccione el **icono Confidencialidad**, situado a la derecha del icono Micrófono (en función del tamaño de la pantalla, es posible que tenga que seleccionar primero los puntos suspensivos y, después, Confidencialidad). En la lista desplegable, seleccione **Extremadamente confidencial** y, a continuación, seleccione **Todos los empleados**.  NOTA: Al usar Microsoft Word en línea, puede experimentar un retraso antes de que la opción para seleccionar Etiquetas de confidencialidad aparezca en la cinta de opciones superior.  Se recomienda completar todos los laboratorios restantes y volver a esta tarea.

1. En la barra de menús de la parte superior, seleccione **Vista** y luego **Vista de lectura**.

1. Observe cómo el documento incluye el pie de página "Clasificado como extremadamente confidencial".  

1. Cierre las pestañas de Microsoft Word que hay abiertas en su explorador para salir de Word.

### Tarea 3 (opcional)

Recuerde de la primera parte de la demostración que la etiqueta Extremamente confidencial: Todos los empleados está configurada para el cifrado. Según los permisos configurados con esta etiqueta, los usuarios del inquilino de Contoso tienen permisos de visualizador para cualquier documento o correo electrónico con la etiqueta aplicada.  En esta sección, enviará el documento que creó anteriormente, que incluye la etiqueta Extremadamente confidencial: Todos los empleados, a una dirección de correo electrónico a la que tiene acceso (una dirección de correo electrónico personal o su correo electrónico de Microsoft) y que no forma parte del dominio de WWLxZZZZ.OnMicrosoft.com.  

1. En la página principal del Portal de cumplimiento de Microsoft Purview, seleccione el **icono del iniciador de aplicaciones**, junto a Contoso Electronics. Seleccione el **icono de Outlook**.

1. Seleccione **Nuevo correo electrónico** en la esquina superior izquierda de la pantalla.  Escriba una dirección de correo electrónico a la que tenga acceso y que no forme parte del dominio WWLxZZZZ.OnMicrosoft.com, y escriba **Prueba** en la línea de asunto.

1. Seleccione **Datos adjuntos** (icono de clip).

1. Seleccione **OneDrive**.

1. Asegúrese de que esté seleccionada la pestaña **Reciente** del panel de navegación izquierdo.  Seleccione el documento **Test-label.docx** que ha creado y al que ha aplicado la etiqueta Extremadamente confidencial: Todos los empleados en la lista que se muestra. Seleccione la flecha desplegable **Compartir vínculo** y, a continuación, **Adjuntar**.  Presione **Enviar**.

1. Compruebe el correo electrónico al que ha enviado el documento.  Tenga en cuenta que es posible que el correo sea dirigido a su carpeta de correo no deseado.  El correo electrónico se envía correctamente, pero al intentar abrir el archivo de Word adjunto, que originalmente se etiquetó como Extremadamente confidencial: Todos los empleados, verá una notificación de que no tiene permiso para abrir el documento.

1. Cierre Outlook, pero mantenga abierta la pestaña del explorador en la página principal de Microsoft Purview.

### Revisar

En este laboratorio explorará las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.
