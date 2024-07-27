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

**Tiempo estimado**: 45-60 minutos

### Tarea 1

En esta tarea, como administrador, restablecerá la contraseña del usuario Diego Siciliani. Este paso es necesario para que pueda iniciar sesión inicialmente como el usuario en tareas posteriores.

1. Abrir Microsoft Edge.  En la barra de direcciones, escriba **https://entra.microsoft.com**.

1. Inicie sesión con las credenciales de administrador de Microsoft 365 proporcionadas por su ALH.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es su Id. de inquilino único proporcionado por el ALH) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
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

1. Ahora está en la página de inicio rápido de Privileged Identity Management. Revise la información de la página de introducción. Seleccione **Administrar**.

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

En esta tarea, iniciará sesión en Centro de administración Microsoft Entra como Diego Siciliani, para acceder a la capacidad Privileged Identity Management de Microsoft Entra para activar su tarea como Administrador de usuarios.  Una vez activada, realizará algunos cambios de configuración en un usuario existente. Nota: Para esta tarea necesitará tener acceso a un dispositivo móvil al que tenga acceso inmediato y donde pueda recibir mensajes de texto.

1. Abrir Microsoft Edge.  En la barra de direcciones del explorador, escriba **Entra.microsoft.com**.

1. Inicie sesión como Diego Siciliani.
    1. En la ventana de inicio de sesión, escriba **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña temporal que anotó en la tarea anterior y seleccione **Iniciar sesión**.  Seleccione **Iniciar sesión**.
    1. Como la contraseña que escribió era temporal, deberá actualizarla ahora. Escriba la contraseña actual, escriba una nueva contraseña y confírmela.  Anote la nueva contraseña, ya que la necesitará para completar la tarea.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. Debería haber iniciado sesión correctamente en el Centro de administración Microsoft Entra.
1. En el panel de navegación izquierdo, en expanda **Gobernanza de identidad** y, a continuación, seleccione **Privileged Identity Management**.
1. En el panel de navegación izquierdo, seleccione **Mis roles**.  Ahora está viendo información para las tareas elegibles.  Verá que a usted, Diego, se le asignó el rol de Administrador de usuarios.  
1. En la última columna de la tabla, Acción etiquetada, seleccione **Activar**.
1. Verá un icono de advertencia que indica que se necesita verificación adicional.  Seleccione **Haga clic para continuar**.  Recuerde que la configuración del PIM para el Rol de administrador de usuarios requiere una autenticación multifactor.  Además, como la información de contacto de Diego para su uso con MFA (métodos de autenticación) no se configuró anteriormente, debe registrar su información para poder usar la MFA.  Aunque tendrá que realizar la MFA cada vez que inicie sesión como administrador de usuarios, dentro del período de la tarea, el proceso de registro de la MFA solo se requiere una vez.
1. Se le notificará que se necesita más información, seleccione **Siguiente**.
1. Escriba su contraseña.
1. En la parte inferior izquierda de la ventana Microsoft Authenticator, seleccione **Quiero configurar un método diferente**.
1. Se le solicitará que seleccione otro método.  Junto a donde dice Aplicación Authenticator, seleccione la flecha hacia abajo.   Seleccione **Teléfono** y luego **Confirmar**.
1. Se le solicitará que escriba un número de teléfono que le gustaría utilizar. Asegúrese de que el país y el código de país del número de teléfono se correspondan.  Escriba el número de teléfono, asegúrese de que **Enviarme un código por mensaje de texto** esté seleccionado y, a continuación, seleccione **Siguiente**.
1. Escriba el código de 6 dígitos que reciba en su teléfono y seleccione **Siguiente**.
1. Verá una notificación que dice que el teléfono se ha registrado correctamente. Seleccione **Siguiente** y después **Listo**.
1. Se le preguntará si quiere mantener la sesión iniciada.  Seleccione **Sí**.
1. Aparecerá la ventana Activar administrador de usuarios.  Se le solicitará que escriba el motivo de la activación.  En el cuadro que aparece, escriba cualquier motivo que desee (máximo de 500 caracteres) y seleccione **Activar**.
1. Verá el estado (tres etapas del progreso), mientras se procesa la activación.
1. Una vez completada la activación, volverá a abrirse la página Mis roles | Roles de Microsoft Entra ID, donde verá una notificación que indica que ha activado un rol.  Seleccione **Haga clic aquí** para ver los roles activos.  Si observa que la hora de finalización es diferente de la configurada originalmente, seleccione Actualizar en la parte superior de la página (puede tardar unos minutos en actualizarse).
1. Para volver a la página principal del Centro de administración de Microsoft Entra, seleccione **Inicio** en el panel de navegación izquierdo. 
1. Como administrador de usuarios de Microsoft Entra ID puede crear usuarios y grupos, administrar licencias y mucho más. En el panel de navegación izquierdo, expanda **Identidad**, seleccione **Usuarios** y luego seleccione **Todos los usuarios**.
1. En la lista de usuarios, seleccione **Bianca Pisani**.
1. En el panel de navegación izquierdo, seleccione **Licencias**.
1. Fíjese en que Bianca no tiene ninguna licencia asignada.  En la parte superior de la página, seleccione **Asignaciones**.
1. En la lista Seleccionar licencias, selecciona **Microsoft Power Apps para desarrolladores** y **Microsoft Power Automate gratis**.
1. En la parte inferior de la página, seleccione **Guardar**.  Verá una breve notificación en la parte superior derecha de la página que indica que las licencias se asignaron correctamente.
1. Salga de la página de asignaciones de licencias actualizada, para ello, seleccione la **X** de la esquina superior derecha de la página.
1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador.
1. La duración del rol de administrador de usuarios se limita al tiempo configurado.

### Revisar

En este laboratorio exploró la PIM.  Como administrador, configuró al usuario Diego con privilegios de administrador de usuarios durante un período de tiempo especificado.  A continuación, como Diego, recorrió el proceso de activación de los privilegios de administrador de usuarios y la configuración de las opciones de usuario.  Recuerde que la PIM requiere una licencia de Microsoft Entra ID Premium P2.
