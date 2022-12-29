<a name="---"></a><!---
---
Laboratorio: Título: "Exploración de Microsoft Defender for Cloud" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft; Módulo 2: Descripción de las funcionalidades de administración de seguridad de Azure; Unidad 3: Descripción de Microsoft Defender for Cloud"
---
--->

# <a name="lab-explore-microsoft-defender-for-cloud"></a>Laboratorio: Exploración de Microsoft Defender for Cloud

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft.
- Módulo: Descripción de las funcionalidades de administración de seguridad de Azure
- Unidad: Descripción de Microsoft Defender for Cloud

## <a name="lab-scenario"></a>Escenario del laboratorio

En este laboratorio, explorará Microsoft Defender for Cloud.  NOTA: La suscripción de Azure proporcionada por el host de laboratorio autorizado (ALH) limita el acceso y puede experimentar retrasos más largos que los normales.

**Tiempo estimado**: 30 minutos

### <a name="task-1"></a>Tarea 1

En esta tarea, realizará un tutorial de alto nivel de algunas de las funcionalidades de Microsoft Defender for Cloud.

1. Abrir Microsoft Edge. En la barra de direcciones escriba **portal.azure.com**.
1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana Inicio de sesión, escriba el nombre de usuario proporcionado por el proveedor de hospedaje de laboratorio y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En la barra de búsqueda azul escriba **Microsoft Defender for Cloud** y, luego, en la lista de resultados, seleccione **Microsoft Defender for Cloud**.

1. Si es la primera vez que entra en Microsoft Defender for Cloud con su suscripción, es posible que llegue a la página de introducción y se le pida que actualice.  Desplácese hasta la parte inferior de la página y seleccione **Recordarme más tarde** (u **Omitir**).  Se le dirigirá a la página de información general.

1. En la página de información general de Microsoft Defender for Cloud, observe la información disponible en la página (si ve 0 recursos evaluados y recomendaciones activas, actualice la página del explorador; esto puede tardar unos minutos).  La información en la parte superior de la página incluye el número de suscripciones de Azure, el número de recursos evaluados, el número de recomendaciones activas y cualquier alerta de seguridad.  En el cuerpo principal de la página, hay tarjetas que representan la posición de seguridad, el cumplimiento normativo, la información, etc.  Nota: La iniciativa de directiva predeterminada de Microsoft Defender for Cloud, que normalmente tendría que asignar el administrador, ya se ha asignado como parte de la configuración de la suscripción de Azure. Sin embargo, la puntuación segura se mostrará como 0 % porque puede haber un retraso de hasta 24 horas para que Azure refleje una puntuación inicial.

1. En la parte superior de la página, seleccione **Recursos evaluados**.  (Tenga en cuenta que esto equivale a haber seleccionado Inventario en el panel de navegación izquierdo de la página principal de Microsoft Defender for Cloud).
    1. Esto le lleva a la página **Inventario** que muestra los recursos actuales. Seleccione el recurso de máquina virtual **sc900-winwm**. Este recurso está asociado a la máquina virtual que usó en el laboratorio anterior.
    1. La página de estado de los recursos de la máquina virtual ofrece una lista de recomendaciones.  En la lista disponible, seleccione cualquier elemento de la lista que muestre un estado **incorrecto**.
    1. Observe la descripción detallada.  Seleccione la flecha desplegable situada junto a Pasos de corrección. Observe cómo se proporcionan las instrucciones de corrección (o vínculos a instrucciones) junto con la opción de tomar medidas.  Salga de la ventana sin realizar ninguna acción.
    1. Vuelva a la página de información general de Microsoft Defender for Cloud; para ello, seleccione **Microsoft Defender for Cloud | Información general** de la parte superior de la página, encima de donde dice Estado de los recursos.

1. En el panel de navegación izquierdo, seleccione **Recomendaciones**.  (Tenga en cuenta que esto equivale a haber seleccionado Recomendaciones activas en la parte superior de la página de información general de Microsoft Defender for Cloud).
    1. Compruebe que la pestaña **Todas las recomendaciones** está seleccionada (subrayada).  Tenga en cuenta la vista del panel que muestra recomendaciones activas por gravedad, estados de los recursos y mucho más.
    1. Observe que algunos elementos aparecen como recursos incorrectos, como se muestra en la barra roja situada a la derecha del elemento de línea.  En la lista, seleccione **Se debe habilitar Microsoft Defender para Resource Manager**.  En la página que se abre, verá una descripción, los pasos de corrección y los recursos afectados. Puede salir de esta página si selecciona la **X** en la esquina superior derecha de la pantalla.
    1. Puede salir de la página de recomendaciones si selecciona la **X** en la esquina superior derecha de la pantalla, para volver a la página de información general.

1. En el panel de navegación izquierdo principal, seleccione **Cumplimiento normativo**. En la página de cumplimiento normativo se proporciona una lista de controles de cumplimiento basados en la prueba comparativa de punto de referencia de seguridad en la nube de Microsoft (compruebe que la pestaña de prueba comparativa de punto de referencia de seguridad en la nube de Microsoft esté seleccionada o subrayada). En cada dominio de control hay un subconjunto de controles y para cada control hay una o varias evaluaciones. Cada evaluación proporciona información, incluida la descripción, la corrección y los recursos afectados.
    1. Vamos a explorar una de las áreas de dominios de control. Seleccione (expanda) **NS. Seguridad de red**. Se muestra una lista de controles relacionados con la seguridad de red.
    1. Seleccione **NS-10. Microsoft Defender para DNS debe estar habilitado**. Tenga en cuenta la lista de evaluaciones automatizadas (que incluyen evaluaciones automatizadas para AWS) y cómo cada elemento de línea de evaluación proporciona información, incluido el tipo de recurso, los recursos con errores y las estaciones de cumplimiento. Seleccione las evaluaciones enumeradas.  Aquí verá información que incluye una descripción, pasos de corrección y recursos afectados.
    1. Cierre la página con la **X** de la esquina superior derecha de la pantalla.
    1. Seleccione **Información general** en el panel de navegación izquierdo para volver a la página de información general de Microsoft Defender for Cloud.
    1. Deje abierta la página de información general de Microsoft Defender for Cloud, porque la utilizará en la tarea siguiente.

### <a name="task-2"></a>Tarea 2

Recuerde que Microsoft Defender for Cloud se ofrece en dos modos: sin características de seguridad mejoradas (gratis) y con características de seguridad mejoradas, disponibles a través de los planes de Microsoft Defender for Cloud. En esta tarea, descubrirá cómo habilitar o deshabilitar los distintos planes de Microsoft Defender for Cloud.

1. En la página de información general de Microsoft Defender for Cloud, seleccione la **configuración del Entorno** en el panel de navegación de la izquierda.
1. Seleccione el cuadro **Expandir todo** y, a continuación, seleccione la suscripción **MOC Subscription--lodXXXXXXXXXXX** que aparece junto al icono de llave amarilla.
1. En la página de planes para Defender, tenga en cuenta que puede seleccionar Habilitar todo o seleccionar planes individuales de Defender. 
    1. Compruebe que el estado de CSPM está establecido en **Activado**, si no es así, establézcalo ahora.  
    1. Habilite el plan para servidores.  Seleccione **Activado** para el elemento de línea Servidores y, a continuación, seleccione **Guardar** en la parte superior de la página.
1. Cierre todas las pestañas abiertas del explorador.

### <a name="review"></a>Revisar

En este laboratorio, ha explorado Microsoft Defender for Cloud.
