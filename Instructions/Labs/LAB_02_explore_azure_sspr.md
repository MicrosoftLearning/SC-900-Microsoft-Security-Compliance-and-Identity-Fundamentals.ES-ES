<!---
---
Laboratorio: Título: "Exploración de la Autenticación de Azure AD con el autoservicio de restablecimiento de contraseña" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de Azure Active Directory (Azure AD), parte de Microsoft Entra; Módulo 2: Descripción de las funcionalidades de autenticación de Azure AD; Unidad 4: Descripción del autoservicio de restablecimiento de contraseña"
---
--->

# Laboratorio: Autoservicio de restablecimiento de contraseña de Microsoft Entra

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Entra
- Módulo: Descripción de las funcionalidades de autenticación de Microsoft Entra ID
- Unidad: Descripción del autoservicio de restablecimiento de contraseña

## Escenario del laboratorio

En este laboratorio, como administrador, revisará el proceso de agregar un usuario al grupo de seguridad de SSPR, que ya está configurado en el inquilino de Microsoft 365. Cuando el SSPR esté habilitado, asumirá el rol de un usuario y pasará por el proceso de registrarse en el SSPR y también de restablecer su contraseña.  Por último, como administrador, podrá ver los registros de auditoría y los datos de uso e información del SSPR.

**Tiempo estimado**: 15-20 minutos

### Tarea 1

En esta tarea, como administrador, revisará algunas de las opciones de configuración disponibles para SSPR.

1. Abra el explorador de Microsoft Edge. En la barra de direcciones, escriba **https://entra.microsoft.com** e inicie sesión con las credenciales de administrador de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el ALH) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En el panel de navegación izquierdo, expanda la opción **Protección** y seleccione **Restablecimiento de contraseña**.  

1. Se mostrarán las propiedades para el autoservicio de restablecimiento de contraseñas. Seleccione el icono de información junto a donde dice **Autoservicio de restablecimiento de contraseña habilitado** para ver la descripción. Asegúrese de que **Seleccionado** esté resaltado en azul. Coloque el cursor sobre el icono de información junto a **Seleccionar grupo** y observe que diga: "Define el grupo de usuarios a los que se permite restablecer sus propias contraseñas". Debe incluir usuarios en el grupo. No puede seleccionar usuarios de forma individual. Observe que ya aparece un grupo: SSPRSecurityGroupUsers (este grupo estaba preconfigurado como parte del inquilino de Microsoft 365). Por último, observe el cuadro de información azul: "Esta configuración solo se aplica a los usuarios finales de su organización. Los administradores siempre están habilitados para el autoservicio de restablecimiento de contraseña y deben utilizar dos métodos de autenticación para restablecer su contraseña".

1. En el panel de navegación izquierdo de restablecimiento de contraseña, seleccione **Métodos de autenticación**.

1. En Número de métodos requeridos para el restablecimiento, seleccione **1**. Observe el cuadro de información de la pantalla.

1. Observe los diferentes métodos disponibles para los usuarios.  **Correo electrónico** y **Teléfono móvil (solo SMS)** ya deberían estar marcados; si no es así, selecciónelos.

1. En el panel de navegación izquierdo de restablecimiento de contraseña, seleccione **Registro**.  

1. Asegúrese de que la opción Exigir a los usuarios que se registren al iniciar sesión esté establecida a **Sí**.  Deje el Número de días antes de que se solicite a los usuarios que vuelvan a confirmar su información de autenticación, en el valor predeterminado 180.   Observe el cuadro de información de la página.

1. En el panel de navegación izquierdo de restablecimiento de contraseña, seleccione **Notificaciones**.  

1. Asegúrese de que la opción Notificar a los usuarios los restablecimientos de contraseña esté establecida a **Sí**.  Deje la configuración Notificar a todos los administradores cuando otros administradores restablezcan su contraseña en No.

1. Observe que el panel de navegación de Restablecimiento de contraseña también incluye opciones para ver registros de auditorías y Uso e información.

1. Cierre la ventana de restablecimiento de contraseña con la **X** de la esquina superior derecha de la ventana. Esto lo devuelve al Centro de administración de Microsoft Entra.

1. Mantenga abierta la ventana de Microsoft Entra.

### Tarea 2

En esta tarea, como administrador, agregará el usuario que creó en el ejercicio de laboratorio anterior al grupo de seguridad de SSPR.

1. Abra la pestaña del explorador de la página principal del Centro de administración de Microsoft Entra, **[entra.microsoft.com](https://entra.microsoft.com)** . Si es necesario, expanda **Identidad**.

1. En el panel de navegación izquierdo, en "Identidad", expanda **Grupos** y, a continuación, seleccione **Todos los grupos**.

1. Se mostrará una lista de grupos existentes. En el campo Buscar grupos, escriba **SSPR**, a continuación, en los resultados de la búsqueda, seleccione **SSPRSecurityGroupUsers**.  Le llevará a la configuración de este grupo.

1. En el panel de navegación izquierdo, seleccione **Miembros**.

1. En la parte superior de la página, seleccione **+ Agregar miembros**.  

1. En el cuadro de búsqueda, escriba **Sara Perez**.  Cuando el usuario **Sara Perez** aparezca debajo del cuadro de búsqueda, selecciónelo y pulse **Seleccionar** en la parte inferior de la página.  Se le dirigirá de vuelta a la página de miembros.  Seleccione **Actualizar** en la parte superior de la página. Ahora debería ver a Sara Perez como miembro en el grupo de seguridad de SSPR.

1. Para cerrar sesión de todas las pestañas del navegador, haga clic en el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla. A continuación, cierre todas las ventanas del navegador.

### Tarea 3

En esta tarea, aprenderá el proceso de registro para el autoservicio de restablecimiento de contraseña como el usuario Sara Perez.  Esta tarea requiere que tenga acceso a un dispositivo móvil donde pueda recibir mensajes de texto o una cuenta de correo electrónico personal a la que pueda acceder

1. Abra Microsoft Edge y, en la barra de direcciones, introduzca **https://login.microsoft.com** .

1. Inicie sesión como Sara Perez.

1. Aparecerá una ventana emergente que indica que se requiere más información.  Esto se debe a que, como miembro del grupo SSPRSecurityGroupUsers, la configuración requiere que sus miembros se registren cuando inician sesión.  Haga clic en el botón **Siguiente**.  Nota:  Una alternativa a que los usuarios hagan el registro por sí mismos es que los administradores configuren directamente los métodos de autenticación cuando agregan a un usuario. Esto requiere que los administradores conozcan y establezcan los números de teléfono y las direcciones de correo electrónico que utilizan los usuarios para realizar el autoservicio de restablecimiento de contraseña, y para restablecer la contraseña de un usuario.

1. Se abrirá la página "Garantizar la seguridad de la cuenta".  La ventana que aparece es para el método de autenticación por teléfono, si no tiene un dispositivo móvil con usted que pueda recibir mensajes de texto, pase al siguiente paso.  Se le solicita que escriba un número de teléfono. Asegúrese de que la opción **Enviarme un código por mensaje de texto** esté activada.   Escriba un número de teléfono donde pueda recibir un código de texto y seleccione el **botón Siguiente**.  Se abrirá una nueva ventana que indica que se ha enviado un código al teléfono que escribió.  Escriba el código que recibió y seleccione **Siguiente**. Se abrirá una ventana de confirmación que muestra su método de inicio de sesión predeterminado.  Seleccione **Listo**.  
    1. También puede configurar un método diferente como se muestra en la parte inferior izquierda de la ventana.  Si elige configurar un método diferente, seleccione **Quiero configurar otro método**, aparecerá una ventana emergente que le pregunta ¿Qué método quiere usar?  En el menú desplegable, seleccione su método preferido, **Correo electrónico**, y luego seleccione el botón **Confirmar**.  Escriba la dirección de correo electrónico que desea utilizar y seleccione **Siguiente**.  Se abrirá una nueva ventana que indica que se ha enviado un código al correo electrónico que escribió.  Acceda al correo electrónico para conseguir el código.  Escriba el código que recibió y seleccione **Siguiente**. Se abrirá una ventana de confirmación que muestra su método de inicio de sesión predeterminado.  Seleccione **Listo**.

1. Ahora puede completar el inicio de sesión. Si su tiempo de inicio de sesión expira, simplemente vuelva a escribir la contraseña.

1. Para cerrar sesión de todas las pestañas del navegador, haga clic en el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla. A continuación, cierre todas las ventanas del navegador.

### Tarea 4 (opcional)

En esta tarea, recorrerá el proceso de restablecimiento de contraseña como Sara Perez.

1. Abrir Microsoft Edge.

1. En la barra de direcciones, escriba **https://login.microsoftonline.com** .

1. Inicie sesión como Sara Perez, escriba el correo electrónico **sara@WWLxZZZZ.onmicrosoft.com** (donde ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de hospedaje de laboratorio) y seleccione el botón **Siguiente**. Quizás se abra una ventana para elegir una cuenta, si es así, seleccione la cuenta de Sara Perez.

1. En la ventana Escribir contraseña, seleccione **He olvidado mi contraseña**.

1. Se abrirá la ventana Volver a su cuenta.   Compruebe que el correo electrónico de Sara Perez, sara@WWLxZZZZ.onmicrosoft.com, se muestre en el cuadro de correo electrónico o nombre de usuario.  Si no es así, escríbalo.  

1. En el cuadro vacío, escriba los caracteres que aparecen en la imagen o las palabras del audio. Cuando los haya escrito, seleccione **Siguiente**.

1. La pantalla muestra Volver a su cuenta y Verificación, paso 1 > elegir una contraseña nueva. Deje el valor predeterminado **Enviar mensaje de texto a mi teléfono móvil.**  Se le solicitará que escriba su número de teléfono.  Cuando lo haya escrito, seleccione el **botón Texto**.  Si durante el registro seleccionó el correo electrónico, la ventana Volver a su cuenta indicará que recibirá un correo electrónico con un código de verificación en su dirección de correo electrónico alternativa.  Seleccione **Correo electrónico**.

1. Escriba el código de verificación y presione **Siguiente**.

1. En la siguiente pantalla se le solicitará que escriba y confirme su contraseña nueva.  Escríbalos y seleccione el botón **Finalizar**.

1. Verá un mensaje en la pantalla que indica que la contraseña se ha restablecido.  Seleccione **haga clic aquí** para iniciar sesión con la contraseña nueva.

1. En el cuadro de información sobre la cuenta, seleccione **sara@WWLxZZZZZZ.onmicrosoft.com** , escriba su contraseña nueva y, luego, seleccione el botón **Iniciar sesión**.  Si se le pregunta si desea mantener la sesión iniciada, seleccione **No**.

1. Ahora debería estar en el Portal de Office.

1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador

### Tarea 5 (opcional)

En esta tarea, como administrador, verá brevemente los registros de auditoría, así como los datos de uso e información asociados al restablecimiento de contraseñas

1. Abrir Microsoft Edge.

1. En la barra de direcciones, escriba **https://entra.microsoft.com** e inicie sesión con las credenciales de administrador de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).

1. Está en el Centro de administración de Microsoft Entra.  En el panel de navegación izquierdo, expanda la opción **Protección** y seleccione **Restablecimiento de contraseña**.

1. En el panel de navegación izquierdo, seleccione **Registros de auditoría**.  Observe la información y los filtros disponibles.  Observe también que se pueden descargar los registros.  

1. Seleccione **Descargar**.  Observe que al descargar puede elegir los formatos de archivo CSV o JSON.  Cierre la ventana con la **X** de la esquina superior derecha de la pantalla.

1. En el panel de navegación izquierdo, seleccione **Uso e información**.

1. Observe la información disponible sobre el registro.  Observe que estos datos pueden tardar en actualizarse, incluso después actualizar, por lo que puede que aún no se reflejen los datos de registro o uso de la tarea anterior.

1. En la parte superior de la página, seleccione **Uso** para ver el número de autoservicios de restablecimiento de contraseña y desbloqueos de cuentas por método.  Observe que estos datos pueden tardar en actualizarse, incluso después actualizar, por lo que puede que aún no se reflejen los datos de uso de la tarea anterior.

1. Cierre las pestañas abiertas del explorador.

### Revisar

En este laboratorio, como administrador, aprendió el proceso para habilitar el autoservicio de restablecimiento de contraseña. Cuando habilitó el SSPR, asumió el rol de un usuario y pasó por el proceso de registrarse en el SSPR y también de restablecer su contraseña.  Por último, como administrador, aprendió dónde acceder a los registros de auditoría y a los datos de uso e información del SSPR.
