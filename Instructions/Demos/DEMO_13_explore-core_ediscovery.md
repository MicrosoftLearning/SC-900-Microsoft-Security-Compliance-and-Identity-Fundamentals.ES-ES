<!---
---
Demo: Título: "Exploración de eDiscovery" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Priva y Microsoft Purview; Módulo 3: Descripción de las soluciones de cumplimiento de datos de Microsoft Purview; Unidad 2: Descripción de eDiscovery"
---
--->

# Demo: Exploración de eDiscovery (Estándar)

Esta demo está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Priva y Microsoft Purview
- Módulo: Descripción de las soluciones de cumplimiento de datos de Microsoft Purview
- Unidad: Descripción de eDiscovery

## Supuesto de demostración

En esta demo, explorarás los pasos necesarios para configurar eDiscovery, incluida la configuración de los permisos de rol, la creación de un caso de eDiscovery, la creación de una suspensión de eDiscovery y la creación de una consulta de búsqueda.  NOTA: En el portal de Microsoft Purview, las actualizaciones de la interfaz de usuario se están implementando gradualmente. Es posible que algunos inquilinos de laboratorio o demo aún no muestren la interfaz de usuario más reciente, por lo que todos los pasos del laboratorio se muestran con la interfaz de usuario clásica de eDiscovery.

### Demo, parte 1

Para acceder a eDiscovery, o para que se le agregue como miembro de un caso de eDiscovery, el usuario debe tener asignados los permisos adecuados. En esta parte de la demostración, como administrador global, recorrerás el proceso de agregar usuarios específicos como miembros del grupo de roles de Supervisor de eDiscovery.

1. Abre la pestaña del explorador para **Microsoft Purview**. Si lo cerró anteriormente, abra una pestaña del explorador y, en la barra de direcciones, escriba **https://purview.microsoft.com** y seleccione **Introducción**.  
1. En el panel de navegación de la izquierda, selecciona **Configuración**.
1. En el panel de navegación que se abre, selecciona **Roles y ámbito** para expandir la opción y luego selecciona **Grupos de roles**.
1. En el cuadro de búsqueda del lado derecho de la pantalla, busca el término **eDiscovery**.  Selecciona **Supervisor de eDiscovery**.
    1. Selecciona **Editar**.
    1. Selecciona **Elegir usuarios**.
    1. Para buscar el administrador MOD, selecciona el cuadro situado junto a **Administrador MOD** y luego selecciona el botón **Seleccionar** situado en la parte inferior de la página.
    1. Selecciona **Siguiente**, luego **Guardar** y, por último, **Listo**.

1. Mantén abierta esta pestaña del explorador.

### Demo, parte 2

En esta parte, como administrador de eDiscovery (el administrador de MOD es un administrador de eDiscovery), creará un caso para empezar a usar eDiscovery.

1. Debería estar en la página principal de Microsoft Purview portal.

1. En el panel de navegación izquierdo, debajo de Soluciones, expanda **eDiscovery** y, a continuación, seleccione **Casos**.

1. En la página "Casos", seleccione **Crear caso**.

1. En la ventana "Nuevo caso", escriba un nombre de caso, **Caso de prueba SC900** y, a continuación, seleccione **Crear**.

1. El caso debería aparecer ahora en la lista.

1. Como creador del caso y como tienes privilegios de Administrador de eDiscovery, puede empezar a trabajar con él.  

1. Deja esta pestaña del explorador abierta, porque la utilizarás en la siguiente tarea.

### Demo, parte 3

Con un caso creado, puede empezar a trabajar con el caso. Esto incluye la creación de una consulta de búsqueda para buscar datos y contenido relevante para su caso, aplicar una directiva de retención, crear un conjunto de revisión y exportar datos. En esta tarea explorará algunas de estas opciones. NOTA: Se recomienda pasar por la tarea de crear una búsqueda y un conjunto de revisión antes de la entrega para que los resultados del conjunto de la búsqueda y del conjunto de revisión estén disponibles fácilmente durante la demostración, ya que estas acciones pueden tardar varios minutos en completarse.  

1. Abra la pestaña Caso de prueba SC900 en su explorador.

1. En la página "Caso de prueba SC900", seleccione **Crear una búsqueda**.

1. En el campo de nombre, escriba **Búsqueda de caso SC900** y seleccione **Crear**.

1. Seleccione **Agregar orígenes**. Tenga en cuenta las opciones de filtro y la configuración predeterminada. En el cuadro de búsqueda, escriba **`Pradeep`** y, a continuación, seleccione **Buscar**. En los resultados de la búsqueda, seleccione **Pradeep Gupta** y, a continuación, seleccione **Guardar y cerrar**. El generador de condiciones permite crear una consulta de búsqueda basada en palabras clave o condiciones específicas que se cumplen. En el cuadro de palabra clave, escriba **Ventas**. Desde aquí puede seleccionar **Ejecutar la consulta** en la ventana "Elegir los resultados de la búsqueda". Para el inquilino del laboratorio, solo está disponible la vista de estadísticas de los resultados de búsqueda. Observe las opciones para organizar por indicadores principales. Seleccione **Ejecutar consulta**.  Este proceso podría tardar varios minutos.

1. Con los resultados de la consulta devueltos en forma de estadísticas, puede exportar los resultados.  En la parte superior derecha de la pantalla (junto a donde dice "Agregar al conjunto de revisión"), seleccione **Exportar** para ver las opciones disponibles y, a continuación, seleccione **Cancelar**.

1. Puede agregarlos a un conjunto de revisión para su posterior procesamiento.  Seleccione **Agregar al conjunto de revisión**. Escriba un nombre para el nuevo conjunto de revisión, **`SC900-review-set`**, deje la configuración predeterminada y seleccione **Agregar al conjunto de revisión**. Esto puede tardar varios minutos en completarse. Una vez presentados los resultados del conjunto de revisión, puede explorar las distintas opciones, entre las que se incluyen Análisis, Consulta, Acciones, Etiquetar archivos y Administrar.

1. También puede crear directivas de retención para conservar el contenido relevante para su caso. En la ventana "Conjunto de revisión", seleccione la pestaña **Retener**.  Esta acción le lleva a la ventana "Directivas de retención". Seleccione **Nueva directiva**.  Escriba un nombre para la directiva, **`SC900-hold`** y seleccione **Crear**.  Como en la búsqueda, debe agregar orígenes de datos para la retención y puede agregar palabras clave y condiciones para usarlas en la directiva de retención y, a continuación, puede seleccionar **Aplicar retención**.  Las acciones que puede realizar en una directiva de retención incluyen reintento, desactivar una directiva y eliminar una directiva de retención.

1. Cierre la sesión y cierre todas las ventanas del explorador abiertas.

### Revisar

En esta demostración le hemos guiado a través de los pasos necesarios para empezar a trabajar con eDiscovery, incluida la configuración de los permisos de roles para eDiscovery y la creación de un caso de eDiscovery.  Con el caso, ha explorado la configuración para crear una búsqueda y exportar los resultados, agregarlos a un conjunto de revisión y crear una retención.
