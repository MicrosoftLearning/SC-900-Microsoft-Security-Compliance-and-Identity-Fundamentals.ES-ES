<!---
---
Laboratorio: Título: "Exploración del flujo de trabajo de eDiscovery (estándar)" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft; Módulo 5: Descripción de las funcionalidades de eDiscovery y de auditoría de Microsoft Purview; Unidad 2: Descripción de las soluciones de eDiscovery en Microsoft 365"
---
--->

# Laboratorio: Explore el flujo de trabajo de eDiscovery (Standard)

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de las funcionalidades de eDiscovery y de auditoría de Microsoft Purview
- Unidad: Describir las soluciones de eDiscovery en Microsoft Purview

## Escenario del laboratorio

En este laboratorio, explorará los pasos necesarios para configurar eDiscovery, incluida la configuración de permisos de rol, la creación de un caso de eDiscovery, la creación de una suspensión de eDiscovery y la creación de una consulta de búsqueda.  Nota:  Para obtener una licencia de eDiscovery (Standard), es necesario disponer de la suscripción de organización y las licencias por usuario adecuadas. Si no sabe con seguridad cuáles son las licencias compatibles con eDiscovery (Standard), visite [Introducción a eDiscovery (Standard) en Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Tiempo estimado**: 25-30 minutos

### Tarea 1

Para acceder a eDiscovery (Standard), o para que se le agregue como miembro de un caso de eDiscovery, el usuario debe tener asignados los permisos adecuados. En esta tarea, como administrador global, agregará usuarios específicos como miembros del grupo de roles de Supervisor de eDiscovery

1. Abra la pestaña del explorador para la página principal de Microsoft Purview.  Si la había cerrado, abra otra y escriba **https://admin.microsoft.com** . Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.  


1. En el panel de navegación izquierdo, expanda (seleccione la flecha abajo) **Roles y ámbitos** y, a continuación, seleccione **Permisos**.

1. En Soluciones de Microsoft Purview, seleccione **Roles**.

1. En el campo de búsqueda, escriba **eDiscovery** y presione Entrar en el teclado.  Seleccione **Supervisor de eDiscovery**.

1. Seleccione **Editar**.  Observe que hay dos subgrupos, Supervisor de eDiscovery y Administrador de eDiscovery.  
    1. La página "Administrar administrador de eDiscovery" le permite agregar usuarios al rol de administrador de eDiscovery. En este laboratorio, vamos a agregar miembros al subgrupo Administrador de eDiscovery. Seleccione **Siguiente**.
    1. En la página "Administrar administrador de eDiscovery", seleccione **Elegir usuarios**. Busque y seleccione **Administrador de MOD** y **Megan Bowen** y, a continuación, presione **Seleccionar** en la parte inferior de la página, seleccione **Siguiente** y, después, **Guardar**.
    1. En la página "Ha actualizado correctamente el grupo de roles", seleccione **Listo**.

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### Tarea 2

En esta tarea, como administrador de eDiscovery (un administrador MOD es un administrador de eDiscovery), creará un caso para empezar a utilizar eDiscovery (Standard).

1. Debería seguir en la página Roles del portal de cumplimiento. Si ha cerrado la pestaña del explorador de la tarea anterior, abra una nueva y escriba **compliance.microsoft.com**

1. En el panel de navegación izquierdo, debajo de Soluciones, expanda **eDiscovery** y luego **Standard**.

1. En la parte superior de la página eDiscovery (Standard), seleccione **+ Crear un caso**.

1. En la ventana Nuevo caso, escriba un nombre para el caso, **Caso de prueba SC900**, y luego seleccione **Guardar** en la parte inferior de la página.

1. Ahora el caso debería aparecer en la lista.

1. Como creador del caso, y dado que tiene privilegios de administrador de eDiscovery, puede empezar a trabajar con él.  

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### Tarea 3

Ahora que ha creado un caso de eDiscovery (Standard), puede empezar a trabajar con él.  En esta tarea, creará una suspensión de eDiscovery para el caso que ha creado.  En concreto, creará una suspensión para el Buzón de Exchange de Adele Vance.

1. Abra la pestaña eDiscovery (Standard) en su explorador.

1. En la página eDiscovery (Standard), seleccione el caso que ha creado en la pestaña anterior, **Caso de prueba SC900**.

1. En la página principal del caso, seleccione **Suspensión** y luego seleccione **+Crear**.

1. En el campo Nombre, escriba **Suspensión de prueba** y luego seleccione **Siguiente**.

1. En la página Elegir ubicaciones, seleccione el interruptor que hay junto a **Buzones de correo de Exchange** para configurar el estado en **Activado**.  

1. Ahora seleccione **Elegir usuarios, grupos o equipos**.  En el cuadro de búsqueda, escriba **Adele** y luego presione Entrar en su teclado. En los resultados de búsqueda, seleccione **Adele Vance** y luego **Listo**.

1. En la página Elegir ubicaciones, seleccione **Siguiente**.  Para ahorrar tiempo en el laboratorio, no se incluirá ninguna otra ubicación en esta suspensión.

1. La página Condiciones de la consulta le permite crear una suspensión basada en palabras clave o en el cumplimiento de condiciones específicas. Seleccione **+Agregar condición** para ver las opciones disponibles.  Seleccione **Siguiente**. Si no se establece ninguna condición, la suspensión preservará todo el contenido de la ubicación especificada.

1. Revise su configuración y seleccione **Enviar**. Es posible que tarde un minuto. Luego, seleccione **Listo**.  La suspensión de prueba debería aparecer en la lista.  Si no aparece inmediatamente, seleccione **Actualizar**.

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### Tarea 4

Ahora que la suspensión está lista, creará una consulta de búsqueda.  Una vez completada la búsqueda, eDiscovery admite acciones, como exportar y descargar los resultados para una investigación futura.   Nota:  Las búsquedas asociadas con un caso de eDiscovery (Standard) no aparecen en la página Búsqueda de contenido del Portal de cumplimiento de Microsoft Purview. Estás búsquedas aparecen únicamente en la página Búsquedas del caso de eDiscovery (Standard) asociado.

1. Abra la pestaña Caso de prueba SC900 en su explorador.

1. En la página Caso de prueba SC900, seleccione  **Búsquedas**.

1. En la página Búsqueda, seleccione **+ Nueva búsqueda**.

1. En el campo Nombre, escriba **Suspensión de prueba: Búsqueda de Ventas** y luego seleccione **Siguiente** en la parte inferior de la página.

1. En la página Elegir ubicaciones, seleccione las **ubicaciones en espera** y anule la selección de **Agregar contenido de la aplicación para usuarios locales**, ya que el entorno de laboratorio no tiene usuarios locales. A continuación, seleccione **Siguiente**.

1. La página Condiciones de la consulta le permite crear una suspensión basada en palabras clave o en el cumplimiento de condiciones específicas. En el campo Palabras clave, escriba **Ventas** y seleccione **Siguiente**.

1. Revise su configuración y seleccione **Enviar**. Es posible que tarde un minuto. Luego, seleccione **Listo**.  La búsqueda debería aparecer en la lista.  Si no aparece inmediatamente, seleccione **Actualizar**.

1. En la ventana Búsquedas, seleccione la búsqueda que ha creado, **Suspensión de prueba: Búsqueda de Ventas**.  Se abre una ventana con la pestaña Resumen seleccionada.  Una vez que la búsqueda haya finalizado, en el estado se mostrará el mensaje correspondiente.  Verá la pestaña Estadísticas de búsqueda (si no ve esta pestaña, es posible que la búsqueda no haya finalizado todavía y que tarde unos minutos en hacerlo).  Seleccione la pestaña **Estadísticas de búsqueda** y seleccione el menú desplegable junto a la opción Contenido de la búsqueda.  También puede ver más información sobre las opciones Informe de condiciones y Ubicaciones principales.  

1. En la parte inferior de la página, seleccione **Acciones**.  Tenga en cuenta las opciones disponibles que incluyen opciones de exportación (las opciones de exportación no se pueden seleccionar desde dentro de la plataforma de laboratorio proporcionada por el host de laboratorio autorizado, pero están disponibles en un entorno de producción y se consideran parte del flujo de trabajo estándar). Seleccione **Cerrar**.

1. Cierre la sesión y cierre todas las ventanas abiertas del explorador.

### Revisar

En este laboratorio le hemos guiado a través de los pasos necesarios para empezar a trabajar con eDiscovery (Standard), incluida la configuración de los permisos de roles y la creación de un caso de eDiscovery.  Una vez creado el caso, ha realizado un recorrido por los elementos del flujo de trabajo de eDiscovery (Standard). Para ello, ha creado una suspensión de eDiscovery y una consulta de búsqueda.
