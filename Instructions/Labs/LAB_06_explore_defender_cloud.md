<!---
---
Laboratorio: Título: "Explorar Microsoft Defender for Cloud" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft; Módulo 2: Descripción de las funcionalidades de administración de seguridad de Azure; Unidad 3: Descripción de Microsoft Defender for Cloud"
---
--->

# Laboratorio: Explorar Microsoft Defender for Cloud

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de administración de seguridad de Azure
- Unidad: Describir la administración de la posición de seguridad en la nube

## Escenario del laboratorio

En este laboratorio, explorará Microsoft Defender for Cloud.  NOTA: La suscripción de Azure proporcionada por el host de laboratorio autorizado (ALH) limita el acceso y puede experimentar retrasos más largos que los normales.

**Tiempo estimado**: 30 minutos

### Tarea 1

En esta tarea, realizará un tutorial de alto nivel de algunas de las funcionalidades de Microsoft Defender for Cloud.

1. Debe ser la página principal de los servicios de Azure.  Si ha cerrado previamente el explorador, abra Microsoft Edge. En la barra de direcciones, escriba **portal.azure.com** e inicie sesión con sus credenciales de administrador.

1. En la barra de búsqueda azul escriba **Microsoft Defender for Cloud** y, luego, en la lista de resultados, seleccione **Microsoft Defender for Cloud**.

1. Si es la primera vez que entra en Microsoft Defender for Cloud con su suscripción, es posible que llegue a la página de introducción y se le pida que actualice.  Desplácese hasta la parte inferior de la página y seleccione **Recordarme más tarde** (u **Omitir**).  Se le dirigirá a la página de información general.

1. En la página de información general de Microsoft Defender for Cloud, observe la información disponible en la página (si ve 0 recursos evaluados y recomendaciones activas, actualice la página del explorador; esto puede tardar unos minutos).  La información de la parte superior de la página de información general de incluye el número de suscripciones de Azure, el número de recursos evaluados, el número de recomendaciones activas y cualquier alerta de seguridad.  En el cuerpo principal de la página, hay tarjetas que representan la posición de seguridad, el cumplimiento normativo, la información, etc.  Nota: La iniciativa de directiva predeterminada de Microsoft Defender for Cloud, que normalmente tendría que asignar el administrador, ya se ha asignado como parte de la configuración de la suscripción de Azure. Sin embargo, la puntuación segura se mostrará como 0 % porque puede haber un retraso de hasta 24 horas para que Azure refleje una puntuación inicial.

1. En la parte superior de la página, seleccione **Recursos evaluados**. 
    1. Esto le lleva a la página **Inventario** que muestra los recursos actuales. Seleccione el recurso de máquina virtual **sc900-winwm**. Este recurso está asociado a la máquina virtual que usó en el laboratorio anterior.
    1. La página de estado de los recursos de la máquina virtual ofrece una lista de recomendaciones.  En la lista disponible, seleccione cualquier elemento de la lista que muestre un estado **incorrecto**.
    1. Observe la descripción detallada.  Seleccione la flecha desplegable situada junto a Pasos de corrección. Observe cómo se proporcionan las instrucciones de corrección (o vínculos a instrucciones) junto con la opción de tomar medidas.  Salga de la ventana sin realizar ninguna acción.
    1. Vuelva a la página de información general de Microsoft Defender for Cloud; para ello, seleccione **Microsoft Defender for Cloud | Información general** de la parte superior de la página, encima de donde dice Estado de los recursos.

1. En el panel de navegación izquierdo, seleccione **Recomendaciones**.  
    1. Compruebe que la pestaña **Todas las recomendaciones** está seleccionada (subrayada).  Tenga en cuenta la vista del panel que muestra recomendaciones activas por gravedad, estados de los recursos y mucho más.
    1. Seleccione un elemento de la lista.  En la página que se abre, verá una descripción e información adicional que puede incluir los pasos de corrección, los recursos afectados y más. Salga de la página, para ello, seleccione la **X** de la esquina superior derecha de la página.

1. En el panel de navegación izquierdo principal, seleccione **Cumplimiento normativo**.  **NOTA**: Si ve que no hay ninguna suscripción para calcular el cumplimiento, es porque puede haber hasta un retraso de 24 horas para que aparezca información. Pase a la tarea 2.  Si ve información, continúe con los siguientes pasos.
    1. En la página de cumplimiento normativo se proporciona una lista de controles de cumplimiento basados en la prueba comparativa de punto de referencia de seguridad en la nube de Microsoft (compruebe que la pestaña de prueba comparativa de punto de referencia de seguridad en la nube de Microsoft esté seleccionada o subrayada). En cada dominio de control hay un subconjunto de controles y para cada control hay una o varias evaluaciones. Cada evaluación proporciona información, incluida la descripción, la corrección y los recursos afectados.
    1. Vamos a explorar una de las áreas de dominios de control. Seleccione (expanda) **NS. Seguridad de red**. Se muestra una lista de controles relacionados con la seguridad de red.
    1. Seleccione **NS-10. Confirmar la seguridad del Sistema de nombres de dominio (DNS)**. Tenga en cuenta la lista de evaluaciones automatizadas (que incluyen evaluaciones automatizadas para AWS) y cómo cada elemento de línea de evaluación proporciona información, incluido el tipo de recurso, los recursos con errores y las estaciones de cumplimiento. Seleccione las evaluaciones enumeradas.  Aquí verá información que incluye una descripción, pasos de corrección y recursos afectados.
    1. Cierre la página con la **X** de la esquina superior derecha de la pantalla.
    1. Seleccione **Información general** en el panel de navegación izquierdo para volver a la página de información general de Microsoft Defender for Cloud.
    1. Deje abierta la página de información general de Microsoft Defender for Cloud, porque la utilizará en la tarea siguiente.

### Tarea 2

Recuerde que Microsoft Defender for Cloud se ofrece en dos modos: sin características de seguridad mejoradas (gratis) y con características de seguridad mejoradas, disponibles a través de los planes de Microsoft Defender for Cloud. En esta tarea, descubrirá cómo habilitar o deshabilitar los distintos planes de Microsoft Defender for Cloud.

1. En la página de información general de Microsoft Defender for Cloud, seleccione la **configuración del Entorno** en el panel de navegación de la izquierda.
1. Seleccione el cuadro **Expandir todo** y, a continuación, seleccione la suscripción **MOC Subscription--lodXXXXXXXXXXX** que aparece junto al icono de llave amarilla.
1. En la página de planes para Defender, tenga en cuenta que puede seleccionar Habilitar todo o seleccionar planes individuales de Defender. 
    1. Compruebe que el estado de CSPM está establecido en **Activado**, si no es así, establézcalo ahora.  
    1. Habilite el plan para servidores.  Seleccione **Activado** para el elemento de línea Servidores y, a continuación, seleccione **Guardar** en la parte superior de la página.
1. En la esquina superior izquierda de la ventana, justo debajo de la barra azul donde pone "Microsoft Azure", seleccione **Inicio** para volver a la página principal de los servicios de Azure.
1. Mantenga abierta la pestaña de Azure en el explorador.

### Revisar

En este laboratorio, ha explorado Microsoft Defender for Cloud.
