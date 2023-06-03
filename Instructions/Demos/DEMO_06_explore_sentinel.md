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

En esta demostración, realizará un recorrido por el proceso de creación de una instancia de Microsoft Sentinel.  Además, configurará los permisos para garantizar el acceso a los recursos que se implementarán para admitir Microsoft Sentinel.  Una vez finalizada esta configuración básica, recorrerá los pasos para conectar Microsoft Sentinel a los orígenes de datos y seleccionar un libro para supervisar y visualizar los datos.  Por último, mostrará algunas de las otras opciones disponibles, incluido el análisis integrado para recibir notificaciones de cualquier cosa sospechosa, la funcionalidad de automatización, etc.

### <a name="pre-demo-setup--create-a-microsoft-sentinel-instance"></a>Configuración previa a la demostración:  Creación de una instancia de Microsoft Sentinel

1. Abra la pestaña del explorador **Inicio: Microsoft Azure**.  Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba portal.azure.com y vuelva a iniciar sesión.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escriba **Microsoft Sentinel** y seleccione **Microsoft Sentinel** en los resultados de búsqueda.

1. En la página Microsoft Sentinel, seleccione **Crear Microsoft Sentinel**.

1. En la pantalla Agregar Microsoft Sentinel a una página de área de trabajo, seleccione **Crear un área de trabajo nueva**.

1. En la pestaña Aspectos básicos de Crear un área de trabajo de Log Analytics, escriba lo siguiente:
    1. Suscripción: deje el valor predeterminado.
    1. Grupo de recursos: seleccione **Crear nuevo**, escriba el nombre **SC900-Sentinel-RG** y seleccione **Aceptar**.
    1. Nombre: **SC900-LogAnalytics-workspace**.
    1. Región: **Este de EE. UU.** (se puede seleccionar una región predeterminada diferente en función de la ubicación)
    1. Seleccione **Revisar y crear** (no se configurarán etiquetas).
    1. Compruebe la información que ha escrito y luego seleccione **Crear**.
    1. El área de trabajo puede tardar un minuto o dos en mostrarse; si todavía no la ve, seleccione **Actualizar** y después **Agregar**.

1. Una vez que se haya agregado la nueva área de trabajo, se mostrará la página Microsoft Sentinel | Noticias y guías, lo que indica que se ha activado la evaluación gratuita de Microsoft Sentinel.  Seleccione **Aceptar**.  Tenga en cuenta los tres pasos que se muestran en la página Empezar.

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

    1. Cierre la ventana seleccionando la **X** de la esquina superior derecha de la ventana.

1. En la página Control de acceso, seleccione la **X** de la esquina superior derecha de la ventana para cerrarla.

### <a name="demo-part-3"></a>Demo, parte 3

En esta parte de la demostración, mostrará los pasos para conectarse a un origen de datos.  En concreto, se conectará al conector de datos de Microsoft Defender for Cloud.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escriba **Microsoft Sentinel** y seleccione **Microsoft Sentinel** en los resultados de búsqueda.

1. En la página Microsoft Sentinel, seleccione el área de trabajo que creó con la instancia de Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

1. El primer paso con Microsoft Sentinel es poder recopilar datos. En el panel de navegación izquierdo, seleccione **Conectores de datos**, que se muestran en Configuración.

1. En la página Conectores de datos, desplácese hacia abajo en la ventana principal para ver la amplia lista de conectores disponibles. En el cuadro de búsqueda de la página de conectores de datos, escriba **Microsoft Defender for Cloud** y, a continuación, en la lista, seleccione **Microsoft Defender for Cloud**.

1. Se abrirá la ventana del conector de Microsoft Defender for Cloud. Revise la descripción y, a continuación, seleccione **Abrir la página de conectores**.

1. En la página de conectores de Microsoft Defender for Cloud, revise la descripción en el lado izquierdo de la ventana.

1. La pestaña de instrucciones de la ventana principal proporciona los requisitos previos.  Revise las instrucciones y la información de configuración.
    La pestaña de instrucciones de la ventana principal proporciona los requisitos previos.  Revise las instrucciones y la información de configuración.
    1. En la sección de configuración, active la casilla vacía situada junto a la suscripción enumerada, **MOC Subscription--lodXXXXXXXX** para que aparezca una marca de verificación en un cuadro azul; a continuación, seleccione la opción **Conectar**, que se muestra encima del cuadro de búsqueda.  Aparecerá una ventana Conectar; seleccione **Aceptar**.  En la columna de estado, junto a la suscripción, debería ver esa actualización de estado en Conectado.  No se preocupe si no ve el estado conectado en la ventana del lado izquierdo de la página, NO actualice el explorador.
    1. Desplácese hacia abajo en la página y seleccione **Habilitar** para crear incidentes automáticamente a partir de todas las alertas generadas en el servicio conectado.
    1. Ahora, seleccione la pestaña **Pasos siguientes** en la parte superior de la página para ver los libros recomendados para este conector de datos.  Microsoft Sentinel incluye plantillas de libro integradas que le permiten obtener rápidamente conclusiones sobre los datos en cuanto usted conecta un origen de datos.
    1. Seleccione **Cumplimiento y protección de ASC** (nota: ASC o Azure Security Center ahora se denomina Microsoft Defender for Cloud).  Se abrirá la página de libros.  En el lado derecho de la pantalla, revise la descripción y seleccione **Guardar** en la parte inferior de la pantalla; a continuación, seleccione **Aceptar** para guardar el libro en la ubicación predeterminada.  Ahora seleccione **Ver libro guardado**.  
    1. En el campo Área de trabajo, seleccione **SC900-LogAnalytics-workspace**.
    1. En la parte superior de la página del libro, seleccione **Actualizar automáticamente: desactivado**, seleccione **5 minutos** y seleccione **Aplicar**.
    1. En la parte superior de la página del libro, seleccione el **icono Guardar**.
    1. Seleccione **Microsoft Sentinel** en la esquina superior izquierda de la página Libros, encima de la palabra Libros. Volverá a la página de información general. Ahora debería ver el número 1 en la parte superior, donde dice "Conectado", para indicar un conector activo (es posible que tenga que seleccionar Actualizar).

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### <a name="demo-part-4"></a>Demo, parte 4

En esta parte de la demostración, mostrará algunas de las opciones disponibles en Sentinel.

1. En el panel de navegación izquierdo, seleccione **Búsqueda**.  En la pestaña **Consultas**, que está seleccionada (subrayada), seleccione cualquier consulta de la lista.  Una vez seleccionada una consulta, observe la información proporcionada sobre esa consulta, incluido el código de la consulta, así como la opción para ejecutar la consulta y ver los resultados.  No seleccione nada.

1. En el panel de navegación izquierdo, seleccione **MITRE ATT&CK**.  MITRE ATT&CK es una base de conocimiento accesible públicamente de tácticas y técnicas que suelen usar los atacantes. Con Microsoft Sentinel puede ver las detecciones que ya están activas en el área de trabajo, así como las que están disponibles para configurarlas, con el fin de que conozca la cobertura de seguridad de su organización, según las tácticas y técnicas del marco MITRE ATTCK®.  Seleccione cualquier celda de la matriz y anote la información disponible en el lado derecho de la pantalla.  

1. En el panel de navegación izquierdo, seleccione **Comunidad**. Los analistas de seguridad de Microsoft crean y agregan constantemente nuevos libros, cuadernos de estrategias, consultas de búsqueda, etc., y los publican en la comunidad para que los pueda usar en el entorno. Puede descargar contenido de ejemplo del repositorio de GitHub privado de la comunidad para crear libros personalizados, consultas de búsqueda, cuadernos y cuadernos de estrategias Microsoft Azure Sentinel.  Seleccione **Incorporar contenido de la comunidad**.  Se abre una nueva pestaña en el repositorio GitHub, donde puede descargar contenido para habilitar los escenarios.  Vuelva a la pestaña Azure en el explorador.

1. En el panel de navegación izquierdo, seleccione **Análisis**.  Seleccione el primer elemento de la lista **Detección avanzada de ataques de varias fases**.  Anote la información detallada.  Microsoft Sentinel usa Fusion, un motor de correlación basado en algoritmos de aprendizaje automático escalable, para detectar automáticamente ataques de varias fases (también conocidos como amenazas persistentes avanzadas) al identificar combinaciones de comportamientos anómalos y actividades sospechosas que se observan en diversas fases de la cadena de eliminación. A partir de estas detecciones, Microsoft Sentinel genera incidentes que, de otro modo, serían muy difíciles de detectar.

1. En el panel de navegación izquierdo, seleccione **Automatización**.  Aquí puede crear de forma sencilla reglas de automatización, integrarlas con cuadernos de estrategias existentes o crear nuevos cuadernos de estrategias.  Seleccione **+ Crear** y, luego, **Regla de automatización**.  Observe la ventana que se abre en el lado derecho de la pantalla y las opciones disponibles para crear condiciones y acciones.  Seleccione **Cancelar** en la parte inferior de la página.

1. En el panel de navegación izquierdo, seleccione **Libros**. En la página Libros, seleccione la pestaña **Mis libros**, sobre el cuadro de búsqueda.  El libro que guardó anteriormente aparecerá en la lista y estará disponible para que pueda ver y supervisar sus datos.   NOTA: No hay ninguna actividad real que ocurra en la suscripción de Azure para reflejarse en el libro y las suscripciones de laboratorio de Azure pueden experimentar retrasos mayores que los normales en la recopilación de datos que se pueden visualizar en el libro.

1. Cierre la ventana seleccionando la **X** de la esquina superior derecha de la ventana.

1. En la esquina superior izquierda de la ventana, justo debajo de la barra azul, seleccione **Inicio** para volver a la página principal del Azure Portal.  

### <a name="review"></a>Revisar

En esta demostración, ha seguido los pasos para conectar Microsoft Sentinel a orígenes de datos, ha configurado un libro y ha recorrido varias opciones disponibles en Microsoft Sentinel.
