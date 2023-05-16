---
demo:
  title: 'Azure Policy'
  module: 'Módulo 6: Descripción de las funcionalidades de gobernanza de recursos en Azure'
---


# <a name="demo-azure-policy"></a>Demostración: Azure Policy

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de las funcionalidades de gobernanza de recursos en Azure
- Unidad: Descripción de Azure Policy

## <a name="demo-scenario"></a>Escenario de la demo

En esta demostración, recorrerá el proceso de configuración de una directiva de Azure y el impacto de la misma.

### <a name="demo-part-1"></a>Demo, parte 1

Crear una directiva para exigir una etiqueta en un grupo de recursos (se muestran los pasos para crear una directiva a partir de una plantilla)

1. Abrir Microsoft Edge. En la barra de direcciones escriba **portal.azure.com**.  Ya debería haber iniciado la sesión; si no, debe hacerlo con sus credenciales de administrador.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a donde pone Microsoft Azure, escriba **directiva** y seleccione **Directiva** en los resultados de la búsqueda.

1. Ahora se encuentra en la vista de información general de la página Directiva. Observe la información disponible en el panel.

1. Desde el panel de navegación izquierdo, en Creación, seleccione **Asignaciones**.  Observará que ya existe una asignación de directiva; seleccione **Predeterminada de ASC**.  Revise el campo de descripción. NOTA: El campo de descripción hace referencia a Azure Security Center, cuyo nombre ha cambiado a Microsoft Defender for Cloud.  Vuelva a la página de Asignaciones de directivas seleccionando la **X** en la esquina superior derecha de la página.

1. En la parte superior de la página, seleccione **Asignar directiva**. El asistente de asignación de directivas se abre para guiar al administrador en el proceso de asignación de una directiva.

1. Se empieza en la pestaña Aspectos básicos.
    1. En Ámbito, deje la configuración predeterminada. En este caso, el ámbito de la directiva es la suscripción de Azure proporcionada por el host de laboratorio autorizado (ALH).
    1. En Definición de directiva, seleccione los **puntos suspensivos**.  Se aporta una lista de las definiciones de directiva disponibles.  En la barra de búsqueda, escriba **Requerir una etiqueta**. En los resultados de la búsqueda, seleccione **Exigir una etiqueta en un grupo de recursos** (es posible que deba desplazarse hacia abajo), y pulse **Seleccionar**.  Nota: El efecto de esta directiva es denegar la creación de cualquier nuevo grupo de recursos que no satisfaga el requisito.  
    1. Tenga en cuenta el nombre de la asignación por defecto.  Mantenga el nombre tal como está.
    1. Asegúrese de que el Cumplimiento de directivas esté establecido en **Habilitado** y seleccione **Siguiente**.

1. Ahora se encuentra en la pestaña Parámetros. En el campo Nombre de etiqueta, escriba **Entorno** y, a continuación, seleccione **Siguiente**.

1. En la pestaña Corrección, deje la configuración predeterminada y, a continuación, seleccione **Siguiente**.

1. Ahora se encuentra en la pestaña Mensajes de no cumplimiento. En el campo Mensaje de no cumplimiento, escriba **Se requiere una etiqueta** y, a continuación, seleccione **Siguiente**. Nota: Este mensaje aparecerá como motivo de no cumplimiento para los grupos de recursos que se crearon antes de la asignación de la directiva y no tienen una etiqueta Entorno.  

1. Revise la asignación de la directiva y luego seleccione **Crear**.  Si no ve inmediatamente la directiva, seleccione **Actualizar**. Nota: La directiva puede tardar hasta 30 minutos en entrar en vigor, aunque el proceso suele ser mucho más rápido.

1. Puede salir de la página de Asignaciones de directivas seleccionando la **X** en la esquina superior derecha de la página.

1. Ahora se encuentra en la página principal de los servicios de Azure.  Mantenga esta página abierta, porque la necesitará para la siguiente tarea.

### <a name="demo-part-2"></a>Demo, parte 2

En esta tarea, verá el impacto de la asignación de directivas de Azure intentando crear un grupo de recursos en Azure que no tiene una etiqueta.

1. Abra la pestaña del explorador Inicio: Microsoft Azure.

1. En la parte superior de la página, debajo de las palabras Servicios de Azure, seleccione **Grupos de recursos**.

1. En la esquina superior izquierda de la página, seleccione **+ Crear**.

1. En la pestaña Aspectos básicos de Crear un grupo de recursos, deje el campo Suscripción como está.

1. En el campo Grupo de recursos, escriba, **SC900-Labs**.

1. Deje la configuración predeterminada de la región y seleccione **Siguiente: Etiquetas**.

1. Deje vacíos los campos Nombre y Valor de la etiqueta.  NO LOS RELLENE. Luego, seleccione **Revisar y crear**.

1. Verá un mensaje de validación superada (el nombre y el valor de la etiqueta no son campos obligatorios en el asistente); a continuación, seleccione **Crear**.

1. Verá un mensaje de error en la parte superior de la pantalla: "Error al crear el grupo de recursos. Seleccione **Ver detalles del error**". La condición que forma parte de la directiva de Azure no se ha cumplido, por lo que se ha bloqueado la creación del grupo de recursos por falta de cumplimiento. Nota: Si no ve el mensaje de error y se creó el grupo de recursos, es porque la directiva todavía no ha surtido efecto.  Vaya a la página Directivas y consulte la directiva que ha creado en la tarea anterior; una vez que la directiva surta efecto, verá que el recurso no es compatible.  La página de detalles incluirá el mensaje de falta de cumplimiento.

1. El resumen del error muestra el tipo de error, "La directiva desautorizó el recurso SC900-Labs".  Cierre esta ventana con la **X** en la esquina superior izquierda de la pantalla.

1. En la ventana "Crear un grupo de recursos", seleccione **Anterior**.

1. Ha vuelto a la página Etiquetas para Crear un grupo de recursos.  En el campo Nombre escriba Entorno y, en el campo Valor, escriba **SC900-Labs**. Después, seleccione **Siguiente: Revisar y crear >** .

1. Compruebe la etiqueta y seleccione **Crear**.

1. En el campo Nombre, escriba **Entorno** y, en el campo Valor, escriba **Labs** (este valor podría ser cualquier cosa, la directiva simplemente requiere un valor de etiqueta); a continuación, seleccione **Siguiente: Revisar y crear >** y, después, seleccione **Crear**.

1. Verá el grupo de recursos en la lista.  

1. Advierta a los alumnos de que, si se hubiera creado un grupo de recursos antes de crear la directiva, ese grupo de recursos se mostraría ahora como no compatible con esta asignación de directiva y tendría que corregirse mediante la aplicación de la etiqueta Entorno.  Hay un grupo de recursos existente previamente con la etiqueta ResourceGroup1 no compatible y que se puede corregir, pero el tiempo para que el estado se actualice, después de la corrección, es más largo de lo normal para el entorno de laboratorio.

### <a name="review"></a>Revisar

En esta demostración, ha mostrado el proceso de configuración de una directiva de Azure y el impacto de la misma.
