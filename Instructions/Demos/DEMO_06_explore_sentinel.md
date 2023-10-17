<!---
---
Demostración: Título: "Microsoft Sentinel" Ruta de aprendizaje/Módulo/Título: "Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft; Módulo 3: Descripción de las funcionalidades de seguridad de Microsoft Sentinel; Unidad 3: Descripción de las funcionalidades de detección y mitigación de amenazas en Microsoft Sentinel"
---
--->

# Demostración: Microsoft Sentinel

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de seguridad de Microsoft Sentinel
- Unidad: Descripción de las funcionalidades de detección y mitigación de amenazas en Microsoft Sentinel

## Escenario de la demo

En esta demostración, recorrerá algunas de las opciones disponibles con Microsoft Sentinel, incluido el uso del centro de conectividad para encontrar soluciones empaquetadas que puedas implementar.  Pero antes, le explicaremos el proceso de configuración de los permisos de control de acceso basado en roles para los usuarios que necesitarían acceder a sus recursos de Microsoft Sentinel.

### Demo, parte 1

Ya debería haberse creado una instancia de Microsoft Sentinel como parte de la configuración previa a la demostración. Compruebe que se ha creado.

1. Abra la pestaña del explorador **Inicio: Microsoft Azure**.  Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba **https://portal.azure.com** . Inicie sesión con las credenciales de Azure proporcionadas por el host de laboratorio autorizado (ALH).  Esto le llevará a la página principal de servicios de Azure.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escriba **Microsoft Sentinel** y seleccione **Microsoft Sentinel** en los resultados de búsqueda.  

1. En la página de Microsoft Sentinel, debería ver su instancia de Sentinel y seleccionarla.  Si no aparece en la lista, créela ahora.
    1. En la página Microsoft Sentinel, seleccione **Crear Microsoft Sentinel**.

    1. En la pantalla Agregar Microsoft Sentinel a una página de área de trabajo, seleccione **Crear un área de trabajo nueva**. En la pestaña Aspectos básicos de Crear un área de trabajo de Log Analytics, escriba lo siguiente:
        1. Suscripción: deje el valor predeterminado.
        1. Grupo de recursos: seleccione **Crear nuevo**, escriba el nombre **SC900-Sentinel-RG** y seleccione **Aceptar**.
        1. Nombre: **SC900-LogAnalytics-workspace**.
        1. Región: **Este de EE. UU.** (se puede seleccionar una región predeterminada diferente en función de la ubicación)
        1. Seleccione **Revisar y crear** (no se configurarán etiquetas).
        1. Compruebe la información que ha escrito y luego seleccione **Crear**.
        1. El área de trabajo puede tardar un minuto o dos en mostrarse; si todavía no la ve, seleccione **Actualizar** y después **Agregar**.
        1. Una vez que se haya agregado la nueva área de trabajo, se mostrará la página Microsoft Sentinel | Noticias y guías, lo que indica que se ha activado la evaluación gratuita de Microsoft Sentinel.  Seleccione **Aceptar**.

1. Mantenga abierta esta página, ya que la usará en una tarea posterior.

### Demo, parte 2

Al igual que con todos los recursos de Azure, quiere asegurarse de que los usuarios tengan los permisos adecuados para acceder a los recursos de Microsoft Sentinel. Aquí se muestran los pasos para asignar un rol y los roles disponibles para su uso con Microsoft Sentinel.  

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a donde pone Microsoft Azure, escriba **grupos de recursos** y seleccione **Grupos de recursos** en los resultados de búsqueda. La asignación del rol a nivel de grupo de recursos garantizará que el rol se aplique a todos los recursos que se implementan para admitir Microsoft Sentinel.

1. En la página Grupos de recursos, seleccione el grupo de recursos que creó con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. En la página SC900-Sentinel-RG, seleccione **Control de acceso (IAM)** en el panel de navegación izquierdo.

1. En la página Control de acceso, seleccione **Ver mi acceso**.  Si está usando la suscripción de Skillable Cloud Slice, la asignación de rol se establece en Propietario de LOD, que es una asignación de rol personalizada configurada para esta suscripción de Cloud Slice y que le otorgará los permisos necesarios. Sin embargo, a efectos de demostración, es bueno mostrar los roles específicos de Sentinel.  Cierre la ventana de asignaciones seleccionando la **X** de la esquina superior derecha de la ventana.

    1. En la página Control de acceso, seleccione **+Agregar** y después seleccione **Agregar asignación de roles**.

    1. Se abre la ventana Agregar asignación de roles.  En el cuadro de búsqueda, seleccione **Microsoft Sentinel** para ver los roles asociados a Microsoft Sentinel.
    1. En cualquiera de los roles enumerados, seleccione **ver** para ver los detalles de ese rol.  El procedimiento recomendado es asignar los privilegios mínimos necesarios para el rol.  

    1. Cierre la ventana seleccionando la **X** de la esquina superior derecha de la ventana.

1. En la página Control de acceso, seleccione la **X** de la esquina superior derecha de la ventana para cerrarla.

### Demo, parte 3

En esta parte de la demostración, mostrará los pasos para conectarse a un origen de datos. Muchos conectores de datos se implementan como parte de la solución Microsoft Sentinel, junto con contenido relacionado, como reglas de análisis, libros y cuadernos de estrategias. El centro de contenido de Microsoft Sentinel es la ubicación centralizada para detectar y administrar el contenido de serie (integrado). En este paso, usará el centro de contenido para implementar la solución Microsoft Defender for Cloud para Microsoft Sentinel.  Esta solución permite ingerir alertas de seguridad notificadas en Microsoft Defender for Cloud.

1. Abra la pestaña del explorador para Microsoft Sentinel.

1. En el panel de navegación izquierdo, seleccione **Centro de contenido**.

1. Tómese un momento para desplazarse hacia abajo y ver la larga lista de soluciones disponibles y las opciones para filtrar la lista.  Para esta demostración, estamos buscando **Microsoft Defender for Cloud**.  Selecciónelo en la lista.  En la ventana lateral que se abre, lea la descripción y seleccione **Instalar**.  Esta solución incluye un conector de datos y una regla de análisis. Puede tardar un minuto en instalarse.  Seleccione **Administrar**.

1. Seleccione el cuadro situado junto a donde dice Microsoft Defender for Cloud.  Se abrirá una ventana en la parte derecha de la página.  Seleccione **Open connector page** (Abrir página del conector).

1. Anote las instrucciones de configuración.  Seleccione la casilla situada junto al nombre de la suscripción y seleccione **Conectar**.  El estado se moverá a conectado.  El conector está ahora habilitado, aunque puede tardar algún tiempo en aparecer en la página de conectores de datos.  

1. Ahora, vea información sobre la regla de análisis.  En la parte superior de la página (en la ruta de navegación), seleccione **Microsoft Defender for Cloud**.  Seleccione la casilla situada junto a donde dice "Detectar actividad de eliminación de CoreBackUp a partir de alertas de seguridad relacionadas". En la ventana que se abre, verá información sobre la regla y lo que hace.  Puede elegir seguir los pasos para configurar la regla.  **NOTA**: Los detalles de la lógica de la regla están fuera del ámbito de los aspectos básicos, pero puede mostrar el tipo de información que se puede configurar como parte de la regla.  
    1. Seleccione **Configuración**.
    1. Seleccione la regla **Detectar actividad de eliminación de CoreBackUp en alertas de seguridad relacionadas**.
    1. En la ventana que se abre en el lado derecho de la página, seleccione **Crear regla**.
    1. Recorra cada una de las páginas de configuración, muy brevemente y a nivel general. Después, seleccione **Revisar y crear**, seleccione **Guardar**.

1. Vuelva a la página de Sentinel seleccionando **Microsoft Sentinel | Centro de contenido** en la barra de navegación en la parte superior de la página, encima de donde dice Reglas de análisis.

1. Señale que usando el centro de conectividad se puede implementar una solución fácil y rápidamente.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### Demo, parte 4

En esta parte de la demostración, mostrará algunas de las opciones disponibles en Sentinel.

1. En el panel de navegación izquierdo, seleccione **Búsqueda**.  En la parte superior de la página, seleccione la pestaña **consultas**. Lea la descripción de lo que es una consulta de búsqueda. Las consultas de búsqueda se pueden agregar a través del centro de contenido. Las consultas instaladas anteriormente se mostrarían aquí. Seleccione **Ir al centro de contenido**.  El centro de contenido muestra el contenido que incluye consultas como parte de una solución o como una consulta independiente.  Desplácese hacia abajo para ver las opciones disponibles.

1. En el panel de navegación izquierdo, seleccione **MITRE ATT&CK**.  MITRE ATT&CK es una base de conocimiento accesible públicamente de tácticas y técnicas que suelen usar los atacantes. Con Microsoft Sentinel puede ver las detecciones que ya están activas en el área de trabajo, así como las que están disponibles para configurarlas, con el fin de que conozca la cobertura de seguridad de su organización, según las tácticas y técnicas del marco MITRE ATTCK®.  Seleccione cualquier celda de la matriz y anote la información disponible en el lado derecho de la pantalla.  

1. En el panel de navegación izquierdo, seleccione **Comunidad**. Los analistas de seguridad de Microsoft crean y agregan constantemente nuevos libros, cuadernos de estrategias, consultas de búsqueda, etc., y los publican en la comunidad para que los pueda usar en el entorno. Puede descargar contenido de ejemplo del repositorio de GitHub privado de la comunidad para crear libros personalizados, consultas de búsqueda, cuadernos y cuadernos de estrategias Microsoft Azure Sentinel.  Seleccione **Incorporar contenido de la comunidad**.  Se abre una nueva pestaña en el repositorio GitHub, donde puede descargar contenido para habilitar los escenarios.  Vuelva a la pestaña Azure en el explorador.

1. En el panel de navegación izquierdo, seleccione **Análisis**.  Debería haber dos reglas activas, una que está disponible de manera predeterminada y la regla que creó en la tarea anterior. Seleccione la regla predeterminada **Detección avanzada de ataques de varias fases**.  Anote la información detallada.  Microsoft Sentinel usa Fusion, un motor de correlación basado en algoritmos de aprendizaje automático escalable, para detectar automáticamente ataques de varias fases (también conocidos como amenazas persistentes avanzadas) al identificar combinaciones de comportamientos anómalos y actividades sospechosas que se observan en diversas fases de la cadena de eliminación. A partir de estas detecciones, Microsoft Sentinel genera incidentes que, de otro modo, serían muy difíciles de detectar.

1. En el panel de navegación izquierdo, seleccione **Automatización**.  Aquí puede crear reglas de automatización sencillas, integrarlas con cuadernos de estrategias existentes o crear nuevos cuadernos de estrategias.  Seleccione **+ Crear** y, luego, **Regla de automatización**.  Observe la ventana que se abre en el lado derecho de la pantalla y las opciones disponibles para crear condiciones y acciones.  Seleccione **Cancelar** en la parte inferior de la página.

1. En el panel de navegación izquierdo, seleccione **Libros**. Lea la descripción de lo que es un libro de Microsoft Sentinel.  Los libros se pueden agregar a través del centro de contenido. Los libros instalados anteriormente se mostrarían aquí. Seleccione **Ir al centro de contenido**.  El centro de contenido muestra el contenido que incluye libros como parte de una solución o como un libro independiente. Desplácese hacia abajo para ver las opciones disponibles.

1. Cierre la ventana seleccionando la **X** de la esquina superior derecha de la ventana.

1. En la esquina superior izquierda de la ventana, justo debajo de la barra azul, seleccione **Inicio** para volver a la página principal del Azure Portal.  

### Revisar

En esta demostración, ha seguido los pasos para conectar Microsoft Sentinel a orígenes de datos, ha configurado un libro y ha recorrido varias opciones disponibles en Microsoft Sentinel.
