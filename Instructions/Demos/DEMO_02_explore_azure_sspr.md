---
Demo:
  title: Autoservicio de restablecimiento de contraseña de Azure Active Directory
  module: 'Module 2 Lesson 2: Describe the capabilities of Microsoft Identity and access management solutions: Describe the different authentication methods of Azure AD'
ms.openlocfilehash: 8b5ab5e9ba2670841d8bcf897cbfb4f6e76c9265
ms.sourcegitcommit: a341c2fc38e9b37dafb792d82e3c948f7ba4a099
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2022
ms.locfileid: "137894381"
---
# <a name="demo-azure-active-directory-self-service-password-reset-sspr"></a>Demostración: Autoservicio de restablecimiento de contraseña de Azure Active Directory (SSPR)

### <a name="demo-scenario"></a>Escenario de la demo

En esta demo, hará un recorrido por las diferentes configuraciones asociadas a la habilitación del autoservicio de restablecimiento de contraseña.

1. Vaya a la pestaña de Microsoft Azure: Contoso que hay abierta en su explorador. Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba portal.azure.com y seleccione Azure Active Directory. Debería haber iniciado sesión como administrador en Azure Portal; si no es así, vuelva a iniciar sesión.

1. En el panel de navegación izquierdo, seleccione Restablecer contraseña.

1. La pestaña Propiedades aparecerá resaltada.  En la ventana Propiedades, observe que el SSPR puede habilitarse para Ninguno, Seleccionar o Todos.
    1. Ponga el cursor sobre el icono de información junto a las palabras "Autoservicio de restablecimiento de contraseña habilitado" y haga hincapié en que puede elegir "Seleccionado" para restringir el restablecimiento de la contraseña a un grupo limitado de usuarios, o bien seleccionar Ninguno o Todos.
    1. Ponga su cursor sobre el icono de información que aparece junto al texto "Seleccionar grupo" y recalque que aquí es donde identifica al grupo de usuarios que tienen permiso para restablecer sus propias contraseñas.   Debe incluir usuarios en el grupo. No puede seleccionar usuarios de forma individual.  Además, si cambia el grupo, el grupo que seleccione reemplazará al grupo que aparezca en la lista en ese momento.  Por lo tanto, se recomienda que simplemente agregue los usuarios al grupo del SSPR.
    1. Observe el cuadro de información de color azul claro y señale su contenido a los estudiantes. Esta configuración solo se aplica a los usuarios finales de su organización. Los administradores siempre están habilitados para el autoservicio de restablecimiento de contraseña y deben utilizar dos métodos de autenticación para restablecer su contraseña.

1. En el panel de navegación izquierdo de restablecimiento de contraseña, seleccione Métodos de autenticación.
    1. Ponga el cursor sobre el icono de información que aparece junto al texto "Número de métodos requeridos para el restablecimiento".  Explique que esta opción configura el número de métodos de identificación alternativos de los que debe disponer un usuario de este directorio para restablecer su contraseña.   No cambie la configuración.
    1. Haga hincapié en los diferentes "métodos disponibles para los usuarios", incluyendo la idea de que el SSPR admite preguntas de seguridad. Seleccione Preguntas de seguridad para mostrar las opciones para utilizar preguntas de seguridad. Una vez que haya terminado de comentar las opciones, vuelva atrás y seleccione Preguntas de seguridad para quitar la marca de verificación.

1. En el panel de navegación izquierdo de restablecimiento de contraseña, seleccione Registro.
    1. Mantenga el puntero sobre el icono de información junto al texto "Requerir a los usuarios que se registren al iniciar sesión".   Recalque este punto a los usuarios.  
    1. Mantenga el puntero sobre el icono de información que aparece junto al texto "Número de días antes de que al usuario se le pida que vuelva a confirmar su información de autenticación".   Recalque este punto a los usuarios.  

1. En el panel de navegación izquierdo de restablecimiento de contraseña, seleccione Notificaciones.  Haga hincapié en las dos configuraciones. Mantenga el puntero sobre el icono de información para ver la descripción.

1. Observe que el panel de navegación de Restablecimiento de contraseña también incluye opciones para ver registros de auditorías y Uso e información.

1. Seleccione la X en la esquina superior derecha de la página. Esto le devolverá a la página principal del inquilino de Contoso.

1. Mantenga la página del explorador abierta para la siguiente demo.

#### <a name="review"></a>Revisar

En esta demo, ha realizado un recorrido por la configuración asociada al autoservicio de restablecimiento de contraseña. 

