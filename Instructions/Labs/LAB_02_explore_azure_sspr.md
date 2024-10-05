---
lab:
  title: "Autoservicio de restablecimiento de contraseña de Microsoft\_Entra"
  module: Describe the authentication capabilities of Microsoft Entra ID
---

<!---
---
Laboratorio: Título: "Explorar la Autenticación de Azure AD con el autoservicio de restablecimiento de contraseña" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Describir las capacidades de Azure Active Directory (Azure AD), parte de Microsoft Entra; Módulo 2: Describir las capacidades de autenticación de Azure AD; Unidad 4: Describir el autoservicio de restablecimiento de contraseña"
---
--->

# Laboratorio: Autoservicio de restablecimiento de contraseña de Microsoft Entra

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Entra
- Módulo: Descripción de las funcionalidades de autenticación de Microsoft Entra ID
- Unidad: Descripción del autoservicio de restablecimiento de contraseña

## Escenario del laboratorio

En este laboratorio, como administrador, verá el proceso de agregar un usuario al grupo de seguridad SSPR, que ya está configurado en el inquilino de Microsoft 365. Cuando el SSPR esté habilitado, asumirá el rol de un usuario y pasará por el proceso de registrarse en el SSPR y también de restablecer su contraseña.  Por último, como administrador, podrá ver los registros de auditoría y los datos de uso e información de uso para SSPR.

**Tiempo estimado**: 30 minutos

### Tarea 1

En esta tarea, como administrador, verá algunas de las opciones de configuración disponibles para SSPR.

1. Abra el explorador Microsoft Edge. En la barra de direcciones, escriba **https://entra.microsoft.com** e inicie sesión con las credenciales de administrador de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es su Id. de inquilino único proporcionado por el ALH) y seleccione **Siguiente**.
    1. Escribe la contraseña de administrador que debería haberte proporcionado tu proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Si has iniciado sesión anteriormente como administrador, se te pedirá que completes una autenticación secundaria, como parte de MFA. Si no has iniciado sesión anteriormente como administrador, se te pedirá que completes el proceso de registro de MFA. Sigue las indicaciones en la pantalla para configurar MFA.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En el panel de navegación izquierdo, expanda la opción **Protección** y seleccione **Restablecimiento de contraseña**.  

1. Se mostrarán las propiedades del autoservicio de restablecimiento de contraseña. Seleccione el icono de información situado junto a donde dice **Autoservicio de restablecimiento de contraseña habilitado** para ver la descripción. Asegúrese de que **Seleccionado** está resaltado en azul. Coloque el cursor sobre el icono de información junto a **Seleccionar grupo** y observe lo que dice: "Define el grupo de usuarios a los que se permite restablecer sus propias contraseñas". Debe incluir usuarios en el grupo, no puede seleccionar usuarios individualmente. Fíjese que ya aparece un grupo: SSPRSecurityGroupUsers (este grupo estaba preconfigurado como parte del inquilino de Microsoft 365). Por último, fíjese en el cuadro de información azul: "Esta configuración solo se aplica a los usuarios finales de su organización. Los administradores siempre están habilitados para el autoservicio de restablecimiento de contraseña y deben utilizar dos métodos de autenticación para restablecer su contraseña".

1. En el panel de navegación izquierdo de Restablecimiento de contraseña, seleccione **Métodos de autenticación**.

1. En Número de métodos requeridos para el restablecimiento, seleccione **1**. Observe el cuadro de información de la pantalla.

1. Fíjese en los distintos métodos disponibles para los usuarios.  Las opciones **Correo electrónico** y **Teléfono móvil** ya deberían estar marcadas; si no es así, selecciónalas.

1. En el panel de navegación izquierdo de Restablecimiento de contraseña, seleccione **Registro**.  

1. Asegúrese de que la configuración Exigir a los usuarios que se registren al iniciar sesión sea **Sí**.  Deja el Número de días antes de que se solicite a los usuarios que vuelvan a confirmar su información de autenticación, en el valor predeterminado **180**.   Fíjese en el cuadro de información de la página.

1. En el panel de navegación izquierdo de Restablecimiento de contraseña, seleccione **Notificaciones**.  

1. Asegúrese de que la configuración Notificar a los usuarios sobre los restablecimientos de contraseña sea **Sí**.  Deja la configuración de Notificar a todos los administradores cuando otros administradores restablezcan su contraseña en **No**.

1. Observe cómo el panel de navegación Restablecimiento de contraseña también incluye opciones para ver los registros de auditoría y Usage & insights (Uso e información).

1. Cierre la ventana de restablecimiento de contraseña, para hacerlo, seleccione la **X** de la esquina superior derecha de la ventana. Esto le devolverá al Centro de administración de Microsoft Entra.

1. Mantenga la ventana de Microsoft Entra abierta.

### Tarea 2

En esta tarea, como administrador, agregará el usuario que creó en el ejercicio de laboratorio anterior al grupo de seguridad SSPR.

1. Abra la pestaña del explorador de la página principal del centro de Administración de Microsoft Entra **[ entra.microsoft.com](https://entra.microsoft.com)**. Si es necesario, expanda **Identidad**.

1. En el panel de navegación izquierdo, bajo Identidad, expanda **Grupos** y luego seleccione **Todos los grupos**.

1. Se mostrará una lista de grupos existentes. En el campo Buscar grupos, escriba **SSPR** y, a continuación, en los resultados de la búsqueda, seleccione **SSPRSecurityGroupUsers**.  Le llevará a la opción para configurar este grupo.

1. En el panel de navegación izquierdo, seleccione **Miembros**.

1. En la parte superior de la página, seleccione **+ Agregar miembros**.  

1. En el cuadro de búsqueda, escriba **Sara Perez**.  Una vez que el usuario **Sara Perez**, aparezca debajo del cuadro de búsqueda, selecciónelo y, a continuación, presione **Seleccionar** en la parte inferior de la página.  Volverá a la página de miembros.  Seleccione **Actualizar** en la parte superior de la página. Ahora debería ver Sara Perez como miembro en el grupo de seguridad SSPR.

1. Cierre sesión en todas las pestañas del explorador, para hacerlo, haga clic en el icono de usuario situado junto a la dirección de correo electrónico de la esquina superior derecha de la pantalla. A continuación, cierre todas las ventanas del explorador.

### Tarea 3

En esta tarea, como usuario Sara Perez, realizará el registro para el autoservicio de restablecimiento de contraseña.

1. Abra Microsoft Edge y, en la barra de direcciones, escriba **https://login.microsoft.com**.

1. Inicie sesión como Sara Perez. El proceso de inicio de sesión puede requerir MFA.

1. Aparecerá un elemento emergente que indica que se requiere más información.  Esto se debe a que, como miembro del grupo SSPRSecurityGroupUsers, la configuración requiere que sus miembros se registren cuando inician sesión.  Haga clic en el botón **Siguiente**.  Nota: Una alternativa a hacer que los usuarios realicen el registro es que los administradores configuren directamente los métodos de autenticación cuando agregan un usuario. Esto requiere que los administradores conozcan y establezcan los números de teléfono y las direcciones de correo electrónico que utilizan los usuarios para realizar el autoservicio de restablecimiento de contraseña, y para restablecer la contraseña de un usuario.

1. Se abre la página "Mantenga su cuenta segura".  La ventana que aparece y los pasos que siguen son para el método de aplicación Microsoft Authenticator. Si, en su lugar, deseas usar el correo electrónico, selecciona **Quiero configurar un método diferente** y sigue los pasos.
    1. Si ya has instalado la aplicación Microsoft Authenticator en tu dispositivo móvil, selecciona **Siguiente**. De lo contrario, selecciona **Descargar ahora** y sigue los pasos.
    1. Comenzarás a configurar tu cuenta.  Seleccione **Siguiente**.
    1. Con la aplicación Microsoft Authenticator en el dispositivo móvil, selecciona **+** para agregar una cuenta y, después, **Cuenta profesional o educativa**.
    1. Selecciona la opción para **Escanear el código QR** y luego usa tu dispositivo móvil para escanear el código QR en la pantalla del equipo.
    1. Sigue los pasos del PC y dispositivo móvil y, después, selecciona **Siguiente**.
    1. Una vez que hayas configurado la información de seguridad, verás una ventana de operación correcta.  Seleccione **Listo**.

1. Ahora puede completar el inicio de sesión. Si el tiempo de inicio de sesión expira, simplemente vuelva a escribir la contraseña.

1. Cierre sesión en todas las pestañas del explorador, para hacerlo, haga clic en el icono de usuario situado junto a la dirección de correo electrónico de la esquina superior derecha de la pantalla. A continuación, cierre todas las ventanas del explorador.

### Tarea 4 (opcional)

En esta tarea, como usuario Sara Perez, realizará el proceso de restablecer la contraseña

1. Abrir Microsoft Edge.

1. En la barra de direcciones, escriba **https://login.microsoft.com**.

1. Inicie sesión como Sara Perez, para hacerlo, escriba su correo electrónico **sara@WWLxZZZZ.onmicrosoft.com** (donde ZZZZZZ es su identificador de inquilino único que proporciona su proveedor de hospedaje de laboratorio) y seleccione el botón **Siguiente**. Como alternativa, quizá vea la ventana Elegir una cuenta abierta, si es así, seleccione la cuenta de Sara Perez.

1. En la ventana Escribir contraseña, seleccione **Olvidé mi contraseña**.

1. Se abrirá la ventana Volver a la cuenta.   Compruebe que el correo electrónico de Sara Perez, sara@WWLxZZZZ.onmicrosoft.com, se muestra en el cuadro de correo electrónico o nombre de usuario.  Si no es así, escríbalo.  

1. En el cuadro vacío, escriba los caracteres que se muestran en la imagen o las palabras del audio. Cuando los haya escrito, seleccione **Siguiente**.

1. En la pantalla se muestra Volver a la cuenta y también Paso 1 de la verificación > elija una nueva contraseña. Selecciona la opción **Aprobar una notificación en la aplicación de autenticador** y, después, selecciona **Enviar notificación**.

1. Anota el número en el PC y sigue las instrucciones para aprobar el inicio de sesión con la aplicación Microsoft Authenticator en el dispositivo móvil.

1. En la siguiente pantalla se le solicitará que escriba y confirme su contraseña nueva.  Escríbala y seleccione el botón **Finalizar**.

1. Verá un mensaje en la pantalla que indica que la contraseña se ha restablecido.  Seleccione **haga clic aquí** para iniciar sesión con la nueva contraseña.

1. En el cuadro de información sobre la cuenta, seleccione **sara@WWLxZZZZZZ.onmicrosoft.com**, escriba su contraseña nueva y, luego, seleccione el botón **Iniciar sesión**.  Si se le pregunta si desea mantener la sesión iniciada, seleccione **No**.

1. Ahora deberías iniciar sesión en la cuenta Microsoft de Sara.

1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador.

### Tarea 5 (opcional)

En esta tarea, como administrador, verá brevemente los registros de auditoría, así como los datos de uso e información asociados al restablecimiento de contraseñas

1. Abrir Microsoft Edge.

1. En la barra de direcciones, escriba **https://entra.microsoft.com** e inicie sesión con las credenciales de administrador de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).

1. Está en el Centro de administración de Microsoft Entra.  En el panel de navegación izquierdo, expanda la opción **Protección** y seleccione **Restablecimiento de contraseña**.

1. En el panel de navegación izquierdo, seleccione **Registro de auditoría**.  Observe la información y los filtros disponibles.  También puede descargar los registros.  

1. Seleccione **Descargar**.  Tenga en cuenta que puede dar formato a la descarga como CSV o JSON.  Cierre la ventana, para ello, seleccione la **X** de la esquina superior derecha de la ventana.

1. En el panel de navegación izquierdo, seleccione **Uso e información**.

1. Observe la información disponible que pertenece Registro.  Tenga en cuenta que puede llevar algún tiempo actualizar estos datos, incluso después de realizar una actualización, por lo que es posible que aún no se reflejen los datos de registro o de uso de la tarea anterior.

1. En la parte superior de la página, seleccione **Uso** para ver el número de restablecimientos de contraseña de autoservicio y desbloqueos de cuenta por método.  Tenga en cuenta que puede llevar algún tiempo actualizar estos datos, incluso después de realizar una actualización, por lo que es posible que aún no se reflejen los datos de uso de la tarea anterior.

1. Cierre las pestañas abiertas del explorador.

### Revisar

En este laboratorio, como administrador, realizó el proceso de habilitación del autoservicio de restablecimiento de contraseña. Cuando habilitó el SSPR, asumió el rol de un usuario y pasó por el proceso de registrarse en el SSPR y también de restablecer su contraseña.  Por último, como administrador, aprendió dónde puede acceder a los registros de auditoría y a los datos de uso e información para SSPR.
