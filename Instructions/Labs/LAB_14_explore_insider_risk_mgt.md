---
lab:
  title: "Explorar la administración de riesgos internos en Microsoft\_Purview"
  module: Describe the data security solutions of Microsoft Purview
---

# Laboratorio: Explorar la administración de riesgos internos en Microsoft Purview

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Priva y Microsoft Purview
- Módulo: Descripción de las soluciones de seguridad de datos de Microsoft Purview
- Unidad: Descripción de la administración de riesgos internos en Microsoft Purview

## Escenario del laboratorio

En este laboratorio, te familiarizarás con el proceso de configurar una directiva de riesgos internos y los requisitos básicos previos para configurar y usar directivas de Administración de riesgos internos.  Nota: Este laboratorio únicamente abordará los requisitos necesarios para configurar la Administración de riesgos internos y las opciones relativas a la creación de directivas.  Este laboratorio no incluye la tarea de desencadenar la directiva, ya que el número de eventos que tendrían que producirse para desencadenar una directiva y el tiempo requerido quedan fuera del ámbito de este ejercicio.

**Tiempo estimado**: 60 minutos

### Tarea 1

En esta tarea, explorará los distintos permisos de rol para Administración de riesgos internos y comprobará que ya se han incluido usuarios específicos en el grupo de roles Administración de riesgos internos. Asegurarse de que los usuarios tengan los permisos de rol adecuados garantiza que los usuarios designados puedan acceder a las características de administración de riesgos internos y administrarlos. Al agregar miembros a un grupo de roles, los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios de toda la organización.

1. Abre la pestaña del explorador para la página principal de Microsoft Purview.  Si la habías cerrado, abre otra y escribe **https://admin.microsoft.com** . Inicia sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). 

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Microsoft Purview**.  Se abrirá una nueva página del explorador con la página principal del Portal de Microsoft Purview.  

1. En el panel de navegación izquierdo, selecciona **Configuración**, expande **Roles y ámbitos** y, después, selecciona **Grupos de roles**.

1. En el campo de búsqueda, en la parte superior derecha de la página, escribe **Riesgo interno** y presiona Entrar en el teclado.  Observa los numerosos roles que aparecen.  Cada uno de ellos tiene diferentes niveles de acceso.  Selecciona **Administración de riesgos internos** y revisa la descripción.  Desplázate hacia abajo hasta donde se muestran los miembros y observa que se muestran el administrador MOD y Megan Bowen. Cierre la ventana con la **X** de la esquina superior derecha de la ventana.

1. En el panel de navegación izquierdo, selecciona **Inicio** para volver a la página del portal de Microsoft Purview.

1. Mantén esta ventana del navegador abierta, ya que volverás a ella en una tarea posterior.

### Tarea 2

En esta tarea explorarás las opciones relativas a la solución Administración de riesgos internos.  La configuración de administración de riesgos internos se aplica a todas las directivas de administración de riesgos internos, independientemente de la plantilla que elijas al crear una directiva.

1. Deberías encontrarte en la página principal del portal de Microsoft Purview.

1. Antes de empezar a configurar una directiva, hay algunas opciones con las que un administrador debe estar familiarizado y configurarlas según sea necesario para la organización. En el panel de navegación izquierdo, selecciona **Configuración** y, después, selecciona **Administración de riesgos internos**.  Aquí explorarás algunas de las opciones de configuración disponibles.
    1. Selecciona **Privacidad**: para los usuarios que realizan actividades que coinciden con sus directivas de riesgos internos, esta configuración determinará si se deben mostrar los nombres reales o usar versiones anónimas para ocultar su identidad.  Para este tutorial, puedes dejar la configuración predeterminada.
    1. Selecciona **Indicadores de directiva**. Cuando se produzca un evento de desencadenamiento de directiva, las actividades que se asignan a los indicadores seleccionados se usan para determinar la puntuación de riesgo para el usuario. Los indicadores de directiva seleccionados aquí se incluyen las plantillas de directiva de riesgo interno.  Desplázate para ver todos los indicadores disponibles y cualquier información asociada.  En **Indicadores de Office**, seleccione **Seleccionar todo**. Las opciones que seleccione en esta pantalla se incluyen en las plantillas de directiva.
    1. Selecciona **Períodos de tiempo de directiva**. Los períodos de tiempo que elijas aquí entrarán en vigor para un usuario cuando desencadenen una coincidencia para una directiva de riesgo interno.   La ventana Activación determina durante cuánto tiempo detectarán activamente la actividad de los usuarios y se desencadena cuando un usuario realiza la primera actividad que coincide con una directiva. La detección de actividad pasada determina cuánto debe remontarse hacia atrás una directiva para detectar la actividad del usuario y se desencadena cuando un usuario realiza la primera actividad que coincide con una directiva.  Deja los valores predeterminados.
    1. Selecciona **Detecciones inteligentes**. Revisa las opciones aquí.  Ten en cuenta la configuración de dominios y cómo se relacionan con los indicadores.
    1. Explora los otros elementos que aparecen en la configuración y observa que muchos de ellos están en versión preliminar.

1. En el panel de navegación izquierdo, selecciona **Soluciones** y, después, selecciona **Administración de riesgos internos**.

1. Deja esta pestaña del explorador abierta, porque la utilizarás en la siguiente tarea.

### Tarea 3

Al crear una directiva para Administración de riesgos internos, tiene dos opciones: una directiva rápida o una directiva personalizada. La configuración rápida de directivas se rellena automáticamente a partir de los procedimientos recomendados o en los resultados del examen de análisis más reciente de la organización.  En esta tarea, se familiarizará con la configuración para crear una directiva personalizada. El objetivo es simplemente hacerse una idea de las distintas opciones y flexibilidad asociadas a la creación de una directiva.

1. Debes estar en la página de información general de administración de riesgos internos.  Si no estás ahí, selecciona **Soluciones** en el panel de navegación izquierdo y, después, selecciona **Administración de riesgos internos**.

1. En la página de información general de Administración de riesgos internos, seleccione la pestaña **Directivas**, luego seleccione **+Crear directiva** y, a continuación, elija **Directiva personalizada**. Configura cada una de las siguientes pestañas de directiva.

    1. Plantilla de directiva: en la categoría Pérdidas de datos, selecciona **Pérdidas de datos**.  Lee los detalles asociados a esta plantilla. En los requisitos previos, la directiva DLP se muestra con una marca de verificación en un círculo verde para indicar que se cumple el requisito previo.  Hay una directiva DLP preconfigurada para este inquilino de laboratorio. Seleccione **Siguiente**.
    1. Nombre y descripción: escriba un nombre **`SC900-InsiderRiskPolicy`** y, a continuación, seleccione **Siguiente**.
    1. Usuarios y grupos: revisa el cuadro de información.  Deja la configuración predeterminada, **Incluir todos los usuarios y grupos**.  Seleccione **Siguiente**.
    1. Excluir usuarios y grupos (opcional): aquí puede enumerar los usuarios y grupos que se van a excluir. No hagas ningún cambio. Selecciona **Siguiente**.
    1. Contenido para priorizar: según la descripción, se aumentan las puntuaciones de riesgo para cualquier actividad que contenga contenido de prioridad, lo que a su vez aumenta la posibilidad de generar una alerta de gravedad alta. Para simplificar, selecciona **No quiero priorizar el contenido en este momento** y, a continuación, selecciona **Siguiente**.
    1. Desencadenadores: el evento desencadenador determina cuándo comenzará una directiva a asignar puntuaciones de riesgo a la actividad de un usuario.  Puedes elegir entre una directiva DLP existente o si el usuario realiza una actividad de filtración. Selecciona **Usuario coincide con una directiva de prevención de pérdida de datos (DLP)** y, a continuación, en la lista desplegable, selecciona **Datos financieros de EE. UU.** Seleccione **Siguiente**.
    1. Indicadores: expanda **Indicadores de Office**. Observe que ya se ha seleccionado el área de indicadores de Office, que se basa en la configuración de la tarea anterior.  Puede anular la selección de algunos indicadores seleccionados o agregar otros nuevos seleccionando "Elegir indicadores". Para este ejercicio, deje la configuración actual y seleccione **Siguiente**.
    1. En la página Opciones de detección, deja todas las opciones predeterminadas, pero lee la descripción asociada a las distintas opciones y mantén el puntero sobre el icono de información para obtener información más detallada sobre una configuración específica.  Selecciona **Siguiente**.
    1. En la página para Decidir si deseas usar umbrales predeterminados o de indicador de cliente, deja el valor predeterminado **Aplicar umbrales proporcionados por Microsoft** y, a continuación, selecciona **Siguiente**.
    1. Para terminar, revisa la configuración, selecciona **Enviar**.
    1. Revisa la descripción de lo que sucede a continuación y selecciona **Listo**.

1. Has vuelto a la pestaña Directivas de la página Administración de riesgos internos.  La directiva que has creado aparecerá en la lista.  Si no la ves, selecciona el icono **Actualizar**.

1. Como administrador, puedes empezar inmediatamente a asignar puntuaciones de riesgo a los usuarios en función de la actividad detectada por las directivas seleccionadas. Esto omite el requisito de que se detecte primero un evento desencadenador (como una coincidencia de directiva DLP).  Un administrador puede hacerlo seleccionando el cuadrado vacío junto al nombre de la directiva para seleccionarla, y luego selecciona la opción **Empezar a puntuar la actividad de los usuarios** que aparece encima de la tabla de directivas.  Se abre una nueva ventana que requiere que el administrador rellene los campos disponibles. Deja los campos vacíos, ya que no configurarás esta opción, pero para obtener más información sobre por qué un administrador desea hacerlo, selecciona **¿Por qué haría esto?**  Cierra la ventana con la **X** de la esquina superior derecha de la ventana.

1. En el panel de navegación izquierdo, selecciona **Inicio** para volver a la página de aterrizaje del portal de Microsoft Purview.

1. Deja abierta la pestaña del explorador.

### Revisar

En este laboratorio, te familiarizaste con el proceso de configurar una directiva de riesgos internos y los requisitos básicos previos para configurar y usar directivas de administración de riesgos internos.
