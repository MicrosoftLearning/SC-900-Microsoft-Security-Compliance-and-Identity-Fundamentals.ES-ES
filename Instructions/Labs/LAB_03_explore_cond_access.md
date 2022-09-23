---
ms.openlocfilehash: 5d7767e0187f043004b0c9d17e7cd1d1915613cc
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892166"
---
<a name="---"></a><!---
---
Laboratorio: Ruta de aprendizaje: "Descripción de las funcionalidades de Azure Active Directory (Azure AD), parte de Microsoft Entra" Módulo: "Descripción de las funcionalidades de administración de acceso de Azure AD" Unidad: "Descripción del acceso condicional en Azure AD"
---
--->

# <a name="lab-explore-access-management-in-azure-ad-with-conditional"></a>Laboratorio: Explorar la administración de accesos en Azure AD con Conditional

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Azure Active Directory (Azure AD), parte de Microsoft Entra
- Módulo: Descripción de las funcionalidades de administración de acceso de Azure AD
- Unidad: Descripción del acceso condicional en Azure AD

## <a name="lab-scenario"></a>Escenario del laboratorio

En este laboratorio explorará el acceso condicional MFA, desde la perspectiva de un administrador y un usuario.  Como administrador, creará una directiva que requerirá que un usuario pase por la autenticación multifactor cuando acceda a una aplicación de administración de Microsoft Azure basada en la nube.  Desde la perspectiva del usuario, verá el impacto de la directiva de acceso condicional, incluido el proceso para registrarse en MFA.

**Tiempo estimado**: 10-15 minutos.

### <a name="task-1"></a>Tarea 1

En esta tarea, como administrador, restablecerá la contraseña del usuario Debra Berger.  Este paso es necesario para poder iniciar sesión como el usuario en las siguientes tareas.

1. Abrir Microsoft Edge.  En la barra de direcciones, escriba **portal.azure.com**.

2. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es el id. de inquilino único facilitado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Haga clic en **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

3. En la esquina superior izquierda de la pantalla, junto a las palabras Microsoft Azure, seleccione el icono Mostrar el menú del portal (las tres líneas horizontales, también denominadas icono de hamburguesa) y, luego, en el panel de navegación de la izquierda, en Favoritos, seleccione Azure Active Directory. Si no aparece en los favoritos, escriba Azure Active Directory en el cuadro de búsqueda y, a continuación, en la lista de resultados, seleccione **Azure Active Directory**.

4. En el panel de navegación izquierdo, seleccione **Usuarios**.

5. Seleccione **Debra Berger** de la lista de usuarios.

6. Seleccione **Restablecer contraseña** en la parte superior de la página. Como no ha iniciado sesión previamente como Debra Berger, no conoce su contraseña y deberá restablecerla.

7. Cuando se abra la ventana de restablecimiento de contraseña, seleccione **Restablecer contraseña**.  IMPORTANTE: Anote la nueva contraseña, la necesitará en una tarea posterior para poder acceder como usuario.

8. Cierre la ventana de restablecimiento de contraseña con la **X** de la esquina superior derecha de la página.

9. Cierre la ventana Usuarios con la **X** de la esquina superior derecha de la página.

10. Mantenga esta ventana abierta.

### <a name="task-2"></a>Tarea 2

En esta tarea, aprenderá el proceso de creación de una directiva de acceso condicional en Azure AD.

1. Abra la pestaña del navegador etiquetada como Contoso – Microsoft Azure.   Si ha cerrado la pestaña del navegador, abra Microsoft Edge, en la barra de direcciones, escriba portal.azure.com, inicie sesión con sus credenciales de administrador y seleccione Azure Active Directory.  

2. En el panel de navegación izquierdo, seleccione **Seguridad**.

3. En el panel de navegación izquierdo, seleccione **Acceso condicional**.

4. Se mostrará la pantalla Directivas de acceso condicional. Cualquier directiva de acceso condicional existente se mostrará en esta página. Seleccione **Nueva directiva**.

5. En el campo Nombre, escriba **Directiva de prueba para la MFA**.

6. En Usuarios y grupos, seleccione **0 usuarios y grupos seleccionados**.

7. Ahora verá la opción para incluir o excluir usuarios y grupos.  Asegúrese de que **Incluir** esté seleccionado (subrayado).

8. Seleccione la opción de **Seleccionar usuarios y grupos** y seleccione **Usuarios y grupos**.  Se abrirá la ventana Seleccionar usuarios y grupos.  

9. En la barra de búsqueda, escriba **Debra**.  Seleccione **Debra Berger** bajo la barra de búsqueda y luego pulse el botón **Seleccionar** en la parte inferior de la página.  Nota: Una práctica común es asignar la directiva a los usuarios de un grupo.  Para este laboratorio, asignaremos la directiva a un usuario específico.

10. En Aplicaciones o acciones en la nube, seleccione **No hay aplicaciones en la nube o acciones seleccionadas**.

11. Ahora verá la opción de Incluir o Excluir aplicaciones o acciones de usuarios.  Asegúrese de que **Aplicaciones en la nube** esté resaltado y que **Incluir** esté seleccionado (subrayado), luego seleccione **Seleccionar aplicaciones**.  Se abrirá la ventana Seleccionar aplicaciones en la nube.

12. En la barra de búsqueda, escriba **Azure**.  En los resultados de la búsqueda que aparecen bajo el cuadro de búsqueda, seleccione **Administración de Microsoft Azure** y luego pulse **Seleccionar** en la parte inferior de la página.  Observe la advertencia.  

13. En Condiciones, seleccione **0 condiciones seleccionadas**.  Observe las diferentes opciones que puede configurar.  Mediante la directiva, puede controlar el acceso de los usuarios en función de señales de condiciones como el riesgo, la plataforma del dispositivo, la ubicación, las aplicaciones cliente o el estado del dispositivo.  Por ejemplo, puede incluir una condición para que la directiva se aplique a cualquier ubicación, excepto a las seleccionadas o de confianza, como la red de su oficina central.  Para esta directiva, no establezca ninguna condición.

14. Ahora se establecerán los controles de acceso.  En Conceder, seleccione **0 controles seleccionados**.

15. Se abrirá la ventana Conceder.  Asegúrese de que **Conceder acceso** esté seleccionado y luego seleccione **Requerir autenticación multifactor**.  En la sección Para varios controles, deje el valor predeterminado **Requerir todos los controles seleccionados**.  Pulse **Seleccionar** en la parte inferior de la página.

16. En la parte inferior de la página, en Habilitar directiva, seleccione **Activado** y luego pulse el **botón Crear**.

17. Tras unos segundos, la directiva MFA Pilot debería aparecer en la lista de directivas de acceso condicional (si es necesario, seleccione **Actualizar** en la parte superior de la página).

18. Cierre la sesión de Azure y cierre las ventanas del explorador.

### <a name="task-3"></a>Tarea 3

En esta tarea verá el impacto de la directiva de acceso condicional, desde la perspectiva del usuario, Debra Berger. En primer lugar, iniciará sesión en una aplicación que no esté incluida en la directiva de acceso condicional.  Luego repetirá el proceso en una aplicación que esté incluida en la directiva de acceso condicional.  Recuerde que la directiva requiere que el usuario pase por MFA cuando accede a una aplicación de la administración de Microsoft Azure.  Para utilizar la MFA, el usuario debe registrar primero el método de autenticación que se utilizará para la MFA, por ejemplo, un código enviado a un dispositivo móvil o una aplicación de autenticación.

1. Abrir Microsoft Edge.  En la barra de direcciones del explorador, escriba **login.microsoftonline.com/** .

1. Inicie sesión como Debra Burger.
    1. En la ventana de inicio de sesión, escriba **DebraB@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es el id. de inquilino único facilitado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña que anotó en la tarea anterior. Haga clic en **Iniciar sesión**.
    1. Dado que, como administrador, restableció la contraseña, ésta es temporal y, por tanto, deberá actualizarla (esto no es parte de la MFA).  Escriba la contraseña actual y luego, en los campos de nueva contraseña y confirmar contraseña, escriba **SC900-Lab**.
    1. Si se le pregunta si quiere mantener la sesión iniciada, seleccione **Sí**

1. Debería iniciar sesión correctamente en su cuenta de Microsoft 365.  El MFA no era necesaria para esta solicitud, ya que no forma parte de la directiva.

1. Ahora intentará iniciar sesión en una aplicación que cumpla con los criterios de la MFA.  Abra Microsoft Edge y, en la barra de direcciones, escriba **portal.azure.com**.

1. Verá una ventana que indica, Se necesita más información.  Seleccione **Next** (Siguiente).  Tenga en cuenta que esto iniciará el proceso de registro de la MFA, ya que es la primera vez que accede a la aplicación en la nube que se identificó en la directiva de acceso condicional.  Este proceso de registro solo es necesario una vez.   En lugar de que el usuario pase por el proceso de registro, una alternativa es que el administrador configure el método de autenticación a utilizar.

1. En la ventana Garantizar la seguridad de la cuenta, tiene la opción de seleccionar el método a utilizar para la MFA.  Una opción es Microsoft Authenticator. Para este laboratorio, elegirá un método diferente.  Seleccione **Quiero configurar otro método**.  En la ventana emergente Elegir otro método, seleccione la **flecha desplegable** y seleccione **Teléfono**, luego seleccione **Confirmar**.

1. Se abrirá una nueva ventana, asegúrese de que su país o región está seleccionado, luego escriba el número de teléfono móvil que desea utilizar, asegúrese de que **Enviarme un código por mensaje de texto** esté seleccionado y luego presione **Siguiente**.  La pantalla mostrará: "SMS verificado. El teléfono se ha registrado correctamente".  Seleccione **Next** (Siguiente). Después, seleccione **Listo**.  esto completará el único proceso de registro.

1. Puede que reciba un mensaje que indique que su inicio de sesión finalizó.  Solo debe escribir la contraseña **SC900-Lab** y seleccionar **Iniciar sesión**.

1. Verá una ventana que le solicita el código que le enviaron al teléfono.  Escriba el código y seleccione **Siguiente**.  Esta es la experiencia que usted, como Gerhart, experimentará cada vez que acceda a una aplicación en la nube de la administración de Microsoft Azure, como Azure Portal, según la directiva de la MFA.

1. Verá una ventana que le solicita el código que le enviaron al teléfono.  Escriba el código y seleccione el botón **Comprobar**.  Si se le pregunta si quiere mantener la sesión iniciada, seleccione **No**.

1. Ahora debería poder acceder a Azure Portal.  Azure Portal es una aplicación de administración de Microsoft Azure y, por lo tanto, requiere una autenticación multifactor, según la directiva de acceso condicional que se creó.  

1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione Cerrar sesión. A continuación, cierre todas las ventanas del navegador.

### <a name="review"></a>Revisar

En este laboratorio, aprendió el proceso de configuración de una directiva de acceso condicional que requiere que los usuarios pasen por la MFA cuando acceden a la aplicación en la nube de la administración de Microsoft Azure.  Luego, como usuario, aprendió el proceso de registro para la MFA y vio el impacto de la directiva de acceso condicional que necesitaba que usara la MFA al acceder a Azure Portal.
