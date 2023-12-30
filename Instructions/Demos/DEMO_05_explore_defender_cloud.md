<!---
---
Demo: Título: "Microsoft Defender for Cloud" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Describir las capacidades de las soluciones de seguridad de Microsoft; Módulo 2: Describir las capacidades de administración de seguridad de Azure; Unidad 3: Describir Microsoft Defender for Cloud"
---
--->

# Demo: Microsoft Defender for Cloud

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de administración de seguridad de Azure
- Unidad: Describir la administración de la posición de seguridad en la nube

## Supuesto de demostración

En esta demostración, se familiarizará con Microsoft Defender for Cloud y hará una demostración sobre cómo se puede utilizar para mejorar la posición de seguridad de una organización.  NOTA: La suscripción de Azure administrada por el host de laboratorio autorizado (AH) puede limitar algún acceso y experimentar retrasos más largos que los normales.

### Demo, parte 1

En esta tarea de demostración, realizará un tutorial de alto nivel de algunas de las funcionalidades de Microsoft Defender for Cloud.

1. Abra la pestaña del explorador **Inicio- Microsoft Azure**.  Si ha cerrado previamente la pestaña, abra una página del explorador y, en la barra de direcciones, escriba **https://portal.azure.com**. Inicie sesión con las credenciales de Azure que proporciona el host de laboratorio autorizado (ALH).  Esto le llevará a la página principal de servicios de Azure.

1. En la barra de búsqueda azul escriba **Microsoft Defender for Cloud** y, luego, en la lista de resultados, seleccione **Microsoft Defender for Cloud**.

1. Si es la primera vez que entra en Microsoft Defender for Cloud con su suscripción, es posible que llegue a la página de introducción y se le pida que actualice.  Desplácese a la parte inferior de la página y seleccione **Omitir**.  Se le dirigirá a la página de información general. Observe la información disponible en la página de información general de Microsoft Defender for Cloud.  La información de la parte superior de la página de información general de incluye el número de suscripciones de Azure, el número de recursos evaluados, el número de recomendaciones activas y cualquier alerta de seguridad.  En el cuerpo principal de la página hay tarjetas que representan la posición de seguridad, el cumplimiento normativo, la información, etc.  Todas las suscripciones tienen CSPM básico habilitado de forma predeterminada, lo que proporciona una puntuación segura.  
    1. Si la puntuación segura se muestra como 0 %, es porque puede haber un retraso de hasta 24 horas para que Azure refleje una puntuación inicial.  
    1. También es importante destacar que Defender for Cloud es una solución multinube que puede ayudar a mejorar la posición de seguridad no solo con Azure, sino también con AWS y Google Cloud Platform.

1. Lo primero que debe mostrar es que Microsoft Defender for Cloud usa Microsoft Cloud Security Benchmark como iniciativa de directiva predeterminada.  En el panel de navegación de la izquierda, seleccione **Configuración del entorno**. En la ventana principal, seleccione **Expandir todo**.  La vista expandida mostrará su suscripción en texto azul.  Seleccione la suscripción **MOC Subscription--lodXXXXXX**.

1. En el panel de navegación izquierdo, seleccione **Directiva de seguridad**, que aparece en Configuración de directiva. Si no se asigna la iniciativa predeterminada, seleccione **Asignar directiva**.
    1. Tenga en cuenta que, en la pestaña Datos básicos, la definición de la iniciativa es Microsoft Cloud Security Benchmark.  Aparece atenuado porque esta es la iniciativa predeterminada y lo único que estamos haciendo es asignar
    1. Seleccione **Revisar y crear** y, luego, **Crear**. Si quiere, puede desplazarse por los parámetros configurables de las distintas pestañas antes de seleccionar la opción para revisar y crear.
    1. Este es un paso importante para asegurarse de que pueda ver recomendaciones de seguridad basadas en Microsoft Cloud Security Benchmark.  

1. Tenga en cuenta también que hay estándares normativos y del sector que puede agregar que están fuera del cuadro. Si los que aparecen se muestran como en desuso, seleccione **Agregar más estándares** para ver una lista completa.  Seleccione uno de la lista y, a continuación, agréguela manualmente, para hacerlo, seleccione **Revisar y crear** y, a continuación , **Crear**.  Verá que se ha agregado a la lista de regulaciones estándar y del sector.

1. Seleccione **Información general**.  En el cuerpo principal de la página hay tarjetas que representan la posición de seguridad, el cumplimiento normativo, la información, etc.  Todas las suscripciones tienen CSPM básico habilitado, lo que proporciona una puntuación segura. El valor se muestra como 0 % porque puede haber un retraso de hasta 24 horas para que Azure refleje una puntuación inicial.  Aunque la puntuación segura se muestre actualmente como 0 %, Defender for Cloud es una solución multinube que ayuda para mejorar la posición de seguridad no solo con Azure, sino también con AWS y Google Cloud Platform.

1. En la parte superior de la página, seleccione **Recursos evaluados**.  (Tenga en cuenta que esto equivale a haber seleccionado Inventario en el panel de navegación izquierdo de la página principal de Microsoft Defender for Cloud).
    1. Esto le lleva a la página **Inventario** que muestra los recursos actuales. Seleccione el recurso de máquina virtual **sc900-winwm**. Este recurso está asociado a la máquina virtual que usó en el laboratorio / la demostración anterior.
    1. La página de estado de los recursos de la máquina virtual ofrece una lista de recomendaciones.  En la lista disponible, seleccione cualquier elemento de la lista que muestre un estado **incorrecto**.
    1. Observe la descripción detallada.  Seleccione la flecha desplegable situada junto a Pasos de corrección. Observe cómo se proporcionan las instrucciones de corrección (o vínculos a instrucciones) junto con la opción de tomar medidas.  Salga de la ventana sin realizar ninguna acción.
    1. Vuelva a la página de información general de Microsoft Defender for Cloud; para ello, seleccione **Microsoft Defender for Cloud | Información general** de la parte superior de la página, encima de donde dice Estado de los recursos.

1. En el panel de navegación izquierdo, seleccione **Recomendaciones**.  (Tenga en cuenta que esto equivale a haber seleccionado Recomendaciones activas en la parte superior de la página de información general de Microsoft Defender for Cloud).
    1. Compruebe que la pestaña **Todas las recomendaciones** está seleccionada (subrayada).  Tenga en cuenta la vista del panel que muestra recomendaciones activas por gravedad, estados de los recursos y mucho más.
    1. Observe que algunos elementos aparecen como recursos incorrectos, como se muestra en la barra roja situada a la derecha del elemento de línea.  En la lista, seleccione cualquier recurso incorrecto.  En la página que se abre, verá una descripción, los pasos de corrección y los recursos afectados. Salga de la página, para ello, seleccione la **X** de la esquina superior derecha de la página.
    1. Salga de la página de recomendaciones, para hacerlo, seleccione la **X** de la esquina superior derecha de la pantalla.

1. En el panel de navegación izquierdo principal, seleccione **Cumplimiento normativo**.  **NOTA**: Si ve que no hay ninguna suscripción para calcular el cumplimiento, es porque puede haber hasta un retraso de 24 horas para que aparezca información. Pase a la tarea 2.  Si ve información, continúe con los siguientes pasos.
    1. En la página de cumplimiento normativo se proporciona una lista de controles de cumplimiento basados en la prueba comparativa de punto de referencia de seguridad en la nube de Microsoft (compruebe que la pestaña de prueba comparativa de punto de referencia de seguridad en la nube de Microsoft esté seleccionada o subrayada). En cada dominio de control hay un subconjunto de controles y para cada control hay una o varias evaluaciones. Cada evaluación proporciona información, incluida la descripción, la corrección y los recursos afectados.
    1. Vamos a explorar una de las áreas de dominios de control. Seleccione (expanda) **NS. Seguridad de red**. Se muestra una lista de controles relacionados con la seguridad de red.
    1. Seleccione **NS-10. Microsoft Defender para DNS debe estar habilitado**. Tenga en cuenta la lista de evaluaciones automatizadas (que incluyen evaluaciones automatizadas para AWS) y cómo cada elemento de línea de evaluación proporciona información, incluido el tipo de recurso, los recursos con errores y las estaciones de cumplimiento. Seleccione las evaluaciones enumeradas.  Aquí verá información que incluye una descripción, pasos de corrección y recursos afectados.
    1. Cierre la página con la **X** de la esquina superior derecha de la pantalla.
    1. Seleccione **Información general** en el panel de navegación izquierdo para volver a la página de información general de Microsoft Defender for Cloud.
    1. Deje abierta la página de información general de Microsoft Defender for Cloud, porque la utilizará en la tarea siguiente.

### Demo, parte 2

Recuerde que Microsoft Defender for Cloud se ofrece en dos modos: sin características de seguridad mejoradas (gratis) y con características de seguridad mejoradas, disponibles a través de los planes de Microsoft Defender for Cloud. En esta tarea, descubrirá cómo habilitar o deshabilitar los distintos planes de Microsoft Defender for Cloud.

1. En la página de información general de Microsoft Defender for Cloud, seleccione la **configuración del Entorno** en el panel de navegación de la izquierda.
1. Seleccione el cuadro **Expandir todo** y, a continuación, seleccione la suscripción **MOC Subscription--lodXXXXXXXXXXX** que aparece junto al icono de llave amarilla.
1. En la página de planes para Defender, tenga en cuenta que puede seleccionar Habilitar todo o seleccionar planes individuales de Defender. 
    1. Compruebe que el estado de CSPM está establecido en **Activado**, si no es así, establézcalo ahora.  
    1. Habilite el plan para servidores.  Seleccione **Activado** para el elemento de línea Servidores y, a continuación, seleccione **Guardar** en la parte superior de la página.
1. Mantenga abierta la pestaña de Azure en el explorador para la siguiente demostración de Azure.

## Revisar

En esta demostración, recorrió Microsoft Defender for Cloud y mostró cómo se puede utilizar Puntuación de seguridad de Azure para mejorar la posición de seguridad de una organización.
