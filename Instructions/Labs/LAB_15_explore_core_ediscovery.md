---
lab:
  title: Exploración de eDiscovery
  module: Describe the data compliance solutions of Microsoft Purview
---

# Laboratorio: Exploración de eDiscovery

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Priva y Microsoft Purview
- Módulo: Descripción de las soluciones de cumplimiento de datos de Microsoft Purview
- Unidad: Descripción de eDiscovery

## Escenario del laboratorio

En este laboratorio, explorarás los pasos necesarios para configurar eDiscovery, incluida la configuración de permisos de rol, la creación de un caso de eDiscovery, la creación de una suspensión de eDiscovery y la creación de una consulta de búsqueda.  Nota:  Para obtener una licencia de eDiscovery, es necesario disponer de la suscripción de organización y las licencias por usuario adecuadas. Si no sabe con seguridad cuáles son las licencias compatibles con eDiscovery, visite [Introducción a eDiscovery en Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Tiempo estimado**: 45 minutos

### Tarea 1

Para acceder a eDiscovery, o para que se le agregue como miembro de un caso de eDiscovery, el usuario debe tener asignados los permisos adecuados. En esta tarea, como administrador global, agregarás usuarios específicos como miembros del grupo de roles de Supervisor de eDiscovery.

1. Debería estar en la página principal de Microsoft Purview portal.  Si la habías cerrado, abre otra y escribe **https://purview.microsoft.com** .

1. En el panel de navegación izquierdo, selecciona **Configuración**, expande **Roles y ámbitos** y, después, selecciona **Grupos de roles**.

1. En el cuadro de búsqueda, en la parte superior derecha de la página, escribe **eDiscovery** y presiona Entrar en el teclado.  Selecciona **Supervisor de eDiscovery**.

1. Selecciona **Editar**. Para este laboratorio, te establecerás como administrador MOD como Supervisor y administrador de eDiscovery.  En la práctica, designarías usuarios específicos para roles específicos.
    1. La página "Administrar Supervisor de eDiscovery" permite agregar usuarios al rol de administrador de eDiscovery.
    1. Selecciona **Elegir usuarios**. Busca y selecciona **Administrador MOD** y presiona **Seleccionar** en la parte inferior de la página y, después, selecciona **Siguiente**.
    1. En la página "Administrar Administrador de eDiscovery", selecciona **Elegir usuarios** . Busca y selecciona **Administrador MOD** y presiona **Seleccionar** en la parte inferior de la página y, después, selecciona **Siguiente** y **Guardar**.
    1. En la página "Has actualizado correctamente el grupo de roles", selecciona **Listo**.

1. Vuelva a la página principal de Microsoft Purview seleccionando **Inicio** en el panel de navegación izquierdo.

1. Deja esta pestaña del explorador abierta, porque la utilizarás en la siguiente tarea.

### Tarea 2

En esta tarea, como administrador de eDiscovery (un administrador MOD es un administrador de eDiscovery), creará un caso para empezar a utilizar eDiscovery.

1. Debería estar en la página principal de Microsoft Purview portal.

1. En el panel de navegación izquierdo, debajo de Soluciones, expanda **eDiscovery** y, a continuación, seleccione **Casos**.

1. En la página Casos, seleccione el texto de la parte izquierda del cuadro azul que dice **Crear caso**.  Si selecciona la flecha abajo, abrirá la ventana para crear una búsqueda y, en el proceso de creación de una búsqueda, creará un caso.
    1. En la ventana "Nuevo caso", escriba un nombre de caso, **Caso de prueba SC900** y, a continuación, seleccione **Crear**.
    1. El caso debería aparecer ahora en la lista.
    1. Como creador del caso y como tienes privilegios de Administrador de eDiscovery, puede empezar a trabajar con él.  
    1. Deja esta pestaña del explorador abierta, porque la utilizarás en la siguiente tarea.

### Tarea 3

Con un caso creado, puede empezar a trabajar con el caso. Esto incluye la creación de una consulta de búsqueda para buscar datos y contenido relevante para su caso, aplicar una directiva de retención, crear un conjunto de revisión y exportar datos. En esta tarea explorará algunas de estas opciones.

1. Abra la pestaña Caso de prueba SC900 en su explorador.

1. En la página "Caso de prueba SC900", seleccione **Crear una búsqueda**.

1. En el campo de nombre, escriba **Búsqueda de caso SC900** y seleccione **Crear**.

1. Seleccione **Agregar orígenes**. Tenga en cuenta las opciones de filtro y la configuración predeterminada. En el cuadro de búsqueda, escriba **`Pradeep`** y, a continuación, seleccione **Buscar**. En los resultados de la búsqueda, seleccione **Pradeep Gupta** y, a continuación, seleccione **Guardar y cerrar**. El generador de condiciones permite crear una consulta de búsqueda basada en palabras clave o condiciones específicas que se cumplen. En el cuadro de palabra clave, escriba **Ventas**. Desde aquí puede seleccionar **Ejecutar la consulta** en la ventana "Elegir los resultados de la búsqueda". Para el inquilino del laboratorio, solo está disponible la vista de estadísticas de los resultados de búsqueda. Observe las opciones para organizar por indicadores principales. Seleccione **Ejecutar consulta**.  Este proceso podría tardar varios minutos.

1. Con los resultados de la consulta devueltos en forma de estadísticas, puede exportar los resultados.  Seleccione **Exportar** para ver las opciones disponibles y, a continuación, seleccione **Cancelar**.

1. Puede agregarlos a un conjunto de revisión para su posterior procesamiento.  Seleccione **Agregar al conjunto de revisión**. Escriba un nombre para el nuevo conjunto de revisión, **`SC900-review-set`**, deje la configuración predeterminada y seleccione **Agregar al conjunto de revisión**. Esto puede tardar varios minutos en completarse. Una vez presentados los resultados del conjunto de revisión, puede explorar las distintas opciones, entre las que se incluyen Análisis, Consulta, Acciones, Etiquetar archivos y Administrar.

1. También puede crear directivas de retención para conservar el contenido relevante para su caso. En la ventana "Conjunto de revisión", seleccione la pestaña **Retener**.  Esta acción le lleva a la ventana "Directivas de retención". Seleccione **Nueva directiva**.  Escriba un nombre para la directiva, **`SC900-hold`** y seleccione **Crear**.  Como en la búsqueda, debe agregar orígenes de datos para la retención y puede agregar palabras clave y condiciones para usarlas en la directiva de retención y, a continuación, puede seleccionar **Aplicar retención**.  Las acciones que puede realizar en una directiva de retención incluyen reintento, desactivar una directiva y eliminar una directiva de retención.

1. Cierre la sesión y cierre todas las ventanas del explorador abiertas.

### Revisar

En este laboratorio le hemos guiado a través de los pasos necesarios para empezar a trabajar con eDiscovery, incluida la configuración de los permisos de roles para eDiscovery y la creación de un caso de eDiscovery.  Con el caso, ha explorado la configuración para crear una búsqueda y exportar los resultados, agregarlos a un conjunto de revisión y crear una retención.
