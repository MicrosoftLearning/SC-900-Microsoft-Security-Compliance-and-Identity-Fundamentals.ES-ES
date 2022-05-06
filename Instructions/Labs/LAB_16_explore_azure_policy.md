---
lab:
  title: Explorar Azure Policy
  module: 'Module 4 Lesson 6: Describe the capabilities of Microsoft compliance solutions: Describe Azure Policy'
ms.openlocfilehash: 23e8f4f8417367a16cbd41496428918ca219fa40
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557534"
---
# <a name="lab-explore-azure-policy"></a>Laboratorio: Explorar Azure Policy

## <a name="lab-scenario"></a>Escenario del laboratorio

Azure Policy ayuda a aplicar los estándares de la organización y a evaluar el cumplimiento a escala. Para evaluar los recursos de Azure, Azure Policy compara las propiedades de esos recursos con las reglas de negocio. En este laboratorio, empezará por explorar la página de aterrizaje de Azure Policy. Después de llevar a cabo una exploración inicial de la página Azure Policy, creará una directiva y comprobará su impacto.

**Tiempo estimado**: 20-25 minutos

### <a name="task-1"></a>Tarea 1

Explorar brevemente la página Azure Policy

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **portal.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es el id. de inquilino único facilitado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.

    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Haga clic en **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. Ahora se encuentra en Azure Portal.  En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a donde pone Microsoft Azure, escriba **directiva** y seleccione **Directiva** en los resultados de la búsqueda. Esto abrirá la página principal de Directiva, que muestra una vista de panel.  El ámbito para el cual está viendo la información aplica el Pase para Azure que está utilizando como parte de este laboratorio.   Observe la información disponible en el panel.

1. Hay un elemento, denominado Valor predeterminado de ASC (ASC hace referencia a Azure Security Center, que ahora se denomina Microsoft Defender for Cloud), cuyo ámbito es Pase para Azure: Patrocinio.   Seleccione **Predeterminada de ASC**.

1. En la parte superior de la página, debajo de Essentials, puede ver el nombre, la descripción y otro tipo de información esencial.  Lea la descripción (mantenga el puntero del ratón sobre la descripción). NOTA: El campo de descripción hace referencia a Azure Security Center que se ha cambiado de nombre a Microsoft Defender for Cloud.

1. Observe que la información que muestra el panel se actualiza para reflejar el elemento seleccionado, el valor predeterminado de ASC. Este valor predeterminado es la definición de la iniciativa Azure Security Benchmark.  Recuerde que una definición de iniciativa es una colección de definiciones de directiva personalizadas para alcanzar un único objetivo general. La información se puede ver por grupo, directivas, recursos no compatibles o eventos.

1. Seleccione la **X** en la esquina superior derecha de la ventana para salir de la página de ASC y volver a la página principal de la directiva.

1. En el panel de navegación izquierdo, seleccione **Introducción**.  Aquí puede ver las diferentes opciones, incluida la opción de examinar las directivas integradas y asignar directivas a gran escala; puede crear definiciones de directiva personalizadas para su ambiente, recomendar asignaciones de directiva, y mucho más.

1. En el panel de navegación izquierdo, seleccione **Cumplimiento**.  Al igual que en el caso de la página Información general, aquí puede ver el estado de compatibilidad de las directivas o iniciativas que aparecen en la lista.  En la página Cumplimiento de directiva también puede asignar una directiva o una iniciativa (asignará una directiva en la siguiente tarea).

1. En el panel de navegación izquierdo, seleccione **Corrección**.  Esta página muestra una lista de las directivas con recursos no compatibles.  Si selecciona una directiva en la página Corrección, podrá desencadenar la creación de una tarea para corregir la directiva.  

1. En el panel de navegación izquierdo, debajo de Creación, seleccione **Asignaciones**.  Aquí puede ver las asignaciones de directiva o iniciativa actuales, y puede crear asignaciones de directiva o iniciativa.  Volverá a este apartado en la siguiente tarea.  

1. En el panel de navegación izquierdo, seleccione **Definiciones**.  En esta página, seleccione **Realizar una auditoría de las máquinas virtuales que cuentan con una configuración de seguridad de contraseña no segura**.  Se trata de una definición de iniciativa que incluye numerosas directivas.  Para ver el aspecto de una definición de directiva, seleccione **Realizar una auditoría de las máquinas virtuales Windows cuyas contraseñas no tienen una vigencia máxima de 70 días**.  Cuando la página se abra, verá la definición de directiva real en la estructura Notación de objetos JavaScript (JSON).   Como puede ver en el texto en rojo, la definición de directiva contiene elementos que definen el nombre para mostrar, la descripción, los parámetros, las reglas de directiva, etc. NO cambie nada.  

1. Salga de la página Definición de directiva. Para ello, seleccione la **X** que aparece en la esquina superior derecha de la página.

1. Salga de la página Definición de iniciativa. Para ello, seleccione la **X** que aparece en la esquina superior derecha de la página.

1. Deje esta pestaña del explorador (Directiva: Microsoft Azure) abierta para la siguiente tarea.

### <a name="task-2"></a>Tarea 2

En esta tarea, creará una asignación de directiva básica para requerir una etiqueta en los grupos de recursos

1. Abra la pestaña del explorador Directiva: Microsoft Azure.

1. Desde el panel de navegación de la izquierda, en Creación, seleccione **Asignaciones**.

1. En la parte superior de la página, seleccione **Asignar directiva**.

1. El asistente de asignación de directivas se abre para guiar al administrador en el proceso de asignación de una directiva.  Junto al campo Definición de directiva, seleccione los **puntos suspensivos**.  Se aporta una lista de las definiciones de directiva disponibles.  

1. En la barra de búsqueda, escriba **Etiqueta**.

1. En los resultados de la búsqueda, seleccione **Exigir una etiqueta en un grupo de recursos** (es posible que deba desplazarse hacia abajo), y pulse **Seleccionar**.  Nota: El efecto de esta directiva es denegar la creación de cualquier nuevo grupo de recursos que no satisfaga el requisito.  

1. Tenga en cuenta el nombre de la asignación por defecto.  Mantenga el nombre como está y en el fondo de la página, seleccione **Siguiente**.

1. En el campo Nombre de etiqueta, escriba **Ambiente** y luego seleccione **Siguiente**.

1. Deje la configuración de corrección predeterminada, ya que luego seleccionarán **Siguiente**.

1. En el mensaje de no cumplimiento, escriba **Se requiere una etiqueta de entorno**, luego seleccione **Siguiente**. Nota: Este mensaje aparecerá como motivo de no cumplimiento para los grupos de recursos que se crearon antes de la asignación de la directiva y no tienen una etiqueta Entorno.  Para los grupos de recursos creados después de la directiva, se denegará la creación del grupo de recursos si no hay ninguna etiqueta de entorno.

1. Revise la asignación de la directiva y luego seleccione Crear.  Si no ve inmediatamente la directiva, seleccione **Actualizar**. Nota: La directiva puede tardar hasta 30 minutos en surtir efecto.

1. Puede salir de la página de Asignaciones de directivas seleccionando la **X** en la esquina superior derecha de la página.

1. Ahora se encuentra en la página principal de los servicios Azure.  Mantenga esta página abierta, la necesitará para la siguiente tarea.

### <a name="task-3"></a>Tarea 3

En esta tarea, comprobará el impacto de la asignación de una directiva de Azure Policy. Para ello, creará un grupo de recursos sin etiqueta en Azure y luego aprenderá a actualizarlo para incluir una etiqueta.  Nota: La directiva creada en la tarea anterior puede tardar hasta 30 minutos en entrar en vigor, aunque el proceso suele ser más rápido

1. Abra la pestaña del explorador Inicio: Microsoft Azure.

1. En la parte superior de la página, debajo de las palabras Servicios de Azure, seleccione **Grupos de recursos**.

1. En la esquina superior izquierda de la página, seleccione **+ Crear**.

1. En la pestaña Conceptos básicos del grupo Crear un recurso, deje el campo Suscripción como está, Pase para Azure - Patrocinio.

1. En el campo Grupo de recursos, escriba, **SC900-Labs**.

1. Deje la configuración predeterminada de la región y seleccione **Siguiente: Etiquetas**.

1. Deje vacíos los campos Nombre y Valor de la etiqueta.  NO LOS RELLENE. Luego, seleccione **Revisar y crear**.

1. Verá una validación superada (el nombre y el valor de la etiqueta no son campos obligatorios en el asistente), luego seleccione **Crear**.

1. Verá un mensaje de error en la parte superior de la pantalla, "Error al crear el grupo de recursos. Ver detalles del error".  Seleccione **Ver detalles del error**. La condición que forma parte de la directiva de Azure no se ha cumplido, por lo que se bloqueó la creación del grupo de recursos por falta de cumplimiento.

    Nota: Si no ve el mensaje de error y se creó el grupo de recursos, es porque la directiva todavía no ha surtido efecto.  Vaya a la página Directivas y consulte la directiva que creó en la tarea anterior y una vez que la directiva surta efecto, verá que el recurso no es compatible.  La página de detalles incluirá el mensaje de falta de cumplimiento. Si recibe el error, los pasos siguientes muestran cómo corregir la implementación.

1. El resumen del error muestra el tipo de error, "La directiva desautorizó el recurso SC900-Labs".  Cierre esta ventana con la **X** en la esquina superior izquierda de la pantalla.

1. En la ventana "Crear un grupo de recursos", seleccione **Anterior**.

1. Ha vuelto a la página Etiquetas para Crear un grupo de recursos.  En el campo Nombre escriba Entorno y, en el campo Valor, escriba **SC900-Labs**. Después, seleccione **Siguiente: Revisar y crear >** .

1. Compruebe la etiqueta y seleccione **Crear**.

1. Podrá ver el grupo de recursos en la lista.  Como la etiqueta se aportó en el grupo de recursos, se ha cumplido la condición incluida como parte de la directiva de Azure.  El grupo de recursos es compatible con la directiva.

1. Antes de salir, quite la directiva de Azure Policy.
    1. En la esquina superior izquierda de la página, seleccione Inicio para volver a la página principal de Azure.

    1. Debajo de las palabras Servicios de Azure, seleccione Azure Policy.
    1. En medio de la página verá una lista de las asignaciones de directiva/iniciativa de Azure Policy.  Seleccione el icono de puntos suspensivos que aparece junto a la asignación de directiva Requerir una etiqueta en los grupos de recursos y luego seleccione Eliminar asignación.
    1. Se le pedirá que confirme que desea eliminar la asignación.  Seleccione Sí.

### <a name="review"></a>Revisar

En este laboratorio ha realizado un recorrido por la página de aterrizaje de Azure Policy. Después de llevar a cabo una exploración inicial de la página, se ha familiarizado con el proceso de creación de una directiva y ha tenido la oportunidad de comprobar su impacto.
