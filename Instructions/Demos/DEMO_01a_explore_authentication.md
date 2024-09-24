<!---
---
Demo: Título: "Exploración de la configuración de usuario de Microsoft Entra ID" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Entra; Módulo 2: Descripción de las funcionalidades de autenticación de Microsoft Entra ID; Unidad 3: Descripción de los métodos de autenticación y Unidad 4: Descripción de la autenticación multifactor"
---
--->

# Demo: métodos de autenticación y MFA

Esta demo está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra.
- Módulo 2: Descripción de las funcionalidades de autenticación de Microsoft Entra ID.
- Unidades: Descripción de los métodos de autenticación y Descripción de la autenticación multifactor.

## Supuesto de demostración

En esta demostración, explorará las distintas opciones de configuración disponibles para la autenticación en Microsoft Entra.

1. Vuelve a la pestaña abierta del explorador titulada "Inicio-Centro de administración Microsoft Entra".  Si has cerrado previamente esa pestaña del explorador, abre Microsoft Edge e inicia sesión en **[entra.microsoft.com](https://entra.microsoft.com)** con tus credenciales de administrador de Microsoft 365.

1. En el panel de navegación izquierdo, expande **Protección** y selecciona **Métodos de autenticación**.

1. Al seleccionar métodos de autenticación se muestra la página de directivas.  Aquí verás los métodos de autenticación integrados disponibles y si están habilitados.  Veremos algunos de estos métodos:  

    1. Seleccione **Microsoft Authenticator**.  Este es el principal método de autenticación.  
        1. Aquí habilitarás las características y seleccionarás a quién incluir.  Puedes hacerlo para todos los usuarios o grupos. Una vez que hayas identificado qué usuarios o grupos incluir, puedes identificar grupos específicos que se van a excluir.  
        1. En la pestaña **Configurar**, puedes seleccionar si Microsoft administra una característica específica. Esta configuración es una manera cómoda para que una organización permita que Microsoft habilite o deshabilite una característica de forma predeterminada. Esto puede ayudar a una organización a mejorar su posición de seguridad.
        1. No cambies ninguna configuración. Sal de la página, seleccionando la **X** en la esquina superior derecha de la página.

    1. Seleccione **SMS**.  Lea la descripción en la parte superior de la página: "Este método de autenticación entrega un código de un solo uso a través de SMS al teléfono de un usuario y, a continuación, el usuario introduce ese código para iniciar sesión. SMS se puede usar para la autenticación multifactor y el autoservicio de restablecimiento de contraseña; también se puede configurar para que se use como primer factor."
        1. Un punto que se debe señalar aquí es que algunos métodos de autenticación se pueden usar para MFA o SSPR.  Algunos solo se pueden usar como forma principal de autenticación, mientras que otros solo se pueden usar como forma secundaria de autenticación.
        1. Para configurar un método de autenticación concreto, debe habilitarlo y después seleccionar los usuarios y/o grupos que desea incluir.  También puede seleccionar los grupos que se van a excluir.
        1. No cambies ninguna configuración.  Salga de la página de configuración de SMS seleccionando la **X** en la parte superior derecha de la página.  
    1. Echemos un vistazo a la configuración de llamadas de voz.  Seleccione **Llamada de voz**, en la descripción puede ver una diferencia importante.  Las llamadas de voz no se puede usar como método de autenticación de primer factor. Sal de la página, seleccionando la **X** en la esquina superior derecha de la página.

 
1. Ahora, en la página Métodos de autenticación, echemos un vistazo a la protección con contraseña. Selecciona **Protección con contraseña**.  Observa los diferentes parámetros de configuración disponibles.  
    1. Selecciona el icono de información situado junto a **Umbral de bloqueo** para ver el significado de este parámetro.  Actualmente está establecido en 10, lo que significa que puede haber hasta 10 inicios de sesión fallidos antes de que se bloquee la cuenta. Parece un poco alto, así que puedes establecer un valor diferente.
    1. Selecciona el icono de información de cada uno de los diferentes parámetros y coméntalo brevemente.  Sobre todo querrás mencionar la lista personalizada de contraseñas prohibidas.

1. En la página Métodos de autenticación, selecciona **Niveles de intensidad de autenticación**.  Los niveles de intensidad de autenticación es un control de acceso condicional que permite a los administradores especificar qué combinación de métodos de autenticación se puede usar para acceder a un recurso. Verás esto en Acceso condicional.  Selecciona **Nuevos niveles de intensidad de autenticación** para ver las opciones disponibles. No cambies nada.  Cierre la ventana Nuevos niveles de intensidad de autenticación.

1. En la página Métodos de autenticación, selecciona **Actividad**.
    1. El **Registro** se muestra con un subrayado azul.  Aquí puedes ver la actividad de registro para distintos métodos de autenticación.
    1. Selecciona **Uso** para ver los detalles de uso y ten en cuenta que puedes agregar diferentes filtros.

1. En este módulo también hablaste sobre la autenticación multifactor. Tratarás más sobre el MFA en la demo sobre el acceso condicional, pero quizá quieras tomarte un minuto para mostrar algunas configuraciones básicas.  En el panel de navegación del Centro de administración Microsoft Entra, en Protección, selecciona **Autenticación multifactor**.  Es posible que tengas que seleccionar **Mostrar más** en la sección Protección, en el panel de navegación izquierdo.
    1. En la página de **Introducción**, se muestra que la mejor forma de aplicarla a los usuarios es a través del acceso condicional, pero aquí se establecen algunas configuraciones específicas.
    1. Selecciona **Bloqueo de cuenta** y menciona los parámetros de bloqueo configurables.
    1. Selecciona **Bloquear o desbloquear usuarios**, señala que aquí es donde un administrador puede bloquear y desbloquear usuarios manualmente.  Recuerda que un usuario bloqueado permanecerá bloqueado durante 90 días a menos que se desbloquee manualmente.
    1. Selecciona **Alerta de fraude**.  De este modo, los administradores pueden permitir a los usuarios informar de un fraude si reciben una solicitud de verificación en dos pasos que ellos no han iniciado.
    1. Selecciona **Notificaciones**.  Puedes configurar Microsoft Entra para enviar notificaciones por correo electrónico cuando los usuarios informen de alertas de fraude. Normalmente, estas notificaciones se envían a los administradores de identidad, ya que es probable que las credenciales de la cuenta del usuario estén en peligro.
    1. Sal de la página seleccionando la **X** en la esquina superior derecha de la ventana.  Después, repite este paso para volver al Centro de administración Microsoft Entra.

1. Mantén abierta la pestaña del explorador, ya que volverás al Centro de administración Microsoft Entra para la siguiente demo.

### Revisar

En esta demostración, has mostrado los métodos de autenticación disponibles en Microsoft Entra.  También se muestran algunos de los parámetros configurables asociados a la autenticación multifactor.
