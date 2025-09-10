---
lab:
  title: Configuración del laboratorio
  module: Setup your Microsoft 365 lab tenant (not associated with a Learn module)
---

# Laboratorio: Configuración del inquilino de Microsoft 365

## Inquilinos de WWL: términos de uso
Si se te proporciona un inquilino porque estás realizando un curso dirigido por un instructor, ten en cuenta que ese inquilino está disponible únicamente como apoyo para los laboratorios prácticos del curso.

Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino usado en este curso es un inquilino de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y no es apto para la extensión.

Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento.

## Escenario del laboratorio

Este laboratorio de configuración consta de habilitar las funcionalidades de supervisión de archivos y registro de auditoría de Microsoft en el inquilino de Microsoft 365.

**Tiempo estimado**: 10-15 minutos

### Configuración: habilitación del registro de auditoría y la supervisión de archivos de Microsoft 365

En esta tarea de configuración, habilitarás las funcionalidades de registro de auditoría y supervisión de archivos de Microsoft 365.  

1. Abre Microsoft Edge. En la barra de direcciones, escribe **`https://admin.microsoft.com`**.

1. Inicia sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, selecciona **Mostrar todo**.

1. En Centros de administración, selecciona **Seguridad**.  Se abrirá una nueva página del explorador con la página de bienvenida de Microsoft Defender.

1. En el panel de navegación izquierdo, desplázate hacia abajo y expande **Sistema**.  Selecciona **Auditoría** en la lista expandida.  Nota: la funcionalidad de auditoría también es accesible a través del portal de Microsoft Defender.

1. Una vez que llegues a la página Auditoría, espera de 1 a 2 minutos.  Si Auditoría NO está habilitada, verás una barra azul en la parte superior de la página donde pone "Comenzar a registrar la actividad del usuario y del administrador".  Selecciona **Comenzar a registrar la actividad del usuario y del administrador**.  Una vez habilitada Auditoría, la barra azul desaparecerá.  Si la barra azul no aparece, eso significará que la opción Auditoría ya está habilitada, y no necesitarás hacer nada más.  Si ves un mensaje, "Lo sentimos, tenemos problemas para averiguar si se está grabando la actividad. Pruebe a actualizar la página". Si, después de actualizar la página, no hay cambios, deberá habilitar la auditoría a través de PowerShell.
    1. Haz clic con el botón derecho en el icono Windows PowerShell en la barra de tareas y selecciona **Ejecutar como administrador**.
    1. Instale el módulo Exchange Online PowerShell con **`Install-Module -Name ExchangeOnlineManagement`**.  Cuando se le pregunte "¿Está seguro de que desea instalar los módulos desde 'PSGallery'", seleccione **`[A]` Sí a Todo**.
    1. Ahora, carga el módulo; para ello, escribe **`Import-Module ExchangeOnlineManagement`**.
    1. Para conectar, escribe **`Connect-ExchangeOnline -UserPrincipalName admin@WWLxZZZZZZ.onmicrosoft.com`**.  Para el UPN, escribe el nombre de usuario del administrador que se encuentra en la pestaña recursos del laboratorio.
    1. Se le solicitará que inicie sesión.  Escribe el nombre de usuario administrativo y la contraseña que se encuentran en la pestaña recursos del laboratorio.
    1. Para activar la auditoría, escribe **`Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true`**. Se muestra un mensaje que indica que el cambio podría tardar hasta 60 minutos en surtir efecto.
    1. Aunque puede tardar hasta 60 minutos en surtir efecto, puedes comprobar que el comando se recibió si escribes **`Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled`**.  Si la auditoría está habilitada, la propiedad UnifiedAuditLogIngestionEnabled mostrará un valor de verdadero.

1. En el panel de navegación de la izquierda, en Sistema, selecciona **Configuración**.

1. En la página de configuración, selecciona **Aplicaciones en la nube**.   Desplázate hacia abajo y en **Information Protection**, selecciona **Archivos**.

1. Si aún no está habilitado, selecciona la casilla situada junto a donde dice **Habilitar supervisión de archivos** y, después, selecciona **Guardar**.  

1. Esto concluye la configuración del laboratorio en el inquilino de Microsoft 365.
1. Puede cerrar la pestaña del explorador, "Cloud Apps-Microsoft Defender", pero mantenga abierta la pestaña "Centro de administración de Microsoft 365" para el ejercicio siguiente.

### Revisar

En esta configuración, has habilitado las funcionalidades de registro de auditoría y supervisión de archivos de Microsoft 365.
