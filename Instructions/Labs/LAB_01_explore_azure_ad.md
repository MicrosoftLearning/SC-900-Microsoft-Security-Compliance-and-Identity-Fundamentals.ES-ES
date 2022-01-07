---
lab:
    title: 'Explorar Azure Active Directory'
    module: 'Módulo 2, lección 1: Describir las funcionalidades de las soluciones de administración de identidades y acceso de Microsoft: Explorar los servicios y tipos de identidad de Azure AD'
---

# Laboratorio: Explorar Azure Active Directory

## Escenario del laboratorio

En este laboratorio accederá a Azure Active Directory.  Además, creará un usuario y establecerá la configuración, que incluye agregar licencias.  



**Tiempo estimado**: 10-15 minutos

#### Tarea 1:  Como es suscriptor de Microsoft 365, ya utiliza Azure AD.  En esta tarea, aprenderá cómo acceder a Azure AD a través del portal de administración de Microsoft 365 y a través de Azure Portal.

1. Abra Microsoft Edge.

2. En la barra de direcciones escriba **admin.microsoft.com** para acceder al Centro de administración de Microsoft 365.

3. Inicie sesión con sus credenciales de administrador. 
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

4. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

5. En Centros de administración, seleccione **Azure Active Directory** (es posible que deba desplazarse hacia abajo).  Se abrirá una nueva página del navegador con la página Mi panel del Centro de administración de Azure Active Directory. En las ventanas principales del panel, verá varios iconos, incluido el icono de identidad de la organización (Contoso, el inquilino y la edición de Azure AD), un icono para usuarios y grupos, y más.

6. En el panel de navegación izquierdo, en favoritos, seleccione **Azure Active Directory**.  En la ventana principal verá otro panel de navegación que enumera todos los servicios que están disponibles en Azure AD. A la derecha, verá información sobre el inquilino de Contoso y vínculos a los tipos de identidad que puede crear y a los servicios destacados.  

7. Ahora abra una nueva ventana del navegador y, en la barra de direcciones, escriba **portal.azure.com**.  Como ya ha iniciado la sesión como admin@WWLxZZZZZZ.onmicrosoft.com y originalmente utilizó esas mismas credenciales para canjear su pase para Azure, debería iniciar sesión como administrador cuando acceda a Azure Portal.  Puede comprobarlo al revisar su correo electrónico en la esquina superior derecha de la página y pasar el ratón por encima del icono del usuario.

8. La página principal de Azure Portal muestra los servicios de Azure, incluidos Azure Active Directory, VM, cuentas de almacenamiento, bases de datos y mucho más.  Seleccione **Azure Active Directory**.  

9. Verá el Azure Active Directory para su inquilino de Microsoft 365 Contoso.    Sea cual sea el método que utilice para acceder a los servicios de Azure Active Directory (el portal de administración de Microsoft 365 o Azure Portal), acabará en el mismo lugar: el Contoso Azure Active Directory, donde podrá administrar todos los servicios de Azure AD.

10. Mantenga esta página del navegador abierta para la siguiente tarea.


#### Tarea 2:  En esta tarea, aprenderá cómo crear un nuevo usuario en Azure Active Directory y explorará algunos de los servicios que se pueden administrar como usuario.

1. Vaya a la pestaña de Microsoft Azure: Contoso que hay abierta en su explorador. Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba portal.azure.com y seleccione Azure Active Directory.  Debería haber iniciado sesión como administrador en Azure Portal; si no es así, vuelva a iniciar sesión.

2. En el panel de navegación izquierdo, seleccione **Usuarios**.  Verá que su inquilino ya está configurado con usuarios.

3. Seleccione **+ Nuevo usuario** en la parte superior de la página.

4. **Crear usuario** ya debería estar seleccionado, si no es así, seleccione esa opción.

5. Rellene los campos de **Identidad** como se indica a continuación:

    1. Nombre de usuario: **sara**.

    2. Campo del nombre: **Sara Pérez**.

    3. Nombre: **Sara**.

    4. Apellido: **Pérez**.

6. Rellene los campos de **Contraseña** como se indica a continuación:

    1. Seleccione **Permitirme crear una contraseña**.

    1. Contraseña inicial: **Naja8996**. Cuando Sara se registre por primera vez, se le solicitará que cambie su contraseña.

7. Configurar **Grupos y roles**.

    1. Junto a Grupos, seleccione **0 grupos seleccionados**.  Esto muestra los grupos disponibles.  Observe la lista de grupos disponibles.

    2. Seleccione **Operaciones**, es posible que deba desplazarse hacia abajo, luego pulse **Seleccionar**. Observe cómo el texto junto a Grupos se ha actualizado para reflejar 1 grupo seleccionado.  

    3. Junto a Roles, seleccione **Usuario**. Aparece la lista de roles del directorio.  Desplácese hacia abajo para ver los distintos roles integrados, para ver los distintos roles, pero no cambie el rol del usuario.  Cierre esta ventana con la **X** de la esquina superior derecha de la página.

8. Definir la **Configuración**

    1. Bloquear el inicio de sesión:  **No** (dejar la configuración predeterminada).

    1. Ubicación de uso: **Estados Unidos** (seleccione el desplegable y luego desplácese hacia abajo para encontrar esta opción).  Es necesario configurar la ubicación de uso para asignar las licencias.

9. En la parte inferior de la página, seleccione el botón **Crear**.

10. Compruebe que el usuario aparece en la lista de usuarios (los nombres aparecen en orden alfabético).

11. En la lista de usuarios seleccione el usuario que acaba de crear, **Sara Pérez**.  Se abrirá la página del perfil.

12. El panel de navegación izquierdo muestra las opciones que se pueden configurar para el usuario.  Seleccione **Grupos**.  Aquí puede ver información adicional sobre el grupo.  Compruebe que el grupo de operaciones aparece en la lista (la asignación del grupo puede tardar varios minutos en aparecer).  Nota:  También verá el grupo Contoso, aunque solamente asignamos un grupo cuando creamos el usuario.  Esto se debe a una directiva preconfigurada en el inquilino, que asigna automáticamente los usuarios nuevos al grupo Contoso.

13. En el panel de navegación izquierdo, seleccione **Licencias**.  Observe que no se ha encontrado ninguna asignación de licencia para este usuario.  

14. Para agregar una licencia seleccione **+ Asignaciones** en la parte superior de la ventana principal.

15. En Seleccionar licencias, seleccione **Office 365 E3** y **Windows 10 Enterprise E3** y luego seleccione el botón **Guardar** en la parte inferior de la pantalla. En la esquina superior derecha de la pantalla debería aparecer una notificación que indique que la asignación de licencias se ha realizado con éxito.

16. Seleccione la **X** de la esquina superior derecha de la pantalla para cerrar la ventana Asignación de licencias.

17. Seleccione el **icono de Actualizar** en la parte superior de la página para confirmar la asignación de licencias.

18. Para volver a la página Contoso Overview Azure Active Directory, seleccione **Contoso** en la parte superior izquierda de la pantalla (la ruta de navegación), encima de Sara Pérez | Licencias.

19. Ha creado y configurado correctamente un usuario en Azure Active Directory.

20.	Para cerrar sesión de todas las pestañas del navegador, haga clic en el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla. A continuación, cierre todas las ventanas del navegador.

#### Tarea 3:  En esta tarea, iniciará sesión como Sara Pérez por primera vez.

1. Abra Microsoft Edge.

2. En la barra de direcciones escriba **login.microsoft.com**.

3. Inicie sesión como **sara@WWLxZZZZZ.onmicrosoft.com**, (donde ZZZZZZ es su ID de inquilino única ofrecida por su proveedor de hospedaje de laboratorio).

4. Escriba la contraseña temporal **Naja8996**.

5. Luego, se le solicitará actualizar su contraseña. En el campo Contraseña actual, escriba **Naja8996**.

6. En el campo Contraseña nueva, escriba **SC900-Lab**.  En el campo Confirme su contraseña, escriba SC900-Lab y seleccione Iniciar sesión. Nota: Como procedimiento recomendado, se debería utilizar una contraseña más segura. Elegiremos esta contraseña por conveniencia y solo para el propósito de este laboratorio.

7. Ahora, habrá iniciado sesión correctamente en Microsoft 365.

8. Para **Cerrar sesión** de todas las pestañas del navegador, haga clic en el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla. A continuación, cierre todas las ventanas del navegador.



#### Revisión
En este laboratorio, empezó su exploración inicial de Azure AD. Dado que los suscriptores de Microsoft 365 utilizan automáticamente Azure AD, comprobó que puede acceder a las características y servicios de Azure AD a través del portal de administración de Microsoft 365 o a través de Azure Portal.  Sea cual sea el método que prefiera para llegar al mismo lugar.  También aprendió el proceso de creación de un nuevo usuario y las configuraciones diferentes que se pueden establecer, incluidos los grupos a los que se puede asignar el usuario, la disponibilidad de roles y la asignación de licencias de usuario.


