---
lab:
  title: "Acceso condicional de Microsoft\_Entra"
  module: Describe the access management capabilities of Microsoft Entra
---

# Laboratorio: Acceso condicional de Microsoft Entra

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de la funcionalidad de Microsoft Entra
- Módulo: Descripción de las funcionalidades de administración de acceso de Microsoft Entra
- Unidad: Descripción del acceso condicional

## Escenario del laboratorio

En este laboratorio explorarás el acceso condicional MFA, desde la perspectiva de un administrador y un usuario.  Como administrador, crearás una directiva que requerirá que un usuario pase por la autenticación multifactor cuando acceda a cualquier portal de administración de Microsoft.  Desde la perspectiva del usuario, verás el impacto de la directiva de acceso condicional, incluido el proceso para registrarse en MFA.

**Tiempo estimado**: 45 minutos

### Tarea 1

En esta tarea, como administrador, restablecerás la contraseña del usuario Debra Berger.  Este paso es necesario para que puedas iniciar sesión inicialmente como el usuario en tareas posteriores.

1. Abre Microsoft Edge.  En la barra de direcciones, escribe **https://entra.microsoft.com** e inicia sesión con tus credenciales de administrador.
    1. En la ventana de inicio de sesión, escribe **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y selecciona **Siguiente**.
    1. Escribe la contraseña de administrador que debería haberte proporcionado tu proveedor de servicios de hospedaje de laboratorios. Selecciona **Iniciar sesión**.
    1. Según el proveedor de servicios de hosting del laboratorio y, si es la primera vez que inicias sesión en el inquilino, te pedirán que completes el proceso de registro de MFA. Sigue las indicaciones en la pantalla para configurar MFA.
    1. Cuando hayas iniciado sesión, te llevarán a la página Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo, expande **Identidad** y **Users**, luego selecciona **Todos los usuarios**.

1. Selecciona **Debra Berger** de la lista de usuarios.

1. En la parte superior de la página, selecciona **Restablecer contraseña**. Como no has iniciado sesión previamente como Debra Berger, no conoces su contraseña y deberás restablecerla.

1. Cuando se abra la página de restablecimiento de contraseña, selecciona **Restablecer contraseña**.  IMPORTANTE: anota la nueva contraseña, la necesitarás en una tarea posterior para poder acceder como usuario.

1. Cierra la ventana de restablecimiento de contraseña seleccionando la **X** en la esquina superior derecha de la página y, a continuación, cierra la ventana Debra Berger seleccionando la **X** en la esquina superior derecha de la página.

1. En el panel de navegación izquierdo, selecciona **Inicio** para volver al Centro de administración Microsoft Entra.

1. Mantén esta ventana abierta.

### Tarea 2

En esta tarea, recorrerás el proceso de creación de una directiva de acceso condicional en Microsoft Entra ID.

1. Abre una nueva pestaña del explorador con la página principal del Centro de administración Microsoft Entra.   Si ya habías cerrado esta pestaña del explorador, abre Microsoft Edge, escribe **`https://entra.microsoft.com`** en la barra de direcciones y luego inicia sesión con las credenciales de administrador de Microsoft 365 proporcionadas por el ALH.

1. En el panel de navegación izquierdo, asegúrese de que **Entra ID** está expandido, desplácese hacia abajo y seleccione **Acceso condicional**.

1. Se muestra la página de información general sobre el acceso condicional. Cuando llegues a la página de información general, la pestaña **Introducción** aparecerá seleccionada (subrayada). Selecciona la pestaña **Información general**. Aquí verás mosaicos que muestran el resumen de la directiva y las alertas generales.

1. En el panel de navegación izquierdo, seleccione **Directivas** y, a continuación, seleccione **+Nueva directiva**.

1. En el campo Nombre, escribe **Bloquear portales de administración**.

1. En Usuarios, selecciona **0 usuarios y grupos seleccionados**.

1. Ahora verás la opción para incluir o excluir usuarios y grupos.  Asegúrate de que **Incluir** está seleccionado (subrayado).

1. Selecciona la opción **Seleccionar usuarios y grupos** y selecciona **Usuarios y grupos**.  Se abre la ventana para seleccionar usuarios o grupos.  

1. En la barra de búsqueda, escribe **Debra**.  Selecciona **Debra Berger** debajo de la barra de búsqueda y presiona el botón **Seleccionar** en la parte inferior de la página.  Ten en cuenta que una práctica habitual es asignar la directiva a los usuarios de un grupo.  Para agilizar este laboratorio, asignaremos la directiva a un usuario específico.

1. En Recursos de destino, selecciona **No se ha seleccionado ningún recurso de destino**.

1. En el campo debajo de donde dice**Seleccionar lo que se aplica a esta directiva**, selecciona la flecha hacia abajo y anota las opciones disponibles.  Mantenga la configuración predeterminada, **Recursos (anteriormente Aplicaciones de nube)**.  Asegúrate de que la pestaña **Incluir** está subrayada.  Elija **Seleccionar recursos** y, a continuación, debajo, donde dice **Seleccionar**, seleccione **Ninguno**.  Se abre la ventana para seleccionar aplicaciones en la nube.

1. Selecciona **Portales de administración de Microsoft** y después haz clic en **Seleccionar** en la parte inferior de la página.  Observa la advertencia.  

1. En Red, selecciona **Cualquier red o ubicación**.  Revisa las opciones, pero no selecciones ninguna opción.

1. En Condiciones, selecciona **0 condiciones seleccionadas**.  Observa las distintas opciones que puedes configurar.  A través de la directiva, puedes controlar el acceso de los usuarios en función de las señales de las condiciones, incluidas: riesgo de usuario, riesgo de inicio de sesión, plataforma de dispositivo, ubicación, aplicaciones cliente o filtro para dispositivos.  Explora estas opciones configurables, pero no establezcas ninguna condición.

1. Ahora se establecerán los controles de acceso.  En Conceder, selecciona **0 controles seleccionados**.

1. Se abre la ventana Conceder.  Seleccione **Bloquear acceso**. Pulsa **Seleccionar** al final de la página.

1. En la parte inferior de la página, en Habilitar directiva, selecciona **Activado** y luego selecciona **Crear**.

1. En el panel de navegación, selecciona **Directivas**. La directiva **Bloquear portales de administración** que acabas de crear debe aparecer en la lista de directivas de acceso condicional (si es necesario, selecciona el **icono Actualizar** en la barra de comandos de la parte superior de la página).

1. Para cerrar la sesión selecciona el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y selecciona **Cerrar sesión**. A continuación, cierra todas las ventanas del navegador.

### Tarea 3

En esta tarea verás el impacto de la directiva de acceso condicional, desde la perspectiva del usuario, Debra Berger. En primer lugar, iniciarás sesión en una aplicación que no esté incluida en la directiva de acceso condicional (el portal de Microsoft 365 en https://login.microsoftonline.com)).  Luego repetirás el proceso en una aplicación que esté incluida en la directiva de acceso condicional (Azure Portal en https://portal.azure.com)).  Recuerda que la directiva bloquea el accesso a cualquiera de los portales de administración de Microsoft, incluido Azure Portal.  NOTA: por motivos de seguridad, todas las cuentas de usuario que acceden a cualquier portal deben usar MFA.  El requisito de MFA es independiente de este ejercicio de laboratorio.

1. Abre Microsoft Edge.  En la barra de direcciones, escribe **https://login.microsoftonline.com**.
    1. Inicia sesión como **DebraB@WWLxZZZZZZ.onmicrosoft.com**, (donde ZZZZZZ es el identificador de inquilino único proporcionado por el proveedor de hospedaje del laboratorio) y después selecciona **Siguiente**.
    1. Escribe la contraseña que anotaste en la tarea anterior. Selecciona **Iniciar sesión**.
    1. Dado que, como administrador, restableciste la contraseña, esta es temporal y, por tanto, deberás actualizarla. Escribe la contraseña actual y, a continuación, escribe una nueva contraseña y confírmala.  Toma nota de la nueva contraseña, ya que la necesitarás para completar la tarea.
    1. Dado que esta es la primera vez que inicias sesión como Debra Berger, es posible que se te pida configurar MFA. Sigue las indicaciones en la pantalla para configurar MFA.
    1. Cuando aparezca un mensaje para preguntarte si quieres mantener la sesión iniciada, selecciona **Sí**.  Deberías haber iniciado sesión correctamente en tu cuenta de Microsoft 365.

1. Ahora intentarás iniciar sesión en una aplicación que cumpla con los criterios de la directiva de acceso condicional. Abre una nueva pestaña del explorador y escribe **https://portal.azure.com**, que es el portal de administración de Azure.  Aparece una ventana emergente que indica "No tienes acceso a esto".  Este es el resultado de la directiva de acceso condicional que te bloquea el acceso a todos los portales de administración de Microsoft.

1. Para cerrar la sesión selecciona el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y selecciona Cerrar sesión. A continuación, cierra todas las ventanas del navegador.

### Revisar

En este laboratorio, aprendiste el proceso de configuración de una directiva de acceso condicional que bloquea el acceso a los portales de administración de Microsoft a todos los usuarios incluidos en la directiva.  A continuación, experimentaste como usuario el impacto de la directiva de acceso condicional al acceder a Azure Portal.
