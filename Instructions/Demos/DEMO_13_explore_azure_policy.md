---
Demo:
  title: Azure Policy
  module: 'Module 4 Lesson 6: Describe the capabilities of Microsoft compliance solutions: Describe Azure Policy'
ms.openlocfilehash: d336b34711cbfd458d25cf7692bea27ad34f86ab
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557139"
---
# <a name="demo-azure-policy"></a>Demostración: Azure Policy

## <a name="demo-scenario"></a>Escenario de la demo

En esta demostración, recorrerá el proceso de configuración de una directiva de Azure y el impacto de la misma.

### <a name="demo-part-1"></a>Demo, parte 1

Crear una directiva para exigir una etiqueta en un grupo de recursos (se muestran los pasos para crear una directiva a partir de una plantilla)

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **portal.microsoft.com**.  Ya debería haber iniciado la sesión, si no, debe hacerlo con sus credenciales de administrador.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a donde pone Microsoft Azure, escriba **directiva** y seleccione **Directiva** en los resultados de la búsqueda.

1. Ahora está en la vista de información general de la página Directiva. Observe la información disponible en el panel.

1. Desde el panel de navegación de la izquierda, en Creación, seleccione **Asignaciones**.  Observará que ya existe una asignación de directiva, seleccione **Predeterminada de ASC**.  Revise el campo de descripción. NOTA: El campo de descripción hace referencia a Azure Security Center que se ha cambiado de nombre a Microsoft Defender for Cloud.  Vuelva a la página de Asignaciones de directivas seleccionando la **X** en la esquina superior derecha de la página.

1. En la parte superior de la página, seleccione **Asignar directiva**.

1. El asistente de asignación de directivas se abre para guiar al administrador en el proceso de asignación de una directiva.  Junto al campo Definición de directiva, seleccione los **puntos suspensivos**.  Se aporta una lista de las definiciones de directiva disponibles.  

1. En la barra de búsqueda, escriba **Etiqueta**.

1. En los resultados de la búsqueda, seleccione **Exigir una etiqueta en un grupo de recursos** (es posible que deba desplazarse hacia abajo), y pulse **Seleccionar**.  Nota: El efecto de esta directiva es denegar la creación de cualquier nuevo grupo de recursos que no satisfaga el requisito.  

1. Tenga en cuenta el nombre de la asignación por defecto.  Mantenga el nombre como está y en el fondo de la página, seleccione **Siguiente**.

1. En el campo con el nombre de la etiqueta, escriba **Entorno** (los grupos de recursos exigirán una etiqueta Entorno) y seleccione **Siguiente**.  

1. En la pestaña Corrección, lea la descripción pero no cambie la configuración. Seleccione **Siguiente**.

1. En el mensaje de no cumplimiento, escriba **Se requiere una etiqueta de entorno**, luego seleccione **Siguiente**. Nota: Este mensaje aparecerá como motivo de no cumplimiento para los grupos de recursos que se crearon antes de la asignación de la directiva y no tienen una etiqueta Entorno.  Para los grupos de recursos creados después de la directiva, se denegará la creación del grupo de recursos si no hay ninguna etiqueta de entorno.

1. Revise la asignación de la directiva y luego seleccione Crear.  Si no ve inmediatamente la directiva, seleccione **Actualizar**. Nota: La directiva puede tardar hasta 30 minutos en surtir efecto.

1. Puede salir de la página de Asignaciones de directivas seleccionando la **X** en la esquina superior derecha de la página.

1. Ahora se encuentra en la página principal de los servicios Azure.  Mantenga esta página abierta, la necesitará para la siguiente tarea.

### <a name="demo-part-2"></a>Demo, parte 2

Muestre el impacto de la directiva creando un grupo de recursos sin etiqueta, y luego arréglelo para que tenga una etiqueta.

1. En la parte superior de la página, debajo de donde pone Servicios de Azure, seleccione **Grupos de recursos**. Si no ve la opción en la lista, escriba Grupos de recursos en la barra de búsqueda y selecciónela desde allí.

1. En la esquina superior izquierda de la página, seleccione **+ Crear**.

1. En la pestaña Conceptos básicos del grupo Crear un recurso, deje el campo Suscripción como está, Pase para Azure - Patrocinio.

1. En el campo Grupo de recursos, escriba, **SC900-Labs**.

1. Deje la configuración predeterminada de la región y seleccione **Siguiente: Etiquetas**.

1. Deje vacíos los campos Nombre y Valor de la etiqueta.  NO LOS RELLENE. Luego, seleccione **Revisar y crear**.

1. Verá una validación superada (el nombre y el valor de la etiqueta no son campos obligatorios en el asistente), luego seleccione **Crear**.

1. Verá un mensaje de error en la parte superior de la pantalla, "Error al crear el grupo de recursos. Ver detalles del error".  Seleccione **Ver detalles del error**. La condición que forma parte de la directiva de Azure no se ha cumplido, por lo que se bloqueó la creación del grupo de recursos por falta de cumplimiento. Nota: Si no ve el mensaje de error y se creó el grupo de recursos, es porque la directiva todavía no ha surtido efecto.  Vaya a la página Directivas y consulte la directiva que creó en la tarea anterior y una vez que la directiva surta efecto, verá que el recurso no es compatible.  La página de detalles incluirá el mensaje de falta de cumplimiento.

1. El resumen del error muestra el tipo de error, "La directiva desautorizó el recurso SC900-Labs".  Cierre esta ventana con la **X** en la esquina superior izquierda de la pantalla.

1. En la ventana Crear un grupo de recursos, seleccione **<Anterior**.

1. Ha vuelto a la página Etiquetas para Crear un grupo de recursos.  En el campo Nombre escriba Entorno y, en el campo Valor, escriba **SC900-Labs**. Después, seleccione **Siguiente: Revisar y crear >** .

1. Compruebe la etiqueta y seleccione **Crear**.

1. Podrá ver el grupo de recursos en la lista.  Como la etiqueta se aportó en el grupo de recursos, se ha cumplido la condición incluida como parte de la directiva de Azure.  El grupo de recursos es compatible con la directiva.

### <a name="review"></a>Revisar

En esta demostración, ha mostrado el proceso de configuración de una directiva de Azure y el impacto de la misma.
