---
lab:
  title: Exploración de la administración de identidades con privilegios
  module: Describe the identity protection and governance capabilities of Microsoft Entra
---

# Laboratorio: Explorar Privileged Identity Management

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra
- Módulo: Describir las capacidades de gobernanza y protección de identidades de Microsoft Entra
- Unidad: Descripción de las funcionalidades de Privileged Identity Management

## Escenario del laboratorio

En este laboratorio, explorará algunas de las funcionalidades básicas de Privileged Identity Management (PIM). PIM requiere licencias de Microsoft Entra ID P2.  En este laboratorio, como administrador, configurará uno de los usuarios, Diego Siciliani, con un rol de administrador de usuarios de Microsoft Entra, a través de privileged ID management (PIM).   Con privilegios de administración de usuarios, Diego podrá crear usuarios y grupos, administrar licencias, etc.  Tanto el administrador como el usuario, Diego, deben configurarse para licencias de Microsoft Entra ID P2.

**Tiempo estimado**: 60 minutos

### Tarea 1

En esta tarea, como administrador, restablecerá la contraseña del usuario Diego Siciliani. Este paso es necesario para que pueda iniciar sesión inicialmente como el usuario en tareas posteriores.

1. Abrir Microsoft Edge.  En la barra de direcciones, escriba **https://entra.microsoft.com**.

1. Inicie sesión con las credenciales de administrador de Microsoft 365 proporcionadas por su ALH.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es su Id. de inquilino único proporcionado por el ALH) y seleccione **Siguiente**.
    1. Escribe la contraseña de administrador que debería haberte proporcionado tu proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Si has iniciado sesión anteriormente como administrador, es posible que se te pida que completes una autenticación secundaria, como parte de MFA. Si no has iniciado sesión anteriormente como administrador, es posible que se te pida que completes el proceso de registro de MFA. Sigue las indicaciones en la pantalla para configurar MFA.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En el panel de navegación izquierdo, expanda **Identidad**, **Usuarios** y luego seleccione **Todos los usuarios**.

1. Seleccione **Diego Siciliani** de la lista de usuarios.

1. En la parte superior de la página, seleccione **Restablecer contraseña**. Como no ha iniciado sesión previamente como Diego Siciliani, no conoce su contraseña y deberá restablecerla.

1. Cuando se abra la página de restablecimiento de contraseña, seleccione **Restablecer contraseña**.  IMPORTANTE: Anote la nueva contraseña, la necesitará en una tarea posterior para poder acceder como usuario.

1. En el panel de navegación izquierdo, seleccione **Inicio** para volver a la página principal del Centro de administración Microsoft Entra.

1. Mantenga abierta la ventana del navegador, la necesitará en la siguiente tarea.

### Tarea 2

En esta tarea, como administrador, asignará a Diego un rol de Microsoft Entra ID en Privileged Identity Management.

1. Abra una pestaña del explorador con la página principal del Centro de administración de Microsoft Entra.

1. En el panel de navegación izquierdo, en "Identidad", expanda **Gobernanza de identidad** y, a continuación, seleccione **Privileged Identity Management**.

1. Ahora está en la página de inicio rápido de Privileged Identity Management. Revise la información de la página de introducción. En la ventana principal, donde dice Administrar acceso, selecciona **Administrar**.

1. Ahora está en la página Roles de Contoso.  En la barra de búsqueda de la parte superior de la página, escriba **usuario**.  En los resultados de la búsqueda, seleccione **Administrador de usuarios**.

1. En la parte superior de la página, seleccione **+ Agregar tareas**.

1. En la página Agregar tareas, asegúrese de que **la pertenencia** está subrayada.  Aquí se configuran los ajustes de pertenencia al rol de administrador de usuarios en PIM.

1. Deje el tipo de ámbito en su valor predeterminado, Directorio.  

1. En Seleccionar miembros, seleccione **No hay miembros seleccionados**. Se abrirá la ventana Seleccionar un miembro.

1. En la barra de búsqueda, escriba **Diego**.  En los resultados de la búsqueda, seleccione **Diego Siciliani** y presione **Seleccionar** en la parte inferior de la página.  

1. En Seleccionar miembros verá 1 miembro seleccionado y el nombre y correo electrónico del miembro seleccionado, Diego Siciliani. En la parte inferior de la página Agregar tarea, seleccione **Siguiente**.  

1. Ahora está en la página Configuración.  Deje el tipo de tarea con la configuración predeterminada, Elegible.

1. Si está activada la casilla Permanentemente elegible, seleccione **Permanentemente elegible** para quitar la marca de verificación.

1. En los campos Inicio de tarea, mantenga la fecha y la hora predeterminadas, que es hoy y la hora actual.

1. En los campos Finalización de la tarea, cambie la fecha a la fecha de hoy (tenga en cuenta que la configuración predeterminada es de un año desde hoy, por lo que debe cambiar el año). Para la hora, establezca la hora en dos horas a partir de la hora actual. Después de establecer el campo de hora para la hora en que finalizará la tarea, presione el tabulador del teclado y seleccione **Asignar** en la parte inferior de la página.  

1. Esto le lleva de vuelta a la ventana Tareas.  Después de unos segundos debería ver Diego Siciliani en la tabla Administrador de usuarios, junto con los detalles de la tarea. Si después de unos segundos aún no ve la actualización, seleccione **Actualizar** en la parte superior de la página.

1. En la parte superior de la página, seleccione **Configuración**.

1. En los detalles de configuración del rol Administrador de usuario, observe las distintas opciones.  Tenga en cuenta que la opción "Requerir justificación en la activación" está establecida en Sí y "Al activar, requerir Azure MFA" también está establecida en Sí.  Verá ambas cosas en la siguiente tarea cuando Diego active el rol.  Tenga en cuenta también que "Solicitud de aprobación para activar" está establecido en No.  Deje toda la configuración en sus valores predeterminados.  Cierre la ventana, para ello, seleccione la **X** de la esquina superior derecha de la ventana.

1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador.

### Tarea 3

En esta tarea, iniciará sesión en Centro de administración Microsoft Entra como Diego Siciliani, para acceder a la capacidad Privileged Identity Management de Microsoft Entra para activar su tarea como Administrador de usuarios.  Una vez activada, realizará algunos cambios de configuración en un usuario existente. Nota: para esta tarea, necesitarás acceso a un dispositivo móvil para usarlo con la aplicación Microsoft Authenticator.

1. Abrir Microsoft Edge.  En la barra de direcciones del explorador, escriba **Entra.microsoft.com**.

1. Inicie sesión como Diego Siciliani.
    1. En la ventana de inicio de sesión, escriba **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña temporal que anotó en la tarea anterior y seleccione **Iniciar sesión**.  Seleccione **Iniciar sesión**.
    1. Como la contraseña que escribió era temporal, deberá actualizarla ahora. Escriba la contraseña actual, escriba una nueva contraseña y confírmela.  Anote la nueva contraseña, ya que la necesitará para completar la tarea.
    1. Dado que esta es la primera vez que inicias sesión como Diego, es posible que se te pida configurar MFA. Sigue las indicaciones en la pantalla para configurar MFA.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. Debería haber iniciado sesión correctamente en el Centro de administración Microsoft Entra.
1. En el panel de navegación izquierdo, en expanda **Gobernanza de identidad** y, a continuación, seleccione **Privileged Identity Management**.
1. En el panel de navegación izquierdo, seleccione **Mis roles**.  Ahora está viendo información para las tareas elegibles.  Verá que a usted, Diego, se le asignó el rol de Administrador de usuarios.  
1. En la última columna de la tabla, Acción etiquetada, seleccione **Activar**.
1. Verá un icono de advertencia que indica que se necesita verificación adicional.  Seleccione **Haga clic para continuar**.  Recuerde que la configuración del PIM para el Rol de administrador de usuarios requiere una autenticación multifactor.  Además, como la información de contacto de Diego para su uso con MFA (métodos de autenticación) no se configuró anteriormente, debe registrar su información para poder usar la MFA.  Aunque tendrá que realizar la MFA cada vez que inicie sesión como administrador de usuarios, dentro del período de la tarea, el proceso de registro de la MFA solo se requiere una vez.
1. La ventana que aparece y los pasos que siguen son para el método de aplicación Microsoft Authenticator. .
    1. Si ya has instalado la aplicación Microsoft Authenticator en tu dispositivo móvil, selecciona **Siguiente**. De lo contrario, selecciona **Descargar ahora** y sigue los pasos.
    1. Comenzarás a configurar tu cuenta.  Seleccione **Siguiente**.
    1. Con la aplicación Microsoft Authenticator en el dispositivo móvil, selecciona **+** para agregar una cuenta y, después, **Cuenta profesional o educativa**.
    1. Selecciona la opción para **Escanear el código QR** y luego usa tu dispositivo móvil para escanear el código QR en la pantalla del equipo.
    1. Con la aplicación Microsoft Authenticator de tu dispositivo móvil, escanea el código QR.
    1. Sigue los pasos del PC y dispositivo móvil y, después, selecciona **Siguiente**.
    1. Una vez que hayas configurado la información de seguridad, verás una ventana de operación correcta.  Seleccione **Listo**.

1. Una vez completado el proceso de registro de MFA, se te devolverá a la página Administrador de usuarios activos de PIM.
1. Aparecerá la ventana Activar administrador de usuarios.  Se le solicitará que escriba el motivo de la activación.  En el cuadro que aparece, escriba cualquier motivo que desee (máximo de 500 caracteres) y seleccione **Activar**.
1. Verá el estado (tres etapas del progreso), mientras se procesa la activación.
1. Una vez completada la activación, volverá a abrirse la página Mis roles | Roles de Microsoft Entra ID, donde verá una notificación que indica que ha activado un rol.  Seleccione **Haga clic aquí** para ver los roles activos.  Si observa que la hora de finalización es diferente de la configurada originalmente, seleccione Actualizar en la parte superior de la página (puede tardar unos minutos en actualizarse).
1. Para volver a la página principal del Centro de administración de Microsoft Entra, seleccione **Inicio** en el panel de navegación izquierdo. 
1. Como administrador de usuarios de Microsoft Entra ID puede crear usuarios y grupos, administrar licencias y mucho más. En el panel de navegación izquierdo, expande **Identidad** y selecciona **Usuarios**.
1. En la lista de usuarios, seleccione **Bianca Pisani**.
1. En el panel de navegación izquierdo, seleccione **Grupos**.
1. Observa los grupos a los que ya está asignado Bianca. En la parte superior de la página, selecciona **+ Pertenencias**.
1. En la lista de grupos, selecciona **Mark 8 Project Team**.
1. En la parte inferior de la página, selecciona **Seleccionar**.
1. En la página Grupos, observa que el grupo Mark 8 Project Team se ha agregado a la lista (si no lo ves inmediatamente, selecciona el botón **Actualizar**).
1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador.
1. La duración del rol de administrador de usuarios se limita al tiempo configurado.

### Revisar

En este laboratorio exploró la PIM.  Como administrador, configuró al usuario Diego con privilegios de administrador de usuarios durante un período de tiempo especificado.  A continuación, como Diego, recorriste el proceso de activación de los privilegios de administrador de usuarios y un usuario a un grupo.  Recuerde que la PIM requiere una licencia de Microsoft Entra ID Premium P2.
