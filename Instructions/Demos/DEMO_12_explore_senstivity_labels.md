---
Demo:
    title: 'Etiquetas de confidencialidad en Microsoft 365'
    module: 'Módulo 4, lección 2: Describir las funcionalidades de las soluciones de cumplimiento de Microsoft. Describir las funcionalidades de gobierno y protección de la información de Microsoft 365'
---


# Demo: Etiquetas de confidencialidad en Microsoft 365

### Escenario de la demo
En esta demo hará una demostración de las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad existentes creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.


#### Demo, parte 1: En esta demo mostrará la configuración de una etiqueta de confidencialidad existente y la directiva correspondiente para publicarla

1. Abra Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del Centro de cumplimiento de Microsoft 365.  

1. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, seleccione **Mostrar todo**.

1. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **Information Protection**.

1. En el cuadro de información amarillo, indique que su organización no ha activado la capacidad de procesar el contenido de los archivos en línea de Office a los que se les ha aplicado etiquetas de confidencialidad cifradas y que se han almacenado en OneDrive y SharePoint.  Seleccione Activar ahora.  Una vez hecho esto, es posible que la configuración tarde unos minutos en propagarse por el sistema.

1. Compruebe que la pestaña **Etiquetas** esté seleccionada (subrayada) en la parte superior de la página.

1. Observe que ya hay tres etiquetas creadas en el centro de la página.  Seleccione **Finanzas: Confidencial**.  Se abrirá una ventana que proporciona información sobre esta etiqueta.  Observe que esta etiqueta está configurada para admitir tanto el cifrado como el marcado de contenido.  Seleccione **Modificar etiqueta** en la parte superior de la página para ver algunas de las opciones de configuración básicas.

    1. El primer paso para completar la configuración es dar un nombre y una descripción a su etiqueta.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.

    1. Anote el ámbito de esta etiqueta.  El ámbito está configurado en Archivos y correos, para los cuales puede configurar las opciones de cifrado y marcado de contenido para proteger los correos y los archivos de Office etiquetados.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.

    1. Puede configurar las opciones para cifrar o marcar el contenido del ámbito seleccionado —Archivos y correos—.  Observe que se han configurado las opciones de protección de los archivos y los correos para cifrar y marcar el contenido de los archivos.  Revise la definición de ambas opciones.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.

    1. La ventana Cifrado muestra la configuración de las opciones de cifrado.  No haga ningún cambio.  Revise el cuadro de información debajo de Configuración de cifrado y revise los valores de la configuración. Observe que el acceso del usuario al contenido está configurado en No expira nunca.  También puede asignar permisos a usuarios y grupos específicos para que solo ellos puedan interactuar con el contenido al que se ha aplicado esta etiqueta.  Debajo de Usuarios y grupos, la cuenta empresarial está definida para que todos los usuarios de su cuenta puedan ver el contenido etiquetado con esta etiqueta.  El equipo de Finanzas también aparece en la lista, y tiene permisos de coautoría.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

    1. En la página Marcados de contenido, tome nota del cuadro de información de la parte superior de la página.  Los marcados de contenido se aplicarán a los documentos, pero a los correos solo se les aplicarán los encabezados y los pies de página. En otras palabras, las marcas de agua no se aplicarán a los correos.  El marcado de contenido asociado a esta etiqueta es una marca de agua.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

    1. Ahora se encuentra en la ventana Etiquetado automático de archivos y correos.  Lea la descripción del etiquetado automático en la parte superior de la página y el cuadro de información que aparece debajo.  Tome nota también de que esta etiqueta está configurada en Etiquetado automático para determinadas condiciones específicas. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

    1. La siguiente ventana define la configuración de protección de los equipos, grupos y sitios a los que se les ha aplicado esta etiqueta. Esta opción no está habilitada. Seleccione **Siguiente** en la parte inferior de la página. 

    1. La siguiente ventana es una característica en versión preliminar para aplicar automáticamente esta etiqueta a las columnas de las bases de datos de Azure (como SQL, Synapse, etc.) que contienen los tipos de información confidencial que ha elegido.  Esta característica no está habilitada. Seleccione **Cancelar** en la parte inferior de la página para salir del asistente de configuración de etiquetas y volver a la página Information Protection. 

1. En la parte superior de la página Information Protection, seleccione **Directivas de etiquetas**.  Las etiquetas de confidencialidad se pueden publicar mediante directivas de etiquetas.  

1. Seleccione **Directiva Finanzas: Confidencial**.  Se abrirá una ventana que proporciona información sobre la directiva.  Esta directiva sirve para publicar las etiquetas de la directiva Finanzas:Confidencial y protege los datos que contienen los datos financieros de Contoso.  Observe que esta directiva está publicada para todos.  

1. Seleccione **Editar** directiva en la parte superior de la ventana.

    1. Lea la descripción que aparece debajo de "Elija etiquetas de confidencialidad para publicar".  Observe la etiqueta que aparece en la lista.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

    1. Lea la descripción que aparece debajo de "Publicar para usuarios y grupos".  Observe que esta etiqueta está disponible para todos los usuarios.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

    1. Revise la configuración de la directiva.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

    1. La última opción de la configuración le permite dar un nombre a su directiva.  No cambie la configuración.  Seleccione **Cancelar** en la parte inferior de la página para salir de la configuración de la directiva y vuelva a la página Information protection.

1. En la página Information protection, seleccione Etiquetado automático.  Observe que no hay ninguna directiva de etiquetado automático configurada.  No cambie la configuración.  Si se está preguntando por qué no hay ninguna directiva aquí, dado que las etiquetas están configuradas en Etiquetado automático de archivos y correos, vuelva a los pasos en los que examinó la configuración de las etiquetas y revise la descripción y los cuadros de información relacionados con el etiquetado automático de archivos y correos.  Sugerencia:  En la pestaña Etiquetado automático del laboratorio Sensibilidad, aparece el siguiente mensaje:  "Debe crear una directiva de etiquetado automático para aplicar automáticamente esta etiqueta a archivos que ya se han guardado (en SharePoint y OneDrive) o a correos que ya han sido procesados mediante Exchange".

1. En el panel de navegación izquierdo, seleccione Inicio para volver al Centro de cumplimiento de Microsoft 365.

1. Deje esta página abierta. La utilizará en la siguiente tarea.


#### Demo, parte 2:  En este paso, hará una demostración del proceso de aplicar una etiqueta desde la perspectiva del usuario (en este caso el usuario es el administrador) y ver el marcado de contenido generado por la etiqueta

1. En la página principal del Centro de cumplimiento de Microsoft 365, seleccione el **icono del iniciador de aplicaciones** junto a las palabras Contoso Electronics. **Haga clic con el botón derecho en el icono de Word** y luego seleccione **Abrir en una nueva pestaña**.  

1. Seleccione **+ Nuevo documento en blanco** y luego escriba algo de texto en la página.  En la barra azul de la parte superior de la página, seleccione la flecha hacia abajo que hay junto a las palabras DocumentoXX: Guardado y, en el cuadro Nombre de archivo, escriba **Etiqueta:Prueba**.

1. En la barra de menús de la parte superior, seleccione **Sensibilidad**. Si no ve inmediatamente esta opción, actualice la página. En el menú desplegable, seleccione **Finanzas: Confidencial**. 

1. En la barra de menús de la parte superior, seleccione **Vista** y luego **Vista de lectura**.

1. Observe que el documento incluye la marca de agua.  

1. Cierre las pestañas de Microsoft Word que hay abiertas en su explorador para salir de Word.

#### Demo, parte 3 (opcional): Además del marcado de contenido, se ha configurado el cifrado en las opciones de configuración de la protección de etiquetas. Debido a los permisos que se han configurado con esta etiqueta, los miembros del grupo Finanzas pueden trabajar en coautoría en los documentos a los que se les ha aplicado esta etiqueta, y los usuarios de la cuenta empresarial de Contoso pueden verlos (así como cualquier documento o correo al que se le haya aplicado la etiqueta).  En esta sección enviará este documento a una dirección de correo electrónico a la que tenga acceso (p. ej., una dirección de correo electrónico personal o su correo electrónico de Microsoft) y que no forme parte del dominio WWLxZZZZ.OnMicrosoft.com, y verá lo que ocurre cuando intenta abrir los datos adjuntos.  

1. En la página principal del Centro de cumplimiento de Microsoft 365, seleccione el **icono del iniciador de aplicaciones** que aparece junto a las palabras Contoso Electronics. **Haga clic con el botón derecho en el icono de Outlook** y seleccione **Abrir en una nueva pestaña**.

1. Seleccione **Nuevo mensaje** en la esquina superior izquierda de la pantalla.  Escriba una dirección de correo electrónico a la que tenga acceso y que no forme parte del dominio WWLxZZZZ.OnMicrosoft.com, y escriba **Prueba** en la línea de asunto.

1. Seleccione **Adjuntar**.

1. Seleccione **Examinar las ubicaciones de la nube**.

1. Seleccione el documento que ha creado y al que ha aplicado la etiqueta **Etiqueta:Prueba** en la lista que se muestra. Seleccione **Siguiente** y **Adjuntar como una copia**.  Presione **Enviar**.

1. Compruebe el correo electrónico al que ha enviado el documento.  Tenga en cuenta que es posible que el correo sea dirigido a su carpeta de correo no deseado.  Cuando intente abrir el archivo de Word adjunto, verá una notificación informándole de que no tiene permiso para abrir el documento.

1. Cierre las pestañas abiertas del explorador.


#### Revisión
En esta demo ha mostrado el funcionamiento de las etiquetas de confidencialidad.  Ha realizado un recorrido por la configuración de las etiquetas de confidencialidad existentes que habían sido creadas previamente y por la directiva correspondiente para publicar la etiqueta. Luego ha explicado cómo aplicar una etiqueta y el impacto que tiene esa etiqueta desde la perspectiva de un usuario.
