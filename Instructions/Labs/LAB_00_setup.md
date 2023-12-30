<!---
---
Laboratorio: Título: "Configuración"
---
--->

# Laboratorio: Configuración

## Inquilinos de WWL: términos de uso
Si se le proporciona un inquilino porque está realizando un curso dirigido por un instructor, tenga en cuenta que ese inquilino está disponible únicamente como apoyo para los laboratorios prácticos del curso.

Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino usado en este curso es un inquilino de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y no sea apto para la extensión.

Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento.

## Escenario del laboratorio

Este laboratorio de configuración consiste en habilitar el registro de auditoría de Microsoft.

**Tiempo estimado**: 5-10 minutos

### Configuración: Habilitar el registro de auditoría de Microsoft 365

En esta tarea de configuración, habilitará la capacidad Registro de auditoría de Microsoft 365.  Aunque la documentación indica que el registro de auditoría está habilitado de manera predeterminada, la mayoría de los inquilinos del laboratorio no tienen habilitada esta función y pueden pasar varias horas hasta que surta efecto.  Habilitar esta característica resulta útil, ya que Microsoft 365 utiliza los registros de auditoría para conseguir información sobre los usuarios y las actividades identificadas en las directivas y los análisis.

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.  

1. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **Auditoría**.  Nota: También se puede acceder a la capacidad de auditoría a través de la página principal de Microsoft 365 Defender (anteriormente denominada Centro de seguridad de Microsoft 365).

1. Compruebe que la pestaña **Nueva búsqueda** está seleccionada (subrayada).

1. Una vez que llegue a la página Auditoría, espere de 2 a 3 minutos.  Si Auditoría NO está habilitada, verá una barra azul en la parte superior de la página donde pone "Comenzar a registrar la actividad del usuario y del administrador".  Seleccione **Comenzar a registrar la actividad del usuario y del administrador**.  Si se le pide que confirme que la configuración de la organización debe actualizarse, seleccione **Sí**. Una vez habilitada Auditoría, la barra azul desaparecerá.  Si la barra azul no aparece, eso significará que la opción Auditoría ya está habilitada, y no necesitará hacer nada más.  Otra manera de comprobar si Auditoría está habilitada es a través de PowerShell, pero eso está fuera del ámbito de este curso.

1. Para volver a la página principal del Portal de cumplimiento de Microsoft Purview, seleccione **Inicio** en el panel de navegación izquierdo con el fin de cerrar sesión de Microsoft 365. Para cerrar sesión, seleccione el icono en la esquina superior derecha de la ventana de Microsoft 365 que se muestra como un círculo con las letras MA (junto al icono de signo de interrogación) y, a continuación, seleccione **Cerrar sesión**. Después, cierre el explorador.

### Revisar

En esta configuración, ha habilitado la funcionalidad de registro de auditoría de Microsoft 365.
