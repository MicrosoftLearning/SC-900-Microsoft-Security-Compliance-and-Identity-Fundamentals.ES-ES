<!---
---
Laboratorio: Título: "Exploración de la configuración de usuario de Microsoft Entra ID" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra; Módulo 1: Descripción de los tipos de función e identidad de Microsoft Entra ID; Unidad 3: Descripción de los tipos de identidad de Microsoft Entra"
---
--->

# Laboratorio: Exploración de Microsoft Entra ID

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra.
- Módulo: Descripción de los tipos de función e identidad de Microsoft Entra ID.
- Unidad: Descripción de los tipos de identidades.

## Escenario del laboratorio

En este laboratorio, accederá a Microsoft Entra ID (anteriormente denominado Azure Active Directory).  Además, creará un usuario y establecerá la configuración, que incluye agregar licencias.  

**Tiempo estimado**: 10-15 minutos.

### Tarea 1

Como suscriptor a Microsoft 365, ya usa Microsoft Entra ID (anteriormente denominado Azure AD).  En esta tarea, aprenderá cómo crear un nuevo usuario en Microsoft Entra ID y explorará algunos de los servicios que se pueden administrar como usuario.

1. Abra el explorador de Microsoft Edge. En la barra de direcciones, escriba **[admin.microsoft.com](https://admin.microsoft.com)** e inicie sesión con las credenciales de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el ALH) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En Centros de administración, seleccione **Identidad** (puede que tenga que seleccionar **Mostrar todo** y desplazarse hacia abajo).  Se abre una nueva página del explorador con la página de información general del Centro de administración de Microsoft Entra. Aquí se muestra información básica sobre el inquilino Contoso. Si se desplaza hacia abajo en la ventana principal, también verá información sobre las alertas, mi fuente, aspectos destacados de las características, etc.

1. En el panel de navegación izquierdo, expanda **Usuarios** y seleccione **Todos los usuarios**. Verá que su inquilino ya está configurado con usuarios.

1. En la parte superior de la página, seleccione **+ Nuevo usuario** y, después, en el cuadro desplegable, seleccione **Crear nuevo usuario**.

1. Ahora está en la pestaña **Aspectos básicos** de la página Crear nuevo usuario. Rellene los campos de la siguiente manera:
    1. Nombre principal de usuario: **sara**.

    1. Alias de correo: deje el valor predeterminado, que está establecido para que se derive del nombre principal de usuario.

    1. Nombre para mostrar: **Sara Pérez**.

    1. Contraseña: desactive la casilla que indica Generar automáticamente la contraseña y escriba una contraseña temporal que cumpla los requisitos de contraseña y tome nota de ella, ya que la necesitará para completar la tarea posterior.

    1. Cuenta habilitada: deje la marca de verificación para asegurarse de que la cuenta está habilitada.

    1. En la parte inferior de la página, seleccione **Siguiente: Propiedades**.

1. Aquí configurará algunos de los campos de la pestaña **Propiedades**.

    1. Nombre: Sara

    1. Apellido: Pérez

    1. Tipos de usuario: deje el valor predeterminado en **Miembro**, pero tenga en cuenta que en la lista desplegable tiene la opción de seleccionar Invitado.

    1. Ubicación de uso: elija el país o región donde se encuentra.  Tenga en cuenta que, para llegar al campo Ubicación de uso, deberá desplazarse hacia abajo en la página, ya que es el último campo de esta.  **NOTA**: si no lo hace, no podrá asignar una licencia en un paso posterior.

    1. Seleccione **Siguiente: Asignaciones**.

1. Ahora está en la pestaña **Asignaciones**, donde agrega una asignación de grupo y ve las opciones disponibles para agregar un rol.

    1. Seleccione **Agregar grupo**.

    1. La ventana que se abre muestra todos los grupos disponibles.  

    1. Observe la lista de grupos disponibles.  En la lista, seleccione **Operaciones**.  En la parte inferior de la página, seleccione el botón **Seleccionar**.  Puede tardar unos segundos, pero debería ver el grupo de operaciones en la página Asignaciones.

    1. En la parte superior de la página, seleccione **Agregar rol**.  Se abre una ventana que muestra todos los roles de directorio disponibles.  Vea las opciones disponibles, pero no agregue ningún nuevo rol.  Cierre esta página haciendo clic sobre la **X** de la esquina superior derecha de la página Roles de directorio.
    1. En la parte inferior de la página, seleccione **Revisar y crear**. Se mostrará un resumen de la configuración.  En la parte inferior de la página, seleccione **Crear**.

1. Se le devuelve a la página de usuarios.  Después de unos segundos, Sara Pérez aparecerá en la lista.  Es posible que tenga que hacer clic sobre el icono de **actualización** de la parte superior de la página.

1. En la lista de usuarios seleccione el usuario que acaba de crear, **Sara Perez**.  Se abre la página **Información general**.

1. El panel de navegación izquierdo muestra las opciones que se pueden configurar para el usuario. Ver las opciones disponibles.

1. En el panel de navegación izquierdo seleccione **Licencias**.  Observe que no se ha encontrado ninguna asignación de licencia para este usuario.  NOTA: Las licencias solo se pueden asignar si se configuró una ubicación de uso. Si no estableció la ubicación de uso, vuelva a ese paso en la tarea anterior.

    1. Para agregar una licencia seleccione **+ Asignaciones** en la parte superior de la ventana principal.

    1. En Seleccionar licencias, seleccione **Office 365 E3** y **Windows 10/11 Enterprise E3** y luego seleccione el botón **Guardar** en la parte inferior de la pantalla. En la esquina superior derecha de la pantalla debería aparecer una notificación que indique que la asignación de licencias se ha realizado con éxito.

    1. Seleccione la **X** de la esquina superior derecha de la pantalla para cerrar la ventana Asignación de licencias.

    1. Seleccione el **icono de Actualizar** en la parte superior de la página para confirmar la asignación de licencias.

1. Vuelva al centro de administración de Microsoft Entra seleccionando **Inicio** en el panel de navegación izquierdo o en la parte superior izquierda de la pantalla (la ruta de navegación), encima de donde dice Sara Pérez | Licencias.

1. Ha creado y configurado correctamente un usuario en Microsoft Entra ID.

1. Cierre la sesión de todas las pestañas abiertas del explorador. Para cerrar la sesión, haga clic sobre el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y haga clic sobre **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador.

### Tarea 2

En esta tarea, iniciará sesión como Sara Pérez por primera vez.

1. Abrir Microsoft Edge.

2. En la barra de direcciones, escriba **https://login.microsoft.com** .

3. Inicie sesión como **sara@WWLxZZZZZ.onmicrosoft.com** , (ZZZZZZ es el identificador de inquilino único proporcionado por el proveedor de ALH).
4. Escriba la contraseña temporal que estableció en la tarea anterior.

5. Luego, se le solicitará actualizar su contraseña. En el campo Contraseña actual, escriba la contraseña temporal de la tarea anterior.

6. En el campo Nueva contraseña, escriba una nueva contraseña, confírmela y seleccione **Iniciar sesión**.  Anote la nueva contraseña, ya que la necesitará para el ejercicio de laboratorio posterior en SSPR.

7. Ahora, habrá iniciado sesión correctamente en Microsoft 365.

8. Cierre la sesión seleccionando el icono en la esquina superior derecha de la ventana de Microsoft 365 que se muestra como un círculo con las letras SP (junto al icono de signo de interrogación) y, a continuación, seleccione **Cerrar sesión** y, después, cierre el explorador.

### Revisar

En este laboratorio, empezó su exploración inicial de Azure AD. Dado que los suscriptores de Microsoft 365 utilizan automáticamente Azure AD, comprobó que puede acceder a las características y servicios de Azure AD a través del portal de administración de Microsoft 365 o a través de Azure Portal.  Sea cual sea el método que prefiera para llegar al mismo lugar.  También aprendió el proceso de creación de un nuevo usuario y las configuraciones diferentes que se pueden establecer, incluidos los grupos a los que se puede asignar el usuario, la disponibilidad de roles y la asignación de licencias de usuario.
