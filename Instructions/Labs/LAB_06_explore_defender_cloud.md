---
lab:
  title: Exploración de Microsoft Defender for Cloud
  module: 'Module 3 Lesson 2: Describe the capabilities of Microsoft security solutions: Describe security management capabilities of Azure'
ms.openlocfilehash: 208e11a7e82497fbb900b4fa024fb6fb367d458e
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2022
ms.locfileid: "137894228"
---
# <a name="lab-explore-microsoft-defender-for-cloud"></a>Laboratorio: Exploración de Microsoft Defender for Cloud

## <a name="lab-scenario"></a>Escenario del laboratorio
En este laboratorio, explorará Microsoft Defender for Cloud y aprenderá cómo puede utilizar Puntuación de seguridad de Azure para mejorar la posición de seguridad de su organización.

**Tiempo estimado**: 30 minutos

#### <a name="task-1-in-this-task-you-will-take-a-brief-tour-of-microsoft-defender-for-cloud"></a>Tarea 1: En esta tarea, dará un paseo introductorio por Microsoft Defender for Cloud.
1.  Abrir Microsoft Edge. En la barra de direcciones, escriba **portal.azure.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Haga clic en **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En la esquina superior izquierda de la pantalla, junto a las palabras Microsoft Azure, seleccione el icono Mostrar el menú del portal (las tres líneas horizontales, también denominadas icono de hamburguesa) y, luego, en el panel de navegación de la izquierda, en Favoritos, seleccione **Microsoft Defender for Cloud**.  Si no aparece en los favoritos, escriba **Microsoft Defender for Cloud** en el cuadro de búsqueda y, luego, en la lista de resultados, seleccione **Microsoft Defender for Cloud**.

1. Observe la información disponible en la página de información general de Microsoft Defender for Cloud.  

1. Es posible que vea un cuadro de información azul en la parte superior de la página que indica que puede estar viendo información limitada.  Seleccione **Haga clic aquí**.
    1. Para asegurarse de que tiene una visibilidad completa del inquilino, asígnese el rol necesario.  Seleccione **Administrador de seguridad** y luego **Obtener acceso** en la parte inferior de la página.
    1. Es probable que vea el mensaje "El grupo de administración raíz no existe".  Tal y como se indica en la descripción, el sistema creará el grupo por usted.  Esta operación puede tardar hasta 15 minutos, pero suele ser más rápida.  Una vez que se le haya concedido acceso, seleccione **Microsoft Defender for Cloud** en la esquina superior izquierda de la página, encima de la opción Obtener permisos y, luego, actualice la página de información general de Microsoft Defender for Cloud.

1. La información en la parte superior de la página incluye el número de suscripciones de Azure, el número de recursos evaluados, el número de recomendaciones activas y cualquier alerta de seguridad.  En el cuerpo principal de la página hay tarjetas que representan la puntuación de seguridad, el cumplimiento normativo, la información, etc.  

1. En la parte superior de la página, seleccione **Recursos evaluados**.  (Tenga en cuenta que esto equivale a haber seleccionado Inventario en el panel de navegación izquierdo de la página principal de Microsoft Defender for Cloud).
    1. De esta forma irá a la página de **Inventario**, que muestra su suscripción al pase para Azure.  Seleccione **Pase para Azure – Patrocinio**.
    1. La página de estado de los recursos ofrece una lista de recomendaciones.  En la lista disponible, seleccione **Debe haber más de un propietario asignado a su suscripción**.
    1. Seleccione la flecha desplegable situada junto a Pasos de corrección. Observe cómo se aportan pasos detallados de corrección junto a la opción de tomar medidas.  
    1. Seleccione **Microsoft Defender for Cloud** en la esquina superior izquierda de la pantalla para volver a la página de información general de Microsoft Defender for Cloud.

1. En la parte superior de la página, seleccione **Recomendaciones activas**.  (Tenga en cuenta que esto equivale a haber seleccionado Recomendaciones en el panel de navegación izquierdo de la página principal de Microsoft Defender for Cloud).
    1. La página de recomendaciones muestra su panel de Puntuación de seguridad.
    1. Debajo del panel de Puntuación de seguridad hay una lista de controles. Cada control de seguridad representa un riesgo de seguridad que debe mitigarse y también incluye información sobre la puntuación máxima asociada a ese control, la puntuación actual, el aumento potencial de la puntuación y el estado de los recursos.  
    1. Seleccione uno de los controles, como **Habilitar MFA**.  Seleccione uno de los subelementos, como **debe habilitarse MFA en las cuentas con permisos de propietario en su suscripción**.  En la página que se abre, verá una descripción, los pasos de corrección y los recursos afectados. Puede salir de esta página si selecciona la **X** en la esquina superior derecha de la pantalla.
    1. Puede salir de la página de recomendaciones si selecciona la **X** en la esquina superior derecha de la pantalla, para volver a la página de información general.

1. En la página principal, seleccione **Cumplimiento normativo**. La página de cumplimiento normativo ofrece una lista de controles de cumplimiento.  Bajo cada control hay un conjunto de evaluaciones que se basan en Azure Security Benchmark y ofrecen recomendaciones sobre cómo puede asegurar sus soluciones en la nube en Azure.
    1. Seleccione **IM. Administración de identidades** y, luego, seleccione **IM-6 Usar controles con autenticación sólida**.  La lista muestra las acciones de responsabilidad del cliente que pueden tomarse para mejorar la posición de cumplimiento.
    1. Seleccione la **X** en la esquina superior derecha de la pantalla para cerrar la página y volver a la página Información general de Microsoft Defender for Cloud. 
    1. Deje abierta la página de información general de Microsoft Defender for Cloud. La utilizará en la tarea siguiente.


#### <a name="task-2-in-this-task-you-will-navigate-to-azure-secure-score-and-explore-recommendations-that-can-improve-your-secure-score"></a>Tarea 2: En esta tarea se desplazará a la Puntuación de seguridad de Azure y explorará las recomendaciones que pueden contribuir a mejorar su Puntuación de seguridad 

1. En la página de información general de Microsoft Defender for Cloud, seleccione la tarjeta **Puntuación segura**.
1. Seleccione **Pase para Azure – Patrocinio**.  Observe su Puntuación de seguridad.
1. En la página de recomendaciones, seleccione **Implementación de procedimientos recomendados de seguridad** para expandir la lista. Observe que muestra el estado de mantenimiento del recurso en rojo.
1. Seleccione el elemento **Debe haber más de un propietario asignado a la suscripción**, que muestra el estado del recurso en rojo. 
1. Abajo, donde dice **Recursos afectados**, asegúrese de que los recursos incorrectos están seleccionados o subrayados y, a continuación, seleccione la suscripción de Azure que aparece.
1. En la parte superior de la página Control de acceso (IAM), seleccione **+ Agregar** y luego seleccione **Agregar asignación de roles** en el menú desplegable.
    1. En el lado izquierdo de la página, seleccione **Propietario** (debe ser el primer elemento de la lista) para que la fila aparezca resaltada en gris y, luego, seleccione **Siguiente** en la parte inferior de la página.
    1. Seleccione la opción **+ Seleccionar miembros**, que se encuentra junto a Miembros. 
    1. En la ventana Seleccionar miembros que se abre en el lado derecho de la pantalla, seleccione **Alex Wilber** y presione **Seleccionar** en la parte inferior de la página.  
    1. En la página Agregar asignación de roles, compruebe que Alex Wilber aparece como miembro y, luego, seleccione **Siguiente** y **Revisar y asignar**.
    1. El estado puede tardar hasta 24 horas en actualizarse, pasadas las cuales su Puntuación de seguridad también se actualizará, dado que todos los elementos del grupo Administrar acceso y permisos se han cumplido.
    1. En la esquina superior izquierda de la página, encima de las palabras Pase para Azure, seleccione **Microsoft Defender for Cloud** para volver a la página de información general de Microsoft Defender for Cloud.
1. Mantenga esta página del abierta para la siguiente tarea.


#### <a name="task-3--recall-that-microsoft-defender-for-cloud-is-offered-in-two-modes-without-enhanced-security-features-free-and-with-enhanced-security-features-which-are-available-through-the-microsoft-defender-for-cloud-plans-in-this-task-you-discover-how-to-enabledisable-the-various-microsoft-defender-for-cloud-plans"></a>Tarea 3:  Recuerde que Microsoft Defender for Cloud se ofrece en dos modos: sin características de seguridad mejoradas (gratis) y con características de seguridad mejoradas, disponibles a través de los planes de Microsoft Defender for Cloud. En esta tarea, descubrirá cómo habilitar o deshabilitar los distintos planes de Microsoft Defender for Cloud.

1.  En la página de información general de Microsoft Defender for Cloud, seleccione la **configuración del Entorno** en el panel de navegación de la izquierda.
1. Seleccione el signo mayor que **>** que se encuentra junto a Grupo raíz de inquilinos para expandirlo (no seleccione Grupo raíz de inquilinos directamente, porque esto lo redirigirá a otra página) y, luego, seleccione **Pase para Azure: Patrocinio**.
1.  En la página de planes para Defender, tenga en cuenta que puede seleccionar Habilitar todo o seleccionar planes individuales de Defender. Deje la configuración tal como está, con todos los planes establecidos en desactivados.
1.  Ya puede cerrar la pestaña del explorador para salir de Azure Portal.


#### <a name="review"></a>Revisar
En este laboratorio, exploró Microsoft Defender for Cloud y aprendió cómo puede utilizar Puntuación de seguridad de Azure para mejorar la posición de seguridad de su organización.

