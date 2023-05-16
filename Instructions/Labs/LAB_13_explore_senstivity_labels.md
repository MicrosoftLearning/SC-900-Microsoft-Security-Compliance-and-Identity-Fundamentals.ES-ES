---
lab:
  title: 'Exploración de las etiquetas de confidencialidad en Microsoft Purview'
  module: 'Módulo 3: Descripción de la protección de la información y la administración del ciclo de vida de los datos en Microsoft Purview'
---


# <a name="lab-explore-sensitivity-labels-in-microsoft-purview"></a>Laboratorio: Explorar las etiquetas de confidencialidad en Microsoft Purview

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de la protección de la información y la administración del ciclo de vida de los datos en Microsoft Purview
- Unidad: Descripción de las etiquetas de confidencialidad

## <a name="lab-scenario"></a>Escenario del laboratorio

En este laboratorio explorará las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad existentes creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.

**Tiempo estimado**: 20-25 minutos

### <a name="task-1"></a>Tarea 1

En esta tarea descubrirá las posibilidades que ofrecen las etiquetas de confidencialidad. Para ello, realizará un recorrido por las opciones de configuración de una etiqueta de confidencialidad existente creada previamente y la directiva correspondiente para publicarla.

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.

    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.  

1. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **Information Protection**.

1. En la página de información general, observe que el cuadro de información amarillo indica que su organización no ha activado la capacidad de procesar el contenido de los archivos en línea de Office a los que se les ha aplicado etiquetas de confidencialidad cifradas y que se han almacenado en OneDrive y SharePoint.  Seleccione **Activar ahora**.  Una vez hecho esto, es posible que la configuración tarde unos minutos en propagarse por el sistema.  Revise también la información disponible en esta página de información general.

1. Seleccione la pestaña **Etiquetas** en la parte superior de la página.

1. Observe que ya hay etiquetas creadas en el centro de la página.  Seleccione **Finanzas: Confidencial**.  Se abrirá una ventana que proporciona información sobre esta etiqueta.  Observe que esta etiqueta está configurada para admitir tanto el cifrado como el marcado de contenido.  Seleccione **Modificar etiqueta** en la parte superior de la página para ver algunas de las opciones de configuración básicas.  A medida que avance y vea las distintas opciones de configuración, NO cambie nada.

1. El primer paso para completar la configuración es dar un nombre y una descripción a su etiqueta.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.

1. Anote el ámbito de esta etiqueta.  El ámbito se establece en **Elementos**.  Lea la descripción, pero no cambie nada.  Seleccione **Siguiente** en la parte inferior de la página.

1. Puede configurar las opciones para cifrar o marcar el contenido del ámbito o elementos seleccionados.  Observe que se han configurado las opciones de protección de los archivos y los correos para cifrar y marcar el contenido de los archivos.  Revise la definición de ambas opciones.  No haga ningún cambio.  Seleccione **Siguiente** en la parte inferior de la página.

1. La ventana Cifrado muestra la configuración de las opciones de cifrado.  No haga ningún cambio.  Revise el cuadro de información debajo de Configuración de cifrado y revise los valores de la configuración. Observe que el acceso del usuario al contenido está configurado en No expira nunca.  También puede asignar permisos a usuarios y grupos específicos para que solo ellos puedan interactuar con el contenido al que se ha aplicado esta etiqueta.  Debajo de Usuarios y grupos, la cuenta empresarial está definida para que todos los usuarios de su cuenta puedan ver el contenido etiquetado con esta etiqueta.  El equipo de Finanzas también aparece en la lista, y tiene permisos de coautoría.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

1. En la página Marcados de contenido, tome nota del cuadro de información de la parte superior de la página.  Los marcados de contenido se aplicarán a los documentos, pero a los correos solo se les aplicarán los encabezados y los pies de página. En otras palabras, las marcas de agua no se aplicarán a los correos.  El marcado de contenido asociado con esta etiqueta es una marca de agua que indica EXTREMADAMENTE CONFIDENCIAL.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

1. Ahora se encuentra en la ventana Etiquetado automático de archivos y correos.  Lea la descripción del etiquetado automático en la parte superior de la página y el cuadro de información que aparece debajo.  Tome nota también de que esta etiqueta está configurada en Etiquetado automático para determinadas condiciones específicas. No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.

1. La siguiente ventana define la configuración de protección de los grupos y sitios a los que se les ha aplicado esta etiqueta. Esta opción no está habilitada. Seleccione **Siguiente** en la parte inferior de la página.

1. Esta ventana siguiente es una característica en vista previa para el etiquetado automático para los recursos de datos esquematizados. lea la descripción.  Esta característica no está habilitada. Seleccione **Cancelar** en la parte inferior de la página para salir del asistente de configuración de etiquetas y volver a la página Information Protection.

1. En la parte superior de la página Information Protection, seleccione **Directivas de etiquetas**.  Las etiquetas de confidencialidad se pueden publicar mediante directivas de etiquetas.  

1. En este caso, seleccione **Directiva de etiqueta de confidencialidad global**.  Se abrirá una ventana que proporciona información sobre la directiva.  Tenga en cuenta la descripción, esta es la directiva de etiqueta de confidencialidad predeterminada para todos los usuarios y grupos. Esta directiva sirve para publicar la mayoría de las etiquetas preconfiguradas para este inquilino de laboratorio de Microsoft 365 y se muestran en la pestaña etiquetas.  

1. Seleccione **Editar** directiva en la parte superior de la ventana.
    1. Lea la descripción que aparece debajo de "Elija etiquetas de confidencialidad para publicar".  Observe la etiqueta que aparece en la lista.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción que aparece debajo de "Publicar para usuarios y grupos".  Observe que esta etiqueta está disponible para todos los usuarios.  No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la configuración de la directiva.  Seleccionar **Requiere que los usuarios apliquen una etiqueta a su correo electrónico o sus documentos**. Revise la descripción proporcionada. Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción en "Aplicar una etiqueta predeterminada a los documentos". En el campo Etiqueta predeterminada, seleccione la flecha abajo y, a continuación, seleccione **General/Todos los empleados (sin restricciones)** .  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción en "Aplicar una etiqueta predeterminada a los correos electrónicos". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Lea la descripción en "Aplicar una etiqueta predeterminada al contenido de Power BI". No cambie la configuración.  Seleccione **Siguiente** en la parte inferior de la página.
    1. La última opción de la configuración le permite dar un nombre a su directiva.  Puesto que está editando la directiva, el campo de nombre está atenuado.  Seleccione **Siguiente** en la parte inferior de la página.
    1. Revise la configuración de directiva y, a continuación, seleccione **Enviar** y, a continuación, seleccione **Listo** para volver a la página Information Protection.

1. En la página Information protection, seleccione Etiquetado automático.  Observe que no hay ninguna directiva de etiquetado automático configurada.  No cambie la configuración.  Si se está preguntando por qué no hay ninguna directiva aquí, dado que las etiquetas están configuradas en Etiquetado automático de archivos y correos, vuelva a los pasos en los que examinó la configuración de las etiquetas y revise la descripción y los cuadros de información relacionados con el etiquetado automático de archivos y correos.  Sugerencia:  En la pestaña Etiquetado automático del laboratorio Sensibilidad, aparece el siguiente mensaje:  "Debe crear una directiva de etiquetado automático para aplicar automáticamente esta etiqueta a archivos que ya se han guardado (en SharePoint y OneDrive) o a correos que ya han sido procesados mediante Exchange".

1. En el panel de navegación izquierdo, seleccione Inicio para volver al Portal de cumplimiento de Microsoft Purview.

1. Deje esta página abierta. La utilizará en la siguiente tarea.

### <a name="task-2"></a>Tarea 2

En esta tarea, se familiarizará con el proceso de aplicar una etiqueta desde la perspectiva del usuario (en este caso el usuario es el administrador) y ver el marcado de contenido generado por la etiqueta.

1. En la página principal del Portal de cumplimiento de Microsoft Purview, seleccione el **icono del iniciador de aplicaciones**, junto a Contoso Electronics. Seleccione el **icono de Word**.  

1. En Crear nuevo, seleccione **Documento en blanco** y escriba algún texto en la página.  En la parte superior de la página, seleccione la flecha hacia abajo que hay junto a las palabras DocumentoXX: Guardado y, en el cuadro Nombre de archivo, escriba **Etiqueta:Prueba** y pulse **Entrar** en el teclado.

1. En la barra de menús superior, seleccione el **icono Confidencialidad**, situado a la derecha del icono Micrófono (en función del tamaño de la pantalla, es posible que tenga que seleccionar primero los puntos suspensivos y, después, Confidencialidad). En el menú desplegable, seleccione **Finanzas: Confidencial**.  NOTA: Si no ve la opción Confidencialidad, actualice la página. Al tratarse de un entorno de inquilino de laboratorio, puede haber retrasos más prolongados de lo normal (10-15 minutos).

1. En la barra de menús de la parte superior, seleccione **Vista** y luego **Vista de lectura**.

1. Observe que el documento incluye la marca de agua.  

1. Cierre las pestañas de Microsoft Word que hay abiertas en su explorador para salir de Word.

### <a name="task-3-optional"></a>Tarea 3 (opcional)

Recuerde de la primera parte de la demostración que la etiqueta Finanzas: Confidencial está configurada para el cifrado. Según los permisos configurados con esta etiqueta, los usuarios del inquilino de Contoso tienen permisos de visualizador para cualquier documento o correo electrónico con la etiqueta aplicada.  En esta sección, enviará el documento que creó anteriormente, que incluye la etiqueta Finanzas: Confidencial, a una dirección de correo electrónico a la que tiene acceso (es decir, una dirección de correo electrónico personal o su correo electrónico de Microsoft) y que no forma parte del dominio de WWLxZZZZ.OnMicrosoft.com.  

1. En la página principal del Portal de cumplimiento de Microsoft Purview, seleccione el **icono del iniciador de aplicaciones**, junto a Contoso Electronics. Seleccione el **icono de Outlook**.

1. Seleccione **Nuevo correo electrónico** en la esquina superior izquierda de la pantalla.  Escriba una dirección de correo electrónico a la que tenga acceso y que no forme parte del dominio WWLxZZZZ.OnMicrosoft.com, y escriba **Prueba** en la línea de asunto.

1. Seleccione **Datos adjuntos** (icono de clip).

1. Seleccione **OneDrive**.

1. Asegúrese de que esté seleccionada la pestaña **Reciente** del panel de navegación izquierdo.  Seleccione el documento que ha creado y al que ha aplicado la etiqueta **Etiqueta:Prueba** en la lista que se muestra. Seleccione **Siguiente** y **Adjuntar como una copia**.  Presione **Enviar**.

1. Compruebe el correo electrónico al que ha enviado el documento.  Tenga en cuenta que es posible que el correo sea dirigido a su carpeta de correo no deseado.  El correo electrónico se envía correctamente, pero al intentar abrir el archivo de Word adjunto, que originalmente se etiquetó como Finanzas: Confidencial, verá una notificación de que no tiene permiso para abrir el documento.

1. Cierre las pestañas abiertas del explorador.

### <a name="review"></a>Revisar

En este laboratorio explorará las funcionalidades de las etiquetas de confidencialidad.  Realizará un recorrido por la configuración de las etiquetas de confidencialidad creadas previamente y por la directiva correspondiente para publicar la etiqueta.   Después aprenderá a aplicar una etiqueta y comprobará el impacto que tiene esta desde la perspectiva de un usuario.
