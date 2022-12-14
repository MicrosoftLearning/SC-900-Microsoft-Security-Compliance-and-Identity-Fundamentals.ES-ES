<a name="---"></a><!---
---
Laboratorio: Título: "Exploración de Azure Policy" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft; Módulo 6: Descripción de las funcionalidades de gobernanza de recursos en Azure; Unidad 2: Descripción de Azure Policy"
---
--->

# <a name="lab-explore-azure-policy"></a>Laboratorio: Explorar Azure Policy

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de las funcionalidades de gobernanza de recursos en Azure
- Unidad: Descripción de Azure Policy

## <a name="lab-scenario"></a>Escenario del laboratorio

Azure Policy ayuda a aplicar los estándares de la organización y a evaluar el cumplimiento a escala. Para evaluar los recursos de Azure, Azure Policy compara las propiedades de esos recursos con las reglas de negocio. En este laboratorio, creará una directiva y verá qué impacto tiene.  También explorará la información de cumplimiento y corrección disponible en la página de directivas.

**Tiempo estimado**: 15-20 minutos

### <a name="task-1"></a>Tarea 1

En esta tarea, creará una asignación de directiva básica para requerir una etiqueta en un grupo de recursos.
1.  Abrir Microsoft Edge. En la barra de direcciones escriba **portal.azure.com**.

1. Inicie sesión con credenciales de administrador para la suscripción de Azure (estas credenciales de administrador son diferentes de las credenciales de administrador de Microsoft 365).
    1. En la ventana de inicio de sesión, escriba **User1-XXXXXXXX@LODSPRODMSLEARNMCA.onmicrosoft.com** (donde XXXXXXXX es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.

    1. Escriba la contraseña de administrador que le ha proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Si aparece un mensaje para preguntarle si quiere mantener iniciada la sesión, seleccione **Sí**.

1. Ahora se encuentra en Azure Portal.  En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a donde pone Microsoft Azure, escriba **directiva** y seleccione **Directiva** en los resultados de la búsqueda. Esto abrirá la página principal de Directiva, que muestra una vista de panel.  El ámbito de la vista Panel es la suscripción de Azure proporcionada por el host de laboratorio autorizado (ALH). Verá una directiva en la lista, que es una directiva creada por ALH, para el uso de la suscripción de Azure.

1. Desde el panel de navegación de la izquierda, en Creación, seleccione **Asignaciones**.

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

### <a name="task-2"></a>Tarea 2

En esta tarea, verá el impacto de la asignación de directivas de Azure intentando crear un grupo de recursos en Azure que no tiene una etiqueta.

1. Abra la pestaña del explorador Inicio: Microsoft Azure.

1. En la parte superior de la página, debajo de las palabras Servicios de Azure, seleccione **Grupos de recursos**.

1. En la esquina superior izquierda de la página, seleccione **+ Crear**.

1. En la pestaña Aspectos básicos de Crear un grupo de recursos, deje el campo Suscripción como está.

1. En el campo Grupo de recursos, escriba, **SC900-Labs**.

1. Deje la configuración predeterminada de la región y seleccione **Siguiente: Etiquetas**.

1. Deje vacíos los campos Nombre y Valor de la etiqueta.  NO LOS RELLENE. Luego, seleccione **Revisar y crear**.

1. Verá un mensaje de validación superada (el nombre y el valor de la etiqueta no son campos obligatorios en el asistente); a continuación, seleccione **Crear**.

1. Verá un mensaje de error en la parte superior de la pantalla: "Error al crear el grupo de recursos". Seleccione **Ver detalles del error**. La condición que forma parte de la directiva de Azure no se ha cumplido, por lo que se ha bloqueado la creación del grupo de recursos por falta de cumplimiento. Nota: Si no ve el mensaje de error y se creó el grupo de recursos, es porque la directiva todavía no ha surtido efecto.  Vaya a la página Directivas y consulte la directiva que ha creado en la tarea anterior; una vez que la directiva surta efecto, verá que el recurso no es compatible.  La página de detalles incluirá el mensaje de falta de cumplimiento.

1. El resumen del error muestra el tipo de error, "La directiva desautorizó el recurso SC900-Labs".  Cierre esta ventana con la **X** en la esquina superior izquierda de la pantalla.

1. En la ventana "Crear un grupo de recursos", seleccione **Anterior**.

1. Ha vuelto a la página Etiquetas para Crear un grupo de recursos.  En el campo Nombre escriba Entorno y, en el campo Valor, escriba **SC900-Labs**. Después, seleccione **Siguiente: Revisar y crear >** .

1. Compruebe la etiqueta y seleccione **Crear**.

1. En el campo Nombre, escriba **Entorno** y, en el campo Valor, escriba **Labs** (este valor podría ser cualquier cosa, la directiva simplemente requiere un valor de etiqueta); a continuación, seleccione **Siguiente: Revisar y crear >** y, después, seleccione **Crear**.

1. Verá el grupo de recursos en la lista.  

1. Seleccione **Inicio** en la ruta de navegación de la parte superior de la página para volver a la página principal de Azure.

1. Deje la pestaña del explorador abierta, porque la necesitará para la siguiente tarea.

### <a name="task-3-optional"></a>Tarea 3 (opcional)

En esta tarea, realizará un recorrido por los pasos para corregir un grupo de recursos no compatible. NOTA: La suscripción de Azure usada para el laboratorio experimentará un retraso más largo que el normal para actualizar el estado de cumplimiento de un grupo de recursos corregido.

1. En la página principal de Azure, seleccione **Directiva**. Esto abrirá la página principal de Directiva, que muestra una vista de panel.  El ámbito de la vista Panel es la suscripción de Azure proporcionada por el host de laboratorio autorizado.  

1. Debería ver la directiva que ha creado anteriormente; selecciónela.

1. En la parte superior de la página, debajo de Essentials, puede ver el nombre, la descripción y otro tipo de información esencial.  Observe que la directiva se muestra como no compatible.  Seleccione la directiva para obtener más información sobre por qué no es compatible. Aquí puede ver que un recurso que aparece como reourgegroup1 no es compatible.  Este es un ejemplo de un grupo de recursos que se creó antes de crear la directiva. Haga clic en **Detalles** para obtener más información.  Aquí puede ver el mensaje de cumplimiento que indica que se requiere una etiqueta de entorno.  Seleccione la **X** en la parte superior derecha para cerrar la ventana.

1. Seleccione **resourcegroup1** y, después, en la parte superior de la página, seleccione **Ver recurso**.
    1. Junto a la parte en la que dice Etiquetas, seleccione **Editar**.
    1. Coloque el cursor del mouse en el campo Etiqueta y seleccione **Entorno**.
    1. Coloque el cursor del mouse en el campo Valor, seleccione **Labs** y, a continuación, seleccione **Guardar**.

1. Ahora vuelva a la página de la directiva.  Coloque el cursor del mouse en el cuadro de búsqueda azul de la parte superior de la página y seleccione **Directiva**.

1. En el panel de navegación izquierdo, seleccione **Cumplimiento**.  Al igual que en el caso de la página Información general, aquí puede ver el estado de compatibilidad de las directivas o iniciativas que aparecen en la lista.  NOTA: Aunque ha agregado la etiqueta al grupo de recursos, el estado tardará algún tiempo en actualizarse.  Las suscripciones de Azure que se usan con fines de laboratorio pueden experimentar retrasos más largos que los normales. Si quiere esperar a que se actualice el estado de cumplimiento de este recurso, no finalice el laboratorio. En función del entorno de laboratorio, puede tardar una hora o más en actualizarse.  

### <a name="review"></a>Revisar

En este laboratorio, ha realizado un recorrido por el proceso de creación de una asignación de directiva de Azure y ha podido ver el impacto de esa directiva.
