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

En este laboratorio, explorará los pasos necesarios para configurar eDiscovery, incluida la configuración de permisos de rol, la creación de un caso de eDiscovery, la creación de una suspensión de eDiscovery y la creación de una consulta de búsqueda.  nota: Las licencias para eDiscovery (Estándar) requieren la suscripción de organización y las licencias por usuario adecuadas. Si no sabe con seguridad cuáles son las licencias compatibles con eDiscovery (Standard), visite [Introducción a eDiscovery (Standard) en Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

**Tiempo estimado**: 45 minutos

### Tarea 1

Para acceder a eDiscovery (Standard), o para que se le agregue como miembro de un caso de eDiscovery, el usuario debe tener asignados los permisos adecuados. En esta tarea, como administrador global, agregará usuarios específicos como miembros del grupo de roles de Supervisor de eDiscovery.

1. Abra la pestaña del explorador para la página principal de Microsoft Purview.  Si la había cerrado, abra otra y escriba **https://admin.microsoft.com** . Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). Si has iniciado sesión anteriormente como administrador, se te pedirá que completes una autenticación secundaria, como parte de MFA. Si no has iniciado sesión anteriormente como administrador, se te pedirá que completes el proceso de registro de MFA. Sigue las indicaciones en la pantalla para configurar MFA.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de Microsoft Purview.  

1. En el panel de navegación izquierdo, selecciona **Configuración**, expande **Roles y ámbitos** y, después, selecciona **Grupos de roles**.

1. En el cuadro de búsqueda, en la parte superior derecha de la página, escribe **eDiscovery** y presiona Entrar en el teclado.  Selecciona **Supervisor de eDiscovery**.

1. Seleccione **Editar**. Para este laboratorio, te establecerás como administrador MOD como Supervisor y administrador de eDiscovery.  En la práctica, designarías usuarios específicos para roles específicos.
    1. La página "Administrar Supervisor de eDiscovery" permite agregar usuarios al rol de administrador de eDiscovery.
    1. Selecciona **Elegir usuarios**. Busca y selecciona **Administrador MOD** y presiona **Seleccionar** en la parte inferior de la página y, después, selecciona **Siguiente**.
    1. En la página "Administrar Administrador de eDiscovery", seleccione **Elegir usuarios** . Busca y selecciona **Administrador MOD** y presiona **Seleccionar** en la parte inferior de la página y, después, selecciona **Siguiente** y **Guardar**.
    1. En la página "Ha actualizado correctamente el grupo de roles", seleccione **Listo**.

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### Tarea 2

En esta tarea, como administrador de eDiscovery (un administrador MOD es un administrador de eDiscovery), creará un caso para empezar a utilizar eDiscovery (Standard).

1. Debería seguir en la página Roles del portal de cumplimiento. Si has cerrado la pestaña del explorador de la tarea anterior, abre una nueva pestaña del explorador y escribe **compliance.microsoft.com** para ir al Portal de Microsoft Purview.

1. En el panel de navegación izquierdo, en Soluciones, expande **eDiscovery** y, luego, selecciona **Casos estándar**.

1. En la parte superior de la página eDiscovery (Estándar), selecciona **+ Crear un caso**.

1. En la ventana Nuevo caso, escribe un nombre de caso, **SC900 Test Case** y, a continuación, selecciona **Guardar** en la parte inferior de la página.

1. El caso debería aparecer ahora en la lista.

1. Como creador del caso y como tiene privilegios de Administrador de eDiscovery, puede empezar a trabajar con él.  

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### Tarea 3

Ahora que ha creado un caso de eDiscovery (Standard), puede empezar a trabajar con él.  En esta tarea, creará una suspensión de eDiscovery para el caso que ha creado.  En concreto, creará una suspensión para el Buzón de Exchange de Adele Vance.

1. Abra la pestaña eDiscovery (Standard) en su explorador.

1. En la página eDiscovery (Standard), seleccione el caso que ha creado en la pestaña anterior, **Caso de prueba SC900**.

1. En la página principal del caso, seleccione la pestaña **Mantener** y, a continuación, seleccione **+Crear**.

1. En el campo Nombre, escribe **Suspensión de prueba** y luego selecciona **Siguiente**.

1. En la página Elegir ubicaciones, selecciona el interruptor que hay junto a **Buzones de correo de Exchange** para configurar el estado en **Activado**.  

1. Ahora selecciona **Elegir usuarios, grupos o equipos**.  En el cuadro de búsqueda, escribe **Adele** y presiona Entrar en el teclado. En los resultados de búsqueda, selecciona **Adele Vance** y luego **Listo**.

1. En la página Elegir ubicación de instalación, seleccione **Siguiente**.  Para mayor comodidad durante el laboratorio, no se incluirá ninguna otra ubicación en esta suspensión.

1. La página Condiciones de la consulta le permite crear una suspensión basada en palabras clave o en el cumplimiento de condiciones específicas. Seleccione **+Agregar condición** para ver las opciones disponibles.  Selecciona **Siguiente**. Sin ninguna condición, la suspensión conservará todo el contenido de la ubicación especificada.

1. Revisa la configuración y selecciona **Enviar**, puede tardar un minuto, luego, selecciona **Listo**.  La suspensión de prueba debería aparecer en la lista.  Si no la ve inmediatamente, seleccione **Actualizar**

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### Tarea 4

Ahora que la suspensión está lista, creará una consulta de búsqueda.  Una vez completada la búsqueda, eDiscovery admite acciones, como exportar y descargar los resultados para una investigación futura.   Nota: Las búsquedas asociadas con un caso de eDiscovery (Estándar) no aparecen en la página Búsqueda de contenido del portal de cumplimiento de Microsoft Purview. Estás búsquedas aparecen únicamente en la página Búsquedas del caso de eDiscovery (Standard) asociado.

1. Abra la pestaña Caso de prueba SC900 en su explorador.

1. En la página Caso de prueba SC900, seleccione **Búsquedas**.

1. En la página Buscar, selecciona **+ Nueva búsqueda**.

1. En el campo Nombre, escriba **Test Hold – Sales Search (Suspensión de prueba: Búsqueda de ventas)** y, a continuación, seleccione **Siguiente** en la parte inferior de la página.

1. En la página Elegir ubicaciones, seleccione las **ubicaciones en espera** y anule la selección de **Agregar contenido de la aplicación para usuarios locales**, ya que el entorno de laboratorio no tiene usuarios locales. A continuación, seleccione **Siguiente**.

1. La página Condiciones de la consulta le permite crear una búsqueda basada en palabras clave específicas o en el cumplimiento de condiciones específicas. En el campo Teclado escriba **Sales (Ventas)** y seleccione **Siguiente**.

1. Revisa la configuración y selecciona **Enviar**, puede tardar un minuto, luego, selecciona **Listo**.  La búsqueda debería aparecer en la lista.  Si no la ves inmediatamente, selecciona **Actualizar**

1. En la ventana Búsquedas, selecciona la búsqueda que has creado, **Test Hold - Sales Search**.  Ventana que se abre con la pestaña Resumen seleccionada.  Una vez que la búsqueda haya finalizado, en el estado se mostrará el mensaje correspondiente.  Verá la pestaña Estadísticas de búsqueda (si no ve esta pestaña, es posible que la búsqueda no haya finalizado todavía y que tarde unos minutos en hacerlo).  Seleccione la pestaña **Buscar estadísticas** y seleccione la flecha hacia abajo situada junto a Buscar contenido.  También puede ver más información sobre el informe de condiciones y las ubicaciones principales.  

1. En la parte inferior de la página, seleccione **Acciones**.  Tenga en cuenta las opciones disponibles que incluyen opciones de exportación (las opciones de exportación no se pueden seleccionar desde dentro de la plataforma de laboratorio proporcionada por el host de laboratorio autorizado, pero están disponibles en un entorno de producción y se consideran parte del flujo de trabajo estándar). Seleccione **Close** (Cerrar).

1. Cierre la sesión y cierre todas las ventanas del explorador abiertas.

### Revisar

En este laboratorio le hemos guiado a través de los pasos necesarios para empezar a trabajar con eDiscovery (Standard), incluida la configuración de los permisos de roles y la creación de un caso de eDiscovery.  Una vez creado el caso, ha realizado un recorrido por los elementos del flujo de trabajo de eDiscovery (Standard). Para ello, ha creado una suspensión de eDiscovery y una consulta de búsqueda.
