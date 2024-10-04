---
lab:
  title: "Exploración de la configuración de usuario de Microsoft\_Entra\_ID"
  module: Describe the function and identity types of Microsoft Entra ID
---

# Laboratorio: Exploración de la configuración de usuario de Microsoft Entra ID

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra.
- Módulo: Descripción de los tipos de función e identidad de Microsoft Entra ID.
- Unidad: Descripción de los tipos de identidades.

## Escenario del laboratorio

En este laboratorio, accederás a Microsoft Entra ID (anteriormente denominado Azure Active Directory).  Además, crearás un usuario y establecerás la configuración, que incluye agregar licencias.  

**Tiempo estimado**: 30 minutos

### Tarea 1

Como suscriptor de Microsoft 365, ya usas Microsoft Entra ID (anteriormente denominado Azure AD).  En esta tarea, aprenderás a crear un nuevo usuario en Microsoft Entra ID y a explorar algunos de los servicios que se pueden administrar a nivel de usuario.

1. Abre el explorador Microsoft Edge. En la barra de direcciones, escribe **[admin.microsoft.com](https://admin.microsoft.com)** e inicia sesión con las credenciales de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).
    1. En la ventana de inicio de sesión, escribe **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es tu id. de inquilino único proporcionado por el ALH) y selecciona **Siguiente**.
    1. Escribe la contraseña de administrador que debería haberte proporcionado tu proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Dado que esta es la primera vez que inicias sesión, es posible que se te pida configurar MFA. Sigue las indicaciones en la pantalla para configurar MFA.
    1. Si aparece un mensaje para preguntarle si quiere mantener iniciada la sesión, seleccione **Sí**.

1. En Centros de administración, selecciona **Identidad** (puede que tengas que seleccionar **Mostrar todo** y desplazarte hacia abajo).  Se abre una nueva página del explorador con la página de información general del Centro de administración Microsoft Entra.

1. En el panel de navegación izquierdo, expande **Usuarios** y selecciona **Todos los usuarios**. Ten en cuenta que tu inquilino ya está configurado con usuarios.

1. En la parte superior de la página, selecciona **+ Nuevo usuario** y, después, en el cuadro desplegable, selecciona **Crear nuevo usuario**.

1. Ahora estás en la pestaña **Datos básicos** de la página Crear nuevo usuario. Rellena los campos como se indica a continuación:
    1. Nombre principal de usuario: **sara**.

    1. Alias de correo: deja el valor predeterminado, que se establece para derivar del nombre principal de usuario.

    1. Nombre para mostrar: **Sara Perez**.

    1. Contraseña: desactiva la casilla que dice "Generar automáticamente la contraseña", escribe una contraseña temporal que cumpla los requisitos y toma nota de ella, ya que la necesitarás para completar la tarea posterior.

    1. Cuenta habilitada: deja la marca de verificación para asegurarte de que la cuenta está habilitada.

    1. En la parte inferior de la página, selecciona **Siguiente: Propiedades**.

1. Aquí configurarás algunos de los campos de la pestaña **Propiedades**.

    1. Nombre: Sara

    1. Apellidos: Perez

    1. Tipos de usuario: deja el valor predeterminado **Miembro**, pero ten en cuenta que en la lista desplegable tienes la opción de seleccionar Invitado.

    1. Ubicación de uso: elige el país o la región donde se encuentra.  Ten en cuenta que para llegar al campo de ubicación de uso, deberás desplazarte hacia abajo en la página, ya que es el último campo de la página.  **NOTA**: si no lo haces, no podrás asignar una licencia en un paso posterior.

    1. Selecciona **Siguiente: Asignaciones**.

1. Ahora estás en la pestaña **Asignaciones** donde agregas una asignación de grupo y mira las opciones disponibles para agregar un rol.

    1. Selecciona **Agregar grupo**.

    1. La ventana que se abre muestra todos los grupos disponibles.  

    1. Observa la lista de todos los grupos disponibles.  Selecciona **Operaciones** de la lista.  En la parte inferior de la página, selecciona el botón **Seleccionar**.  Puedes tardar unos segundos, pero deberías ver la presentación del grupo de operaciones en la página de asignaciones.

    1. En la parte superior de la página, selecciona **+ Agregar rol**.  Se abre una ventana que muestra todos los roles de directorio disponibles.  Mira las opciones disponibles, pero no agregues ningún rol nuevo.  Cierra esta página, para hacerlo, selecciona la **X** de la esquina superior derecha de la página.
    1. En la parte inferior de la página, selecciona **Revisar y crear**. Se mostrará un resumen de la configuración.  En la parte inferior de la página, selecciona **Crear**.

1. Volverás a la página Usuarios.  Después de unos segundos, Sara Perez estará en la lista.  Es posible que tengas que seleccionar el icono **Actualizar** de la parte superior de la página.

1. En la lista de usuarios selecciona el usuario que acabas de crear, **Sara Perez**.  Se abre la página **Información general**.

1. En el panel de navegación izquierdo se muestran las distintas opciones que se pueden configurar para el usuario. Mira la opciones disponibles.

1. En el panel de navegación izquierdo, selecciona **Licencias**.  Ten en cuenta que no se encuentran asignaciones de licencias para este usuario, observa también el icono de advertencia que indica que "Agregar, quitar y volver a procesar asignaciones de licencias solo está disponible en el Centro de administración de M365".  Lo harás en la tarea siguiente.  NOTA: las licencias solo se pueden asignar si se configuró una ubicación de uso. Si no estableciste la ubicación de uso, vuelve a ese paso ahora.

### Tarea 2

En esta tarea, asignarás una licencia al usuario que acabas de crear mediante el Centro de administración de Microsoft 365.

1. Abre la pestaña del explorador **Inicio - Centro de administración de Microsoft 365**.

1. En el panel de navegación izquierdo, en usuarios, selecciona **Usuarios activos**.  En la lista de usuarios, selecciona **Sara Perez**.  Se abre una ventana que muestra información sobre el usuario.  

    1. Selecciona la pestaña **Licencias y aplicaciones**.
    1. Para cada una de las licencias enumeradas, verás el número de licencias disponibles.  Puesto que no hay licencias disponibles de Microsoft 365 E5 (ya se han asignado a otros usuarios), asigna las licencias de **Microsoft Power Apps Developer** y **Microsoft Power Automate Free** activando la casilla situada junto a ellas.
    1. Selecciona **Guardar cambios**. Una notificación en la esquina superior derecha de la pantalla debería mostrar que las asignaciones de licencias se realizaron correctamente.
    1. Cierra la página seleccionando la **X** en la esquina superior derecha de la página.

1. Vuelve al Centro de administración Microsoft Entra, para hacerlo, selecciona **Inicio** en el panel de navegación izquierdo o en la parte superior izquierda de la pantalla (la ruta de navegación), encima de donde dice Sara Perez | Licencias.

1. Has asignado correctamente las licencias al usuario.

1. Cierra la sesión de todas las pestañas abiertas del explorador. Para cerrar la sesión, selecciona el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y selecciona **Cerrar sesión**. Cierra todas las ventanas del explorador.

### Tarea 3

En esta tarea, iniciarás sesión como Sara Pérez por primera vez.

1. Abre Microsoft Edge.

1. En la barra de direcciones, escribe **https://login.microsoft.com**.

1. Inicia sesión como **sara@WWLxZZZZZ.onmicrosoft.com**, (donde ZZZZZZ es el Id. de inquilino único proporcionado por el ALH)
1. Escribe la contraseña temporal que configuraste en la tarea anterior.

1. Se te pedirá que actualices tu contraseña. En el campo Contraseña actual, escribe la contraseña temporal de la tarea anterior.

1. En el campo Nueva contraseña, escribe una nueva contraseña, confírmala y selecciona **Iniciar sesión**.  Anota la contraseña nueva, ya que la necesitarás para el ejercicio de laboratorio posterior en SSPR.

1. Dado que esta es la primera vez que inicias sesión como Sara Perez, es posible que se te pida configurar MFA. Sigue las indicaciones en la pantalla para configurar MFA.

1. Ahora deberías haber iniciado sesión en la cuenta Microsoft de Sara.  Ten en cuenta que las licencias de Sara que has asignado en la tarea anterior solo se limitaban a Power Automate gratis y Power Apps para desarrolladores y no incluían las licencias de E5.

1. Cierra la sesión seleccionando el icono en la esquina superior derecha de la ventana de Microsoft 365 que se muestra como un círculo con las letras SP (junto al icono de signo de interrogación) y, a continuación, selecciona **Cerrar sesión** y, después, cierra el explorador.

### Revisar

En este laboratorio, has empezado la exploración inicial de Microsoft Entra ID. Como los suscriptores de Microsoft 365 utilizan automáticamente Microsoft Entra ID, has comprobado que puedes acceder a las características y servicios de Microsoft Entra ID desde el portal de administración de Microsoft 365 o Azure Portal.  Sea cual sea el enfoque que prefieras para llegar al mismo lugar.  También aprendiste el proceso de creación de un nuevo usuario y las configuraciones diferentes que se pueden establecer, incluidos los grupos a los que se puede asignar el usuario, la disponibilidad de roles y la asignación de licencias de usuario.
