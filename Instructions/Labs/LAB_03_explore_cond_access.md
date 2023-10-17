<!---
---
Laboratorio: Ruta de aprendizaje: "Descripción de las funcionalidades de Microsoft Entra" Módulo: "Descripción de las funcionalidades de administración de acceso de Microsoft Entra ID" Unidad: "Descripción del acceso condicional"
---
--->

# Laboratorio: Acceso condicional de Microsoft Entra

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra
- Módulo: Descripción de las capacidades de administración de acceso de Microsoft Entra ID
- Unidad: Descripción del acceso condicional

## Escenario del laboratorio

En este laboratorio explorará el acceso condicional MFA, desde la perspectiva de un administrador y un usuario.  Como administrador, creará una directiva que requerirá que un usuario pase por la autenticación multifactor cuando acceda a una aplicación de administración de Microsoft Azure basada en la nube.  Desde la perspectiva del usuario, verá el impacto de la directiva de acceso condicional, incluido el proceso para registrarse en MFA.

**Tiempo estimado**: 30 minutos

### Tarea 1

En esta tarea, como administrador, restablecerá la contraseña del usuario Debra Berger.  Este paso es necesario para poder iniciar sesión como el usuario en las siguientes tareas.

1. Abrir Microsoft Edge.  En la barra de direcciones, escriba **https://entra.microsoft.com** e inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En el panel de navegación izquierdo, expanda **Identidad**, **Usuarios** y, a continuación, seleccione **Todos los usuarios**.

1. Seleccione **Debra Berger** de la lista de usuarios.

1. Seleccione **Restablecer contraseña** en la parte superior de la página. Como no ha iniciado sesión previamente como Debra Berger, no conoce su contraseña y deberá restablecerla.

1. Cuando se abra la ventana de restablecimiento de contraseña, seleccione **Restablecer contraseña**.  IMPORTANTE: Anote la nueva contraseña, la necesitará en una tarea posterior para poder acceder como usuario.

1. Cierre la ventana de restablecimiento de contraseña seleccionando la **X** en la esquina superior derecha de la página y, a continuación, cierre la ventana Debra Berger seleccionando la **X** en la esquina superior derecha de la página.

1. En el panel de navegación izquierdo, seleccione **Inicio** para volver al Centro de administración de Microsoft Entra.

1. Mantenga esta ventana abierta.

### Tarea 2

En esta tarea, aprenderá el proceso de creación de una directiva de acceso condicional en Azure AD.

1. Abra la pestaña del explorador en la página principal del Centro de administración de Microsoft Entra.   Si ya había cerrado la pestaña del explorador, abra Microsoft Edge, escriba **https://entra.microsoft.com** en la barra de direcciones y, luego, inicie sesión con las credenciales de administrador de Microsoft 365 que proporcionó ALH.

1. En el panel de navegación izquierdo, expanda **Protección** y, a continuación, seleccione **Acceso condicional**.

1. Se muestra la página de información general sobre el acceso condicional.  Aquí verá iconos que muestran el resumen de la directiva y las alertas generales.  En el panel de navegación izquierdo, seleccione **Directivas**.

1. En el panel de navegación izquierdo, seleccione **Directivas**. Cualquier directiva de acceso condicional existente se mostrará en esta página. Seleccione **+ Nueva directiva**.

1. En el campo Nombre, escriba **Directiva de prueba para la MFA**.

1. En Usuarios, seleccione **0 usuarios y grupos seleccionados**.

1. Ahora verá la opción para incluir o excluir usuarios y grupos.  Asegúrese de que **Incluir** esté seleccionado (subrayado).

1. Seleccione la opción de **Seleccionar usuarios y grupos** y seleccione **Usuarios y grupos**.  Se abrirá la ventana Seleccionar usuarios y grupos.  

1. En la barra de búsqueda, escriba **Debra**.  Seleccione **Debra Berger** bajo la barra de búsqueda y luego pulse el botón **Seleccionar** en la parte inferior de la página.  Nota: Una práctica común es asignar la directiva a los usuarios de un grupo.  Para este laboratorio, asignaremos la directiva a un usuario específico.

1. En Recursos de destino, seleccione **No hay recursos de destino seleccionados**.

1. En el campo debajo de **Seleccione a qué se aplica esta directiva**, seleccione la flecha abajo y anote las opciones disponibles.  Mantenga la configuración predeterminada, **Aplicaciones en la nube**.  Asegúrese de que la pestaña **Incluir** está subrayada.  Seleccione **Seleccionar aplicaciones**, luego debajo de **Seleccionar**, seleccione **Ninguno**.  Se abrirá la ventana Seleccionar aplicaciones en la nube.

1. En la barra de búsqueda, escriba **Azure**.  En los resultados de la búsqueda que aparecen bajo el cuadro de búsqueda, seleccione **Administración de Microsoft Azure** y luego pulse **Seleccionar** en la parte inferior de la página.  Observe la advertencia.  

1. En Condiciones, seleccione **0 condiciones seleccionadas**.  Observe las diferentes opciones que puede configurar.  A través de la directiva, puede controlar el acceso de los usuarios en función de señales de condiciones como: riesgo del usuario, riesgo de inicio de sesión, plataforma del dispositivo, ubicación, aplicaciones cliente o filtro para dispositivos.  Explore estas opciones configurables, pero no establezca ninguna condición.

1. Ahora se establecerán los controles de acceso.  En Conceder, seleccione **0 controles seleccionados**.

1. Se abrirá la ventana Conceder.  Asegúrese de que **Conceder acceso** esté seleccionado y luego seleccione **Requerir autenticación multifactor**. Desplácese hacia abajo un poco en la ventana derecha y, en la sección para varios controles, deje el valor predeterminado **Requerir todos los controles seleccionados**.  Pulse **Seleccionar** en la parte inferior de la página.

1. En la parte inferior de la página, en Habilitar directiva, seleccione **Activado** y luego seleccione **Crear**.

1. En el panel de navegación izquierdo, seleccione **Directivas**. La directiva MFA Pilot debería aparecer en la lista de directivas de acceso condicional (si es necesario, seleccione el **icono Actualizar** en la barra de comandos de la parte superior de la página).

1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador

### Tarea 3

En esta tarea verá el impacto de la directiva de acceso condicional, desde la perspectiva del usuario, Debra Berger. En primer lugar, iniciará sesión en una aplicación que no esté incluida en la directiva de acceso condicional (el portal de Microsoft 365 en https://login.microsoftonline.com) ).  Luego repetirá el proceso en una aplicación que esté incluida en la directiva de acceso condicional (Azure Portal en https://portal.azure.com) ).  Recuerde que la directiva requiere que el usuario pase por MFA cuando accede a una aplicación de la administración de Microsoft Azure.  Para utilizar la MFA, el usuario debe registrar primero el método de autenticación que se utilizará para la MFA, por ejemplo, un código enviado a un dispositivo móvil o una aplicación de autenticación.

1. Abrir Microsoft Edge.  En la barra de direcciones, escriba **https://login.microsoftonline.com** .
    1. Inicie sesión como **DebraB@WWLxZZZZZZ.onmicrosoft.com** , (donde ZZZZZZ es el identificador de inquilino único proporcionado por el proveedor de hospedaje del laboratorio) y después seleccione **Siguiente**.
    1. Escriba la contraseña que anotó en la tarea anterior. Haga clic en **Iniciar sesión**.
    1. Dado que, como administrador, restableció la contraseña, esta es temporal y, por tanto, deberá actualizarla (esto no es parte de la directiva de MFA). Escriba la contraseña actual y, a continuación, escriba una nueva contraseña y confirme la nueva contraseña.  Anote la nueva contraseña, ya que la necesitará para completar la tarea.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.  Debería iniciar sesión correctamente en su cuenta de Microsoft 365. El MFA no era necesaria para esta solicitud, ya que no forma parte de la directiva.

1. Ahora intentará iniciar sesión en una aplicación que cumpla con los criterios de la MFA. Abra una nueva pestaña del explorador y escriba **https://portal.azure.com** .

1. Verá una ventana que indica, Se necesita más información.  Seleccione **Next** (Siguiente).  Tenga en cuenta que esto iniciará el proceso de registro de la MFA, ya que es la primera vez que accede a la aplicación en la nube que se identificó en la directiva de acceso condicional.  Este proceso de registro solo es necesario una vez.   En lugar de que el usuario pase por el proceso de registro, una alternativa es que el administrador configure el método de autenticación a utilizar.

1. En la ventana Garantizar la seguridad de la cuenta, tiene la opción de seleccionar el método a utilizar para la MFA.  Una opción es Microsoft Authenticator. Para este laboratorio, elegirá un método diferente.  Seleccione **Quiero configurar otro método**.  En la ventana emergente Elegir otro método, seleccione la **flecha desplegable** y seleccione **Teléfono**, luego seleccione **Confirmar**.

1. Se abrirá una nueva ventana, asegúrese de que su país o región está seleccionado, luego escriba el número de teléfono móvil que desea utilizar.  Asegúrese de que **Enviarme un código por mensaje de texto** esté seleccionado y luego presione **Siguiente**.  Recibirá un mensaje de texto en el teléfono con un código que deberá escribir donde dice escribir código.  Escriba el código que recibió y pulse **Siguiente**.  Una vez confirmado, la pantalla mostrará: "SMS verificado. El teléfono se ha registrado correctamente".  Seleccione **Next** (Siguiente). Después, seleccione **Listo**.  esto completará el único proceso de registro.

1. Ahora debería poder acceder a Azure Portal.  Azure Portal es una aplicación de administración de Microsoft Azure y, por lo tanto, requiere una autenticación multifactor, según la directiva de acceso condicional que se creó.  
    1. Si recibe un mensaje que indique que su inicio de sesión finalizó. Escriba la contraseña y seleccione **Iniciar sesión**.
    1. Verá una ventana que requiere que verifique su identidad.  Seleccione donde dice Text =X XXXXXXX para recibir un código en el teléfono móvil, escriba el código y seleccione **Verificar**.
    1. Si se le pregunta si desea mantener la sesión iniciada, seleccione **No**.

1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione Cerrar sesión. A continuación, cierre todas las ventanas del navegador.

### Revisar

En este laboratorio, aprendió el proceso de configuración de una directiva de acceso condicional que requiere que los usuarios pasen por la MFA cuando acceden a la aplicación en la nube de la administración de Microsoft Azure.  Luego, como usuario, aprendió el proceso de registro para la MFA y vio el impacto de la directiva de acceso condicional que necesitaba que usara la MFA al acceder a Azure Portal.
