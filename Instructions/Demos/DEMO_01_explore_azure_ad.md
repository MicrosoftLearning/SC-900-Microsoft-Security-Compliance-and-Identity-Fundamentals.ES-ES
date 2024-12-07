<!---
---
Demostración: Título: "Exploración de la configuración de usuario de Microsoft Entra ID" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra; Módulo 1: Descripción de los tipos de función e identidad de Microsoft Entra ID; Unidad 3: Descripción de los tipos de identidad de Microsoft Entra"
---
--->

# Demostración: Configuración de usuario de Microsoft Entra ID

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra.
- Módulo: Descripción de los tipos de función e identidad de Microsoft Entra ID.
- Unidad: Descripción de los tipos de identidades.

## Supuesto de demostración

En esta demostración, accederá a Microsoft Entra ID y verá las distintas opciones de configuración para un usuario.

1. Abrir Microsoft Edge.

1. En la barra de direcciones, escriba **admin.microsoft.com** para acceder al Centro de administración de Microsoft 365.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escribe la contraseña de administrador que debería haberte proporcionado tu proveedor de servicios de hospedaje de laboratorios. Selecciona **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Identidad** (puede que se tenga que desplazar hacia abajo).  Se abre una nueva página del explorador con la página de información general del Centro de administración de Microsoft Entra. Aquí se muestra información básica sobre el inquilino Contoso. Si se desplaza hacia abajo en la ventana principal, también verá información sobre las alertas, mi fuente, aspectos destacados de las características, etc.  
    1. Nota para el presentador o instructor: también se puede acceder al Centro de administración de Microsoft Entra yendo directamente a **[entra.microsoft.com](https://entra.microsoft.com)** .

1. En el panel de navegación izquierdo, expanda **Usuarios** y seleccione **Todos los usuarios**.  En la página de usuarios puede ver más opciones de navegación y la lista de usuarios. Su inquilino ya está configurado con usuarios.

1. En la lista de usuarios, seleccione **Adele Vance**.

1. Observe que en el panel de navegación izquierdo, **Información general** está resaltado en gris claro.  Muestre o explique el contenido de la página de información general.  Seleccione la pestaña **Supervisión** en la parte superior de la página que muestra los inicios de sesión del usuario (no se mostrará ningún inicio de sesión si no ha iniciado sesión antes como Adele Vance).  A continuación, seleccione **Propiedades** para ver todas las propiedades del objeto de usuario Adele Vance.

1. En el panel de navegación izquierdo, seleccione **Roles asignados**.  Este usuario no tiene asignado ningún rol administrativo.  En la parte superior de la página, seleccione **+ Agregar asignaciones** y, en la página Agregar asignaciones, expanda el campo Buscar rol en Seleccionar rol para ver una lista de los tipos de roles administrativos disponibles.  No agregue nada, simplemente cierre la página, para ello, seleccione la **X** de la esquina superior derecha de la página.

1. En el panel de navegación izquierdo, seleccione **Grupos**.  Hable del hecho de que este usuario sea miembro de varios grupos.  Aquí puede hablar con los tipos de grupos.  Para agregar este usuario a otros grupos, basta con seleccionar **+ Agregar pertenencias**.  No agregue ningún grupo nuevo, solo hable de lo fácil que es agregar un usuario a los grupos existentes. Seleccione la **X** de la esquina superior derecha de la página para cerrar la ventana Seleccionar grupos.

1. En el panel de navegación izquierdo, seleccione **Licencias**. Tenga en cuenta que este usuario tiene asignadas licencias de Microsoft 365 E5 y de emS.  Para agregar una licencia, seleccione **+ Asignaciones** de la parte superior de la ventana principal.  Mostrar las licencias de este usuario. NO cambie nada.  Seleccione la **X** de la esquina superior derecha de la página para cerrarla.

1. En el panel de navegación izquierdo, seleccione **Dispositivos**.  No aparece nada, pero puede decir que si este usuario tuviera dispositivos asignados, aquí es donde se mostrarían.

1. En el panel de navegación izquierdo, seleccione **Asignación de roles de Azure**.  Llamada:
    1. Esto es diferente a la pestaña Roles asignados que se ha mostrado antes, ya que esa pestaña anterior es para el control de acceso basado en roles en Microsoft Entra.
    1. Aunque aquí no aparece nada, esta es la pestaña donde podría ver las asignaciones de roles, asignados a Adele, para los recursos de Azure. Por ejemplo, si tuviera que crear un grupo de recursos de Azure y asignara a Adele un rol específico, como propietario o colaborador del grupo de recursos, vería que ese rol aparecería aquí. Esto forma parte del control de acceso basado en roles de Azure (Azure RBAC). Esa asignación de roles se agrega y administra como parte de ese recurso específico.

1. Seleccione la **X** de la esquina superior derecha de la página. Esto le devuelve a la lista de usuarios.

1. Seleccione la **X** de la esquina superior derecha de la página. Esto le devuelve a la página principal del Centro de administración de Microsoft Entra.

1. Deje esta pestaña del explorador abierta, porque la utilizará para la siguiente demostración.

### Revisar

En esta demostración, ha mostrado la configuración de un usuario existente, incluidos los grupos a los que se puede asignar el usuario, la disponibilidad de roles y la asignación de licencias de usuario.
