---
ms.openlocfilehash: 57c3c2d1e24acc7efaab97162e443a664dd76965
ms.sourcegitcommit: 804b98d288b1db2c11a5154b4ded954e87f5ae55
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/28/2022
ms.locfileid: "148119033"
---
<a name="---"></a><!---
---
Laboratorio: Título: "Configuración"
---
--->

# <a name="lab-setup"></a>Laboratorio: Configuración

## <a name="lab-scenario"></a>Escenario del laboratorio

Este laboratorio de configuración consiste en habilitar el registro de auditoría de Microsoft.

**Tiempo estimado**: 5-10 minutos

### <a name="setup---enable-microsoft-365-audit-log"></a>Configuración: Habilitar el registro de auditoría de Microsoft 365

En esta tarea de configuración, habilitará la funcionalidad Registro de auditoría de Microsoft 365.  Aunque la documentación indica que el registro de auditoría está habilitado de manera predeterminada, la mayoría de los inquilinos del laboratorio no tienen habilitada esta función y pueden pasar varias horas hasta que surta efecto.  Habilitar esta función resulta útil, ya que Microsoft 365 utiliza los registros de auditoría para conseguir información sobre los usuarios y las actividades identificadas en las directivas y los análisis.

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es el id. de inquilino único facilitado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del Centro de cumplimiento de Microsoft 365.  

1. En el panel de navegación izquierdo, en Soluciones, seleccione **Auditoría**.  Nota: También se puede acceder a la funcionalidad de auditoría a través de la página principal de Microsoft 365 Defender (anteriormente denominada Centro de seguridad de Microsoft 365).

1. Compruebe que la pestaña **Buscar** está seleccionada (subrayada).

1. Cuando llegue a la página Auditoría, espere entre 2 y 3 minutos.  Si Auditoría NO está habilitada, verá una barra azul en la parte superior de la página donde pone "Comenzar a registrar la actividad del usuario y del administrador".  Seleccione **Iniciar el registro de la actividad de usuarios y administradores**.  Si se le pide que confirme que el ajuste de la organización debe actualizarse, seleccione **Sí**. Una vez que la auditoría esté habilitada, la barra azul desaparecerá.  Si la barra azul no aparece, eso significará que la opción Auditoría ya está habilitada, y no necesitará hacer nada más.  Otra forma de comprobar si la auditoría está habilitada es a través de PowerShell, pero está fuera del ámbito de este curso.

1. Para volver a la página principal del centro de cumplimiento de Microsoft 365, seleccione **Inicio** en el panel de navegación izquierdo.

### <a name="review"></a>Revisar

En esta configuración, ha habilitado la funcionalidad de registro de auditoría de Microsoft 365.
