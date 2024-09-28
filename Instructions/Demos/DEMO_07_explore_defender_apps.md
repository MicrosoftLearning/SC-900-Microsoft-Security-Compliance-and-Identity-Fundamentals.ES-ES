<!---
---
Demo: Título: "Microsoft Defender for Cloud Apps" Módulo: "Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft; Módulo 4: Descripción de las funcionalidades de protección contra amenazas de Microsoft Defender XDR; Unidad 5: Descripción de Microsoft Defender for Cloud Apps"
---
--->

# Demo: Microsoft Defender for Cloud Apps

Esta demo está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de protección contra amenazas de Microsoft Defender XDR
- Unidad: Descripción de las aplicaciones de Microsoft Defender for Cloud

## Supuesto de demostración

En esta demo, harás una demostración de las funcionalidades de Microsoft Defender for Cloud Apps.  Ayudarás al estudiante a realizar un recorrido por la información que se muestra en el panel de Cloud Discovery, el catálogo de aplicaciones en la nube y las funcionalidades disponibles para investigar los resultados con el registro de actividad y archivos, y formas de controlar el impacto en tu organización a través de directivas.  Nota: las organizaciones deben tener una licencia para usar Microsoft Defender for Cloud Apps, que es un servicio de suscripción basado en usuarios.  

### Demo, parte 1: Exploración de Cloud Discovery

1. En la barra de direcciones, escribe **admin.microsoft.com**. Inicia sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionado por el host de laboratorio autorizado (ALH) para acceder al Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, selecciona **Mostrar todo**.

1. En Centros de administración, selecciona **Seguridad**.  Se abrirá una nueva página del explorador con la página de bienvenida del portal de Microsoft Defender.  

1. Si es la primera vez que visitas el portal de Microsoft Defender, puede que aparezca una ventana emergente para realizar un recorrido rápido.

1. En el panel de navegación izquierdo, selecciona **Aplicaciones** en la nube para expandir la lista y, a continuación, selecciona **Cloud Discovery**. Esto te lleva a la vista de Panel.  Habla sobre la información disponible en el panel. En la vista del panel, puedes seleccionar diferentes pestañas en la parte superior de la página.  Recorre cada pestaña de la parte superior de la página.

1. Selecciona **Aplicaciones detectadas**. La ventana aplicaciones descubiertas proporciona una vista más detallada de las aplicaciones descubiertas, incluida la puntuación de riesgo, el tráfico, el número de usuarios y mucho más.
    1. En cualquier elemento de la lista, selecciona los **puntos suspensivos** de la columna de acciones de la tabla.  Ten en cuenta las distintas opciones disponibles, incluida la capacidad de etiquetar una aplicación como autorizada o no autorizada.  Vuelve a seleccionar los puntos suspensivos para cerrar el cuadro Acciones.
    1. Al seleccionar un elemento de línea específico, se abre una página de detalles para la aplicación específica.  Selecciona un elemento de la lista.  Para el elemento seleccionado, selecciona la pestaña **Uso de aplicaciones en la nube** para ver información más detallada, como **Uso**, **Usuarios, IP**, **Direcciones** y **Alertas**. Cuando hayas terminado de explorar la página de detalles, vuelve a la página de aplicaciones detectadas; para ello, selecciona **Cloud Discovery** en la ruta de navegación de la parte superior de la página.  Si seleccionas Cloud Discovery en el panel de navegación izquierdo, volverás a la vista del panel.
    1. En la parte superior de la página, selecciona la pestaña **Direcciones IP**. Aquí encontrarás datos, como el número de transacciones, la cantidad de tráfico y las cantidades de carga, por dirección IP.  Ten en cuenta que también puedes filtrar por dirección IP específica o exportar los datos para su posterior análisis.
    1. En la parte superior de la página, selecciona **Usuarios**.  Es el mismo tipo de información que obtienes al seleccionar Direcciones IP, solo que aquí aparece ordenada por usuarios individuales.  De nuevo, filtrarás por usuario específico y exportarás los datos para su posterior análisis.

1. Algo importante que se debe destacar es que la información proporcionada en la página de Cloud Discovery y las pestañas relacionadas se basa en los informes de instantáneas de los registros de tráfico que cargas manualmente desde tus firewalls y servidores proxy, o en los informes continuos que analizan todos los registros reenviados desde tu red utilizando Cloud App Security.  Para ver dónde se configuran estas opciones, selecciona **Acciones** en la esquina superior derecha de la página.
    1. Selecciona la primera opción, **Crear informe de instantáneas de Cloud Discovery** y luego **Siguiente**. Aquí rellenarías los detalles solicitados y cargaría los registros de tráfico para generar y cargar un informe.  Selecciona **Salir** y, si se te pide, selecciona **Salir** de nuevo.  Los datos que ves sobre tu inquilino de laboratorio proceden de un informe de instantáneas. Puedes ver esta información en la parte superior de la pantalla de Cloud Discovery.
    1. Para ver la opción de los informes continuos, selecciona las **Acciones** en la esquina superior derecha de la página y, en el menú desplegable, selecciona **Configurar la carga automática**.  No hay orígenes de datos conectados, pero aquí es donde agregarías un origen de datos. Selecciona **Agregar origen de datos** y, después, selecciona la flecha desplegable del campo **Seleccionar dispositivo** para ver los tipos de dispositivos que puedes conectar como origen de datos.  Selecciona **Cancelar** para salir.
    1. En el panel de navegación izquierdo, selecciona **Cloud Discovery** para volver a la página Cloud Discovery.

1. Con Microsoft Defender for Cloud Apps puedes conectar aplicaciones directamente mediante la configuración de conectores de aplicaciones que te darán una mayor visibilidad y control sobre tus aplicaciones en la nube. En la esquina superior derecha de la pantalla, selecciona **Acciones** y, después, **Configuración de Cloud Discovery**.  Anota la configuración disponible.
    1. En el panel de navegación izquierdo de la ventana de configuración de las aplicaciones en la nube, selecciona **Conectores de aplicaciones** (puede que tengas que desplazarte hacia abajo).
    1. La página de conectores de aplicaciones es donde podrás ver los conectores de aplicaciones ya configurados y donde podrás agregar un conector de aplicaciones.
    1. Deberías ver Microsoft 365 en la lista. Si muestra un error de conexión, ve a los puntos suspensivos verticales situados a la derecha del elemento de línea y selecciona **Editar configuración**.  Para volver a conectarte, selecciona **Conectar Office 365** en la parte inferior de la página. La página debería mostrar ahora que Office 365 está conectado, selecciona **Listo**.  El estado se mostrará ahora con un signo de advertencia amarillo, lo que indica que no hay ningún estado reciente.  El estado tardará algún tiempo en actualizarse, ya que el período de tiempo de examen retroactivo es diferente en cada aplicación y es posible que los inquilinos de laboratorio experimenten retrasos más largos de lo normal.
    1. Para configurar un nuevo conector de aplicaciones.  Selecciona **+ Conectar una aplicación**.  La lista desplegable muestra una lista entre la que elegir.  También puedes querer destacar que la lista incluye la opción de **Sugerir más aplicaciones**.  
    1. Opcionalmente, puedes querer agregar el conector de Microsoft Azure. En la lista desplegable, selecciona **Microsoft Azure**.  En la ventana emergente de Microsoft Azure, selecciona **Conectar Microsoft Azure** y, a continuación, selecciona **Listo**.  Verás un estado conectado (si no lo ves, actualice el explorador) e información sobre el examen de usuarios, datos y actividades.  

1. Mientras estés en la página de configuración de las aplicaciones en la nube, merece la pena que dediques unos minutos a explorar también algunas de las demás configuraciones de Cloud Discovery.  
    1. Selecciona **Aplicaciones de control de aplicaciones de acceso condicional** y presta atención a la descripción "El Control de aplicaciones de acceso condicional agrega funcionalidades de supervisión y control en tiempo real para las aplicaciones".
    1. Selecciona **Microsoft Information Protection**, menciona las configuraciones disponibles.
    1. Explora otros a tu antojo. Destaca el nivel de integración y la flexibilidad.

1. Vuelve al panel de Cloud Discovery; para ello, selecciona **Cloud Discovery** en el panel de navegación izquierdo.

1. Deja esta página abierta, porque la utilizarás en la siguiente parte.

### Demo, parte 2: Exploración del catálogo de aplicaciones en la nube

En esta parte de la demo, mostrarás las funcionalidades del catálogo de aplicaciones en la nube. Cloud Discovery analiza los registros de tráfico en el catálogo de aplicaciones en la nube de Microsoft Defender for Cloud Apps de más de 31 000 aplicaciones en la nube. Las aplicaciones se clasifican y se puntúan en función de más de 80 factores de riesgo para proporcionar visibilidad continua al uso de la nube, Shadow IT y el riesgo que Shadow IT supone para tu organización.  

1. En el panel de navegación izquierdo, selecciona **Catálogo de aplicaciones en la nube**.

1. El catálogo de aplicaciones de nube te permite elegir qué aplicaciones se ajustan a los requisitos de seguridad de la organización. Los administradores pueden realizar el filtrado básico de las aplicaciones como se muestra en la parte superior de la página, lo que incluye si la aplicación está autorizada, no autorizada o no tiene ninguna etiqueta, puntuación de riesgo, factor de riesgo de cumplimiento y factor de riesgo de seguridad.  Por ejemplo, el filtrado por factor de riesgo de cumplimiento te permite buscar estándares, certificaciones y cumplimiento específicos que la aplicación pueda cumplir. Por ejemplo, HIPAA, ISO 27001, SOC 2 y PCI-DSS. Selecciona **Factor de riesgo de cumplimiento** para ver las opciones disponibles.  Para filtrar aún más por puntuación de riesgo, mueve los controles deslizantes de la puntuación de riesgo en la parte superior de la página. Si has movido el control deslizante, asegúrate de establecerlo para que el intervalo esté en 0 a 10.

1. Los administradores también pueden buscar aplicaciones por categoría.  Por ejemplo, en el campo de búsqueda de categoría, escribe **Red social** y, a continuación, selecciona **Red social**.  Selecciona cualquier elemento de la lista para obtener una vista detallada.  Al mantener el mouse sobre cualquier tema de una categoría determinada se mostrará un icono de información que puedes seleccionar para obtener más información sobre ese tema.

1. Deja esta página abierta, porque la utilizarás en la siguiente tarea.

### Demo, parte 3: Exploración del registro de actividad

Explora las formas en las que puedes investigar las actividades registradas con el registro de actividad.

1. En el panel de navegación izquierdo, selecciona **Registro de actividad**. Aquí podrás ver todas las actividades de las aplicaciones conectadas. Es posible que no veas ningún dato enumerado, ya que puede tardar varias horas en realizar exámenes retroactivos una vez habilitada la auditoría y los inquilinos de laboratorio pueden experimentar retrasos más largos que los normales. Observa las opciones de filtro disponibles y la opción para crear una directiva a partir de la búsqueda.

1. Deja esta página abierta, porque la utilizarás en la siguiente tarea.

### Demo, parte 4: Exploración de directivas

En esta parte, mostrarás las opciones disponibles para las directivas en Microsoft Defender for Cloud Apps.

1. En el panel de navegación izquierdo, selecciona **Directivas**.
    1. Selecciona **Administración de directivas**.  Las directivas enumeradas proporcionan información sobre el número de alertas generadas por la directiva, la gravedad, etc. Al seleccionar cualquier elemento de línea se proporciona información más detallada sobre la directiva. Selecciona un elemento de la lista para ver información detallada sobre la directiva.  Comenta algunas de las opciones y después selecciona **Cancelar**.
    2. Ten en cuenta que también puedes crear una directiva. Selecciona **+ Crear directiva** para ver los tipos de directivas que puedes crear.  Selecciona **Directiva de actividad** para ver las distintas opciones disponibles para crear la directiva.  Selecciona **Cancelar** para salir de la ventana de configuración.
    3. Ten en cuenta que también puedes tener la opción de exportar información de directiva.

1. En el panel de navegación izquierdo, selecciona **Plantillas de directiva**. Para crear una directiva a partir de una de las plantillas disponibles, selecciona **+** en el lado derecho del elemento de línea de plantilla.  Mira las distintas opciones de configuración de la directiva.  Selecciona **Cancelar** para salir de la página.

1. En el panel de navegación izquierdo, selecciona **Inicio** para volver a la página principal de Microsoft Defender.

1. Mantén abierta la pestaña del explorador si tienes previsto continuar con la siguiente demo.

### Revisar

En esta demo, hiciste una demostración de las funcionalidades de Microsoft Defender for Cloud Apps.  Has mostrado la información disponible en el panel de Cloud Discovery, el catálogo de aplicaciones en la nube y las funcionalidades disponibles para investigar los resultados con el registro de actividad y archivos, y formas de controlar el impacto en tu organización a través de directivas
