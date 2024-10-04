---
lab:
  title: Explorar Microsoft Sentinel
  module: Describe the security capabilities of Microsoft Sentinel
---

# Laboratorio: Explorar Microsoft Sentinel

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de seguridad de Microsoft Sentinel
- Unidad: Describir las capacidades de detección y mitigación de amenazas en Microsoft Sentinel

## Escenario del laboratorio

En este laboratorio, realizará un recorrido por el proceso de creación de una instancia de Microsoft Sentinel.  Además, configurará los permisos para garantizar el acceso a los recursos que se implementarán para admitir Microsoft Sentinel.  Una vez finalizada esta configuración básica, recorrerá los pasos para conectar Microsoft Sentinel a los orígenes de datos, configurar un libro y realizar un breve tutorial de algunas de las funcionalidades clave disponibles en Microsoft Sentinel.

**Tiempo estimado**: 60 minutos

### Tarea 1

Creación de una instancia de Microsoft Sentinel

1. Debería estar en la página principal de los servicios de Azure.  Si ha cerrado previamente el explorador, abra Microsoft Edge. En la barra de direcciones, escriba **portal.azure.com** e inicie sesión con sus credenciales de administrador. Si has iniciado sesión anteriormente, es posible que se te pida un formulario de autenticación secundario, como parte de MFA.  Si no has iniciado sesión anteriormente, es posible que se te pida que configures MFA.  Sigue las indicaciones en la pantalla para configurar MFA.

1. En el cuadro de búsqueda azul situado en la parte superior de la página, escriba **Microsoft Sentinel** y, a continuación, seleccione **Microsoft Sentinel** en los resultados de búsqueda.

1. En la página Microsoft Sentinel, seleccione **Crear Microsoft Sentinel**.

1. En la pantalla Agregar Microsoft Sentinel a una página de área de trabajo, selecciona **Crear un área de trabajo nueva**.

1. En la pestaña Datos básicos del área de trabajo Crear Log Analytics, escriba lo siguiente:
    1. Suscripción: deje el valor predeterminado; se trata de la suscripción de Azure proporcionada por el host de laboratorio autorizado (ALH).
    1. Grupo de recursos: seleccione **SC900-Sentinel-RG**. Si este grupo de recursos no aparece en la lista al seleccionar **Crear nuevo**, escriba **SC900-Sentinel-RG** y seleccione **Aceptar**.
    1. Nombre: **SC900-LogAnalytics-workspace**.
    1. Región: **Este de EE. UU.**. (Se puede seleccionar una región predeterminada diferente en función de la ubicación).
    1. Seleccione **Revisar y crear** (no se configurarán etiquetas).
    1. Comprueba que escribiste la información correcta y selecciona **Crear**.
    1. El área de trabajo puede tardar un minuto o dos en aparecer, si todavía no la ves, selecciona **Actualizar** y, a continuación, selecciona **Agregar**.

1. Una vez que se haya agregado la nueva área de trabajo, se mostrará la página Microsoft Sentinel | Noticias y guías, lo que indica que se ha activado la evaluación gratuita de Microsoft Sentinel.  Seleccione **Aceptar**.  Tenga en cuenta los tres pasos que aparecen en la página Introducción.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### Tarea 2

Una vez que se ha creado la instancia de Microsoft Sentinel, es importante que los usuarios que tendrán la responsabilidad de admitir Microsoft Sentinel tengan los permisos necesarios.  Para ello, se deben asignar al usuario designado los permisos de rol necesarios.  En esta tarea, verá los roles integrados de Microsoft Sentinel disponibles.

1. En el cuadro de búsqueda azul, escriba **grupos de recursos** y, a continuación, seleccione **Grupos de recursos**. 

1. En la página Grupos de recursos, seleccione el grupo de recursos que creó con Microsoft Sentinel, **SC900-Sentinel-RG**.  Trabajar en el nivel de grupo de recursos garantizará que cualquier rol seleccionado se aplique a todos los recursos que forman parte de la instancia de Microsoft Sentinel que se ha creado en la tarea anterior.

1. En la página SC900-Sentinel-RG, seleccione **Control de acceso (IAM)** del panel de navegación izquierdo.

1. En la página Control de acceso, seleccione **Ver mi acceso**.  Para la suscripción de Azure proporcionada por el host de laboratorio autorizado, se ha definido un rol que le proporcionará acceso para administrar todos los recursos necesarios, como se muestra en la descripción. Sin embargo, es importante comprender los roles específicos de Sentinel disponibles.  Cierre la ventana de asignaciones seleccionando la **X** de la esquina superior derecha de la ventana.

1. En la página Control de acceso, seleccione la pestaña **Roles** de la parte superior de la página.
    1. En el cuadro de búsqueda, escriba **Microsoft Sentinel** para ver los roles integrados asociados a Microsoft Sentinel.
    1. En cualquiera de los roles enumerados, seleccione **ver** para ver los detalles de ese rol.  Como procedimiento recomendado, debe asignar los privilegios mínimos necesarios para el rol.  
    1. Cierre la ventana seleccionando la **X** de la esquina superior derecha de la ventana.

1. En la página Control de acceso, seleccione la **X** de la esquina superior derecha de la ventana para cerrarla.

1. En la esquina superior izquierda de la ventana, justo debajo de la barra azul donde pone "Microsoft Azure", seleccione **Inicio** para volver a la página principal de los servicios de Azure.

1. Mantenga abierta la pestaña de Azure en el explorador.

### Tarea 3

El propósito de esta tarea es guiarle por los pasos necesarios para conectarse a un origen de datos. Muchos conectores de datos se implementan como parte de la solución Microsoft Sentinel, junto con contenido relacionado, como reglas de análisis, libros y cuadernos de estrategias. El centro de contenidos de Microsoft Sentinel es la ubicación centralizada para detectar y administrar el contenido de serie (integrado). En este paso, usará el centro de conectividad para implementar Microsoft Defender for Cloud para Microsoft Sentinel.  Esta solución le permite ingerir alertas de seguridad notificadas en Microsoft Defender for Cloud.

1. En la página principal de los servicios de Azure, seleccione Microsoft Sentinel y, a continuación, seleccione la instancia que creó, **SC900-LogAnalytics-workspace**.

1. En el panel de navegación de la izquierda, seleccione **Centro de conectividad del contenido**.

1. Dedique un momento a desplazarse hacia abajo para ver la larga lista de soluciones disponibles y las opciones para filtrarla.  Para esta tarea, debe buscar **Microsoft Defender for Cloud**.  Selecciónelo en la lista.  En la ventana lateral que se abre, lea la descripción y seleccione **Instalar**.  Una vez completada la instalación, la columna de estado de la ventana principal se mostrará como instalada.

1. Una vez más, seleccione **Microsoft Defender for Cloud** en la lista. En la ventana de la derecha, seleccione **Administrar**.

1. En el lado derecho de la página de Microsoft Defender for Cloud se muestra la descripción y las notas asociadas a la solución del Centro de contenido y lo que se incluye como parte de esta solución.  En la ventana principal se encuentran los componentes de la solución.  En este caso, hay dos conectores de datos y una regla de datos. El triángulo naranja indica que se necesita alguna configuración. Seleccione el cuadro situado junto a donde dice **Microsoft Defender for Cloud (heredado) basado en suscripciones**.  Se abre una ventana en el lado derecho de la página.  Seleccione **Open connector page** (Abrir página del conector).

1. Fíjese en las instrucciones de configuración.  Seleccione el cuadro situado junto al nombre de la suscripción y, a continuación, seleccione **Conectar**.  Puede aparecer una ventana emergente que indique que solo las suscripciones en las que tiene permisos de Lector de seguridad comenzarán a transmitir alertas de Microsoft Defender for Cloud.  Seleccione **Aceptar**.  El estado cambiará a Conectado.  El conector ahora está habilitado, aunque puede tardar algún tiempo en aparecer en la página conectores de datos.  

1. Ahora vea la información sobre la regla de análisis.  En la parte superior de la página (en la ruta de navegación), seleccione **Microsoft Defender for Cloud**. Quite la seleccione de la casilla situada junto a Microsoft Defender for Cloud, ya que ya ha configurado el conector (puede tardar algún tiempo en desaparecer el icono de advertencia). Seleccione el cuadro situado junto a donde dice, **Detectar actividad de eliminación de CoreBackUp de alertas de seguridad relacionadas**.  Esto abre la página Reglas de análisis.  Nuevamente, seleccione la regla **Detectar actividad de eliminación de CoreBackUp de alertas de seguridad relacionadas**. Ventana que se abre a la derecha, que proporciona información sobre la regla y lo que hace.  Seleccione **Crear regla**.  
    1. Aunque los detalles de la lógica de la regla estén fuera del ámbito de los aspectos básicos, vaya a través de cada pestaña de la creación de reglas para ver el tipo de información que se puede configurar
    1. Cuando llegue a la pestaña Revisar y crear, seleccione **Guardar**.

1. Vuelva a la página de Sentinel, para hacerlo, seleccione **Microsoft Sentinel | Centro de contenido** desde la barra de navegación de la parte superior de la página, encima de donde dice Reglas de análisis.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.


### Tarea 4

En esta tarea, realizará un recorrido por algunas de las opciones disponibles en Sentinel.

1. En el panel de navegación izquierdo, seleccione **Búsqueda**.  En la parte superior de la página, seleccione la pestaña **Consultas**. Lea la descripción de lo que es una consulta de búsqueda. Las consultas de búsqueda se pueden agregar a través del centro de contenido. Las consultas instaladas anteriormente aparecerán aquí. Seleccione **Ir al centro de contenido**.  El centro de contenido muestra el contenido que incluye consultas como parte de una solución o como una consulta independiente.  Desplácese hacia abajo para ver las opciones disponibles. Cierre el centro de contenido, para hacerlo, seleccione la **X** de la esquina superior derecha de la ventana.

1. En el panel de navegación izquierdo, seleccione **MITRE ATT&CK**.  MITRE ATT&CK es una base de conocimiento accesible públicamente de tácticas y técnicas que suelen usar los atacantes. Con Microsoft Sentinel puede ver las detecciones que ya están activas en el área de trabajo, así como las que están disponibles para configurarlas, con el fin de que conozca la cobertura de seguridad de su organización, según las tácticas y técnicas del marco MITRE ATTCK®.  Seleccione cualquier celda de la matriz y anote la información disponible en el lado derecho de la pantalla. **Nota**: Es posible que tenga que seleccionar "**<<**" en el lado derecho de la ventana para ver el panel de información.

1. En el panel de navegación izquierdo, seleccione **Comunidad**. La página de la comunidad incluye información y actualizaciones de ciberseguridad de Microsoft Research, un vínculo a una lista de blogs de Microsoft Sentinel, un vínculo a foros de Microsoft Sentinel, vínculos a las últimas ediciones al Centro de Microsoft Sentinel, etc. Explore esto como desee.

1. En el panel de navegación izquierdo, seleccione **Análisis**.  Debe haber dos reglas activas, una que esté disponible de forma predeterminada y la regla que creó en la tarea anterior. Seleccione la regla predeterminada **Detección avanzada de ataques multistage**.  Anote la información detallada.  Microsoft Sentinel usa Fusion, un motor de correlación basado en algoritmos de aprendizaje automático escalable, para detectar automáticamente ataques de varias fases (también conocidos como amenazas persistentes avanzadas) al identificar combinaciones de comportamientos anómalos y actividades sospechosas que se observan en diversas fases de la cadena de eliminación. A partir de estas detecciones, Microsoft Sentinel genera incidentes que, de otro modo, serían muy difíciles de detectar. **Nota**: Es posible que tenga que seleccionar "**<<**" en el lado derecho de la ventana para ver el panel de información.

1. En el panel de navegación izquierdo, seleccione **Automatización**.  Aquí puede crear reglas de automatización sencillas, integrarlas con cuadernos de estrategias existentes o crear nuevos cuadernos de estrategias.  Seleccione **+ Crear** y, luego, **Regla de automatización**.  Observe la ventana que se abre en el lado derecho de la pantalla y las opciones disponibles para crear condiciones y acciones.  Seleccione **Cancelar** en la parte inferior de la página.

1. En el panel de navegación izquierdo, seleccione **Libros**. Lea la descripción del libro de Microsoft Sentinel.  Los libros se pueden agregar a través del centro de contenido. Cualquier libro instalado anteriormente aparecerá aquí. Seleccione **Ir al centro de contenido**.  El centro de contenido muestra el contenido que incluye libros como parte de una solución o como un libro independiente. Desplácese hacia abajo para ver las opciones disponibles.

1. Cierre la ventana seleccionando la **X** de la esquina superior derecha de la ventana.

1. En la esquina superior izquierda de la ventana, justo debajo de la barra azul, seleccione **Inicio** para volver a la página principal del Azure Portal.

1. Cierre la sesión y cierre todas las pestañas abiertas del explorador.

### Revisar

En esta demostración, siguió los pasos para conectar Microsoft Sentinel a orígenes de datos, configuró un libro y recorrió varias opciones disponibles en Microsoft Sentinel.
