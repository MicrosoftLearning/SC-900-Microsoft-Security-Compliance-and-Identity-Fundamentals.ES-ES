---
lab:
  title: "Explorar la administración de riesgos internos en Microsoft\_Purview"
  module: Describe the insider risk capabilities in Microsoft Purview
---

# Laboratorio: Explorar la administración de riesgos internos en Microsoft Purview

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de las funcionalidades de riesgo interno en Microsoft Purview
- Unidad: Descripción de la administración de riesgos internos

## Escenario del laboratorio

En este laboratorio, se familiarizará con el proceso de configurar una directiva de riesgos internos y los requisitos básicos previos para configurar y usar directivas de Administración de riesgos internos.  Nota: Este laboratorio únicamente abordará los requisitos necesarios para configurar la Administración de riesgos internos y las opciones relativas a la creación de directivas.  Este laboratorio no incluye la tarea de desencadenar la directiva, ya que el número de eventos que tendrían que producirse para desencadenar una directiva y el tiempo requerido quedan fuera del ámbito de este ejercicio.

**Tiempo estimado**: 60 minutos

### Tarea 1

En esta tarea, como administrador global, habilitará los permisos para la administración de riesgos internos.  En concreto, agregará usuarios al grupo de roles de Administración de riesgos internos para asegurarse de que los usuarios designados pueden acceder y administrar las características de administración de riesgos internos.  Los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios de toda la organización.

1. Abra la pestaña del explorador para la página principal de Microsoft Purview.  Si la había cerrado, abra otra y escriba **https://admin.microsoft.com** . Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de Microsoft Purview.  

1. En el panel de navegación izquierdo, selecciona **Configuración**, expande **Roles y ámbitos** y, después, selecciona **Grupos de roles**.

1. En el campo de búsqueda, en la parte superior derecha de la página, escribe **Riesgo interno** y presiona Entrar en el teclado.  Observe los numerosos roles que aparecen.  Cada uno de ellos tiene diferentes niveles de acceso.  Seleccione **Administración de riesgos internos** y revise la descripción.  Desplácese hacia abajo hasta donde se muestran los miembros y observe que se muestran el administrador de MOD y Megan Bowen. Cierre la ventana con la **X** de la esquina superior derecha de la ventana.

1. En el panel de navegación izquierdo, selecciona **Inicio** para volver a la página del portal de Microsoft Purview.

1. Mantenga esta ventana del navegador abierta, ya que volverá a ella en una tarea posterior.

### Tarea 2

En esta tarea explorará las opciones relativas a la solución Administración de riesgos internos.  La configuración de administración de riesgos internos se aplica a todas las directivas de administración de riesgos internos, independientemente de la plantilla que elija al crear una directiva.

1. Deberías encontrarte en la página principal del portal de Microsoft Purview. Si no es así, seleccione la pestaña del explorador **Inicio: Cumplimiento de Microsoft 365**.

1. Antes de empezar a configurar una directiva, hay algunas opciones con las que un administrador debería estar familiarizado y configurar según sea necesario para la organización. En el panel de navegación izquierdo, selecciona **Configuración** y, después, selecciona **Administración de riesgos internos**.  Aquí explorarás algunas de las opciones de configuración disponibles.
    1. Selecciona **Privacidad**: para los usuarios que realizan actividades correspondientes a sus directivas de riesgos internos, esta configuración determinará si se deben mostrar sus nombres reales o usar versiones anónimas para ocultar sus identidades.  Para este tutorial, puede dejar la configuración predeterminada.
    1. Selecciona **Indicadores de directiva**. Cuando se produzca un evento de desencadenamiento de directiva, las actividades que se asignan a los indicadores seleccionados se usan para determinar la puntuación de riesgo para el usuario. Los indicadores de directiva seleccionados aquí se incluyen las plantillas de directiva de riesgo interno.  Desplácese para ver todos los indicadores disponibles y cualquier información asociada. 
    1. Selecciona **Períodos de tiempo de directiva**. Los períodos de tiempo que elijas aquí entrarán en vigor para un usuario cuando desencadenen una coincidencia para una directiva de riesgo interno.   La ventana Activación determina durante cuánto tiempo detectarán activamente la actividad de los usuarios y se desencadena cuando un usuario realiza la primera actividad que coincide con una directiva. La detección de actividad pasada determina cuánto debe remontarse hacia atrás una directiva para detectar la actividad del usuario y se desencadena cuando un usuario realiza la primera actividad que coincide con una directiva.  Deje los valores predeterminados.
    1. Selecciona **Detecciones inteligentes**. Revisa las opciones aquí.  Tenga en cuenta la configuración de dominios y cómo se relacionan con los indicadores.
    1. Explore los otros elementos que aparecen en la configuración y observe que muchos de ellos están en versión preliminar.

1. En el panel de navegación izquierdo, selecciona **Soluciones** y, después, selecciona **Administración de riesgos internos**.

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### Tarea 3

En esta tarea, se familiarizará con la configuración para crear una directiva.  El objetivo es simplemente hacerse una idea de las distintas opciones y flexibilidad asociadas a la creación de una directiva.

1. Debes estar en la página de información general de administración de riesgos internos.  Si aún no estás en ella, selecciona **Soluciones** en el panel de navegación izquierdo y, después, selecciona **Administración de riesgos internos**.

1. En la página de información general de Administración de riesgos internos, seleccione la pestaña **Directivas** y, luego, seleccione **+ Crear directiva**.  Configure cada una de las siguientes pestañas de directiva.

    1. Plantilla de directiva: en la categoría Pérdidas de datos, seleccione **Pérdidas de datos**.  Lea los detalles asociados a esta plantilla. En los requisitos previos, la directiva DLP se muestra con una marca de verificación en un círculo verde para indicar que se cumple el requisito previo.  Hay una directiva DLP preconfigurada para este inquilino de laboratorio. Seleccione **Siguiente**. 
    1. Nombre y descripción: escriba un nombre, **SC900-InsiderRiskPolicy** y, luego, seleccione **Siguiente**.
    1. Usuarios y grupos: revise el cuadro de información.  Deje la configuración predeterminada, **Incluir todos los usuarios y grupos**.  Seleccione **Siguiente**.
    1. Excluir usuarios y grupos (opcional)(versión preliminar): aquí puedes enumerar usuarios y grupos para excluir. No hagas ningún cambio. Seleccione **Siguiente**.
    1. Contenido para priorizar: según la descripción, se aumentan las puntuaciones de riesgo para cualquier actividad que contenga contenido de prioridad, lo que a su vez aumenta la posibilidad de generar una alerta de gravedad alta. Para simplificar, seleccione **No quiero priorizar el contenido en este momento** y, a continuación, seleccione **Siguiente**.
    1. Desencadenadores: el evento desencadenador determina cuándo comenzará una directiva a asignar puntuaciones de riesgo a la actividad de un usuario.  Puede elegir entre una directiva DLP existente o si el usuario realiza una actividad de filtración. Seleccione **Usuario coincide con una directiva de prevención de pérdida de datos (DLP)** y, a continuación, en la lista desplegable, seleccione **Datos financieros de EE. UU.** Seleccione **Siguiente**.
    1. Indicadores: anota los indicadores seleccionados. No hagas ningún cambio. Seleccione **Siguiente**.
    1. En la página Opciones de detección, deje todas las opciones predeterminadas, pero lea la descripción asociada a las distintas opciones y mantenga el puntero sobre el icono de información para obtener información más detallada sobre una configuración específica.  Seleccione **Siguiente**.
    1. En la página para Decidir si desea usar umbrales predeterminados o de indicador de cliente, deje el valor predeterminado **Aplicar umbrales proporcionados por Microsoft** y, a continuación, seleccione **Siguiente**.
    1. Para terminar, revise la configuración, seleccione **Enviar**.
    1. Revise la descripción de lo que sucede a continuación y seleccione **Listo**.

1. Ha vuelto a la pestaña Directivas de la página Administración de riesgos internos.  La directiva que ha creado aparecerá en la lista.  Si no la ve, seleccione el icono **Actualizar**.

1. Como administrador, puede empezar inmediatamente a asignar puntuaciones de riesgo a los usuarios en función de la actividad detectada por las directivas seleccionadas. Esto omite el requisito de que se detecte primero un evento desencadenador (como una coincidencia de directiva DLP).  Un administrador puede hacerlo seleccionando el cuadrado vacío junto al nombre de la directiva para seleccionarla, y luego seleccione la opción **Empezar a puntuar la actividad de los usuarios** que aparece encima de la tabla de directivas.  Se abre una nueva ventana que requiere que el administrador rellene los campos disponibles. Deje los campos vacíos, ya que no configurará esta opción, pero para obtener más información sobre por qué un administrador desea hacerlo, seleccione **¿Por qué haría esto?**  Cierre la ventana con la **X** de la esquina superior derecha de la ventana.

1. En el panel de navegación izquierdo, seleccione **Inicio** para volver a la página principal del Portal de cumplimiento de Microsoft Purview.

1. Deje abierta la pestaña del explorador.

### Revisar

En este laboratorio, se familiarizó con el proceso de configurar una directiva de riesgos internos y los requisitos básicos previos para configurar y usar directivas de administración de riesgos internos.
