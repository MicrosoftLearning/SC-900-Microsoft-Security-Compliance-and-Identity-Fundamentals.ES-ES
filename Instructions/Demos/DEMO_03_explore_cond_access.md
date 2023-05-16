---
demo:
  title: 'Acceso condicional de Azure AD'
  module: 'Módulo 3: "Descripción de las funcionalidades de administración de acceso de Azure AD'
---



# <a name="demo-azure-ad-conditional-access"></a>Demostración: Acceso condicional de Azure AD

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Azure Active Directory (Azure AD), parte de Microsoft Entra
- Módulo: Descripción de las funcionalidades de administración de acceso de Azure AD
- Unidad: Descripción del acceso condicional en Azure AD

## <a name="demo-scenario"></a>Escenario de la demo

En esta demo, realizará un recorrido por las diferentes opciones disponibles para una directiva de acceso condicional.

1. Vaya a la pestaña de **Microsoft Azure: Contoso** que hay abierta en su explorador. Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba portal.azure.com y seleccione Azure Active Directory. Debería haber iniciado sesión como administrador en Azure Portal; si no es así, vuelva a iniciar sesión.

1. En el panel de navegación izquierdo, seleccione **Seguridad**.

1. En el panel de navegación izquierdo, seleccione **Acceso condicional**.

1. Se mostrará la pantalla Directivas de acceso condicional. Cualquier directiva de acceso condicional existente se mostrará en esta página. Para mostrar la configuración asociada con el acceso condicional, seleccione **+ Nueva directiva**.

1. En el campo **Nombre**, tiene que escribir un nombre para la directiva.

1. Observe que hay varias opciones debajo de **Evaluaciones**.  Dado que las directivas de acceso condicional son similares a las instrucciones if/then, la configuración de las evaluaciones es similar a las instrucciones "if".
    1. **Usuarios y grupos**: mantenga el puntero sobre el icono de información que hay junto a la opción “Usuarios y grupos” y haga hincapié que aquí es donde se configuran los usuarios y los grupos del directorio al que se aplica la directiva. Seleccione **0 usuarios y grupos seleccionados**.  Ahora verá la opción para incluir o excluir usuarios y grupos. Seleccione y haga énfasis en la configuración disponible en la pestaña **Incluir** y luego seleccione y comente la configuración disponible en la pestaña **Excluir**.
    1. **Aplicaciones en la nube o acciones**: mantenga el puntero sobre el icono de información que hay junto a "Aplicaciones en la nube o acciones" y comente que aquí es donde se configuran las aplicaciones usadas y las acciones realizadas por el usuario para la directiva de acceso condicional.  Seleccione **No se ha seleccionado ninguna aplicación o acción ni ningún contexto de autenticación**.
        1. Seleccione la flecha desplegable que aparece en el cuadro inferior con el texto **Seleccione a qué se aplica esta directiva** y observe las opciones.  Deje la configuración predeterminada: Aplicaciones en la nube.
        1. Seleccione y comenta la configuración disponible para la pestaña Incluir. Debajo de la pestaña **Incluir**, seleccione **Seleccionar aplicaciones**.  Observe la ventana que se abre y en la que puede seleccionar aplicaciones de una lista.  No seleccione nada. Para cerrar esta ventana, seleccione la **X** en la esquina superior derecha de la ventana. Vuelva a seleccionar **Ninguno** para quitar el error.
        1. Luego seleccione y comente la configuración disponible en la **pestaña Excluir**.  Aquí puede volver a seleccionar aplicaciones específicas para excluirlas.
    1. **Condiciones**: mantenga el puntero sobre el icono de información que hay junto a "Condiciones" y haga hincapié en que esta opción establece cuándo se aplicará la directiva. Seleccione **0 condiciones seleccionadas**. Aborde las diferentes “señales” que se enumeran en la lista.   Seleccione algunas de las opciones. Para ello, seleccione primero el icono de información para definir qué es y luego seleccione **No configurado** para que el elemento específico muestre las diferentes opciones.
        1. **Riesgo de usuario**: un riesgo de usuario representa la probabilidad de que una identidad o cuenta determinada esté en peligro. Los riesgos se calculan sin conexión, usando orígenes de inteligencia sobre amenazas internos y externos de Microsoft.
        1. **Riesgo de inicio de sesión**: un riesgo de inicio de sesión representa la probabilidad de que el propietario de la identidad no haya autorizado una solicitud de autenticación determinada. Los ejemplos pueden incluir el inicio de sesión desde una dirección IP anónima, un viaje atípico, etc.
        1. **Plataforma del dispositivo**: la plataforma desde la que inicia sesión el usuario; por ejemplo, 'iOS’.
        1. **Ubicación**: la ubicación (determinada mediante el intervalo de direcciones IP) desde la que el usuario inicia sesión.
        1. **Aplicaciones cliente**: el software que emplea el usuario para acceder a la aplicación en la nube; por ejemplo, 'Explorador’.
        1. **Filtrar por dispositivos**: al crear directivas de acceso condicional, los administradores pueden dirigirse a dispositivos específicos en su entorno o excluirlos. El administrador puede dirigirse a dispositivos específicos mediante operadores admitidos, propiedades para filtros del dispositivo y otras condiciones de asignación disponibles en las directivas de acceso condicional.

1. **Controles de acceso**: si volvemos a la analogía de que las directivas de acceso condicional son como instrucciones if/then, los controles de acceso serían similares a la instrucción “then”.
    1. **Concesión**: mantenga el puntero sobre el icono de información que hay junto a “Concesión” para ver la descripción.  Seleccione **0 controles seleccionados** para mostrar las diferentes opciones.  Comente algunas de ellas.  Llame específicamente a la opción **Requerir autenticación multifactor** que aparece debajo de Conceder acceso y a cómo se puede utilizar para dar un control detallado respecto a cuándo requerir la MFA.   Haga referencia también a la posibilidad de configurar varios controles y de requerir todos o solo uno de los seleccionados.
    1. **Sesión**: mantenga el puntero sobre el icono de información que hay junto a la palabra "Sesión" para ver la descripción.  Haga énfasis en que los controles de sesión permiten limitar la experiencia en una aplicación en la nube.  Por ejemplo, es posible que el usuario pueda acceder a la aplicación en la nube, pero las opciones para descargar cualquier tipo de contenido o imprimir estarán bloqueadas.  Se trata de un tema más complejo, así que procure no complicar excesivamente la explicación.

1. Para habilitar una directiva después de configurarla, seleccione **Activar** y después presione el botón **Crear** para crear una directiva.

1. Seleccione la **X** en la esquina superior derecha de la página para cerrar la directiva y después seleccione Microsoft Azure en la barra azul de la parte superior de la página para volver a la página principal de Azure Portal.

1. Mantenga la página del explorador abierta para la siguiente demo.

### <a name="review"></a>Revisar

En esta demostración, ha realizado un recorrido por las diferentes opciones disponibles para una directiva de acceso condicional.
