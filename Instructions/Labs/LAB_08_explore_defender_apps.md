---
lab:
  title: 'Exploración de Microsoft Defender for Cloud Apps '
  module: 'Module 3 Lesson 4: Describe the capabilities of Microsoft security solutions: Describe threat protection with Microsoft 365 Defender'
ms.openlocfilehash: aa360b3d9e604e384cc5b040ef747425af76e13b
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2022
ms.locfileid: "137894229"
---
# <a name="lab-explore-microsoft-defender-for-cloud-apps"></a>Laboratorio: Exploración de Microsoft Defender for Cloud Apps

## <a name="lab-scenario"></a>Escenario del laboratorio
En este laboratorio explorará las funcionalidades de Microsoft Defender for Cloud Apps.  Realizará un recorrido por la información que se muestra en el panel de Cloud Discovery y las funcionalidades disponibles para investigar los resultados y controlar el impacto en su organización a través de directivas.  Nota:  Las organizaciones deben tener una licencia para usar Microsoft Defender for Cloud Apps, que es un servicio de suscripción basado en usuarios. 

**Tiempo estimado**: 15-20 minutos

#### <a name="task-1-explore-cloud-discovery"></a>Tarea 1: Explorar Cloud Discovery

1.  Abrir Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es el id. de inquilino único facilitado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Haga clic en **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. Debajo de Centros de administración, seleccione **Seguridad**.  Se abrirá una nueva página del explorador con la página principal del portal de Microsoft 365 Defender.  

1. En la parte inferior del panel de navegación izquierdo de la página de Microsoft 365 Defender, seleccione **Más recursos**.

1. En la tarjeta de **Microsoft Defender for Cloud Apps**, seleccione **Abrir**.  Se abrirá una nueva página del explorador con el panel de Cloud App Security.  Observe las tarjetas de información que hay disponibles.  Es posible que las tarjetas no muestren información, dado que se trata del ambiente de una cuenta empresarial con un laboratorio preconfigurado que no se ha utilizado de forma activa.  

1. En el panel de navegación izquierdo, seleccione **Descubrir** y luego seleccione **panel de Cloud Discovery** en el menú desplegable.  El panel incluye una descripción general de las aplicaciones detectadas, las categorías de aplicaciones, los niveles de riesgo, y mucho más.  
    1. En la parte superior de la página de Cloud Discovery, seleccione la pestaña **Aplicaciones detectadas**  La ventana Aplicaciones detectadas ofrece una vista más detallada de las aplicaciones detectadas, incluyendo la puntuación de riesgo, el tráfico, el número de usuarios, y mucho más.
        1. En uno de los elementos de la lista, seleccione los **puntos suspensivos** de la columna de acciones de la tabla.  Observe las diferentes opciones disponibles, incluida la capacidad de etiquetar una aplicación como autorizada o no autorizada.  Vuelva a seleccionar los puntos suspensivos para cerrar el cuadro Acciones.
        1. Si selecciona un elemento de línea específico, se abrirá una página de detalles para esa aplicación.  Seleccione un elemento de la lista.  Explore las diferentes pestañas del elemento seleccionado en la parte superior de la página de detalles:  **Uso**, **Información, IP**, **Direcciones**, **Usuarios** y **Alertas**. Cuando haya terminado de explorar la página de detalles, vuelva a Aplicaciones detectadas. Para ello, seleccione la opción **Aplicaciones detectadas** en el panel de navegación de la izquierda.
    1. En la parte superior de la página, seleccione la pestaña **Direcciones IP** (esto equivale a seleccionar Direcciones IP en el panel de navegación izquierdo).  Aquí encontrará datos como el número de transacciones, la cantidad de tráfico y el número de subidas, ordenados por dirección IP.  Observe que también puede filtrar por una dirección IP específica o exportar los datos para realizar un análisis más detallado.
    1. En la parte superior de la página (o en el panel de navegación izquierdo), seleccione **Usuarios**.  Es el mismo tipo de información que obtiene al seleccionar Direcciones IP, solo que aquí aparece ordenada por usuarios individuales.  Aquí también puede filtrar por un usuario específico y exportar los datos para realizar un análisis más detallado.

1. La información que se muestra en estas pestañas se basa en los informes de instantáneas de los registros de tráfico que carga manualmente desde sus firewalls y servidores proxy, o en los informes continuos que analizan todos los registros reenviados desde su red utilizando Cloud App Security.  Para ver dónde se configuran estas opciones, seleccione los **puntos suspensivos** verticales de la esquina superior derecha de la página.
    1. Seleccione la primera opción, **Crear informe de instantáneas de Cloud Discovery**. Aquí es donde completaría los detalles requeridos y cargaría los registros de tráfico para generar y cargar un informe.  Seleccione **Salir**.  Los datos que ve sobre su inquilino de laboratorio proceden de un informe de instantáneas. Puede ver esta información en la esquina superior derecha de la pantalla.
    1. Para ver la opción de los informes continuos, seleccione los **puntos suspensivos** en la esquina superior derecha de la página y, en el menú desplegable, seleccione **Configurar la carga automática**.  No hay orígenes de datos conectados, pero aquí es donde agregaría uno. Seleccione **Agregar origen de datos** y, después, en la ventana Agregar origen de datos, seleccione la flecha desplegable del campo Origen para ver los tipos de dispositivos que puede conectar como origen de datos.  Seleccione **Cancelar** para salir.

1. Otro punto a mencionar es que puede conectar aplicaciones directamente mediante la configuración de conectores de aplicaciones que le darán una mayor visibilidad y control sobre sus aplicaciones en la nube. En la esquina superior izquierda de la pantalla, seleccione el **icono en forma de engranaje de configuración** y, en la lista desplegable, seleccione **Conectores de aplicaciones**.  
    1. En la página Aplicaciones conectadas, Office 365 debería aparecer en la lista con el estado "Conectado".  Si Office 365 muestra un error de conexión, lo más probable es que se deba a que la opción Auditoría no está activada.
    1. Seleccione **+Conectar una aplicación** y, en la lista desplegable, seleccione **Microsoft Azure**.  En la ventana emergente de Microsoft Azure, seleccione **Conectar Microsoft Azure**.  Se mostrará el estado "Conectado" e información sobre el examen de usuarios, datos y actividades.  Seleccione el botón **Cerrar**.

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.

#### <a name="task-2-explore-ways-in-which-you-can-investigate-the-recorded-activities"></a>Tarea 2: Explorar las formas de investigar las actividades registradas

1. En el panel de navegación izquierdo, debajo de la opción Investigar, seleccione **Registro de actividad**.  Aquí podrá ver todas las actividades de las aplicaciones que ha conectado.   Dado que ya ha conectado el conector de Office 365, debería poder ver algún dato. Después de conectar Cloud App Security con una aplicación mediante el conector de aplicaciones, Cloud App Security examina todas las actividades que se han producido (el período de tiempo de examen retroactivo varía según la aplicación) y después se actualiza constantemente con nuevas actividades.  

1. Seleccione la columna de actividad de cualquier elemento para mostrar información más detallada. En el extremo derecho del elemento seleccionado, seleccione los **puntos suspensivos** verticales.  Tenga en cuenta las distintas opciones.  Seleccione la columna de actividad del mismo elemento para contraer la vista detallada.

1. Observe la opción para agregar una nueva directiva a partir de la búsqueda o exportar los datos para realizar un análisis más detallado que aparece en la parte superior de la página.  Seleccione **+Nueva directiva a partir de búsqueda**.  Tenga en cuenta que puede crear una directiva a partir de una plantilla, seleccionar la gravedad y la categoría de las directivas, crear filtros para ellas, crear alertas e incluso enviar las alertas a Power Automate.  Seleccione **Cancelar** para salir de la ventana de creación de directivas.

1. En el panel de navegación izquierdo, seleccione y explore la opción **Archivos** y observe las opciones para filtrar datos, crear una directiva de archivos y exportar los datos.  

1. En el panel de navegación izquierdo, seleccione y explore la opción **Usuario y cuentas**.  Observe las opciones para filtrar y exportar los datos.

1. En el panel de navegación de la izquierda, seleccione **Configuración de seguridad**. En esta página encontrará evaluaciones de la configuración de seguridad para sus cuentas de Azure, Amazon Web Services (AWS) y Google Cloud Platform (GCP).

1. Deje esta página abierta, porque la utilizará en la siguiente tarea.


#### <a name="task-3-in-this-task-you-will-explore-the-policies-and-alerts-pages-in-microsoft-defender-for-cloud-apps"></a>Tarea 3: En esta tarea, explorará las páginas Directivas y Alertas en Microsoft Defender for Cloud Apps.

1. En el panel de navegación izquierdo, seleccione la tecla de flecha abajo situada junto a **Control** y, después, seleccione **Directivas**.  Las directivas mostradas proporcionan información sobre el número de alertas generadas por la directiva, la gravedad, etc. Al seleccionar cualquier elemento de línea, como **inicio de sesión de riesgo**, se ofrece la opción de editar la directiva. Seleccione **Cancelar** en la parte inferior de la página. 

1. En el panel de navegación izquierdo, seleccione **Alertas**.  Si hay alguna alerta en la lista, seleccione un elemento de la lista de alertas. Revise la información proporcionada.  En la parte superior derecha de la ventana, seleccione **Cerrar alerta** para ver las opciones para cerrar la alerta.  

1. Cierre la ventana del explorador.

#### <a name="review"></a>Revisar
En este laboratorio exploró las funcionalidades de Microsoft Defender for Cloud Apps.  Ha realizado un recorrido por la información que se muestra en el panel de Cloud Discovery y las funcionalidades disponibles para investigar los resultados y controlar el impacto en su organización a través de directivas.