---
lab:
  title: Explorar el flujo de trabajo de Core eDiscovery
  module: 'Module 4 Lesson 5: Describe the capabilities of Microsoft compliance solutions: Describe the eDiscovery and audit capabilities of Microsoft 365'
ms.openlocfilehash: 0754237aa892e9fe31ad2eea0811642bce929fe8
ms.sourcegitcommit: c14538b208890797642cfe5c35abf6bea45364bf
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/15/2022
ms.locfileid: "142614379"
---
# <a name="lab-explore-the-core-ediscovery-workflow"></a>Laboratorio: Explorar el flujo de trabajo de Core eDiscovery

## <a name="lab-scenario"></a>Escenario del laboratorio
En este laboratorio le guiaremos a través de los pasos necesarios para configurar Core eDiscovery y su flujo de trabajo. Para ello, creará una suspensión de eDiscovery y una consulta de búsqueda, y luego exportará los resultados de la búsqueda.  Nota:  Para obtener una licencia de Core eDiscovery, es necesario disponer de la suscripción de organización y las licencias por usuario adecuadas. Si no está seguro de qué licencias admiten Core eDiscovery, visite Introducción a Core eDiscovery.


**Tiempo estimado**: 20-25 minutos

#### <a name="task-1--to-access-core-ediscovery-or-be-added-as-a-member-of-a-core-ediscovery-case-a-user-must-be-assigned-the-appropriate-permissions-in-this-task-you-as-the-global-admin-will-add-specific-users-as-members-of-the-ediscovery-manager-role-group"></a>Tarea 1:  Para acceder a Core eDiscovery, o para que se le agregue como miembro de un caso de Core eDiscovery, el usuario debe tener asignados los permisos adecuados. En esta tarea, como administrador global, agregará usuarios específicos como miembros del grupo de roles de Supervisor de eDiscovery

 Abrir Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es el id. de inquilino único facilitado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Haga clic en **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del Centro de cumplimiento de Microsoft 365.  

1. En el panel de navegación izquierdo, seleccione **Permisos**. 

1. En la página Permisos y roles, en Centro de cumplimiento, seleccione **Roles**.

1. En el campo de búsqueda, escriba **eDiscovery** y seleccione el icono de búsqueda (la lupa).  Seleccione **Supervisor de eDiscovery**.

1. En la ventana que se abre, observe que hay dos subgrupos, Supervisor de eDiscovery y Administrador de eDiscovery.  Lea sus respectivas descripciones.  En este laboratorio, vamos a agregar miembros al subgrupo Administrador de eDiscovery. Seleccione **Editar** junto al Administrador de eDiscovery.  El procedimiento recomendado es asignar a los usuarios los privilegios mínimos necesarios para el rol.

1. Para agregar miembros a este grupo de roles, asegúrese de que se encuentra en la pestaña **Elegir Administrador de eDiscovery** y luego seleccione **Elegir Administrador de eDiscovery**.

1. Seleccione **+ Agregar** en la parte superior de la página.

1. En la lista de nombres, seleccione **Megan Bowen**, **Administrador MOD** y luego seleccione **Agregar** y **Aceptar** en la parte inferior de la página.

1. Compruebe que ha agregado los miembros correctos y luego seleccione **Guardar**.

1. En la parte inferior de la ventana eDiscovery, seleccione **Cerrar**.

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

#### <a name="task-2--in-this-task-you-as-an-ediscovery-administrator-mod-admin-is-an-ediscovery-administrator-will-create-a-case-to-start-using-core-ediscovery"></a>Tarea 2:  En esta tarea, como administrador de eDiscovery (un administrador MOD es un administrador de eDiscovery), creará un caso para empezar a utilizar Core eDiscovery

1. Debería seguir en la página Roles de Centro de cumplimiento. Si ha cerrado la pestaña del explorador de la tarea anterior, abra una nueva y escriba **compliance.microsoft.com**

1. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **eDiscovery** y luego **Core**.

1. En la parte superior de la página Core eDiscovery, seleccione **+ Crear un caso**.

1. En la ventana Nuevo caso, escriba un nombre para el caso, **Caso de prueba SC900**, y luego seleccione **Guardar** en la parte inferior de la página.

1. Ahora el caso debería aparecer en la lista.

1. Como creador del caso, y dado que tiene privilegios de administrador de eDiscovery, puede empezar a trabajar con él.  

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

#### <a name="task-3--now-that-you-have-created-a-core-ediscovery-case-you-can-begin-to-work-with-the-case--in-this-task-you-will-create-an-ediscovery-hold-for-the-case-for-you-just-created--specifically-you-will-crate-a-hold-for-the-the-exchange-mailbox-belonging-to-adele-vance"></a>Tarea 3:  Ahora que ha creado un caso de Core eDiscovery, puede empezar a trabajar con él.  En esta tarea, creará una suspensión de eDiscovery para el caso que acaba de crear.  En concreto, creará una suspensión para el Buzón de Exchange de Adele Vance

1. Abra la pestaña Core eDiscovery en su explorador.

1. En la página Core eDiscovery, seleccione el caso que ha creado en la pestaña anterior, **Caso de prueba SC900**. 

1. En la página principal del caso, seleccione **Suspensión** y luego seleccione **+Crear**.

1. En el campo Nombre, escriba **Suspensión de prueba** y luego seleccione Siguiente.

1. En la página Elegir ubicaciones, seleccione el interruptor que hay junto a **Buzones de correo de Exchange** para configurar el estado en **Activado** y, a continuación, **Elija usuarios, grupos o equipos**.  En el cuadro de búsqueda, escriba **Adele** y luego presione Entrar en su teclado. En los resultados de búsqueda, seleccione **Adele Vance** y luego Elegir y **Listo**.

1. En la página Elegir ubicaciones, seleccione **Siguiente**.  Para ahorrar tiempo en el laboratorio, no se incluirá ninguna otra ubicación en esta suspensión.

1. La página Condiciones de la consulta le permite crear una suspensión basada en palabras clave o en el cumplimiento de condiciones específicas. Seleccione **+Condiciones** para ver las opciones disponibles.  Seleccione **Siguiente**. Si no se establece ninguna condición, la suspensión preservará todo el contenido de la ubicación especificada.

1. Revise su configuración y seleccione **Enviar**. Es posible que tarde un minuto. Luego, seleccione **Listo**.  La suspensión de prueba debería aparecer en la lista.  Si no aparece inmediatamente, seleccione **Actualizar**.

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

#### <a name="task-4--with-a-hold-in-place-you-will-create-a-search-query--once-your-search-is-complete-you-will-go-export-and-download-the-results-for-future-investigation---note--searches-associated-with-a-core-ediscovery-case-are-not-listed-on-the-content-search-page-in-the-microsoft-365-compliance-center-these-searches-are-listed-only-on-the-searches-page-of-the-associated-core-ediscovery-case"></a>Tarea 4:  Ahora que la suspensión está lista, creará una consulta de búsqueda.  Una vez que la búsqueda haya finalizado, exportará y descargará los resultados para continuar la investigación en el futuro.   Nota:  Las búsquedas asociadas con un caso de Core eDiscovery no aparecen en la página Búsqueda de contenido del Centro de cumplimiento de Microsoft 365. Estás búsquedas aparecen únicamente en la página Búsquedas del caso de Core eDiscovery asociado

1. Abra la pestaña Caso de prueba SC900 en su explorador.

1. En la página Suspensiones del caso, seleccione **Búsquedas**.

1. En la página Búsqueda, seleccione **+ Nueva búsqueda**.

1. En el campo Nombre, escriba **Suspensión de prueba: Búsqueda de Ventas** y luego seleccione **Siguiente** en la parte inferior de la página.

1. En la página Elegir ubicaciones, seleccione las **ubicaciones en espera** y anule la selección de **Agregar contenido de la aplicación para usuarios locales**, ya que el entorno de laboratorio no tiene usuarios locales. A continuación, seleccione **Siguiente**.

1. La página Condiciones de la consulta le permite crear una suspensión basada en palabras clave o en el cumplimiento de condiciones específicas. En el campo Palabras clave, escriba **Ventas** y seleccione **Siguiente**.

1. Revise su configuración y seleccione **Enviar**. Es posible que tarde un minuto. Luego, seleccione **Listo**.  La búsqueda debería aparecer en la lista.  Si no aparece inmediatamente, seleccione **Actualizar**.

1. En la ventana Búsquedas, seleccione la búsqueda que acaba de crear, **Suspensión de prueba: Búsqueda de Ventas**.  Se abre una ventana con la pestaña Resumen seleccionada.  Una vez que la búsqueda haya finalizado, en el estado se mostrará el mensaje correspondiente.  Verá la pestaña Estadísticas de búsqueda (si no ve esta pestaña, es posible que la búsqueda no haya finalizado todavía y que tarde unos minutos en hacerlo).  Seleccione la pestaña **Estadísticas de búsqueda** y seleccione el menú desplegable junto a la opción Contenido de la búsqueda.  También puede ver más información sobre las opciones Informe de condiciones y Ubicaciones principales.  

1. En la parte inferior de la página, seleccione **Acciones**.  Observe las opciones disponibles y luego seleccione **Exportar resultados**.
    
    1. En la ventana Exportar resultados, deje los valores predeterminados y seleccione **Exportar** en la parte inferior de la página. Volverá automáticamente a la ventana "Suspensión de prueba: Búsqueda de Ventas". Seleccione **Cerrar** en la parte inferior de la página.
    
    1. En la página Caso de prueba SC900, seleccione **Exportaciones** en la parte superior de la página.
    1. Seleccione **Suspensión de prueba: Búsqueda de ventas_Exportación**.
    1. En la ventana que se abre, "Suspensión de prueba: Búsqueda de ventas_Exportación", verá una clave de exportación. Seleccione **Copiar al Portapapeles**.
    1. Seleccione **Descargar resultados** en la parte superior de la ventana. Se abrirá una nueva página del explorador y se mostrará una ventana emergente con un mensaje en el que se le preguntará si desea abrir este archivo. Seleccione **Abrir**.
    1. Si esta es la primera vez que descarga el contenido de una búsqueda, se le pedirá que instale la Herramienta de exportación de eDiscovery para Microsoft Office 365.  Seleccione **Instalar**.
    1. Una vez que la instalación haya finalizado, se abrirá la ventana Herramienta de exportación de eDiscovery.  Pegue la clave de exportación que ha copiado a su Portapapeles en el primer campo. Péguela ahora (presione Control + V en su teclado o haga clic con el botón derecho de su ratón y seleccione Pegar).
    1. En el segundo campo, seleccione la ubicación en la que desea almacenar el archivo exportado y luego seleccione **Iniciar**.  Una vez que el proceso de descarga haya finalizado, seleccione **Cerrar** y cierre esta pestaña del explorador.
    1. Ha vuelto a la ventana "Suspensión de prueba: Búsqueda de ventas_Exportación".  Seleccione **Cerrar**.
    1. Revise la ubicación de su descarga para comprobar que ha finalizado correctamente. 


#### <a name="review"></a>Revisar

En este laboratorio le hemos guiado a través de los pasos necesarios para empezar a trabajar con Core eDiscovery, incluida la configuración de los permisos de roles y la creación de un caso de eDiscovery.  Una vez creado el caso, ha realizado un recorrido por el flujo de trabajo de Core eDiscovery. Para ello, ha creado una suspensión de eDiscovery y una consulta de búsqueda, y luego ha exportado los resultados de la búsqueda para usarlos en futuras investigaciones.