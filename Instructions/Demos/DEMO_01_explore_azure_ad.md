---
Demo:
  title: Azure Active Directory user settings
  module: 'Module 2 Lesson 1: Describe the capabilities of Microsoft Identity and access management solutions: Explore the services and identity types of Azure AD'
ms.openlocfilehash: eb1ffc50ce90922dced58726c39879edfc74fb5b
ms.sourcegitcommit: 25998048c2e354ea23d6f497205e8a062d34ac80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2022
ms.locfileid: "144557187"
---
# <a name="demo-azure-active-directory-user-settings"></a>Demostración: Azure Active Directory user settings

## <a name="demo-scenario"></a>Escenario de la demo

En esta demostración, accederá a Azure Active Directory y recorrerá las distintas configuraciones para un usuario.

1. Vaya a la pestaña **Inicio – Microsoft Azure** abierta en su explorador.  Si ha cerrado previamente la pestaña, abra Microsoft Edge y en la barra de direcciones escriba portal.azure.com e inicie sesión con las mismas credenciales de administrador que su inquilino de Microsoft 365.

1. La página de aterrizaje de Azure Portal muestra los servicios de Azure, seleccione **Azure Active Directory**. Si no aparece inmediatamente, en el cuadro de búsqueda al lado de Microsoft Azure, escriba Azure Active Directory.  También es interesante mostrar cómo acceder mediante el icono para mostrar el menú del portal (las tres líneas horizontales, también denominadas icono de hamburguesa, en la barra azul de la parte superior de la página) a la izquierda de Microsoft Azure.

1. En el panel de navegación izquierdo, seleccione **Usuarios**. Verá que su inquilino ya está configurado con usuarios.

1. En la lista de usuarios, seleccione **Adele Vance**.

1. Observe que en el panel de navegación izquierdo está seleccionado **Perfil**.  Mostrar/usar la información mostrada en la página del perfil.

1. En el panel de navegación izquierdo, seleccione **Roles asignados**.  Este usuario no tiene asignado ningún rol administrativo.  En la parte superior de la página, seleccione **+ Agregar asignaciones** para mostrar los tipos de roles administrativos disponibles.  No agregue nada, simplemente cierre la página con la **X** de la parte superior derecha de la página.

1. En el panel de navegación izquierdo, seleccione **Grupos**.  Informe de que este usuario es miembro de varios grupos.  Aquí puede hablar de los tipos de grupos.  Para agregar este usuario a otros grupos, basta con seleccionar **+ Agregar pertenencias**.  No agregue ningún grupo nuevo, solo hable de lo fácil que es agregar un usuario a los grupos existentes. Cierre la ventana de grupos con la **X** de la esquina superior derecha de la página.

1. En el panel de navegación izquierdo, seleccione **Licencias**. Observe que a este usuario se le asignan licencias de Microsoft 365 E5 y EMS.  Para agregar una licencia, seleccione **+ Asignaciones** en la parte superior de la ventana principal.  Muestre las licencias de este usuario. NO cambie nada.  Cierre esta ventana con la **X** de la esquina superior derecha de la página.

1. En el panel de navegación izquierdo, seleccione **Dispositivos**.  No aparece nada, pero puede decir que si este usuario tuviera dispositivos asignados, aquí es donde aparecería.

1. En el panel de navegación izquierdo, seleccione **Asignaciones de roles de Azure**.  A destacar:
    1. Esto es diferente a la pestaña de roles asignados mostrada anteriormente, ya que esa pestaña anterior es para el control de acceso basado en roles en Azure Active Directory (destaque Active Directory).
    1. En esta pestaña, puede ver los roles asignados a los usuarios para los recursos de Azure. Por ejemplo, si crea un grupo de recursos de Azure y asigna a Adele un rol específico, como la de propietaria o colaboradora del grupo de recursos, verá que ese rol aparece aquí. Esto es parte del control del acceso basado en rol de Azure (Azure RBAC). Esa asignación de rol se administra como parte de ese recurso específico.

1. En el panel de navegación izquierdo, seleccione **Métodos de autenticación**.  Llame la atención hacia la descripción que dice: "Aquí puede establecer los números de teléfono y las direcciones de correo electrónico que los usuarios utilizan para realizar la autenticación multifactor (MFA), el autoservicio de restablecimiento de contraseña (SSPR)y restablecer la contraseña de un usuario". Si un usuario está configurado para SSPR o está obligado a usar MFA, y usted, como administrador, rellena esto, entonces ya estará registrado y no tendrá que seguir los pasos de registro para SSPR o MFA.  Es frecuente que el usuario se autorregistre en lugar de que el administrador tenga que hacerlo.

1. En el panel de navegación izquierdo, seleccione **Inicios de sesión**  Aquí puede ver la actividad de inicio de sesión de este usuario.  Es posible que no vea nada para este usuario, ya que todavía no ha iniciado sesión.

1. Seleccione la **X** en la esquina superior derecha de la página. Volverá a la lista de usuarios.  Antes de cerrar la lista de usuarios, puede destacar que la MFA se muestra en la parte superior de la página  Seleccione **Multi-Factor Authentication**.  Se abre una nueva ventana del explorador.  Aquí puede seleccionar en masa las MFA para los usuarios.  Esta es una forma de habilitar la MFA para los usuarios.  En realidad, mostraremos más sobre la MFA en el contexto del acceso condicional que aporta un control más pormenorizado de la MFA.  Cierre la pestaña del explorador para la autenticación multifactor.

1. Seleccione la **X** en la esquina superior derecha de la página. Esto le devolverá a la página principal del inquilino de Contoso.

### <a name="review"></a>Revisar

En esta demostración, ha mostrado la configuración de un usuario existente, incluidos los grupos a los que se puede asignar el usuario, la disponibilidad de roles y la asignación de licencias de usuario.
