<a name="---"></a><!---
---
Laboratorio: Título: "Configuración"
---
--->

# <a name="lab-setup"></a>Laboratorio: Configuración

## <a name="lab-scenario"></a>Escenario del laboratorio

Este laboratorio de configuración consiste en habilitar el registro de auditoría de Microsoft.

**Tiempo estimado**: 5-10 minutos

### <a name="setup---enable-microsoft-365-audit-log"></a>Configuración: Habilitar el registro de auditoría de Microsoft 365

En esta tarea de configuración, habilitará la funcionalidad Registro de auditoría de Microsoft 365.  Aunque la documentación indica que el registro de auditoría está habilitado de manera predeterminada, la mayoría de los inquilinos del laboratorio no tienen habilitada esta función y pueden pasar varias horas hasta que surta efecto.  Habilitar esta función resulta útil, ya que Microsoft 365 utiliza los registros de auditoría para conseguir información sobre los usuarios y las actividades identificadas en las directivas y los análisis.

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.  

1. En el panel de navegación izquierdo, en Soluciones, seleccione **Auditoría**.  Nota: También se puede acceder a la funcionalidad de auditoría a través de la página principal de Microsoft 365 Defender (anteriormente denominada Centro de seguridad de Microsoft 365).

1. Compruebe que la pestaña **Nueva búsqueda** está seleccionada (subrayada).

1. Cuando llegue a la página Auditoría, espere entre 2 y 3 minutos.  Si Auditoría NO está habilitada, verá una barra azul en la parte superior de la página donde pone "Comenzar a registrar la actividad del usuario y del administrador".  Seleccione **Iniciar el registro de la actividad de usuarios y administradores**.  Si se le pide que confirme que la configuración de la organización debe actualizarse, seleccione **Sí**. Una vez que la auditoría esté habilitada, la barra azul desaparecerá.  Si la barra azul no aparece, eso significará que la opción Auditoría ya está habilitada, y no necesitará hacer nada más.  Otra forma de comprobar si la auditoría está habilitada es a través de PowerShell, pero está fuera del ámbito de este curso.

1. Para volver a la página principal del Portal de cumplimiento de Microsoft Purview, seleccione **Inicio** en el panel de navegación izquierdo con el fin de cerrar sesión de Microsoft 365. Para cerrar sesión, seleccione el icono en la esquina superior derecha de la ventana de Microsoft 365 que se muestra como un círculo con las letras MA (junto al icono de signo de interrogación) y, a continuación, seleccione **Cerrar sesión**. Después, cierre el explorador.

### <a name="review"></a>Revisar

En esta configuración, ha habilitado la funcionalidad de registro de auditoría de Microsoft 365.
