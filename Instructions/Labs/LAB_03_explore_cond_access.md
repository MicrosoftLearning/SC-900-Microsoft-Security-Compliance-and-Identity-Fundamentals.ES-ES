---
lab:
  title: "Acceso condicional de Microsoft\_Entra"
  module: Describe the access management capabilities of Microsoft Entra
---

# Laboratorio: Acceso condicional de Microsoft Entra

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra
- Módulo: Descripción de las funcionalidades de administración de acceso de Microsoft Entra
- Unidad: Descripción del acceso condicional

## Escenario del laboratorio

En este laboratorio explorará el acceso condicional MFA, desde la perspectiva de un administrador y un usuario.  Como administrador, creará una directiva que requerirá que un usuario pase por la autenticación multifactor cuando acceda a cualquier portal de administración de Microsoft.  Desde la perspectiva del usuario, verá el impacto de la directiva de acceso condicional, incluido el proceso para registrarse en MFA.

**Tiempo estimado**: 30 minutos

### Tarea 1

En esta tarea, como administrador, restablecerá la contraseña del usuario Debra Berger.  Este paso es necesario para que pueda iniciar sesión inicialmente como el usuario en tareas posteriores.

1. Abrir Microsoft Edge.  En la barra de direcciones, escriba **https://entra.microsoft.com** e inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Si has iniciado sesión anteriormente como administrador, es posible que se te pida que completes una autenticación secundaria, como parte de MFA. Si no has iniciado sesión anteriormente como administrador, es posible que se te pida que completes el proceso de registro de MFA. Sigue las indicaciones en la pantalla para configurar MFA.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En el panel de navegación izquierdo, expanda **Identidad** y **Users**, luego seleccione **Todos los usuarios**.

1. Seleccione **Debra Berger** de la lista de usuarios.

1. En la parte superior de la página, seleccione **Restablecer contraseña**. Como no ha iniciado sesión previamente como Debra Berger, no conoce su contraseña y deberá restablecerla.

1. Cuando se abra la página de restablecimiento de contraseña, seleccione **Restablecer contraseña**.  IMPORTANTE: Anote la nueva contraseña, la necesitará en una tarea posterior para poder acceder como usuario.

1. Cierre la ventana de restablecimiento de contraseña seleccionando la **X** en la esquina superior derecha de la página y, a continuación, cierre la ventana Debra Berger seleccionando la **X** en la esquina superior derecha de la página.

1. En el panel de navegación izquierdo, seleccione **Inicio** para volver al Centro de administración Microsoft Entra.

1. Mantenga esta ventana abierta.

### Tarea 2

En esta tarea, recorrerá el proceso de creación de una directiva de acceso condicional en Microsoft Entra ID.

1. Abra una nueva pestaña del explorador con la página principal del Centro de administración de Microsoft Entra.   Si ya había cerrado esta pestaña del explorador, abra Microsoft Edge, escriba **https://entra.microsoft.com** en la barra de direcciones y, luego, inicie sesión con las credenciales de administrador de Microsoft 365.

1. En el panel de navegación izquierdo, expanda **Protección** y, a continuación, seleccione **Acceso condicional**.

1. Se muestra la página de información general sobre el acceso condicional.  Aquí verá iconos que muestran el resumen de la directiva y las alertas generales.  En el panel de navegación izquierdo, seleccione **Directivas**.

1. En el panel de navegación izquierdo, seleccione **Directivas**. Aquí se enumeran las directivas de acceso condicional existentes. Seleccione **+ Nueva directiva**.

1. En el campo Nombre, escribe **Bloquear portales de administración**.

1. En Usuarios, seleccione **0 usuarios y grupos seleccionados**.

1. Ahora verá la opción para incluir o excluir usuarios y grupos.  Asegúrese de que **Incluir** está seleccionado (subrayado).

1. Seleccione la opción **Seleccionar usuarios y grupos** y seleccione **Usuarios y grupos**.  Se abre la ventana para seleccionar usuarios o grupos.  

1. En la barra de búsqueda, escriba **Debra**.  Seleccione **Debra Berger** debajo de la barra de búsqueda y presione el botón **Seleccionar** en la parte inferior de la página.  Tenga en cuenta que una práctica habitual es asignar la directiva a los usuarios de un grupo.  Para este laboratorio, asignaremos la directiva a un usuario específico.

1. En Recursos de destino, seleccione **No se ha seleccionado ningún recurso de destino**.

1. En el campo debajo de donde dice**Seleccionar lo que se aplica a esta directiva**, seleccione la flecha hacia abajo y anote las opciones disponibles.  Mantenga la configuración predeterminada, **Aplicaciones en la nube**.  Asegúrese de que la pestaña **Incluir** está subrayada.  Seleccione **Seleccionar aplicaciones** y, después, debajo de donde dice **Seleccionar**, seleccione **Ninguna**.  Se abre la ventana para seleccionar aplicaciones en la nube.

1. Selecciona **Portales de administración de Microsoft** y después haz clic en **Seleccionar** en la parte inferior de la página.  Observe la advertencia.  

1. En Red, selecciona **Cualquier red o ubicación**.  Revisa las opciones, pero no selecciones ninguna opción.

1. En Condiciones, seleccione **0 condiciones seleccionadas**.  Observe las distintas opciones que puede configurar.  A través de la directiva, puede controlar el acceso de los usuarios en función de las señales de las condiciones, incluidas: riesgo de usuario, riesgo de inicio de sesión, plataforma de dispositivo, ubicación, aplicaciones cliente o filtro para dispositivos.  Explore estas opciones configurables, pero no establezca ninguna condición.

1. Ahora se establecerán los controles de acceso.  En Conceder, seleccione **0 controles seleccionados**.

1. Se abre la ventana Conceder.  Seleccione **Block access** (Bloquear acceso). Pulse **Seleccionar** al final de la página.

1. En la parte inferior de la página, en Habilitar directiva, seleccione **Activado** y luego seleccione **Crear**.

1. En el panel de navegación, seleccione **Directivas**. La directiva piloto de la MFA debe aparecer en la lista de directivas de acceso condicional (si es necesario, seleccione el **icono Actualizar** en la barra de comandos de la parte superior de la página).

1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador.

### Tarea 3

En esta tarea verá el impacto de la directiva de acceso condicional, desde la perspectiva del usuario, Debra Berger. En primer lugar, iniciará sesión en una aplicación que no esté incluida en la directiva de acceso condicional (el portal de Microsoft 365 en https://login.microsoftonline.com)).  Luego repetirá el proceso en una aplicación que esté incluida en la directiva de acceso condicional (Azure Portal en https://portal.azure.com)).  Recuerda que la directiva bloquea el accesso a cualquiera de los portales de administración de Microsoft, incluido Azure Portal.  NOTA: por motivos de seguridad, todas las cuentas de usuario que acceden a cualquier portal deben usar MFA.  El requisito de MFA es independiente de este ejercicio de laboratorio.

1. Abre Microsoft Edge.  En la barra de direcciones, escriba **https://login.microsoftonline.com**.
    1. Inicie sesión como **DebraB@WWLxZZZZZZ.onmicrosoft.com**, (donde ZZZZZZ es el identificador de inquilino único proporcionado por el proveedor de hospedaje del laboratorio) y después seleccione **Siguiente**.
    1. Escriba la contraseña que anotó en la tarea anterior. Seleccione **Iniciar sesión**.
    1. Dado que, como administrador, restableciste la contraseña, esta es temporal y, por tanto, deberás actualizarla. Escriba la contraseña actual y, a continuación, escriba una nueva contraseña y confírmela.  Tome nota de la nueva contraseña, ya que la necesitará para completar la tarea.
    1. Dado que esta es la primera vez que inicias sesión como Debra Berger, es posible que se te pida configurar MFA. Sigue las indicaciones en la pantalla para configurar MFA.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.  Debería haber iniciado sesión correctamente en su cuenta de Microsoft 365.

1. Ahora intentarás iniciar sesión en una aplicación que cumpla con los criterios de la directiva de acceso condicional. Abre una nueva pestaña del explorador y escribe **https://portal.azure.com**, que es el portal de administración de Azure.  Aparece una ventana emergente que indica "No tienes acceso a esto".  Este es el resultado de la directiva de acceso condicional que te bloquea el acceso a todos los portales de administración de Microsoft.

1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione Cerrar sesión. A continuación, cierre todas las ventanas del navegador.

### Revisar

En este laboratorio, aprendiste el proceso de configuración de una directiva de acceso condicional que bloquea el acceso a los portales de administración de Microsoft a todos los usuarios incluidos en la directiva.  A continuación, experimentaste como usuario el impacto de la directiva de acceso condicional al acceder a Azure Portal.
