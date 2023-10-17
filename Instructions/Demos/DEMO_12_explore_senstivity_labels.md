<!---
---
Demostración: Título: "Etiquetas de confidencialidad en Microsoft Purview" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft; Módulo 3: Descripción de las funcionalidades de protección de la información, administración del ciclo de vida de los datos y gobernanza de los datos en Microsoft Purview; Unidad 4: Descripción de las etiquetas de confidencialidad'
---
--->

# Demostración: Etiquetas de confidencialidad en Microsoft Purview

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de las funcionalidades de protección de la información, administración del ciclo de vida de los datos y gobernanza de los datos en Microsoft Purview
- Unidad: Descripción de las etiquetas de confidencialidad

## Escenario de la demo

En esta demo hará una demostración de las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad existentes creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.  **NOTA**: La primera vez que use Word online con el inquilino de Microsoft 365, la opción Confidencialidad puede tardar 15 minutos en aparecer en la cinta de opciones.  Los moderadores deben ejecutar la segunda parte de la demostración antes de la clase para que la opción tenga el tiempo suficiente para aparecer.

### Demo, parte 1

En esta demo mostrará la configuración de una etiqueta de confidencialidad existente y la directiva correspondiente para publicarla.

1. Abra la pestaña del explorador para la página principal de Microsoft Purview.  Si la había cerrado, abra otra y escriba **https://admin.microsoft.com** . Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.  

1. En el panel de navegación izquierdo, en Soluciones, expanda **Information Protection** y, a continuación, seleccione **Información general**.  La página de información general incluye información sobre las etiquetas de confidencialidad principales aplicadas al contenido, las principales actividades detectadas, las ubicaciones en las que se aplican las etiquetas de confidencialidad y mucho más.  
    1. En la página de información general, puede ver un cuadro de información amarillo que indica que su organización no ha activado la capacidad de procesar el contenido de los archivos en línea de Office a los que se les ha aplicado etiquetas de confidencialidad cifradas y que se han almacenado en OneDrive y SharePoint.  Seleccione **Activar ahora**.  Una vez hecho esto, es posible que la configuración tarde unos minutos en propagarse por el sistema.

1. En el panel de navegación izquierdo, seleccione **Etiquetas**.

1. Algunas etiquetas se han preconfigurado en el inquilino de laboratorio de Microsoft 365, para su comodidad. Expanda la etiqueta denominada **Extremadamente confidencial** seleccionando **>** y, a continuación, seleccione **Todos los empleados**.  Se abrirá una ventana que proporciona información sobre esta etiqueta.  Observe que esta etiqueta está configurada para admitir tanto el cifrado como el marcado de contenido.  Seleccione el **icono de lápiz** de la parte superior de la página para ver algunas de las opciones de configuración básicas. Si no ve el icono de lápiz, seleccione los puntos suspensivos.
    1. El primer paso para completar la configuración es dar un nombre y una descripción a su etiqueta.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Anote el ámbito de esta etiqueta.  El ámbito se establece en Archivos y correos electrónicos.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Esta siguiente pantalla es donde puede elegir la configuración de protección para los elementos etiquetados. Observe que esta etiqueta está configurada para admitir el cifrado y el marcado de contenido. No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.
        1. La ventana Cifrado muestra la configuración de las opciones de cifrado. Revise la configuración actual, pero no cambie nada. Observe que el acceso del usuario al contenido está configurado en No expira nunca.  También puede asignar permisos a usuarios y grupos específicos para que solo ellos puedan interactuar con el contenido al que se ha aplicado esta etiqueta.  Debajo de Usuarios y grupos, la cuenta empresarial está definida para que todos los usuarios de su cuenta puedan ver el contenido etiquetado con esta etiqueta.  El equipo de Finanzas también aparece en la lista, y tiene permisos de coautoría.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
        1. En la página Marcados de contenido, tome nota del cuadro de información de la parte superior de la página.  Los marcados de contenido se aplicarán a los documentos, pero a los correos solo se les aplicarán los encabezados y los pies de página. En otras palabras, las marcas de agua no se aplicarán a los correos.  El marcado de contenido asociado a esta etiqueta es una marca de agua.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Ahora se encuentra en la ventana Etiquetado automático de archivos y correos.  Lea la descripción del etiquetado automático en la parte superior de la página y el cuadro de información que aparece debajo.  Tome nota también de que esta etiqueta está configurada en Etiquetado automático para determinadas condiciones específicas. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. La siguiente ventana define la configuración de protección de los equipos, grupos y sitios a los que se les ha aplicado esta etiqueta. Esta opción no está habilitada. Seleccione **Siguiente** en la parte inferior de la página.
    1. La siguiente ventana es una característica en versión preliminar para aplicar automáticamente esta etiqueta a activos de datos esquematizados en el Mapa de datos de Microsoft Purview (como SQL, Synapse, etc.) que contienen los tipos de información confidencial que ha elegido.  Esta característica no está habilitada. Seleccione **Cancelar** en la parte inferior de la página para salir del asistente de configuración de etiquetas y volver a la página Information Protection.

1. En el panel de navegación izquierdo, seleccione **Directivas de etiquetas**.  Las etiquetas de confidencialidad se pueden publicar mediante directivas de etiquetas.  El inquilino de Microsoft 365 se ha configurado con algunas directivas de etiqueta para su comodidad.

1. En este caso, seleccione **Directiva de etiqueta de confidencialidad global**.  Se abrirá una ventana que proporciona información sobre la directiva.  Tenga en cuenta la descripción: esta directiva de etiqueta se ha configurado para que actúe como directiva de etiqueta de confidencialidad predeterminada para todos los usuarios y grupos. Esta directiva sirve para publicar la mayoría de las etiquetas preconfiguradas para este inquilino de laboratorio de Microsoft 365 y se muestran en la pestaña etiquetas.

1. Seleccione **Editar directiva** en la parte superior de la ventana.
    1. Lea la descripción que aparece debajo de "Elija etiquetas de confidencialidad para publicar".  Observe las etiquetas que aparecen.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. La página siguiente es una versión preliminar para Asignar unidades de administración. Seleccione **Next** (Siguiente).
    1. Lea la descripción que aparece debajo de "Publicar para usuarios y grupos".  Observe que esta etiqueta está disponible para todos los usuarios.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la configuración de la directiva.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción en "Aplicar una etiqueta predeterminada a los documentos". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción en "Aplicar una etiqueta predeterminada a los correos electrónicos". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción en "Configuración predeterminada para reuniones y eventos de calendario". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción en "Aplicar una etiqueta predeterminada al contenido de Power BI". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. La última opción de la configuración le permite dar un nombre a su directiva.  Puesto que está editando la directiva, el campo de nombre está atenuado.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la configuración de la directiva. Dado que no se cambió nada, seleccione **Cancelar** para volver a la página Directivas de etiqueta.

1. En la página Information protection, seleccione Etiquetado automático. Revise la descripción. Observe que crea directivas de etiquetado automático para aplicar automáticamente etiquetas de confidencialidad a los mensajes de correo electrónico o a los archivos de OneDrive y SharePoint que contienen información confidencial. Si hay directivas de etiquetado automático configuradas, seleccione una y revise la información de la directiva en el panel de detalles.  Si no aparece ninguna directiva, puede optar por recorrer los pasos para crear una, si el tiempo lo permite.

1. En el panel de navegación izquierdo, seleccione Inicio para volver al Portal de cumplimiento de Microsoft Purview.

1. Deje esta pestaña del explorador abierta.

### Demo, parte 2

En este paso, hará una demostración del proceso de aplicar una etiqueta desde la perspectiva del usuario (en este caso el usuario es el administrador).  Para ver el impacto de aplicar la etiqueta, seleccionará la etiqueta Confidencial - Finanzas porque esta etiqueta aplica una marca de agua.

1. En la página principal del Portal de cumplimiento de Microsoft Purview, seleccione el **icono del iniciador de aplicaciones**, junto a Contoso Electronics. Seleccione el **icono de Word**.  

1. Seleccione **Documento en blanco** y escriba algún texto en la página.  En la barra azul de la parte superior de la página, seleccione la flecha hacia abajo que hay junto a las palabras DocumentoXX: Guardado y, en el cuadro Nombre de archivo, escriba **Etiqueta:Prueba** y pulse la tecla **Entrar** en el teclado.

1. En la barra de menús superior, seleccione **Icono de sensibilidad** (el icono situado a la derecha del icono de micrófono), si no ve inmediatamente esta opción, actualice la página. En el menú desplegable, seleccione **Finanzas: Confidencial**.   NOTA: Si no ve la opción Confidencialidad, actualice la página. Al tratarse de un entorno de inquilino de laboratorio, puede haber retrasos más prolongados de lo normal (10-15 minutos).
1. 
1. En la barra de menús de la parte superior, seleccione **Vista** y luego **Vista de lectura**.

1. Observe que el documento incluye la marca de agua.  

1. Cierre las pestañas de Microsoft Word que hay abiertas en su explorador para salir de Word.

1. Mantenga abierta la pestaña del navegador de Microsoft Purview para la siguiente demostración.

### Demo, parte 3 (opcional)

Recuerde de la primera parte de la demostración que la etiqueta Finanzas: Confidencial está configurada para el cifrado. Según los permisos configurados con esta etiqueta, los usuarios del inquilino de Contoso tienen permisos de visualizador para cualquier documento o correo electrónico con la etiqueta aplicada.  En esta sección, enviará el documento que creó anteriormente, que incluye la etiqueta Finanzas: Confidencial, a una dirección de correo electrónico a la que tiene acceso (una dirección de correo electrónico personal o su correo electrónico de Microsoft) y que no forma parte del dominio de WWLxZZZZ.OnMicrosoft.com.  

1. En la página principal del Portal de cumplimiento de Microsoft Purview, seleccione el **icono del iniciador de aplicaciones**, junto a Contoso Electronics. Seleccione el **icono de Outlook**

1. Seleccione **Nuevo correo electrónico** en la esquina superior izquierda de la pantalla.  Escriba una dirección de correo electrónico a la que tenga acceso y que no forme parte del dominio WWLxZZZZ.OnMicrosoft.com, y escriba **Prueba** en la línea de asunto.

1. En la cinta de opciones de la parte superior, seleccione el icono del clip y, después, en la lista desplegable, bajo archivos sugeridos, seleccione el documento que creó en el paso anterior, **Etiqueta de prueba** para adjuntarlo al correo electrónico.

1. Presione **Enviar** para enviar el correo electrónico.

1. Compruebe el correo electrónico al que ha enviado el documento.  Tenga en cuenta que es posible que el correo sea dirigido a su carpeta de correo no deseado.  El correo electrónico se envía correctamente, pero al intentar abrir el archivo de Word adjunto, que originalmente se etiquetó como Finanzas: Confidencial, verá una notificación de que no tiene permiso para abrir el documento.

1. Cierre Outlook.

1. Mantenga abierta la pestaña del navegador de Microsoft Purview para la siguiente demostración.


### Revisar

En esta demostración, ha mostrado las opciones que pueden configurarse para las etiquetas de confidencialidad y la configuración de las directivas para publicar etiquetas de confidencialidad. También ha explicado cómo aplicar una etiqueta y el impacto que tiene esa etiqueta desde la perspectiva de un usuario.

