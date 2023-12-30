<!---
---
Laboratorio: Título: "Exploración de la administración de riesgos internos en Microsoft Purview" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft; Módulo 4: Descripción de las funcionalidades de riesgo interno en Microsoft Purview; Unidad 2: Descripción de la administración de riesgos internos"
---
--->

# Laboratorio: Explorar la administración de riesgos internos en Microsoft Purview

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de las funcionalidades de riesgo interno en Microsoft Purview
- Unidad: Descripción de la administración de riesgos internos

## Escenario del laboratorio

En este laboratorio, se familiarizará con el proceso de configurar una directiva de riesgos internos y los requisitos básicos previos para configurar y usar directivas de Administración de riesgos internos.  Nota: Este laboratorio únicamente abordará los requisitos necesarios para configurar la Administración de riesgos internos y las opciones relativas a la creación de directivas.  Este laboratorio no incluye la tarea de desencadenar la directiva, ya que el número de eventos que tendrían que producirse para desencadenar una directiva y el tiempo requerido quedan fuera del ámbito de este ejercicio.

**Tiempo estimado**: 45-60 minutos

### Tarea 1

En esta tarea, como administrador global, habilitará los permisos para la administración de riesgos internos.  En concreto, agregará usuarios al grupo de roles de Administración de riesgos internos para asegurarse de que los usuarios designados pueden acceder y administrar las características de administración de riesgos internos.  Los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios de toda la organización.

1. Abra la pestaña del explorador para la página principal de Microsoft Purview.  Si la había cerrado, abra otra y escriba **https://admin.microsoft.com** . Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.  

1. En el panel de navegación izquierdo, expanda **Roles y ámbitos** y, a continuación, seleccione **Permisos**.

1. En Soluciones de Microsoft Purview, seleccione **Roles**.

1. En el campo de búsqueda, escriba **Riesgo interno** y presione Entrar en el teclado.  Observe los numerosos roles que aparecen.  Cada uno de ellos tiene diferentes niveles de acceso.  Seleccione **Administración de riesgos internos** y revise la descripción.  Desplácese hacia abajo hasta donde se muestran los miembros y observe que se muestran el administrador de MOD y Megan Bowen. Cierre la ventana con la **X** de la esquina superior derecha de la ventana.

1. En el panel de navegación izquierdo, seleccione **Inicio** para volver a la página del Portal de cumplimiento de Microsoft Purview.

1. Mantenga esta ventana del navegador abierta, ya que volverá a ella en una tarea posterior.

### Tarea 2 (NOTA: omita la Tarea 2 si ha realizado la tarea de laboratorio de configuración para habilitar el registro de auditoría)

La administración de riesgo interno utiliza los registros de auditoría de Microsoft 365 para conseguir información sobre los usuarios y las actividades identificadas en las directivas y los análisis. En esta tarea, habilitará la funcionalidad Búsqueda en el registro de auditoría. Nota: Es posible que pasen varias horas después de activar la búsqueda de registros de auditoría antes de que pueda devolver resultados cuando busque el registro de auditoría.  Aunque puede tardar varias horas en buscar en el registro de auditoría, no afectará a la capacidad de completar otras tareas de este laboratorio.

1. Seleccione la pestaña del explorador que tiene la etiqueta **Inicio: Cumplimiento de Microsoft 365**.  Si ya había cerrado esta pestaña del explorador, abra Microsoft Edge, escriba **compliance.microsoft.com** en la barra de direcciones y, luego, inicie sesión con las credenciales de administrador.

1. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **Auditoría**.

1. Compruebe que la pestaña **Nueva búsqueda** está seleccionada (subrayada).

1. Una vez que llegue a la página Auditoría, espere de 2 a 3 minutos.  Si Auditoría NO está habilitada, verá una barra azul en la parte superior de la página donde pone "Comenzar a registrar la actividad del usuario y del administrador".  Seleccione **Comenzar a registrar la actividad del usuario y del administrador**.  Una vez habilitada Auditoría, la barra azul desaparecerá.  Si la barra azul no aparece, eso significará que la opción Auditoría ya está habilitada, y no necesitará hacer nada más.

1. Para volver a la página principal del Portal de cumplimiento de Microsoft Purview, seleccione **Inicio** en el panel de navegación izquierdo.

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### Tarea 3

En esta tarea explorará las opciones relativas a la solución Administración de riesgos internos.  La configuración de administración de riesgos internos se aplica a todas las directivas de administración de riesgos internos, independientemente de la plantilla que elija al crear una directiva.

1. Debería encontrarse en la página principal del Portal de cumplimiento de Microsoft Purview. Si no es así, seleccione la pestaña del explorador **Inicio: Cumplimiento de Microsoft 365**.

1. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **administración de riesgo interno**.

1. Antes de empezar a configurar una directiva, hay algunas opciones con las que un administrador debe estar familiarizado y configurarla según sea necesario para su organización. En la página Administración de riesgos internos, seleccione el **icono de engranaje de Configuración** en la esquina superior derecha de la ventana de administración de riesgos internos para acceder a la configuración de Riesgos internos.  
    1. Compruebe que está en la pestaña **Privacidad**: en el caso de los usuarios que realizan actividades asignadas a sus directivas de riesgos internos, esta configuración determinará si se deben mostrar los nombres reales o usar versiones anónimas para ocultar su identidad.  Para este tutorial, puede dejar la configuración predeterminada.
    1. Seleccione la pestaña **Indicadores de directiva**. Cuando se produzca un evento de desencadenamiento de directiva, las actividades que se asignan a los indicadores seleccionados se usan para determinar la puntuación de riesgo para el usuario. Los indicadores de directiva seleccionados aquí se incluyen las plantillas de directiva de riesgo interno.  Desplácese para ver todos los indicadores disponibles y cualquier información asociada. En **Indicadores de Office**, seleccione **Seleccionar todo** y, a continuación, seleccione **Guardar** en la parte inferior de la página (deberá desplazarse hacia abajo).
    1. Seleccione la pestaña **Períodos de tiempo de la directiva**. Los períodos de tiempo que elija aquí entrarán en vigor para un usuario cuando desencadenen una coincidencia para una directiva de riesgo interno.   La ventana Activación determina durante cuánto tiempo detectarán activamente la actividad de los usuarios y se desencadena cuando un usuario realiza la primera actividad que coincide con una directiva. La detección de actividad pasada determina cuánto debe remontarse hacia atrás una directiva para detectar la actividad del usuario y se desencadena cuando un usuario realiza la primera actividad que coincide con una directiva.  Deje los valores predeterminados.
    1. Seleccione la pestaña **Detecciones inteligentes**. Revise las opciones aquí.  Tenga en cuenta la configuración de dominios y cómo se relacionan con los indicadores.
    1. Explore los otros elementos que aparecen en la configuración y observe que muchos de ellos están en versión preliminar.

1. Para volver a la información general sobre la administración de riesgos internos, seleccione **Administración de riesgos internos** en la esquina superior izquierda de la página, encima de donde dice Configuración.

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### Tarea 4

En esta tarea, se familiarizará con la configuración para crear una directiva.  El objetivo es simplemente hacerse una idea de las distintas opciones y flexibilidad asociadas a la creación de una directiva.

1. Debe estar en la página de administración de riesgos internos.  Si aún no está allí, abra la pestaña del explorador etiquetada, **Administración de riesgos internos: cumplimiento de Microsoft 365**.

1. En la página de información general de Administración de riesgos internos, seleccione la pestaña **Directivas** y, luego, seleccione **+ Crear directiva**.  Configure cada una de las siguientes pestañas de directiva.

    1. Plantilla de directiva: en la categoría Pérdidas de datos, seleccione **Pérdidas de datos**.  Lea los detalles asociados a esta plantilla. En los requisitos previos, la directiva DLP se muestra con una marca de verificación en un círculo verde para indicar que se cumple el requisito previo.  Hay una directiva DLP preconfigurada para este inquilino de laboratorio. Seleccione **Siguiente**. 
    1. Nombre y descripción: escriba un nombre, **SC900-InsiderRiskPolicy** y, luego, seleccione **Siguiente**.
    1. Usuarios y grupos: revise el cuadro de información.  Deje la configuración predeterminada, **Incluir todos los usuarios y grupos**.  Seleccione **Siguiente**.
    1. Contenido para priorizar: según la descripción, se aumentan las puntuaciones de riesgo para cualquier actividad que contenga contenido de prioridad, lo que a su vez aumenta la posibilidad de generar una alerta de gravedad alta. Para simplificar, seleccione **No quiero priorizar el contenido en este momento** y, a continuación, seleccione **Siguiente**.
    1. Desencadenadores: el evento desencadenador determina cuándo comenzará una directiva a asignar puntuaciones de riesgo a la actividad de un usuario.  Puede elegir entre una directiva DLP existente o si el usuario realiza una actividad de filtración. Seleccione **Usuario coincide con una directiva de prevención de pérdida de datos (DLP)** y, a continuación, en la lista desplegable, seleccione **Datos financieros de EE. UU.** Seleccione **Siguiente**.
    1. Indicadores: tenga en cuenta que se seleccionan todos los indicadores de Office seleccionados en la tarea anterior (puede verlo si selecciona la tecla de flecha abajo junto a indicadores de Office) y, a continuación, seleccione **Siguiente**.
    1. En la página Opciones de detección, deje todas las opciones predeterminadas, pero lea la descripción asociada a las distintas opciones y mantenga el puntero sobre el icono de información para obtener información más detallada sobre una configuración específica.  Seleccione **Siguiente**.
    1. En la página para Decidir si desea usar umbrales predeterminados o de indicador de cliente, deje el valor predeterminado **Umbrales predeterminados** y, a continuación, seleccione **Siguiente**.
    1. Para terminar, revise la configuración, seleccione **Enviar**.
    1. Revise la descripción de lo que sucede a continuación y seleccione **Listo**.

1. Ha vuelto a la pestaña Directivas de la página Administración de riesgos internos.  La directiva que ha creado aparecerá en la lista.  Si no la ve, seleccione el icono **Actualizar**.

1. Como administrador, puede empezar inmediatamente a asignar puntuaciones de riesgo a los usuarios en función de la actividad detectada por las directivas seleccionadas. Esto omite el requisito de que se detecte primero un evento desencadenador (como una coincidencia de directiva DLP).  Un administrador puede hacerlo seleccionando el cuadrado vacío junto al nombre de la directiva para seleccionarla, y luego seleccione la opción **Empezar a puntuar la actividad de los usuarios** que aparece encima de la tabla de directivas.  Se abre una nueva ventana que requiere que el administrador rellene los campos disponibles. Deje los campos vacíos, ya que no configurará esta opción, pero para obtener más información sobre por qué un administrador desea hacerlo, seleccione **¿Por qué haría esto?**  Cierre la ventana con la **X** de la esquina superior derecha de la ventana.

1. En el panel de navegación izquierdo, seleccione **Inicio** para volver a la página principal del Portal de cumplimiento de Microsoft Purview.

1. Deje abierta la pestaña del explorador.

### Revisar

En este laboratorio, se familiarizó con el proceso de configurar una directiva de riesgos internos y los requisitos básicos previos para configurar y usar directivas de administración de riesgos internos.
