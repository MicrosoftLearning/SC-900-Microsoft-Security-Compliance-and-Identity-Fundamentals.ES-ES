---
Pre-Demo Setup:
    title: 'Configuración de la demo'
---

# Configuración de la demo previa

### Configuración, parte 1: Canjear Pase para Azure
En esta tarea de configuración, canjeará su Pase para Azure con las mismas credenciales que las de su inquilino de Microsoft 365.  Esto hará que la experiencia no se interrumpa al moverse entre Microsoft 365 y Azure.

1. Si tiene alguna ventana del explorador abierta, se recomienda que las cierre.

1. Haga clic con el botón derecho en el icono de Microsoft Edge y seleccione **Nueva ventana InPrivate** para abrir una nueva sesión InPrivate del explorador. Otros 

1. En la barra de direcciones, escriba **www.microsoftazurepass.com**.  

1. Seleccione el botón **Empezar** para empezar.

    1. En la ventana de inicio de sesión, escriba la dirección de correo electrónico **admin@WWLxZZZZZZ.onmicrosoft.com** (ZZZZZZ será el id. de inquilino único que le dio el proveedor de hospedaje del laboratorio) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**. Si se le pide que mantenga la sesión, seleccione **Sí**.
    1. Seleccione **Confirmar cuenta de Microsoft** si la dirección de correo electrónico que aparece es la correcta.
    1. Escriba el código de promoción en el cuadro Código de promoción y haga clic en **Reclamar código de promoción**.  
    1. En la página Su perfil, deje toda la información predeterminada, seleccione **Acepto el acuerdo de suscripción, los detalles de la oferta y la declaración de privacidad.** y luego seleccione **Inscribirme**.
    1. Si se abre una ventana de encuesta, puede cerrarla con la **X** o responder según corresponda y seleccionar **Enviar**.

1. La activación de la cuenta puede tardar unos minutos.  Una vez activada, se le dirigirá a la página principal de Azure Portal. Se abrirá la ventana Bienvenido a Microsoft Azure, seleccione **Quizás más tarde** . Es posible que aparezca una ventana emergente en la que ponga “Optimice las cargas de trabajo en la nube con recomendaciones personalizadas”; seleccione la **X** en la esquina superior derecha de la ventana.

1. Deje abierta la pestaña del explorador con la página principal de Azure Portal, a la que volverá en la siguiente demostración.

### Configuración, parte 2: Habilitar el registro de auditoría de Microsoft 365
En esta tarea de configuración, habilitará la funcionalidad Registro de auditoría de Microsoft 365.  Aunque la documentación indica que el registro de auditoría está habilitado de manera predeterminada, la mayoría de los inquilinos del laboratorio no tienen habilitada esta función y pueden pasar varias horas hasta que surta efecto.  Habilitar esta función resulta útil, ya que Microsoft 365 utiliza los registros de auditoría para conseguir información sobre los usuarios y las actividades identificadas en las directivas y los análisis.

1. Abra Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del Centro de cumplimiento de Microsoft 365.  

1. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, seleccione **Mostrar todo**.

1. En el panel de navegación izquierdo, en Soluciones, seleccione **Auditoría**.  Nota: la funcionalidad Auditoría también es accesible a través de la página principal de Microsoft 365 Defender.

1. Compruebe que la pestaña **Buscar** está seleccionada (subrayada).

1. Cuando llegue a la página Auditoría, espere entre 2 y 3 minutos.  Si Auditoría NO está habilitada, verá una barra azul en la parte superior de la página donde pone "Comenzar a registrar la actividad del usuario y del administrador".  Seleccione **Iniciar el registro de la actividad de usuarios y administradores**.  Una vez que la auditoría esté habilitada, la barra azul desaparecerá.  Si la barra azul no aparece, eso significará que la opción Auditoría ya está habilitada, y no necesitará hacer nada más.

1. Para volver a la página principal del centro de cumplimiento de Microsoft 365, seleccione **Inicio** en el panel de navegación izquierdo.

### Revisión

En esta configuración, ha canjeado su Pase para Azure con las mismas credenciales que las de su inquilino de Microsoft 365.  También ha habilitado la funcionalidad Informe de auditoría de Microsoft 365.


