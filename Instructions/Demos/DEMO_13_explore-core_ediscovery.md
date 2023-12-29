<!---
---
Demo: Título: "Explorar el flujo de trabajo de eDiscovery (estándar)" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las capacidades de cumplimiento de Microsoft; Módulo 5: Descripción de las capacidades de eDiscovery y de auditoría de Microsoft Purview; Unidad 2: Descripción de las soluciones de eDiscovery en Microsoft 365"
---
--->

# Demo: Explorar el flujo de trabajo de eDiscovery (Estándar)

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de las funcionalidades de eDiscovery y de auditoría de Microsoft Purview
- Unidad: Describir las soluciones de eDiscovery de Microsoft Purview

## Supuesto de demostración

En esta demo, explorará los pasos necesarios para configurar eDiscovery, incluida la configuración de permisos de rol, la creación de un caso de eDiscovery, la creación de una suspensión de eDiscovery y la creación de una consulta de búsqueda.  nota: Las licencias para eDiscovery (Estándar) requieren la suscripción de organización y las licencias por usuario adecuadas. Si no sabe con seguridad cuáles son las licencias compatibles con eDiscovery (Standard), visite [Introducción a eDiscovery (Standard) en Microsoft Purview](https://docs.microsoft.com/microsoft-365/compliance/get-started-core-ediscovery?view=o365-worldwide).

### Demo, parte 1

Para acceder a eDiscovery (Standard), o para que se le agregue como miembro de un caso de eDiscovery, el usuario debe tener asignados los permisos adecuados. En esta parte de la demostración, como administrador global, recorrerá el proceso de agregar usuarios específicos como miembros del grupo de roles de Supervisor de eDiscovery.

1. Abra la pestaña del explorador para la página principal de Microsoft Purview.  Si la había cerrado, abra otra y escriba **https://admin.microsoft.com** . Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH). En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo** y luego seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.  

1. En el panel de navegación izquierdo, expanda (seleccione la flecha hacia abajo) **Roles y ámbitos** y, a continuación, seleccione **Permisos**.

1. En Soluciones de Microsoft Purview, seleccione **Roles**.

1. En el campo de búsqueda, escriba **eDiscovery** y seleccione el icono de búsqueda (la lupa).  Seleccione **Supervisor de eDiscovery**.  Fíjese en los roles del grupo de roles.

1. Seleccione **Editar**.  Observe que hay dos subgrupos, Supervisor de eDiscovery y Administrador de eDiscovery.  
    1. La página "Administrar Supervisor de eDiscovery" permite agregar usuarios al rol de administrador de eDiscovery. En esta demo, agregaremos miembros al subgrupo Administrador de eDiscovery, así que, seleccione **Siguiente**.
    1. En la página "Administrar Administrador de eDiscovery", seleccione **Elegir usuarios** . Busque y seleccione **Administrador de MOD** y **Megan Bowen**, a continuación, pulse **Seleccionar** en la parte inferior de la página y,luego, seleccione **Siguiente** y **Guardar**.
    1. En la página "Ha actualizado correctamente el grupo de roles", seleccione **Listo**.

1. Mantenga abierta esta pestaña del explorador.

### Demo, parte 2

En esta parte, como administrador de eDiscovery (un administrador MOD es un administrador de eDiscovery), creará un caso para empezar a utilizar eDiscovery (Estándar).

1. Debería seguir en la página Roles del portal de cumplimiento. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **eDiscovery** y luego **Standard**.

1. En la parte superior de la página eDiscovery (Standard), seleccione **+ Crear un caso**.

1. En la ventana Nuevo caso, escriba un nombre de caso, **Caso de prueba SC900** y, a continuación, seleccione **Guardar** en la parte inferior de la página.

1. El caso debería aparecer ahora en la lista.

1. Como creador del caso y como tiene privilegios de Administrador de eDiscovery, puede empezar a trabajar con él.  

1. Mantenga abierta esta pestaña del explorador.

### Demo, parte 3

Ahora que ha creado un caso de eDiscovery (Standard), puede empezar a trabajar con él.  En esta parte, creará una suspensión de eDiscovery para el caso que ha creado.  En concreto, creará una suspensión para el Buzón de Exchange de Adele Vance.

1. En la página eDiscovery (Estándar), seleccione el caso que ha creado en la- **Caso de prueba SC900**.

1. En la página principal del caso, seleccione la pestaña **Mantener** y, a continuación, seleccione **+Crear**.

1. En el campo Nombre, escriba **Suspensión de prueba** y luego seleccione **Siguiente**.

1. En la página Elegir ubicaciones, seleccione el interruptor que hay junto a **Buzones de correo de Exchange** para configurar el estado en **Activado**.  

1. Ahora seleccione **Elegir usuarios, grupos o equipos**.  En el cuadro de búsqueda, escriba **Adele** y presione Entrar en el teclado. En los resultados de búsqueda, seleccione **Adele Vance** y luego **Listo**.

1. En la página Elegir ubicación de instalación, seleccione **Siguiente**.  Para mayor comodidad durante la demostración, no se incluirá ninguna otra ubicación en esta suspensión.

1. La página Condiciones de la consulta le permite crear una suspensión basada en palabras clave o en el cumplimiento de condiciones específicas. Seleccione **+Agregar condición** para ver las opciones disponibles.  Seleccione **Siguiente**. Sin ninguna condición, la suspensión conservará todo el contenido de la ubicación especificada.

1. Revise la configuración y seleccione **Enviar**, puede tardar un minuto, luego, seleccione **Listo**.  La suspensión de prueba debería aparecer en la lista.  Si no la ve inmediatamente, seleccione **Actualizar**

1. Mantenga abierta esta pestaña del explorador.

### Demo, parte 4

Ahora que la suspensión está lista, creará una consulta de búsqueda.  Una vez completada la búsqueda, eDiscovery admite acciones, como exportar y descargar los resultados para una investigación futura.   Nota: Las búsquedas asociadas con un caso de eDiscovery (Estándar) no aparecen en la página Búsqueda de contenido del portal de cumplimiento de Microsoft Purview. Estás búsquedas aparecen únicamente en la página Búsquedas del caso de eDiscovery (Standard) asociado.

1. En la página Caso de prueba SC900, seleccione **Búsquedas**.

1. En la página Buscar, seleccione **+ Nueva búsqueda**.

1. En el campo Nombre, escriba **Test Hold – Sales Search (Suspensión de prueba: Búsqueda de ventas)** y, a continuación, seleccione **Siguiente** en la parte inferior de la página.

1. En la página Elegir ubicaciones, seleccione las **ubicaciones en espera** y anule la selección de **Agregar contenido de la aplicación para usuarios locales**, ya que el entorno de laboratorio no tiene usuarios locales. A continuación, seleccione **Siguiente**.

1. La página Condiciones de la consulta le permite crear una búsqueda basada en palabras clave específicas o en el cumplimiento de condiciones específicas. En el campo Teclado escriba **Sales (Ventas)** y seleccione **Siguiente**.

1. Revise la configuración y seleccione **Enviar**, puede tardar un minuto, luego, seleccione **Listo**.  La búsqueda debería aparecer en la lista.  Si no la ve inmediatamente, seleccione **Actualizar**

1. En la ventana Búsquedas, seleccione la búsqueda que ha creado, **Suspensión de prueba: Búsqueda de Ventas**.  Ventana que se abre con la pestaña Resumen seleccionada.  Una vez que la búsqueda haya finalizado, en el estado se mostrará el mensaje correspondiente.  Verá la pestaña Estadísticas de búsqueda (si no ve esta pestaña, es posible que la búsqueda no haya finalizado todavía y que tarde unos minutos en hacerlo).  Seleccione la pestaña **Estadísticas de la búsqueda** y seleccione la flecha hacia abajo situada junto a Buscar contenido.  También puede ver más información sobre el informe de condiciones y las ubicaciones principales.  

1. En la parte inferior de la página, seleccione **Acciones**.  Fíjese en las opciones disponibles que incluyen las opciones de exportación. Seleccione **Close** (Cerrar).

1. Cierre todas las pestañas abiertas del explorador.

### Revisar

En esta demo vio los pasos necesarios para empezar a trabajar con eDiscovery (Estándar), incluida la configuración de los permisos de roles y la creación de un caso de eDiscovery.  Una vez creado el caso, ha realizado un recorrido por los elementos del flujo de trabajo de eDiscovery (Standard). Para ello, ha creado una suspensión de eDiscovery y una consulta de búsqueda.
