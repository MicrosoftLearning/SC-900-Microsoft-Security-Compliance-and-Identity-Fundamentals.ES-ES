<!---
---
Laboratorio: Título: "Explorar la configuración de usuario de Microsoft Entra ID" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Describir la capacidad de Microsoft Entra; Módulo 1: Describir los tipos de función e identidad de Microsoft Entra ID; Unidad 3: Describire los tipos de identidad de Microsoft Entra"
---
--->

# Laboratorio: Explorar Microsoft Entra ID

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra.
- Módulo: Descripción de los tipos de función e identidad de Microsoft Entra ID.
- Unidad: Descripción de los tipos de identidades.

## Escenario del laboratorio

En este laboratorio, accederá a Microsoft Entra ID (anteriormente denominado Azure Active Directory).  Además, creará un usuario y establecerá la configuración, que incluye agregar licencias.  

**Tiempo estimado**: 10-15 minutos

### Tarea 1

Como suscriptor de Microsoft 365, ya usa Microsoft Entra ID (anteriormente denominado Azure AD).  En esta tarea, aprenderá a crear un nuevo usuario en Microsoft Entra ID y a explorar algunos de los servicios que se pueden administrar a nivel de usuario.

1. Abra el explorador Microsoft Edge. En la barra de direcciones, escriba **[admin.microsoft.com](https://admin.microsoft.com)** e inicie sesión con las credenciales de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es su Id. de inquilino único proporcionado por el ALH) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En Centros de administración, seleccione **Identidad** (puede que se tenga que seleccionar **Mostrar todo** y desplazarse hacia abajo).  Se abre una nueva página del explorador con la página de información general del Centro de administración de Microsoft Entra. Aquí se muestra información básica sobre el inquilino Contoso. Si se desplaza hacia abajo en la ventana principal, también verá información sobre las alertas, mi fuente, aspectos destacados de las características, etc.

1. En el panel de navegación izquierdo, expanda **Usuarios** y seleccione **Todos los usuarios**. Tenga en cuenta que su inquilino ya está configurado con usuarios.

1. En la parte superior de la página, seleccione **+ Nuevo usuario** y, después, en el cuadro desplegable, seleccione **Crear nuevo usuario**.

1. Ahora está en la pestaña **Datos básicos** de la página Crear nuevo usuario. Rellenelos campos como se indica a continuación:
    1. Nombre principal de usuario: **sara**.

    1. Alias de correo: deje el valor predeterminado, que se establece para derivar del nombre principal de usuario.

    1. Nombre para mostrar: **Sara Perez**.

    1. Contraseña: desactive la casilla que dice "Generar automáticamente la contraseña", escriba una contraseña temporal que cumpla los requisitos y tome nota de ella, ya que la necesitará para completar la tarea posterior.

    1. Cuenta habilitada: deje la marca de verificación para asegurarse de que la cuenta está habilitada.

    1. En la parte inferior de la página, seleccione **Siguiente: Propiedades**.

1. Aquí configurará algunos de los campos de la pestaña **Propiedades**.

    1. Nombre: Sara

    1. Apellidos: Perez

    1. Tipos de usuario: deje el valor predeterminado **Miembro**, pero tenga en cuenta que en la lista desplegable tiene la opción de seleccionar Invitado.

    1. Ubicación de uso: elija el país o la región donde se encuentra.  Tenga en cuenta que para llegar al campo de ubicación de uso, deberá desplazarse hacia abajo en la página, ya que es el último campo de la página.  **NOTA**: si no lo hace, no podrá asignar una licencia en un paso posterior.

    1. Seleccione **Siguiente: Asignaciones**.

1. Ahora está en la pestaña **Asignaciones** donde agrega una asignación de grupo y ve las opciones disponibles para agregar un rol.

    1. Seleccione **Agregar grupo**.

    1. La ventana que se abre muestra todos los grupos disponibles.  

    1. Observe la lista de todos los grupos disponibles.  Seleccione **Operaciones** de la lista.  En la parte inferior de la página, seleccione el botón **Seleccionar**.  Puede tardar unos segundos, pero debería ver la presentación del grupo de operaciones en la página de asignaciones.

    1. En la parte superior de la página, seleccione **Agregar rol**.  Se abre una ventana que muestra todos los roles de directorio disponibles.  Vea las opciones disponibles, pero no agregue ningún rol nuevo.  Cierre esta página, para hacerlo, seleccione la **X** de la esquina superior derecha de la página.
    1. En la parte inferior de la página, seleccione **Revisar y crear**. Se mostrará un resumen de la configuración.  En la parte inferior de la página, seleccione **Crear**.

1. Volverá a la página Usuarios.  Después de unos segundos, Sara Perez estará en la lista.  Es posible que tenga que seleccionar el icono **Actualizar** de la parte superior de la página.

1. En la lista de usuarios seleccione el usuario que acaba de crear, **Sara Perez**.  Se abre la página **Información general**.

1. En el panel de navegación izquierdo se muestran las distintas opciones que se pueden configurar para el usuario. Vea la opciones disponibles.

1. En el panel de navegación izquierdo, seleccione **Licencias**.  Observe que no se encuentran asignaciones de licencias para este usuario.  NOTA: Las licencias solo se pueden asignar si se configuró una ubicación de uso. Si no estableció la ubicación de uso, vuelva a ese paso de la tarea anterior.

    1. Para agregar una licencia seleccione **+ Asignaciones** de la parte superior de la ventana principal.

    1. En Seleccionar licencias, seleccione **Office 365 E3** y **Windows 10/11 Enterprise E3** y luego seleccione el botón **Guardar** en la parte inferior de la pantalla. Una notificación en la esquina superior derecha de la pantalla debería mostrar que las asignaciones de licencias se realizaron correctamente.

    1. Seleccione la **X** de la parte superior derecha de la pantalla para cerrar la ventana Asignaciones de licencias.

    1. Seleccione el **icono Actualizar** en la parte superior de la página para confirmar las asignaciones de licencias.

1. Vuelva al Centro de administración de Microsoft Entra, para hacerlo, seleccione **Inicio** en el panel de navegación izquierdo o en la parte superior izquierda de la pantalla (la ruta de navegación), encima de donde dice Sara Perez | Licencias.

1. Creó y configurado correctamente un usuario en Microsoft Entra ID.

1. Cierre la sesión de todas las pestañas abiertas del explorador. Para cerrar la sesión, seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. Cierre todas las ventanas del navegador.

### Tarea 2

En esta tarea, iniciará sesión como Sara Pérez por primera vez.

1. Abrir Microsoft Edge.

2. En la barra de direcciones, escriba **https://login.microsoft.com**.

3. Inicie sesión como **sara@WWLxZZZZZ.onmicrosoft.com**, (donde ZZZZZZ es el Id. de inquilino único proporcionado por el ALH)
4. Escriba la contraseña temporal que configuró en la tarea anterior.

5. Se le pedirá que actualice su contraseña. En el campo Contraseña actual, escriba la contraseña temporal de la tarea anterior.

6. En el campo Nueva contraseña, escriba una nueva contraseña, confírmela y seleccione **Iniciar sesión**.  Anote la contraseña nueva, ya que la necesitará para el ejercicio de laboratorio posterior en SSPR.

7. Ahora debería haber iniciado sesión correctamente en Microsoft 365.

8. Cierre la sesión seleccionando el icono en la esquina superior derecha de la ventana de Microsoft 365 que se muestra como un círculo con las letras SP (junto al icono de signo de interrogación) y, a continuación, seleccione **Cerrar sesión** y, después, cierre el explorador.

### Revisar

En este laboratorio, comenzó la exploración inicial de Azure AD. Como los suscriptores a Microsoft 365 usan Azure AD automáticamente, detectó que accede a las características y servicios de Azure AD a través del portal de administración de Microsoft 365 o de Azure Portal.  Sea cual sea el enfoque que prefiera para llegar al mismo lugar.  También aprendió el proceso de creación de un nuevo usuario y las configuraciones diferentes que se pueden establecer, incluidos los grupos a los que se puede asignar el usuario, la disponibilidad de roles y la asignación de licencias de usuario.
