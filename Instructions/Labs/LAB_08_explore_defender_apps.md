---
lab:
  title: Explorar Microsoft Defender for Cloud Apps
  module: Describe the threat protection capabilities of Microsoft 365
---

# Laboratorio: Explorar Microsoft Defender for Cloud Apps

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de protección contra amenazas de Microsoft 365
- Unidad: Descripción de las aplicaciones de Microsoft Defender for Cloud

## Escenario del laboratorio

En este laboratorio explorará las funcionalidades de las aplicaciones de Microsoft Defender for Cloud.  Realizará un recorrido por la información que se muestra en el panel de Cloud Discovery, el catálogo de aplicaciones en la nube, las funcionalidades disponibles para investigar los resultados y formas de controlar el impacto en su organización a través de directivas. Nota: Las organizaciones deben tener una licencia para usar Microsoft Defender for Cloud Apps, que es un servicio de suscripción basado en usuarios.

**Tiempo estimado: 30 minutos**

### Tarea 1: Explorar Cloud Discovery

Explorar Cloud Discovery.

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador para el inquilino de Microsoft 365.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Si has iniciado sesión anteriormente como administrador, se te pedirá que completes una autenticación secundaria, como parte de MFA. Si no has iniciado sesión anteriormente como administrador, se te pedirá que completes el proceso de registro de MFA. Sigue las indicaciones en la pantalla para configurar MFA.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Seguridad**.  Se abrirá una nueva página del explorador con la página de bienvenida del portal de Microsoft 365 Defender.  

1. Si es la primera vez que visita el portal de Microsoft 365 Defender, puede que aparezca una ventana emergente para realizar un recorrido rápido.  Cierre esto.

1. En el panel de navegación izquierdo, seleccione **Aplicaciones** en la nube para expandir la lista y, a continuación, seleccione **Cloud Discovery**. Esto le lleva a la vista de Panel.  Observe la información disponible en el panel. En la vista del panel, puede seleccionar diferentes pestañas en la parte superior de la página.  

1. Seleccione **Aplicaciones detectadas**. La ventana aplicaciones descubiertas proporciona una vista más detallada de las aplicaciones descubiertas, incluida la puntuación de riesgo, el tráfico, el número de usuarios y mucho más.
    1. En uno de los elementos de la lista, seleccione los **puntos suspensivos** (...) de la columna de acciones de la tabla.  Tenga en cuenta las distintas opciones disponibles, incluida la capacidad de etiquetar una aplicación como autorizada o no autorizada.  Seleccione el **puntos suspensivos** (...), de nuevo, para cerrar el cuadro de acciones.
    1. Al seleccionar un elemento de línea específico, se abre una página de detalles para la aplicación específica.  Seleccione un elemento de la lista y revise la información disponible en la página de información general.  Para el elemento seleccionado, seleccione la pestaña **Uso de aplicaciones en la nube** para ver información más detallada, como **Uso**, **Usuarios, IP**, **Direcciones** y **Alertas**. Cuando hayas terminado de explorar la página de detalles, vuelve a la página de aplicaciones detectadas; para ello, selecciona **Cloud Discovery** en la ruta de navegación de la parte superior de la página.  Si seleccionas Cloud Discovery en el panel de navegación izquierdo, volverás a la vista del panel.
    1. En la parte superior de la página, selecciona la pestaña **Direcciones IP**. Aquí encontrarás datos, como el número de transacciones, la cantidad de tráfico y las cantidades de carga, por dirección IP.  Tenga en cuenta que también puede filtrar por dirección IP específica o exportar los datos para su posterior análisis.
    1. En la parte superior de la página, seleccione **Usuarios**.  Es el mismo tipo de información que obtiene al seleccionar Direcciones IP, solo que aquí aparece ordenada por usuarios individuales.  De nuevo, filtrará por usuario específico y exportará los datos para su posterior análisis.

1. La información proporcionada en la página de Cloud Discovery y las pestañas relacionadas se basa en los informes de instantáneas de los registros de tráfico que carga manualmente desde sus firewalls y servidores proxy, o en los informes continuos que analizan todos los registros reenviados desde su red utilizando Cloud App Security.  Para ver dónde se configuran estas opciones, seleccione **Acciones** en la esquina superior derecha de la página.
    1. Selecciona la primera opción, **Crear informe de instantáneas de Cloud Discovery** y luego **Siguiente**. Aquí rellenarías los detalles solicitados y cargaría los registros de tráfico para generar y cargar un informe.  Selecciona **Salir** y, si se te pide, selecciona **Salir** de nuevo.  Los datos que ves sobre tu inquilino de laboratorio proceden de un informe de instantáneas. Puedes ver esta información en la parte superior de la pantalla de Cloud Discovery.
    1. Para ver la opción de los informes continuos, selecciona las **Acciones** en la esquina superior derecha de la página y, en el menú desplegable, selecciona **Configurar la carga automática**.  No hay orígenes de datos conectados, pero aquí es donde agregarías un origen de datos. Seleccione **Agregar origen de datos** y, después, seleccione la flecha desplegable del campo **Seleccionar dispositivo** para ver los tipos de dispositivos que puede conectar como origen de datos.  Seleccione **Cancelar** para salir.
    1. En el panel de navegación izquierdo, seleccione **Cloud Discovery** para volver a la página Cloud Discovery.

1. Puede conectar aplicaciones directamente mediante la configuración de conectores de aplicaciones que le darán una mayor visibilidad y control sobre sus aplicaciones en la nube. En la esquina superior derecha de la pantalla, seleccione **Acciones** y, después, **Configuración de Cloud Discovery**.  En el lado izquierdo de la pantalla, en Aplicaciones conectadas, seleccione **Conectores de aplicación**.  

    1. En la página Aplicaciones conectadas, seleccione **Office 365** de la lista para ver la información detallada disponible y, a continuación, seleccione los puntos suspensivos verticales (⋮) en el lado derecho de la pantalla y seleccione **Ver configuración del conector de aplicaciones** para volver a la página Conectores de aplicaciones. Si Office 365 muestra un error de conexión, lo más probable es que se deba a que la opción Auditoría no está activada.  Si la auditoría está habilitada, vaya a los puntos suspensivos verticales (⋮) en el lado derecho del elemento de línea y seleccione **Editar configuración**.  Para volver a conectarse, seleccione **Conectar Office 365** en la parte inferior de la página. La página debería mostrar ahora que Office 365 está conectado. Seleccione **Listo**.  El estado se mostrará ahora con un signo de advertencia amarillo, lo que indica que no hay ningún estado reciente.  El estado tardará algún tiempo en actualizarse, ya que el período de tiempo de examen retroactivo es diferente en cada aplicación y es posible que los inquilinos de laboratorio experimenten retrasos más largos de lo normal.

    1. Ahora configurará un nuevo conector de aplicaciones. Seleccione **+Conectar una aplicación** y, en la lista desplegable, seleccione **Microsoft Azure**.  En la ventana emergente de Microsoft Azure, seleccione **Conectar Microsoft Azure** y, a continuación, seleccione **Listo**.  Verá un estado conectado (si no lo ve, actualice el explorador). Seleccione **Microsoft Azure** para ver la información detallada sobre el examen de usuarios, datos y actividades.  Vuelva al panel de Cloud Discovery; para ello seleccione **Cloud Discovery** bajo Aplicaciones en la nube, en el panel de navegación izquierdo.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### Tarea 2: Explorar el catálogo de aplicaciones en la nube

Cloud Discovery analiza los registros de tráfico en el catálogo de aplicaciones en la nube de Microsoft Defender for Cloud Apps de más de 31 000 aplicaciones en la nube. Las aplicaciones se clasifican y se puntúan en función de más de 80 factores de riesgo para proporcionar visibilidad continua al uso de la nube, Shadow IT y el riesgo que Shadow IT supone para su organización.  En esta tarea, explorará las funcionalidades del catálogo de aplicaciones en la nube.

1. En el panel de navegación izquierdo, seleccione **Catálogo de aplicaciones en la nube**.

1. El catálogo de aplicaciones de nube te permite elegir qué aplicaciones se ajustan a los requisitos de seguridad de la organización. Los administradores pueden realizar el filtrado básico de las aplicaciones como se muestra en la parte superior de la página, lo que incluye si la aplicación está autorizada, no autorizada o no tiene ninguna etiqueta, puntuación de riesgo, factor de riesgo de cumplimiento y factor de riesgo de seguridad.  Por ejemplo, el filtrado por factor de riesgo de cumplimiento te permite buscar estándares, certificaciones y cumplimiento específicos que la aplicación pueda cumplir. Por ejemplo, HIPAA, ISO 27001, SOC 2 y PCI-DSS. Selecciona **Factor de riesgo de cumplimiento** para ver las opciones disponibles.  Para filtrar aún más por puntuación de riesgo, mueve los controles deslizantes de la puntuación de riesgo en la parte superior de la página. Si has movido el control deslizante, asegúrate de establecerlo para que el intervalo esté en 0 a 10.

1. Los administradores también pueden buscar aplicaciones por categoría.  Por ejemplo, en el campo de búsqueda de categoría, escribe **Red social** y, a continuación, selecciona **Red social**.  Selecciona cualquier elemento de la lista para obtener una vista detallada.  Al mantener el mouse sobre cualquier tema de una categoría determinada se mostrará un icono de información que puedes seleccionar para obtener más información sobre ese tema.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### Tarea 3: Explorar el registro de actividad y los archivos

Explore las formas en las que puede investigar las actividades grabadas con el registro de actividad y los archivos.

1. En el panel de navegación izquierdo, seleccione **Registro de actividad**. Aquí podrás ver todas las actividades de las aplicaciones conectadas. Es posible que no veas ningún dato enumerado, ya que puede tardar varias horas en realizar exámenes retroactivos una vez habilitada la auditoría y los inquilinos de laboratorio pueden experimentar retrasos más largos que los normales. Observe las opciones de filtro disponibles y la opción para crear una directiva a partir de la búsqueda.

1. Para proporcionar protección de datos, Microsoft Defender for Cloud Apps proporciona visibilidad sobre todos los archivos de las aplicaciones conectadas, por ejemplo, todos los archivos almacenados en SharePoint y Salesforce. En el panel de navegación izquierdo, seleccione y explore la opción **Archivos**.
    1. La capacidad de examinar archivos debe estar habilitada como parte de la configuración de Information Protection de las aplicaciones en la nube de Microsoft 365.  Seleccione **Habilitar supervisión de archivos** y seleccione la casilla situada junto a donde dice **Habilitar supervisión de archivos**, después seleccione **Guardar**.  
    1. Vuelva a los archivos seleccionando **Archivos**, que se muestra en aplicaciones en la nube, en el panel de navegación izquierdo. Como se indicó, los archivos pueden tardar varios días en mostrarse, una vez habilitada la supervisión de archivos, merece la pena tener en cuenta que una vez que se muestran los archivos, puede filtrar los datos por aplicación, propietario, nivel de acceso, tipo de archivo y directiva coincidente. También puede crear una nueva directiva a partir de la búsqueda y la exportación de los datos.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### Tarea 4: Explorar las directivas

En esta tarea, explorará las directivas en las aplicaciones de Microsoft Defender for Cloud.

1. En el panel de navegación izquierdo, seleccione **Directivas** y, a continuación, seleccione **Administración de directivas**.  Las directivas enumeradas proporcionan información sobre el número de alertas generadas por la directiva, la gravedad, etc. Al seleccionar cualquier elemento de línea se proporciona información más detallada sobre la directiva.
    1. Tenga en cuenta que también puede crear una directiva. Selecciona **+ Crear directiva** para ver los tipos de directivas que puedes crear.  Selecciona **Directiva de actividad** para ver las distintas opciones disponibles para crear la directiva.  Selecciona **Cancelar** para salir de la ventana de configuración.
    1. Ten en cuenta que también puedes tener la opción de exportar información de directiva.

1. En el panel de navegación izquierdo, seleccione **Plantillas de directiva**. Para crear una directiva a partir de una de las plantillas disponibles, seleccione **+** en el lado derecho del elemento de línea de plantilla.  Vea las distintas opciones de configuración de la directiva.  Seleccione **Cancelar** para salir de la página.

1. Cierre la ventana del explorador.

### Revisar

En este laboratorio exploró las funcionalidades de Microsoft Defender for Cloud Apps.  Ha realizado un recorrido por la información que se muestra en el panel de Cloud Discovery, el catálogo de aplicaciones en la nube, las funcionalidades disponibles para investigar los resultados y formas de controlar el impacto en su organización a través de directivas.
