<!---
---
Demo: Título: "Microsoft Sentinel" Ruta de aprendizaje/Módulo/Título: "Ruta de aprendizaje: Describir las capacidades de las soluciones de seguridad de Microsoft; Módulo 3: Describir las capacidades de seguridad de Microsoft Sentinel; Unidad 3: Describir las capacidades de detección y mitigación de amenazas en Microsoft Sentinel"
---
--->

# Demo: Microsoft Sentinel

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de seguridad de Microsoft Sentinel
- Unidad: Describir las capacidades de detección y mitigación de amenazas en Microsoft Sentinel

## Supuesto de demostración

En esta demo, verá algunas de las opciones disponibles con Microsoft Sentinel, incluido el uso del centro de contenido para encontrar soluciones empaquetadas que puede implementar.  Pero primero, verá el proceso para configurar permisos de control de acceso basado en roles para los usuarios que necesitarían acceder a los recursos de Microsoft Sentinel.

### Demo, parte 1

Debe haberse creado una instancia de Microsoft Sentinel como parte de la configuración previa a la demostración. Compruebe que se creó.

1. Abra la pestaña del explorador **Inicio- Microsoft Azure**.  Si ha cerrado previamente la pestaña, abra una página del explorador y, en la barra de direcciones, escriba **https://portal.azure.com**. Inicie sesión con las credenciales de Azure que proporciona el host de laboratorio autorizado (ALH).  Esto le llevará a la página principal de servicios de Azure.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escriba **Microsoft Sentinel** y seleccione **Microsoft Sentinel** en los resultados de búsqueda.  

1. En la página Microsoft Sentinel, debería ver la instancia de Sentinel en la lista y seleccionarla.  Si no aparece, créela ahora.
    1. En la página Microsoft Sentinel, seleccione **Crear Microsoft Sentinel**.

    1. En la pantalla Agregar Microsoft Sentinel a una página de área de trabajo, selecciona **Crear un área de trabajo nueva**. En la pestaña Datos básicos del área de trabajo Crear Log Analytics, escribe lo siguiente:
        1. Suscripción: deja el valor predeterminado.
        1. Grupo de recursos: selecciona **Crear nuevo**, luego escribe **SC900-Sentinel-RG** y selecciona **Aceptar**.
        1. Nombre: **SC900-LogAnalytics-workspace**.
        1. Región: **Este de EE. UU.**. (Se puede seleccionar una región predeterminada diferente en función de la ubicación).
        1. Seleccione **Revisar y crear** (no se configurarán etiquetas).
        1. Comprueba que escribiste la información correcta y selecciona **Crear**.
        1. El área de trabajo puede tardar un minuto o dos en aparecer, si todavía no la ves, selecciona **Actualizar** y, a continuación, selecciona **Agregar**.
        1. Una vez que se haya agregado la nueva área de trabajo, se mostrará la página Microsoft Sentinel | Noticias y guías, lo que indica que se ha activado la evaluación gratuita de Microsoft Sentinel.  Seleccione **Aceptar**.

1. Deje esta página abierta, la utilizará en la siguiente tarea.

### Demo, parte 2

Al igual que con todos los recursos de Azure, debe asegurarse de que los usuarios tengan los permisos adecuados para acceder a los recursos de Microsoft Sentinel. Aquí mostrará los pasos para asignar un rol y los roles disponibles para usar con Microsoft Sentinel.  

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escriba **grupo de recursos** y seleccione **Grupo de recursos** en los resultados de la búsqueda. La asignación del rol a nivel de grupo de recursos garantizará que el rol se aplique a todos los recursos que se implementan para admitir Microsoft Sentinel.

1. En la página Grupos de recursos, seleccione el grupo de recursos que creó con Microsoft Sentinel, **SC900-Sentinel-RG**.

1. En la página SC900-Sentinel-RG, seleccione **Control de acceso (IAM)** del panel de navegación izquierdo.

1. En la página Control de acceso, seleccione **Ver mi acceso**.  Si usa la suscripción a Skillable Cloud Slice, la asignación de roles se establece en Propietario de LOD, que es una asignación de roles personalizada configurada para esta suscripción a Cloud Slice y que le concederá los permisos necesarios. Sin embargo, para fines de demostración, está bien mostrar los roles específicos de Sentinel.  Cierre la ventana de asignaciones seleccionando la **X** de la esquina superior derecha de la ventana.

    1. Seleccione **+Agregar** y, luego, **Agregar asignación de roles** en la página Control de acceso.

    1. Se abrirá la ventana Agregar asignación de roles.  En el cuadro de búsqueda, escriba **Microsoft Sentinel** para ver los roles asociados a Microsoft Sentinel.
    1. En cualquiera de los roles enumerados, seleccione **ver** para ver los detalles de ese rol.  Como procedimiento recomendado, debe asignar los privilegios mínimos necesarios para el rol.  

    1. Cierre la ventana seleccionando la **X** de la esquina superior derecha de la ventana.

1. En la página Control de acceso, seleccione la **X** de la esquina superior derecha de la ventana para cerrarla.

### Demo, parte 3

En esta parte de la demostración, mostrará los pasos para conectarse a un origen de datos. Muchos conectores de datos se implementan como parte de la solución Microsoft Sentinel, junto con contenido relacionado, como reglas de análisis, libros y cuadernos de estrategias. El centro de contenidos de Microsoft Sentinel es la ubicación centralizada para detectar y administrar el contenido de serie (integrado). En este paso, usará el centro de conectividad para implementar Microsoft Defender for Cloud para Microsoft Sentinel.  Esta solución le permite ingerir alertas de seguridad notificadas en Microsoft Defender for Cloud.

1. Abra la pestaña del explorador para Microsoft Sentinel.

1. En el panel de navegación de la izquierda, seleccione **Centro de conectividad del contenido**.

1. Dedique un momento a desplazarse hacia abajo para ver la larga lista de soluciones disponibles y las opciones para filtrarla.  Para esta tarea, debe buscar **Microsoft Defender for Cloud**.  Selecciónelo en la lista.  En la ventana lateral que se abre, lea la descripción y seleccione **Instalar**.  Una vez completada la instalación, la columna de estado de la ventana principal se mostrará como instalada.

1. En el lado derecho de la página de Microsoft Defender for Cloud se muestra la descripción y las notas asociadas a la solución del Centro de contenido y lo que se incluye como parte de esta solución.  En la ventana principal se encuentran los componentes de la solución.  En este caso, hay dos conectores de datos y una regla de datos. El triángulo naranja indica que se necesita alguna configuración. Seleccione el cuadro situado junto a donde dice **Microsoft Defender for Cloud (heredado) basado en suscripciones**.  Se abre una ventana en el lado derecho de la página.  Seleccione **Open connector page** (Abrir página del conector).

1. Fíjese en las instrucciones de configuración.  Seleccione el cuadro situado junto al nombre de la suscripción y, a continuación, seleccione **Conectar**.  El estado cambiará a Conectado.  El conector ahora está habilitado, aunque puede tardar algún tiempo en aparecer en la página conectores de datos.  

1. Ahora vea la información sobre la regla de análisis.  En la parte superior de la página (en la ruta de navegación), seleccione **Microsoft Defender for Cloud**. Quite la seleccione de la casilla situada junto a Microsoft Defender for Cloud, ya que ya ha configurado el conector (puede tardar algún tiempo en desaparecer el icono de advertencia). Seleccione el cuadro situado junto a donde dice, **Detectar actividad de eliminación de CoreBackUp de alertas de seguridad relacionadas**.  Esto abre la página Reglas de análisis.  Nuevamente, seleccione la regla **Detectar actividad de eliminación de CoreBackUp de alertas de seguridad relacionadas**. Ventana que se abre a la derecha, que proporciona información sobre la regla y lo que hace.  Seleccione **Crear regla**.  
    1. Aunque los detalles de la lógica de la regla estén fuera del ámbito de los aspectos básicos, vaya a través de cada pestaña de la creación de reglas para ver el tipo de información que se puede configurar
    1. Cuando llegue a la pestaña Revisar y crear, seleccione **Guardar**.

1. Vuelva a la página de Sentinel, para hacerlo, seleccione **Microsoft Sentinel | Centro de contenido** desde la barra de navegación de la parte superior de la página, encima de donde dice Reglas de análisis.

1. Remarque que mediante el centro de contenido, una solución se puede implementar fácil y rápidamente.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### Demo, parte 4

En esta parte de la demostración, mostrará algunas de las opciones disponibles en Sentinel.

1. En el panel de navegación izquierdo, seleccione **Búsqueda**.  En la parte superior de la página, seleccione la pestaña **Consultas**. Lea la descripción de lo que es una consulta de búsqueda. Las consultas de búsqueda se pueden agregar a través del centro de contenido. Las consultas instaladas anteriormente aparecerán aquí. Seleccione **Ir al centro de contenido**.  El centro de contenido muestra el contenido que incluye consultas como parte de una solución o como una consulta independiente.  Desplácese hacia abajo para ver las opciones disponibles.

1. En el panel de navegación izquierdo, seleccione **MITRE ATT&CK**.  MITRE ATT&CK es una base de conocimiento accesible públicamente de tácticas y técnicas que suelen usar los atacantes. Con Microsoft Sentinel puede ver las detecciones que ya están activas en el área de trabajo, así como las que están disponibles para configurarlas, con el fin de que conozca la cobertura de seguridad de su organización, según las tácticas y técnicas del marco MITRE ATTCK®.  Seleccione cualquier celda de la matriz y anote la información disponible en el lado derecho de la pantalla.  

1. En el panel de navegación izquierdo, seleccione **Comunidad**. La página de la comunidad incluye información y actualizaciones de ciberseguridad de Microsoft Research, un vínculo a una lista de blogs de Microsoft Sentinel, un vínculo a foros de Microsoft Sentinel, vínculos a las últimas ediciones al Centro de Microsoft Sentinel, etc. Explore esto como desee.

1. En el panel de navegación izquierdo, seleccione **Análisis**.  Debe haber dos reglas activas, una que esté disponible de forma predeterminada y la regla que creó en la tarea anterior. Seleccione la regla predeterminada **Detección avanzada de ataques multistage**.  Anote la información detallada.  Microsoft Sentinel usa Fusion, un motor de correlación basado en algoritmos de aprendizaje automático escalable, para detectar automáticamente ataques de varias fases (también conocidos como amenazas persistentes avanzadas) al identificar combinaciones de comportamientos anómalos y actividades sospechosas que se observan en diversas fases de la cadena de eliminación. A partir de estas detecciones, Microsoft Sentinel genera incidentes que, de otro modo, serían muy difíciles de detectar.

1. En el panel de navegación izquierdo, seleccione **Automatización**.  Aquí puede crear reglas de automatización sencillas, integrarlas con cuadernos de estrategias existentes o crear nuevos cuadernos de estrategias.  Seleccione **+ Crear** y, luego, **Regla de automatización**.  Observe la ventana que se abre en el lado derecho de la pantalla y las opciones disponibles para crear condiciones y acciones.  Seleccione **Cancelar** en la parte inferior de la página.

1. En el panel de navegación izquierdo, seleccione **Libros**. Lea la descripción del libro de Microsoft Sentinel.  Los libros se pueden agregar a través del centro de contenido. Los libros instalados anteriormente se enumerarían aquí. Seleccione **Ir al centro de contenido**.  El centro de contenido muestra el contenido que incluye libros como parte de una solución o como un libro independiente. Desplácese hacia abajo para ver las opciones disponibles.

1. Cierre la ventana seleccionando la **X** de la esquina superior derecha de la ventana.

1. En la esquina superior izquierda de la ventana, justo debajo de la barra azul, seleccione **Inicio** para volver a la página principal del Azure Portal.  

### Revisar

En esta demostración, ha seguido los pasos para conectar Microsoft Sentinel a orígenes de datos, ha configurado un libro y ha recorrido varias opciones disponibles en Microsoft Sentinel.
