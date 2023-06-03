<a name="---"></a><!---
---
Demostración: Título: "Aplicaciones de Microsoft Defender for Cloud" Módulo: "Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft; Módulo 4: Descripción de las funcionalidades de protección contra amenazas de Microsoft 365; Unidad 5: Descripción de las aplicaciones de Microsoft Defender for Cloud Apps"
---
--->

# <a name="demo-microsoft-defender-for-cloud-apps"></a>Demostración: Microsoft Defender for Cloud Apps

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de protección contra amenazas de Microsoft 365
- Unidad: Descripción de las aplicaciones de Microsoft Defender for Cloud

## <a name="demo-scenario"></a>Escenario de la demo

En esta demo, hará una demostración de las funcionalidades de Microsoft Defender for Cloud Apps.  Ayudará al estudiante a realizar un recorrido por la información que se muestra en el panel de Cloud Discovery, el catálogo de aplicaciones en la nube y las funcionalidades disponibles para investigar los resultados con el registro de actividad y archivos, y formas de controlar el impacto en su organización a través de directivas.  Nota:  Las organizaciones deben tener una licencia para usar Microsoft Defender for Cloud Apps, que es un servicio de suscripción basado en usuarios.  

### <a name="demo-part-1-explore-cloud-discovery"></a>Demo, parte 1: Explorar Cloud Discovery

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.  Con esto debería haber iniciado sesión como administrador.  Si no lo ha hecho, inicie sesión con sus credenciales de administrador.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.  Explique breve y concisamente que es posible acceder a los diferentes centros de administración de Microsoft 365 desde aquí.

1. Debajo de Centros de administración, seleccione **Seguridad**.  Se abrirá una nueva página del explorador con la página principal del portal de Microsoft 365 Defender.  

1. Si esta es la primera vez que visita el portal de Microsoft 365 Defender, es posible que vea una ventana emergente para realizar un paseo introductorio.  Ciérrela.

1. En el panel de navegación izquierdo, seleccione **Aplicaciones** en la nube para expandir la lista y, a continuación, seleccione **Cloud Discovery**. Esto le lleva a la vista de Panel.  Hable sobre la información disponible en el panel. En la vista del panel, puede seleccionar diferentes pestañas en la parte superior de la página.  Recorra cada pestaña de la parte superior de la página.
    
1. Seleccione **Aplicaciones detectadas**. La ventana Aplicaciones detectadas ofrece una vista más detallada de las aplicaciones detectadas, incluyendo la puntuación de riesgo, el tráfico, el número de usuarios, y mucho más. 
    1. En uno de los elementos de la lista, seleccione los **puntos suspensivos** de la columna de acciones de la tabla.  Observe las diferentes opciones disponibles, incluida la capacidad de etiquetar una aplicación como autorizada o no autorizada.  Vuelva a seleccionar los puntos suspensivos para cerrar el cuadro Acciones.
    1. Si selecciona un elemento de línea específico, se abrirá una página de detalles para esa aplicación.  Seleccione un elemento de la lista.  Para el elemento seleccionado, seleccione la pestaña **Uso de aplicaciones en la nube** para ver información más detallada, como **Uso**, **Usuarios, IP**, **Direcciones** y **Alertas**. Cuando haya terminado de explorar la página de detalles, vuelva a la página de aplicaciones detectadas; para ello, seleccione **Cloud Discovery** en la ruta de navegación de la parte superior de la página.  Si selecciona Cloud Discovery en el panel de navegación izquierdo, volverá a la vista del panel.
    1. En la parte superior de la página, seleccione la pestaña **Direcciones IP**.  Aquí encontrará datos, como el número de transacciones, la cantidad de tráfico y las cantidades de carga, por dirección IP.  Observe que también puede filtrar por una dirección IP específica o exportar los datos para realizar un análisis más detallado.
    1. En la parte superior de la página, seleccione **Usuarios**.  Es el mismo tipo de información que obtiene al seleccionar Direcciones IP, solo que aquí aparece ordenada por usuarios individuales.  Aquí también puede filtrar por un usuario específico y exportar los datos para realizar un análisis más detallado.

1. Algo importante que se debe destacar es que la información proporcionada en la página de Cloud Discovery y las pestañas relacionadas se basa en los informes de instantáneas de los registros de tráfico que carga manualmente desde sus firewalls y servidores proxy, o en los informes continuos que analizan todos los registros reenviados desde su red utilizando Cloud App Security.  Para ver dónde se configuran estas opciones, seleccione **Acciones** en la esquina superior derecha de la página.
    1. Seleccione la primera opción, **Crear informe de instantáneas de Cloud Discovery** y, a continuación, seleccione **Siguiente**. Aquí es donde completaría los detalles requeridos y cargaría los registros de tráfico para generar y cargar un informe.  Seleccione **Salir** y, si se le pide, seleccione **Salir** de nuevo.  Los datos que ve sobre su inquilino de laboratorio proceden de un informe de instantáneas. Puede ver esta información en la parte superior de la pantalla de Cloud Discovery.
    1. Para ver la opción de los informes continuos, seleccione las **Acciones** en la esquina superior derecha de la página y, en el menú desplegable, seleccione **Configurar la carga automática**.  No hay orígenes de datos conectados, pero aquí es donde agregaría uno. Seleccione **Agregar origen de datos** y, después, seleccione la flecha desplegable del campo **Seleccionar dispositivo** para ver los tipos de dispositivos que puede conectar como origen de datos.  Seleccione **Cancelar** para salir.
    1. En el panel de navegación izquierdo, seleccione **Cloud Discovery** para volver a la página Cloud Discovery.

1. Con Microsoft 365 Defender for Cloud Apps puede conectar aplicaciones directamente mediante la configuración de conectores de aplicaciones que le darán una mayor visibilidad y control sobre sus aplicaciones en la nube.  Un aspecto importante que se debe destacar es consultar la documentación sobre los requisitos previos para conectar conectores de aplicaciones específicos. En la esquina superior derecha de la pantalla, seleccione **Acciones** y, después, **Configuración de Cloud Discovery**.  En el lado izquierdo de la pantalla, en Aplicaciones conectadas, seleccione **Conectores de aplicaciones**.  
    1. En la página Aplicaciones conectadas, seleccione *Office 365** en la lista para ver información detallada. Si Office 365 muestra un error de conexión, lo más probable es que se deba a que la opción Auditoría no está activada.  Si la auditoría está habilitada, vaya a los puntos suspensivos verticales en el lado derecho del elemento de línea y seleccione **Editar configuración**.  Para volver a conectarse, seleccione **Conectar Office 365** en la parte inferior de la página. La página debería mostrar ahora que Office 365 está conectado, seleccione **Listo**.  El estado se mostrará ahora con un signo de advertencia amarillo, lo que indica que no hay ningún estado reciente.  El estado tardará algún tiempo en actualizarse, ya que el período de tiempo de examen retroactivo difiere según la aplicación y los inquilinos de laboratorio pueden experimentar retrasos más largos que los normales (no se espera que el estado cambie durante la demostración, ya que puede tardar muchas horas).
    1. Ahora configurará un nuevo conector de aplicaciones.  Seleccione **+Conectar una aplicación** y, en la lista desplegable, seleccione **Microsoft Azure**.  En la ventana emergente de Microsoft Azure, seleccione **Conectar Microsoft Azure** y, a continuación, seleccione **Listo**.  Verá un estado conectado (si no lo ve, actualice el explorador) e información sobre el examen de usuarios, datos y actividades.  Vuelva al panel de Cloud Discovery; para ello, seleccione **Cloud Discovery** en el panel de navegación izquierdo.

1. Deje esta página abierta, porque la utilizará en la siguiente parte.

### <a name="demo-part-2---explore-the-cloud-app-catalog"></a>Demostración, parte 2: Exploración del catálogo de aplicaciones en la nube

En esta parte de la demostración, mostrará las funcionalidades del catálogo de aplicaciones en la nube. Cloud Discovery analiza los registros de tráfico en el catálogo de aplicaciones en la nube de Microsoft Defender for Cloud Apps de más de 31 000 aplicaciones en la nube. Las aplicaciones se clasifican y se puntúan en función de más de 80 factores de riesgo para proporcionar visibilidad continua al uso de la nube, Shadow IT y el riesgo que Shadow IT supone para su organización.  

1. En el panel de navegación izquierdo, seleccione **Catálogo de aplicaciones en la nube**.

1. El catálogo de aplicaciones de nube le permite elegir qué aplicaciones se ajustan a los requisitos de seguridad de la organización. Los administradores pueden realizar el filtrado básico de las aplicaciones como se muestra en la parte superior de la página, lo que incluye si la aplicación está autorizada, no autorizada o no tiene ninguna etiqueta, puntuación de riesgo, factor de riesgo de cumplimiento y factor de riesgo de seguridad.  Por ejemplo, el filtrado por factor de riesgo de cumplimiento le permite buscar estándares, certificaciones y cumplimiento específicos que la aplicación pueda cumplir. Por ejemplo, HIPAA, ISO 27001, SOC 2 y PCI-DSS. Seleccione **Factor de riesgo de cumplimiento** para ver las opciones disponibles.  Para filtrar aún más por puntuación de riesgo, mueva los controles deslizantes de la puntuación de riesgo en la parte superior de la página. Si ha movido el control deslizante, asegúrese de establecerlo para que el intervalo esté en 0 a 10.

1. Los administradores también pueden buscar aplicaciones por categoría.  Por ejemplo, en el campo de búsqueda de categoría, escriba **Red social** y, a continuación, seleccione **Red social**.  Seleccione **Yammer** para obtener una vista detallada.  Al mantener el mouse sobre cualquier tema de una categoría determinada se mostrará un icono de información que puede seleccionar para obtener más información sobre ese tema.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### <a name="demo-part-3---explore-the-activity-log-and-files"></a>Demostración, parte 3: Exploración del registro de actividad y los archivos

Explore las formas en las que puede investigar las actividades grabadas con el registro de actividad y los archivos.

1. En el panel de navegación izquierdo, seleccione y explore la opción **Archivos** y anote las opciones para filtrar los datos por aplicación, propietario, nivel de acceso, tipo de archivo y directiva coincidente. Además, tenga en cuenta la opción de crear una nueva directiva a partir de la búsqueda y exportación de los datos.
    1. Seleccione **+Nueva directiva a partir de búsqueda**.  Tenga en cuenta que puede crear una directiva a partir de una plantilla, seleccionar la gravedad y la categoría de las directivas, crear filtros para ellas, crear alertas e incluso enviar las alertas a Power Automate.  Seleccione **Cancelar** para salir de la ventana de creación de directivas y, a continuación, seleccione **Salir de la página**.

1. En el panel de navegación izquierdo, seleccione **Registro de actividad**. Aquí podrá ver todas las actividades de las aplicaciones que ha conectado. Es posible que no vea ningún dato enumerado, ya que puede tardar varias horas en realizar exámenes retroactivos una vez habilitada la auditoría y los inquilinos de laboratorio pueden experimentar retrasos más largos que los normales. Observe las opciones de filtro disponibles y la opción para crear una directiva a partir de la búsqueda.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

### <a name="demo-part-4---explore-policies"></a>Demostración, parte 4: Exploración de directivas

En esta parte, mostrará las opciones disponibles para las directivas en Microsoft Defender for Cloud Apps.

1. En el panel de navegación izquierdo, seleccione **Directivas** y, a continuación, seleccione **Administración de directivas**.  Las directivas mostradas proporcionan información sobre el número de alertas generadas por la directiva, la gravedad, etc. Al seleccionar cualquier elemento de línea, se ofrece información más detallada sobre la directiva. Seleccione un elemento de la lista., p. ej., **Inicio de sesión de riesgo**.
    1. Tenga en cuenta que también puede crear una directiva. Seleccione **+ Crear directiva** para ver los tipos de directivas que puede crear.  Seleccione **Directiva de actividad** para ver las distintas opciones disponibles para crear la directiva.  Seleccione **Cancelar** para salir de la ventana de configuración.
    1. Tenga en cuenta que también puede tener la opción de exportar información de directiva.

1. En el panel de navegación izquierdo, seleccione **Plantillas de directiva**. Para crear una directiva a partir de una de las plantillas disponibles, seleccione **+** en el lado izquierdo del elemento de línea de plantilla.  Vea las distintas opciones de configuración de la directiva.  Seleccione **Cancelar** para salir de la página.

1. Cierre la ventana del explorador.

### <a name="review"></a>Revisar

En esta demo, hizo una demostración de las funcionalidades de Microsoft Defender for Cloud Apps.  Ha mostrado la información disponible en el panel de Cloud Discovery, el catálogo de aplicaciones en la nube y las funcionalidades disponibles para investigar los resultados con el registro de actividad y archivos, y formas de controlar el impacto en su organización a través de directivas
