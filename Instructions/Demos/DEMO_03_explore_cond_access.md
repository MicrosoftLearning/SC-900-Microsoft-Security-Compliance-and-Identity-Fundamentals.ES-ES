<!---
---
Demostración: Título: Ruta de aprendizaje/Módulo/Unidad "Acceso condicional de Azure AD": "Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Entra; Módulo 3: Descripción de las funcionalidades de administración de acceso de Microsoft Entra ID; Unidad 2: Descripción del acceso condicional"
---
--->

# Demostración: Acceso condicional de Microsoft Entra

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra
- Módulo: Descripción de las capacidades de administración de acceso de Microsoft Entra ID
- Unidad: Descripción del acceso condicional

## Supuesto de demostración

En esta demo, realizará un recorrido por las diferentes opciones disponibles para una directiva de acceso condicional.

1. Vuelva a la pestaña abierta del explorador titulada "Inicio-Centro de administración de Microsoft Entra".  Si ha cerrado previamente esa pestaña del explorador, abra Microsoft Edge e inicie sesión en **[entra.microsoft.com](https://entra.microsoft.com)** con sus credenciales de administrador de Microsoft 365.

1. En el panel de navegación izquierdo, expanda **Protección** y, a continuación, seleccione **Acceso condicional**.

1. Se muestra la página de información general sobre el acceso condicional.  Aquí verá iconos que muestran el resumen de la directiva y las alertas generales.  En el panel de navegación izquierdo, seleccione **Directivas**.

1. Se muestra la pantalla Directivas de acceso condicional. Aquí se enumeran las directivas de acceso condicional existentes. Para mostrar la configuración asociada al acceso condicional, seleccione **+ Nueva directiva**.

1. En el campo **Nombre**, tiene que escribir un nombre para la directiva.

1. Tenga en cuenta que tiene varias opciones bajo **Asignaciones**.  Como las directivas de acceso condicional son como instrucciones if/then, la configuración de las asignaciones son similares a las instrucciones "if".
    1. **Usuarios**: mantenga el puntero sobre el icono de información que hay junto a la opción “Usuarios” y haga hincapié en que aquí es donde se seleccionan las identidades del directorio al que se aplica la directiva, incluidos los usuarios, los grupos y las entidades de servicio. Seleccione **0 usuarios y grupos seleccionados**.  Ahora verá la opción para incluir o excluir usuarios y grupos. Seleccione y señale la configuración disponible para la pestaña **Incluir** y, a continuación, seleccione y hable de las configuraciones disponibles para la pestaña **Excluir** .
    1. **Recursos de destino**: seleccione **Recursos de destino**.  Aquí se controla el acceso en función de todo el tráfico de acceso a la red, las aplicaciones en la nube o las acciones específicas.  Expanda el campo que se encuentra debajo donde se le dice que seleccione a qué se aplica esta directiva.  Aquí puede seleccionar si la directiva se aplica a aplicaciones en la nube, acciones de usuario o un contexto de autenticación.  
        1. Seleccione **Aplicaciones en la nube** y, en la pestaña Incluir, seleccione la opción **Seleccionar aplicaciones**. Después, debajo de donde se indica **Seleccionar**, seleccione **Ninguna**. Se abrirá una ventana para seleccionar una o varias de las aplicaciones a las que se aplicará la directiva.
        1. Seleccione la **X** de la esquina superior derecha de la ventana para cerrar la ventana Seleccionar aplicaciones en la nube.
        1. Como el tiempo le permite elegir pasar por las otras opciones (acciones de usuario y contexto de autenticación) para ver las opciones de configuración de cada una.
    1. **Condiciones**: mantenga el puntero sobre el icono de información que hay junto a "Condiciones" y haga hincapié en que esta opción establece condiciones que definen cuándo se aplicará la directiva. Por ejemplo, "ubicación". Seleccione **0 condiciones seleccionadas**. Hable de las diferentes "señales" enumeradas.   Seleccione algunas de las opciones, primero seleccione el icono de información para definir lo que es y, a continuación, seleccione **No configurado** para el elemento específico para mostrar las distintas opciones.
        1. **Riesgo de usuario**: un riesgo de usuario representa la probabilidad de que una identidad o cuenta determinada esté en peligro. Los riesgos se calculan sin conexión, usando orígenes de inteligencia sobre amenazas internos y externos de Microsoft.
        1. **Riesgo de inicio de sesión**: un riesgo de inicio de sesión representa la probabilidad de que el propietario de la identidad no haya autorizado una solicitud de autenticación determinada. Los ejemplos pueden incluir que el inicio de sesión procede de una dirección IP anónima o de un viaje atípico, etc.
        1. **Plataforma del dispositivo**: la plataforma desde la que inicia sesión el usuario; Por ejemplo, "iOS".
        1. **Ubicación**: la ubicación (determinada mediante el intervalo de direcciones IP) desde la que el usuario inicia sesión.
        1. **Aplicaciones cliente**: el software que emplea el usuario para acceder a la aplicación en la nube; Por ejemplo, "Explorador"
        1. **Filtrar por dispositivos**: al crear directivas de acceso condicional, los administradores pueden dirigirse a dispositivos específicos en su entorno o excluirlos. El administrador puede dirigirse a dispositivos específicos mediante operadores admitidos, propiedades para filtros del dispositivo y otras condiciones de asignación disponibles en las directivas de acceso condicional.

1. **Controles de acceso**: volviendo a la analogía de que las directivas de acceso condicional son como las instrucciones if/then, los controles de acceso son análogos a la instrucción "then".
    1. **Concesión**: mantenga el puntero sobre el icono de información que hay junto a “Concesión” para ver la descripción.  Seleccione **0 controles seleccionados** para mostrar las distintas opciones.  Hable de algunos de ellos.  Llame específicamente a la opción **Requerir autenticación multifactor** que aparece debajo de Conceder acceso y a cómo se puede utilizar para dar un control detallado respecto a cuándo requerir la MFA.   Señale también que puede establecer varios controles y requerir todos o solo uno de los seleccionados.
    1. **Sesión**: mantenga el puntero sobre el icono de información que hay junto a la palabra "Sesión" para ver la descripción.  Señale que los controles de sesión habilitan la experiencia limitada desde una aplicación en la nube.  Por ejemplo, es posible que el usuario pueda acceder a la aplicación en la nube, pero las opciones para descargar cualquier tipo de contenido o imprimir estarán bloqueadas.  Este es un tema más complejo, por lo hagálo lo más sencillo posible.

1. Una vez configurada una directiva, puede habilitar una directiva al seleccionar **Activar**, a continuación, pulse el botón **Crear** para crear una directiva.

1. Seleccione la **X** de la esquina superior derecha de la página para cerrar la directiva.

1. Cierre las pestañas abiertas del explorador.

### Revisar

En esta demostración, ha realizado un recorrido por las diferentes opciones disponibles para una directiva de acceso condicional.
