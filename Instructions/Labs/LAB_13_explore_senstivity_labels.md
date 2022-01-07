---
lab:
    title: 'Explorar las etiquetas de confidencialidad en Microsoft 365'
    module: 'Módulo 4, lección 2: Describir las funcionalidades de las soluciones de cumplimiento de Microsoft. Describir las funcionalidades de gobierno y protección de la información de Microsoft 365'
---


# Laboratorio: Explorar las etiquetas de confidencialidad en Microsoft 365

## Escenario del laboratorio
En esta laboratorio explorará las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad existentes creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.


**Tiempo estimado**: 20-25 minutos.

#### Tarea 1: En esta tarea descubrirá las posibilidades que ofrecen las etiquetas de confidencialidad. Para ello, realizará un recorrido por las opciones de configuración de una etiqueta de confidencialidad existente creada previamente y la directiva correspondiente para publicarla

1. Abra Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
    
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del Centro de cumplimiento de Microsoft 365.  

1. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **Information Protection**.

1. Seleccione la pestaña **Etiquetas** en la parte superior de la página.

1. Aparecerá un cuadro de información amarillo que indica: "Su organización no ha activado la capacidad de procesar el contenido de los archivos en línea de Office que tienen aplicadas etiquetas de sensibilidad encriptadas y están almacenados en OneDrive y SharePoint...".  Seleccione Activar ahora.  Una vez hecho esto, es posible que la configuración tarde unos minutos en propagarse por el sistema.


1. En el centro de la página hay etiquetas ya creadas.  Seleccione **Finanzas: Confidencial**.  Se abrirá una ventana que proporciona información sobre esta etiqueta.  Observe que esta etiqueta está configurada para admitir tanto el cifrado como el marcado de contenido.  Seleccione Modificar etiqueta en la parte superior de la página para ver algunas de las opciones de configuración básicas.

1. El primer paso para completar la configuración es dar un nombre y una descripción a su etiqueta.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.

1. Anote el ámbito de esta etiqueta.  El ámbito está configurado en Archivos y correos, para los cuales puede configurar las opciones de cifrado y marcado de contenido para proteger los correos y los archivos de Office etiquetados.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.

1. Puede configurar las opciones para cifrar o marcar el contenido del ámbito seleccionado —Archivos y correos—.  Observe que se han configurado las opciones de protección de los archivos y los correos para cifrar y marcar el contenido de los archivos.  Revise la definición de ambas opciones.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.

1. La ventana Cifrado muestra la configuración de las opciones de cifrado.  No haga ningún cambio.  Revise el cuadro de información debajo de Configuración de cifrado y revise los valores de la configuración. Observe que el acceso del usuario al contenido está configurado en No expira nunca.  También puede asignar permisos a usuarios y grupos específicos para que solo ellos puedan interactuar con el contenido al que se ha aplicado esta etiqueta.  Debajo de Usuarios y grupos, la cuenta empresarial está definida para que todos los usuarios de su cuenta puedan ver el contenido etiquetado con esta etiqueta.  El equipo de Finanzas también aparece en la lista, y tiene permisos de coautoría.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

1. En la página Marcados de contenido, tome nota del cuadro de información de la parte superior de la página.  Los marcados de contenido se aplicarán a los documentos, pero a los correos solo se les aplicarán los encabezados y los pies de página. En otras palabras, las marcas de agua no se aplicarán a los correos.  La marca de contenido asociada a esta etiqueta es una marca de agua que dice: EXTREMADAMENTE CONFIDENCIAL.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

1. Ahora se encuentra en la ventana Etiquetado automático de archivos y correos.  Lea la descripción del etiquetado automático en la parte superior de la página y el cuadro de información que aparece debajo.  Tome nota también de que esta etiqueta está configurada en Etiquetado automático para determinadas condiciones específicas. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

1. La siguiente ventana define la configuración de protección de los equipos, grupos y sitios a los que se les ha aplicado esta etiqueta. Esta opción no está habilitada. Seleccione **Siguiente** en la parte inferior de la página. 

1. La siguiente ventana es una característica en versión preliminar para aplicar automáticamente esta etiqueta a las columnas de las bases de datos de Azure (como SQL, Synapse, etc.) que contienen los tipos de información confidencial que ha elegido.  Esta característica no está habilitada. Seleccione **Cancelar** en la parte inferior de la página para salir del asistente de configuración de etiquetas y volver a la página Information Protection. 

1. En la parte superior de la página Information Protection, seleccione **Directivas de etiquetas**.  Las etiquetas de confidencialidad se pueden publicar mediante directivas de etiquetas.  

1. Seleccione **Directiva Finanzas: Confidencial**.  Se abrirá una ventana que proporciona información sobre la directiva.  Esta directiva sirve para publicar las etiquetas de la directiva Finanzas:Confidencial y protege los datos que contienen los datos financieros de Contoso.  Observe que esta directiva está publicada para todos.  

1. Seleccione **Editar** directiva en la parte superior de la ventana.

1. Lea la descripción que aparece debajo de "Elija etiquetas de confidencialidad para publicar".  Observe la etiqueta que aparece en la lista.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

1. Lea la descripción que aparece debajo de "Publicar para usuarios y grupos".  Observe que esta etiqueta está disponible para todos los usuarios.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

1. Revise la configuración de la directiva.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción que aparece debajo de "Aplicar una etiqueta predeterminada a los documentos".  Fíjese que no hay ninguna etiqueta predeterminada. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción que aparece debajo de "Aplicar una etiqueta predeterminada a los correos electrónicos".  Seleccione la flecha desplegable en el cuadro de entrada para ver las opciones disponibles. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción que aparece debajo de "Aplicar una etiqueta predeterminada al contenido de Power BI".  Fíjese que no hay ninguna etiqueta predeterminada. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

1. La última opción de la configuración le permite dar un nombre a su directiva.  No cambie la configuración.  Seleccione **Cancelar** en la parte inferior de la página para salir de la configuración de la directiva y vuelva a la página Information protection.

1. En la página Information protection, seleccione Etiquetado automático.  Observe que no hay ninguna directiva de etiquetado automático configurada.  No cambie la configuración.  Si se está preguntando por qué no hay ninguna directiva aquí, dado que las etiquetas están configuradas en Etiquetado automático de archivos y correos, vuelva a los pasos en los que examinó la configuración de las etiquetas y revise la descripción y los cuadros de información relacionados con el etiquetado automático de archivos y correos.  Sugerencia:  En la pestaña Etiquetado automático del laboratorio Sensibilidad, aparece el siguiente mensaje:  "Debe crear una directiva de etiquetado automático para aplicar automáticamente esta etiqueta a archivos que ya se han guardado (en SharePoint y OneDrive) o a correos que ya han sido procesados mediante Exchange".

1. En el panel de navegación izquierdo, seleccione Inicio para volver al Centro de cumplimiento de Microsoft 365.

1. Deje esta página abierta. La utilizará en la siguiente tarea.


#### Tarea 2:  En esta tarea, se familiarizará con el proceso de aplicar una etiqueta desde la perspectiva del usuario (en este caso el usuario es el administrador) y ver el marcado de contenido generado por la etiqueta

1. En primer lugar, asegúrese de que tiene configurado Office en su máquina virtual (VM) de laboratorio.  Para ello, seleccione la pestaña del **centro de administración de Microsoft 365** que está abierta el navegador.  Si ha cerrado la pestaña, abra una nueva pestaña del navegador y escriba **admin.microsoft.com**.
    1. En el panel de navegación de la izquierda, seleccione **Facturación** para ver todas las opciones y luego, seleccione **Sus productos**.
    1. En la página Sus productos, seleccione **Prueba de Microsoft 365 E5**
    1. En la página de prueba de Microsoft 365 E5, seleccione **Descargar e instalar el software** y siga las instrucciones de la página.

1. En la esquina inferior izquierda del laboratorio de VM, seleccione el icono de Windows, luego seleccione **Word** y luego seleccione **Documento en blanco**.  Esto abrirá un nuevo documento de Word con la versión de escritorio de Word.

1. En la barra de menús superior, seleccione **Confidencialidad**. En el menú desplegable, seleccione **Finanzas: Confidencial**. 

1. Observe que el documento incluye la marca de agua.  La marca de agua aparecerá en un texto pequeño de color gris claro que se mostrará verticalmente en la página. 

1. Guarde el archivo de Word.

1. Cierre las pestañas de Microsoft Word que hay abiertas en su explorador para salir de Word.

#### Tarea 3 (opcional): Además del marcado de contenido, se ha configurado el cifrado en las opciones de configuración de la protección de etiquetas. Según los permisos configurados con esta etiqueta, los miembros del grupo financiero pueden ser coautores de documentos con esta etiqueta aplicada y los usuarios del inquilino de Contoso pueden verlos.  En esta tarea enviará este documento a una dirección de correo electrónico a la que tenga acceso (p. ej., una dirección de correo electrónico personal) y que no forme parte del dominio WWLxZZZZ.OnMicrosoft.com, y verá lo que ocurre cuando intenta abrir los datos adjuntos.  

1. En la página principal del Centro de cumplimiento de Microsoft 365, seleccione el **icono del iniciador de aplicaciones** que aparece junto a las palabras Contoso Electronics. **Haga clic con el botón derecho en el icono de Outlook** y seleccione **Abrir en una nueva pestaña**.

1. Seleccione **Nuevo mensaje** en la esquina superior izquierda de la pantalla.  Escriba una dirección de correo electrónico a la que tenga acceso y que no forme parte del dominio WWLxZZZZ.OnMicrosoft.com, y escriba **Prueba** en la línea de asunto.

1. Seleccione **Adjuntar**.

1. Seleccione **Examinar las ubicaciones de la nube**.

1. Seleccione el documento que ha creado y al que ha aplicado la etiqueta **Etiqueta:Prueba** en la lista que se muestra. Seleccione **Siguiente** y **Adjuntar como una copia**.  Presione **Enviar**.

1. Utilice el navegador web de su VM de laboratorio para iniciar sesión en la cuenta de correo electrónico a la que envió el documento.  Tenga en cuenta que es posible que el correo se dirija a su carpeta de correo no deseado.  Cuando intente abrir el archivo de Word adjunto, verá una notificación informándole de que no tiene permiso para abrir el documento.

1. Cierre las pestañas abiertas del explorador.


#### Revisión
En esta laboratorio explorará las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.
