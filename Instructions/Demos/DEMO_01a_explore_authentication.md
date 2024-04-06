<!---
---
Demostración: Título: "Exploración de la configuración de usuario de Microsoft Entra ID" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Entra; Módulo 2: Descripción de las funcionalidades de autenticación de Microsoft Entra ID; Unidad 3: Descripción de los métodos de autenticación y Unidad 4: Descripción de la autenticación multifactor"
---
--->

# Demostración: métodos de autenticación y MFA

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra.
- Módulo 2: Descripción de las funcionalidades de autenticación de Microsoft Entra ID.
- Unidades: Descripción de los métodos de autenticación y Descripción de la autenticación multifactor.

## Supuesto de demostración

En esta demostración, explorará las distintas opciones de configuración disponibles para la autenticación en Microsoft Entra.

1. Vuelva a la pestaña abierta del explorador titulada "Inicio-Centro de administración de Microsoft Entra".  Si ha cerrado previamente esa pestaña del explorador, abra Microsoft Edge e inicie sesión en **[entra.microsoft.com](https://entra.microsoft.com)** con sus credenciales de administrador de Microsoft 365.

1. En el panel de navegación izquierdo, expanda **Protección** y seleccione **Métodos de autenticación**.

1. Al seleccionar métodos de autenticación se muestra la página de directivas.  Aquí verá los métodos de autenticación disponibles y si están habilitados.  Veremos algunos de estos métodos:  
    1. Seleccione **SMS**.  Lea la descripción en la parte superior de la página: "Este método de autenticación entrega un código de un solo uso a través de SMS al teléfono de un usuario y, a continuación, el usuario introduce ese código para iniciar sesión. SMS se puede usar para la autenticación multifactor y el autoservicio de restablecimiento de contraseña; también se puede configurar para que se use como primer factor."
        1. Un punto que se debe señalar aquí es que algunos métodos de autenticación se pueden usar para MFA o SSPR.  Algunos solo se pueden usar como forma principal de autenticación, mientras que otros solo se pueden usar como forma secundaria de autenticación.
        1. Para configurar un método de autenticación concreto, debe habilitarlo y después seleccionar los usuarios y/o grupos que desea incluir.  También puede seleccionar los grupos que se van a excluir.
        1. No cambie ninguna configuración.  Salga de la página de configuración de SMS seleccionando la **X** en la parte superior derecha de la página.  
    1. Echemos un vistazo a la configuración de llamadas de voz.  Seleccione **Llamada de voz**, en la descripción puede ver una diferencia importante.  Las llamadas de voz no se puede usar como método de autenticación de primer factor.
    1. Ahora seleccione **Microsoft Authenticator**.  Este es el principal método de autenticación.  
        1. Aquí habilitará las características y seleccionará a quién incluir.  Puede hacerlo para todos los usuarios o grupos. Una vez que haya identificado qué usuarios o grupos incluir, puede identificar grupos específicos que se van a excluir.  
        1. En la pestaña **Configurar**, puede seleccionar si Microsoft administra una característica específica. Esta configuración es una manera cómoda para que una organización permita que Microsoft habilite o deshabilite una característica de forma predeterminada. Esto puede ayudar a una organización a mejorar su posición de seguridad.
        1. No cambie ninguna configuración. Salga de la página, seleccionando la **X** en la esquina superior derecha de la página.
 
1. Ahora echemos un vistazo a la protección con contraseña. Seleccione **Protección con contraseña**.  Observe los diferentes parámetros de configuración disponibles.  
    1. Seleccione el icono de información situado junto a **Umbral de bloqueo** para ver el significado de este parámetro.  Actualmente está establecido en 10, lo que significa que puede haber hasta 10 inicios de sesión fallidos antes de que se bloquee la cuenta. Parece un poco alto, así que puede establecer un valor diferente.
    1. Seleccione el icono de información de cada uno de los diferentes parámetros y coméntelo brevemente.  Sobre todo querrá mencionar la lista personalizada de contraseñas prohibidas.

1. La intensidad de autenticación es un control de acceso condicional que permite a los administradores especificar qué combinación de métodos de autenticación se puede usar para acceder a un recurso. Verá esto en Acceso condicional.

1. En el panel de navegación izquierdo de Métodos de autenticación, seleccione **Actividad**.
    1. El **Registro** se muestra con un subrayado azul.  Aquí puede ver la actividad de registro para distintos métodos de autenticación.
    1. Seleccione **Uso** para ver los detalles de uso y tenga en cuenta que puede agregar diferentes filtros.

1. En este módulo también habló sobre la autenticación multifactor. Tratará más sobre el MFA en la demostración sobre el acceso condicional, pero quizá quiera tomarse un minuto para mostrar algunas configuraciones básicas.  En el panel de navegación del Centro de administración de Microsoft Entra, seleccione **Autenticación multifactor**.  Es posible que tenga que seleccionar **Mostrar más** en la sección Protección, en el panel de navegación izquierdo.
    1. En la página de **Introducción**, se muestra que la mejor forma de aplicarla a los usuarios es a través del acceso condicional, pero aquí se establecen algunas configuraciones específicas.
    1. Seleccione **Bloqueo de cuenta** y mencione los parámetros de bloqueo configurables.
    1. Seleccione **Bloquear o desbloquear usuarios**, señale que aquí es donde un administrador puede bloquear y desbloquear usuarios manualmente.  Recuerde que un usuario bloqueado permanecerá bloqueado durante 90 días a menos que se desbloquee manualmente.
    1. Seleccione **Alerta de fraude**.  De este modo, los administradores pueden permitir a los usuarios informar de un fraude si reciben una solicitud de verificación en dos pasos que ellos no han iniciado.
    1. Seleccione **Notificaciones**.  Puede configurar Microsoft Entra para enviar notificaciones por correo electrónico cuando los usuarios informen de alertas de fraude. Normalmente, estas notificaciones se envían a los administradores de identidad, ya que es probable que las credenciales de la cuenta del usuario estén en peligro.
    1. Salga de la página seleccionando la **X** en la esquina superior derecha de la ventana.  Después, repita este paso para volver al centro de administración de Microsoft Entra.

1. Mantenga abierta la pestaña del explorador, ya que volverá al centro de administración de Microsoft Entra para la siguiente demostración.

### Revisar

En esta demostración, ha mostrado los métodos de autenticación disponibles en Microsoft Entra.  También se muestran algunos de los parámetros configurables asociados a la autenticación multifactor.
