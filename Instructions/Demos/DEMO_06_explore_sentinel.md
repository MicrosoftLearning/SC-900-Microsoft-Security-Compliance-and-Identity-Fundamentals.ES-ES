---
ms.openlocfilehash: 8d58cd38338d81136cf0b9b474137354269507e6
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892394"
---
<a name="---"></a><!---
---
Demostración: Título: "Microsoft Sentinel" Ruta de aprendizaje/Módulo/Título: "Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft; Módulo 3: Descripción de las funcionalidades de seguridad de Microsoft Sentinel; Unidad 3: Descripción de cómo Microsoft Sentinel proporciona administración contra amenazas integrada"
---
--->

# <a name="demo-microsoft-sentinel"></a>Demostración: Microsoft Sentinel

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de seguridad de Microsoft Sentinel
- Unidad: Descripción de cómo Microsoft Sentinel proporciona administración contra amenazas integrada

## <a name="demo-scenario"></a>Escenario de la demo

En esta versión de demostración se le guiará por el proceso de creación de una instancia de Microsoft Sentinel.  Además, configurará los permisos para garantizar el acceso a los recursos que se implementarán para admitir Microsoft Sentinel.  Una vez finalizada esta configuración básica, recorrerá los pasos para conectar Microsoft Sentinel a los orígenes de datos y crear un libro para supervisar y visualizar los datos.  Por último, mostrará algunas de las otras opciones disponibles, incluido el análisis integrado para recibir notificaciones de cualquier cosa sospechosa, la funcionalidad de automatización, etc.

### <a name="pre-demo-setup--create-an-microsoft-sentinel-instance"></a>Configuración previa a la demostración:  Creación de una instancia de Microsoft Sentinel

1. Abra la pestaña del explorador **Inicio: Microsoft Azure**.  Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba portal.azure.com y vuelva a iniciar sesión.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escriba **Microsoft Sentinel** y seleccione **Microsoft Sentinel** en los resultados de búsqueda.

1. En la página Microsoft Sentinel, seleccione **Crear Microsoft Sentinel**.

1. En la pantalla Agregar Microsoft Sentinel a una página de área de trabajo, seleccione **Crear un área de trabajo nueva**.

1. En la pestaña Aspectos básicos de Crear un área de trabajo de Log Analytics, escriba lo siguiente:
    1. Suscripción:  **Pase para Azure: Patrocinio**
    1. Grupo de recursos: seleccione **Crear nuevo**, escriba el nombre **SC900-Sentinel-RG** y seleccione **Aceptar**.
    1. Nombre: **SC900-LogAnalytics-workspace**.
    1. Región: **Este de EE. UU.** (se puede seleccionar una región predeterminada diferente en función de la ubicación)
    1. Seleccione **Siguiente: Etiquetas >**

1. Para las Etiquetas, puede dejar este en blanco y después seleccionar **Revisar y crear**.

1. Compruebe la información que ha escrito y luego seleccione **Crear**.

1. El área de trabajo puede tardar un minuto o dos en mostrarse; si todavía no la ve, seleccione **Actualizar** y después **Agregar**.

1. Una vez agregada la nueva área de trabajo, se mostrará la página Microsoft Sentinel | Noticias y guías.  Tenga en cuenta los tres pasos que se muestran en la página Empezar.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### <a name="demo-part-2"></a>Demo, parte 2

Una vez creada la instancia de Microsoft Sentinel, deberá asegurarse de que tiene el acceso necesario a los recursos que se implementan para admitir Microsoft Sentinel.  

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a donde pone Microsoft Azure, escriba **grupos de recursos** y seleccione **Grupos de recursos** en los resultados de búsqueda. La asignación del rol a nivel de grupo de recursos garantizará que el rol se aplique a todos los recursos que se implementan para admitir Microsoft Sentinel.

1. En la página Grupos de recursos, seleccione el grupo de recursos que creó con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. En la página SC900-Sentinel-RG, seleccione **Control de acceso (IAM)** en el panel de navegación izquierdo.

1. En la página Control de acceso, seleccione **Ver mi acceso**.  Como administrador de MOD, el rol actual es Administrador de servicios.  Este rol le concederá los permisos necesarios, pero con fines de demostración puede que quiera mostrar los roles específicos de Sentinel.  Para cerrar la ventana de Asignaciones de administrador MOD, seleccione la **X** en la esquina superior derecha de la ventana.

    1. En la página Control de acceso, seleccione **+Agregar** y después seleccione **Agregar asignación de roles**.

    1. Se abre la ventana Agregar asignación de roles.  En el cuadro de búsqueda, seleccione **Microsoft Sentinel** para ver los 4 roles asociados a Microsoft Sentinel.
    1. En cualquiera de los roles enumerados, seleccione **ver** para ver los detalles de ese rol.  El procedimiento recomendado es asignar los privilegios mínimos necesarios para el rol.  

    1. Para cerrar la ventana, seleccione la **X** en la esquina superior derecha de la ventana.

1. En la página de control de acceso, seleccione la **X** en la esquina superior derecha de la ventana para cerrarla.

### <a name="demo-part-3"></a>Demo, parte 3

En esta parte de la demo, se le guiará a través del proceso de conexión de Microsoft Sentinel a su origen de datos para empezar a recopilar datos.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escriba **Microsoft Sentinel** y seleccione **Microsoft Sentinel** en los resultados de búsqueda.

1. En la página Microsoft Sentinel, seleccione el área de trabajo que creó con la instancia de Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. El primer paso con Microsoft Sentinel es poder recopilar datos. En el panel de navegación izquierdo, seleccione **Conectores de datos**, que se muestran en Configuración.

1. En la página Conectores de datos, desplácese hacia abajo en la ventana principal para ver la amplia lista de conectores disponibles. En el cuadro "Buscar" de la página de conectores de datos, escriba **Office 365** y, luego, en la lista, seleccione **Office 365**.

1. Se abre la ventana de conectores de Office 365.  Seleccione **Open connector page** (Abrir página del conector).

1. En la página de conectores de Office 365, revise la descripción en el lado izquierdo de la ventana.

1. La pestaña de instrucciones de la ventana principal proporciona los requisitos previos para que Microsoft Sentinel se integre con Office 365; todos deben mostrar una marca de verificación verde.   En "Configuración", seleccione **Exchange** y **SharePoint** y, luego, "Aplicar cambios".  Casi inmediatamente verá el estado conectado en el lado izquierdo de la ventana.

1. Seleccione la **X** en la esquina superior derecha de la ventana para cerrarla y volver a la página de conectores de datos.

1. En la parte superior de la página "Conectores de datos", debería aparecer uno conectado, para reflejar que ahora está conectado a Office 365. Si no lo ve, seleccione **Actualizar**. Esta página puede tardar unos minutos en actualizarse.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### <a name="demo-part-4"></a>Demo, parte 4

En esta parte de la demostración, recorrerá el proceso de configuración de un libro para Office 365, con el fin de visualizar y supervisar los datos.

1. En el panel de navegación izquierdo, seleccione **Libros**.

1. En el cuadro de búsqueda, escriba Office 365 y, luego, seleccione **Office 365**.

1. En la ventana que se abre en el lado derecho de la pantalla, revise la descripción y seleccione **Guardar** en la parte inferior de la pantalla; a continuación, elija **Aceptar** para guardar el libro en la ubicación predeterminada.  Ahora seleccione **Ver libro guardado**.

1. Se abre la página de libros de Office 365.  Seleccione la flecha desplegable situada junto a **Operaciones: anular** y, luego, elija **Todo**.  Ahora seleccione la flecha desplegable junto a **Usuarios: consulta pendiente** y elija **Todo**.  Seleccione el **icono de guardar (disco)** . Para cerrar la ventana, seleccione la **X** en la esquina superior derecha de la ventana. Puede que pasen varios minutos antes de que los datos empiecen a aparecer en el libro, por lo que volverá a los libros más adelante.

1. Seleccione **Microsoft Sentinel** en la esquina superior izquierda de la página Libros, encima de la palabra Libros. Volverá a la página de información general.

### <a name="demo-part-5"></a>Demo, parte 5

En esta parte de la demostración, mostrará algunas de las opciones disponibles en Sentinel.

1. En el panel de navegación izquierdo, seleccione **Búsqueda**.  En la pestaña **Consultas**, que está seleccionada (subrayada), seleccione cualquier consulta de la lista.  Una vez seleccionada una consulta, anote la información proporcionada sobre esa consulta, incluido el código de la consulta, así como la opción para ejecutar la consulta y ver los resultados.  No seleccione nada.

1. En el panel de navegación izquierdo, seleccione **MITRE ATT&CK**.  MITRE ATT&CK es una base de conocimiento accesible públicamente de tácticas y técnicas que suelen usar los atacantes. Con Microsoft Sentinel puede ver las detecciones que ya están activas en el área de trabajo, así como las que están disponibles para configurarlas, con el fin de que conozca la cobertura de seguridad de su organización, según las tácticas y técnicas del marco MITRE ATTCK®.  Seleccione cualquier celda de la matriz y anote la información disponible en el lado derecho de la pantalla.  

1. En el panel de navegación izquierdo, seleccione **Comunidad**. Los analistas de seguridad de Microsoft crean y agregan constantemente nuevos libros, cuadernos de estrategias, consultas de búsqueda, etc., y los publican en la comunidad para que los pueda usar en el entorno. Puede descargar contenido de ejemplo del repositorio de GitHub privado de la comunidad para crear libros personalizados, consultas de búsqueda, cuadernos y cuadernos de estrategias Microsoft Azure Sentinel.  Seleccione **Incorporar contenido de la comunidad**.  Se abre una nueva pestaña en el repositorio GitHub, donde puede descargar contenido para habilitar los escenarios.  Vuelva a la pestaña Azure en el explorador.

1. En el panel de navegación izquierdo, seleccione **Análisis**.  Seleccione el primer elemento de la lista **Detección avanzada de ataques de varias fases**.  Anote la información detallada.  Microsoft Sentinel usa Fusion, un motor de correlación basado en algoritmos de aprendizaje automático escalable, para detectar automáticamente ataques de varias fases (también conocidos como amenazas persistentes avanzadas) al identificar combinaciones de comportamientos anómalos y actividades sospechosas que se observan en diversas fases de la cadena de eliminación. A partir de estas detecciones, Microsoft Sentinel genera incidentes que, de otro modo, serían muy difíciles de detectar.

1. En el panel de navegación izquierdo, seleccione **Automatización**.  Aquí puede crear de forma sencilla reglas de automatización, integrarlas con cuadernos de estrategias existentes o crear nuevos cuadernos de estrategias.  Seleccione **+ Crear** y, luego, **Regla de automatización**.  Observe la ventana que se abre en el lado derecho de la pantalla y las opciones disponibles para crear condiciones y acciones.  Seleccione **Cancelar** en la parte inferior de la página.

1. En el panel de navegación izquierdo, seleccione **Libros**. En la página Libros, seleccione la pestaña **Mis libros**, sobre el cuadro de búsqueda.  El libro que guardó anteriormente aparecerá en la lista y estará disponible para que pueda ver y supervisar sus datos.  Seleccione **Office 365** y, en la ventana que se abre en el lado derecho de la pantalla, elija **Ver libro guardado**.  Observe las visualizaciones relacionadas con las cargas de trabajo de Office 365.  

1. Para cerrar la ventana, seleccione la **X** en la esquina superior derecha de la ventana.

1. En la esquina superior izquierda de la ventana, justo debajo de la barra azul, seleccione **Inicio** para volver a la página principal del Azure Portal.

### <a name="post-course-delivery-tear-down"></a>Eliminación de la entrega después del curso

Microsoft Sentinel se factura en función del volumen de datos ingeridos para el análisis en Microsoft Sentinel. Aunque la cantidad de datos ingeridos como resultado de esta demostración es mínima, se recomienda que elimine el grupo de recursos de Microsoft Sentinel cuando haya terminado con la entrega del curso.

1. En la esquina superior izquierda de la página Microsoft Sentinel, encima de las palabras Microsoft Sentinel, seleccione **Todos los servicios**.

2. En el cuadro Filtrar servicios, escriba Grupos de recursos y luego, en la lista que aparece, seleccione **Grupos de recursos**.

3. En la página Grupos de recursos, seleccione el grupo de recursos que ha creado con Microsoft Sentinel, **Grupo de recursos:SC900**.

4. En la parte superior central de la página, seleccione **Eliminar grupo de recursos**.  Revise la advertencia.  Escriba el nombre del grupo de recursos, **Grupo de recursos:SC900**, y luego seleccione **Eliminar** en la parte inferior de la página.  Eliminar el grupo llevará varios minutos.

5. Una vez que haya comprobado que el grupo de recursos se ha eliminado, cierre la página del explorador.

### <a name="review"></a>Revisar

En esta demostración, ha seguido los pasos para conectar Microsoft Sentinel a orígenes de datos, ha configurado un libro y ha recorrido varias opciones disponibles en Microsoft Sentinel.
