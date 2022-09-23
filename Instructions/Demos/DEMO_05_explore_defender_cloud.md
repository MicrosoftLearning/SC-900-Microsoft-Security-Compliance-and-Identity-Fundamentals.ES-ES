---
ms.openlocfilehash: ecea12b9b90c6dc3917d0ee93edcdba0436ccd0d
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892466"
---
<a name="---"></a><!---
---
Demostración: Título: "Microsoft Defender for Cloud" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft; Módulo 2: Descripción de las funcionalidades de administración de seguridad de Azure; Unidad 3: Descripción de Microsoft Defender for Cloud"
---
--->

# <a name="demo-microsoft-defender-for-cloud"></a>Demostración: Microsoft Defender for Cloud

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft.
- Módulo: Descripción de las funcionalidades de administración de seguridad de Azure
- Unidad: Descripción de Microsoft Defender for Cloud

## <a name="demo-scenario"></a>Escenario de la demo

En esta demostración, se familiarizará con Microsoft Defender for Cloud y hará una demostración sobre cómo se puede utilizar la Puntuación de seguridad de Azure para mejorar la posición de seguridad de una organización.  NOTA: En este tutorial de demostración se da por supuesto que el moderador tiene permisos de nivel de administrador para la suscripción de Azure a través de un pase de Azure.  Una suscripción de Azure, como una suscripción de Cloudslice, administrada por el proveedor de servicios de hosting del laboratorio autorizado limita el acceso y la funcionalidad, por lo que es posible que algunos de los pasos siguientes no estén disponibles o no muestren información.

### <a name="demo-setup"></a>Configuración de demostración

En esta tarea de configuración, realizará una configuración básica de Microsoft Defender for Cloud para preparar la suscripción y habilitar y asignar una directiva predeterminada. Hágalo antes de llevar a cabo una demostración delante de la clase. 

1. Abra la pestaña del explorador **Inicio: Microsoft Azure**.  Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba portal.azure.com y vuelva a iniciar sesión.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escriba **Microsoft Defender for Cloud** y, después, seleccione **Microsoft Defender for Cloud** en los resultados de la búsqueda.

1. Si es la primera vez que entra en Microsoft Defender for Cloud con su suscripción, es posible que llegue a la página de introducción y se le pida que actualice.  Desplácese a la parte inferior de la página y seleccione **omitir**.  Se abrirá la página de información general.
    1. En la parte superior de la página, verá un cuadro de información de color azul claro que indica: "Se están preparando las suscripciones. Esta operación puede tardar unos minutos..."
    1. Una vez que la suscripción esté lista, aparecerá un cuadro de información nuevo que indica que "Una suscripción no tiene asignada la directiva predeterminada. Para revisar la lista de suscripciones, abra la página Directiva de seguridad".  Seleccione la flecha derecha al final de la oración.
        1. Ahora se encuentra en la página Configuración del entorno. Seleccione **Pase para Azure – Patrocinio**. 
        1. En el panel de navegación izquierdo, seleccione **Directiva de seguridad**.
        1. En la página principal, donde figura Iniciativa predeterminada, seleccione **Asignar directiva**.
        1. En la parte inferior de la página, seleccione **Revisar y crear**.
        1. En la parte inferior de la página, seleccione **Crear**.
        1. En la parte superior de la página, donde figura Microsoft Azure, seleccione **Microsoft Defender for Cloud** en la ruta de navegación para volver a la página de información general.

### <a name="demo-task"></a>Tarea de demostración

En esta tarea de demostración, realizará un tutorial de alto nivel de algunas de las funcionalidades de Microsoft Defender for Cloud.

1. La información en la parte superior de la página de información general de Microsoft Defender for Cloud incluye el número de suscripciones de Azure, el número de recursos evaluados, el número de recomendaciones activas y cualquier alerta de seguridad.  En el cuerpo principal de la página hay tarjetas que representan la puntuación de seguridad, el cumplimiento normativo, la información, etc.  

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

1. Se volverá a abrir la página Información general de Microsoft Defender for Cloud.  En la página principal, seleccione **Cumplimiento normativo**. (Tenga en cuenta que esto equivale a haber seleccionado Recomendaciones en el panel de navegación izquierdo de la página principal de Microsoft Defender for Cloud).
    1. La página de cumplimiento normativo ofrece una lista de controles de cumplimiento.  Bajo cada control hay un conjunto de evaluaciones que se basan en Azure Security Benchmark y ofrecen recomendaciones sobre cómo puede asegurar sus soluciones en la nube en Azure.
    1. Seleccione **IM. Administración de identidades** y, luego, seleccione **IM-6 Usar controles con autenticación sólida**.  La lista muestra las acciones de responsabilidad del cliente que pueden tomarse para mejorar la posición de cumplimiento.
    1. Seleccione la **X** en la esquina superior derecha de la pantalla para cerrar la página y volver a la página de cumplimiento normativo.
    1. Seleccione la **X** en la esquina superior derecha de la pantalla para volver a la página de información general.

1. Recuerde que Microsoft Defender for Cloud se ofrece en dos modos: sin características de seguridad mejoradas (gratis) y con características de seguridad mejoradas, disponibles a través de los planes de Microsoft Defender for Cloud. Aquí descubrirá cómo habilitar o deshabilitar los distintos planes de Microsoft Defender for Cloud.
    1. En la página de información general de Microsoft Defender for Cloud, seleccione la **configuración del Entorno** en el panel de navegación de la izquierda.
    1. Seleccione el signo mayor que **>** que se encuentra junto a Grupo raíz de inquilinos para expandirlo (no seleccione Grupo raíz de inquilinos directamente, porque esto lo redirigirá a otra página) y, luego, seleccione **Pase para Azure: Patrocinio**.
    1. En la página de planes para Defender, tenga en cuenta que puede seleccionar Habilitar todo o seleccionar planes individuales de Defender. Deje la configuración tal como está, con todos los planes establecidos en desactivados.
    1. Seleccione la **X** en la esquina superior derecha de la pantalla para volver a la página de Configuración del entorno.
    1. Seleccione la **X** en la esquina superior derecha de la pantalla para volver a la página de información general.

1. Vuelva a la página principal del portal Azure si selecciona **Inicio** en la esquina superior izquierda de la página.  Mantenga esta pestaña del explorador disponible, ya que volverá a ella en una demostración posterior.

## <a name="review"></a>Revisar

En esta demostración, se familiarizó con Microsoft Defender for Cloud e hizo una demostración sobre cómo se puede utilizar la Puntuación de seguridad de Azure para mejorar la posición de seguridad de una organización.
