<a name="---"></a><!---
---
Laboratorio: Título "Exploración de la gobernanza de identidades en Azure AD con Privileged Identity Management" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de Azure Active Directory (Azure AD), parte de Microsoft Entra; Módulo 4: Descripción de las funcionalidades de gobernanza y protección de identidades de Azure AD; Unidad 4: Descripción de las funcionalidades de Privileged Identity Management"
---
--->

# <a name="lab-explore-identity-governance-in-azure-ad-with-privileged-identity-management"></a>Laboratorio: Explore identity governance in Azure AD with Privileged Identity management

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Azure Active Directory (Azure AD), parte de Microsoft Entra
- Módulo: Descripción de las funcionalidades de gobernanza y protección de identidades de Azure AD
- Unidad: Descripción de las funcionalidades de Privileged Identity Management

## <a name="lab-scenario"></a>Escenario del laboratorio

En este laboratorio, explorará algunas de las funcionalidades básicas de Privileged Identity Management (PIM). PIM requiere Azure AD Premium P2.  En este laboratorio, como administrador, configurará uno de sus usuarios, Diego Siciliani, con un rol de administrador de usuarios de Azure AD, a través de Priviledged ID Management (PIM).   Gracias a los privilegios de administrador de usuarios, Diego podrá crear usuarios y grupos, administrar licencias y mucho más.  Tanto el administrador como el usuario, Diego, deben tener configurada la licencia de Azure AD Premium P2.

**Tiempo estimado**: 45-60 minutos

### <a name="task-1"></a>Tarea 1

En esta tarea, como administrador, restablecerá la contraseña del usuario Diego Siciliani. Este paso es necesario para poder iniciar sesión como el usuario en las siguientes tareas.

1. Abrir Microsoft Edge.  En la barra de direcciones escriba **portal.azure.com**.

2. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

3. Seleccione **Azure Active Directory**.  

4. En el panel de navegación izquierdo, seleccione **Usuarios**.

5. Seleccione **Diego Siciliani** de la lista de usuarios.

6. Seleccione **Restablecer contraseña** en la parte superior de la página. Como no ha iniciado sesión previamente como Diego Siciliani, no conoce su contraseña y deberá restablecerla.

7. Cuando se abra la ventana de restablecimiento de contraseña, seleccione **Restablecer contraseña**.  IMPORTANTE: Anote la nueva contraseña, la necesitará en una tarea posterior para poder acceder como usuario.

8. Cierre la ventana de restablecimiento de contraseña con la **X** de la esquina superior derecha de la página.

9. Cierre la ventana Perfil de Diego con la **X** de la esquina superior derecha de la página.

10. Cierre la ventana Todos los usuarios con la **X** de la esquina superior derecha de la página. Ahora debería estar en la página Contoso Azure Active Directory.

11. Mantenga abierta la ventana del navegador, la necesitará en la siguiente tarea.

### <a name="task-2"></a>Tarea 2

En esta tarea, como administrador, asignará a Diego un rol de Azure AD en Privileged Identity Management.

1. Vaya a la pestaña abierta del navegador etiquetada como Contoso – Microsoft Azure.   Si ha cerrado la pestaña del navegador, abra Microsoft Edge, en la barra de direcciones, escriba portal.azure.com, inicie sesión con sus credenciales de administrador y seleccione Azure Active Directory.  

2. En el panel de navegación izquierdo, seleccione **Gobierno de identidades**.

3. En el panel de navegación izquierdo, en Privileged Identity Management, seleccione **Roles de Azure AD**.

4. Ahora está en la ventana Inicio rápido de Privileged Identity Management.  Seleccione **Administrar**.

5. Ahora está en la página Roles de Contoso.  En la barra de búsqueda de la parte superior de la página, escriba **usuario**.  En los resultados de la búsqueda, seleccione  **Administrador de usuarios**.

6. En la parte superior de la página, seleccione **+ Asignaciones**.

7. En la página Agregar asignaciones, asegúrese de que **Pertenencia** esté subrayado.  Aquí se configuran los ajustes de pertenencia al rol de administrador de usuarios en PIM.

8. Deje el Tipo de ámbito en su valor predeterminado, Directorio.  

9. En Seleccionar miembros, seleccione **No hay miembros seleccionados**. Se abrirá la ventana Seleccionar un miembro.

10. En la barra de búsqueda, escriba **Diego**.  En los resultados de la búsqueda, seleccione **Diego Siciliani** y luego pulse **Seleccionar** en la parte inferior de la página.  

11. En Seleccionar miembros verá 1 miembro seleccionado y el nombre y correo electrónico del miembro seleccionado, Diego Siciliani. En la parte inferior de la página Agregar asignaciones, seleccione **Siguiente**.  

12. Ahora está en la página Configuración.  Deje el Tipo de asignación en su valor predeterminado, Apto.

13. Si el cuadro Elegibilidad permanente está marcado, seleccione **Elegibilidad permanente**, para desmarcarlo.

14. En los campos Inicio de la asignación, mantenga la fecha y hora predeterminadas, que son la fecha de hoy y la hora actual.

15. En los campos Fin de asignación, cambie la fecha por la de hoy (tenga en cuenta que la configuración predeterminada es de un año a partir de hoy, por lo que debe cambiar el año). En la hora, establezca la hora a dos horas más tarde de la hora actual. Cuando establezca el campo de la hora para la hora de finalización de la Asignación, pulse el tabulador de su teclado y seleccione **Asignar** en la parte inferior de la página.  

16. Esto le llevará de vuelta a la ventana Asignaciones.  Tras unos segundos, debería ver Diego Siciliani en la tabla del Administrador de usuarios, junto con los detalles de la asignación. Si después de unos segundos sigue sin ver la actualización, seleccione **Actualizar** en la parte superior de la página.

17. En la parte superior de la página, seleccione **Configuración**.

18. En los Detalles de configuración de rol para el Administrador de usuarios, observe las diferentes opciones.  Observe que la configuración de "Requerir justificación en las activaciones" está establecida en sí, y "Durante la activación, requerir Azure MFA" también está establecida en sí.  Verá ambas cosas en la siguiente tarea cuando Diego active el rol.  Tenga en cuenta también que "Solicitud de aprobación para activar" está establecido en No.  Deje toda la configuración en sus valores predeterminados.  Cierre la página con la **X** de la esquina superior derecha de la pantalla.

19. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador.

### <a name="task-3"></a>Tarea 3

En esta tarea, iniciará sesión en Azure Portal como Diego Siciliani, para acceder a la funcionalidad Privileged Identity Management de Azure Active Directory para activar su asignación como Administrador de usuarios.  Una vez activada, realizará algunos cambios de configuración en un usuario existente. Nota: Para esta tarea necesitará tener acceso a un dispositivo móvil al que tenga acceso inmediato y donde pueda recibir mensajes de texto.

1. Abrir Microsoft Edge.  En la barra de direcciones del explorador, escriba **portal.azure.com**.

1. Inicie sesión como Diego Siciliani.
    1. En la ventana de inicio de sesión, escriba **DiegoS@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña temporal que anotó en la tarea anterior y seleccione **Iniciar sesión**.  Haga clic en **Iniciar sesión**.
    1. Como la contraseña que escribió era temporal, deberá actualizarla ahora. Escriba la contraseña actual.  En los campos de nueva contraseña y confirmar contraseña, escriba **SC900-Lab**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. Ahora debería iniciar sesión correctamente en Azure Portal.
1. En la página principal, en servicios de Azure, seleccione **Azure Active Directory**.
1. En el panel de navegación izquierdo, seleccione **Gobierno de identidades**.
1. En el panel de navegación izquierdo, en Privileged Identity Management, seleccione **Roles de Azure AD**.
1. En el panel de navegación izquierdo, seleccione **Mis roles**.  Ahora verá la información de sus roles de Azure AD.  Verá que a usted, Diego, se le asignó el rol de Administrador de usuarios.  
1. En la última columna de la tabla, etiquetada como acción, seleccione **Activar**.
1. Verá un icono de advertencia que indica que se necesita verificación adicional.  Seleccione **Haga clic para continuar**.  Recuerde que la configuración del PIM para el Rol de administrador de usuarios requiere una autenticación multifactor.  Además, como la información de contacto de Diego para su uso con la MFA (métodos de autenticación) aún no estaba configurada, deberá registrar su información para poder utilizar la MFA.  Aunque deberá hacer la MFA cada vez que se registre como usuario administrador, durante el período de asignación, el proceso de registro de la MFA se requerirá solo una vez.
1. Se le notificará que se necesita más información, seleccione **Siguiente**.
1. Escriba su contraseña, **SC900-Lab**.
1. En la parte inferior izquierda de la ventana Microsoft Authenticator, seleccione **Quiero configurar otro método**.
1. Se le solicitará que seleccione otro método.  Al lado de Aplicación Authenticator, seleccione la tecla con la flecha hacia abajo.   Seleccione **Teléfono** y luego **Confirmar**.
1. Se le solicitará que escriba un número de teléfono que le gustaría utilizar. Asegúrese de que el código de país o región de su número de teléfono sea correcto.  Escriba su número de teléfono, asegúrese de que esté seleccionada la opción **Enviarme un código por mensaje de texto** y luego seleccione **Siguiente**.
1. Escriba el código de seis dígitos que recibió y seleccione **Siguiente**.
1. Verá una notificación que dice que el teléfono se ha registrado correctamente. Seleccione **Siguiente** y luego **Listo**.
1. Se le preguntará si quiere mantener la sesión iniciada.  Seleccione **Sí**.
1. Aparecerá la ventana Activar el administrador de usuarios.  Se le solicitará que escriba el motivo de la activación.  En el cuadro que aparece, escriba el motivo que desee (máximo 500 caracteres) y luego seleccione **Activar**.
1. Verá el estado (tres etapas del progreso), mientras se procesa la activación.
1. Una vez completada la activación, volverá a abrirse la página Mis roles | Roles de Azure AD, donde verá una notificación que indica que ha activado un rol.  Seleccione **Haga clic aquí** para ver sus roles activos.  Si observa que la hora de finalización es diferente a la configurada, seleccione la tecla de actualización en la parte superior de la página (puede tardar unos minutos en actualizarse).
1. Cierre la ventana con la **X** de la esquina superior derecha de la pantalla.
1. Para cerrar la ventana Privileged Identity Management | Inicio rápido, seleccione la **X** en la esquina superior derecha de la pantalla.
1. Cierre la ventana Gobierno de identidades con la **X** de la esquina superior derecha de la pantalla.
1. Ahora debería estar en la página Contoso Azure Active Directory.  Como administrador de usuarios de Azure AD puede crear usuarios y grupos, administrar licencias y mucho más.   En el panel de navegación izquierdo, seleccione **Usuarios**.
1. En la lista de usuarios, seleccione **Bianca Pisani**.
1. En el panel de navegación izquierdo seleccione **Licencias**.
1. Verá que Bianca no tiene licencias asignadas.  En la parte superior de la página, seleccione **+ Asignaciones**.
1. En la lista de selección de licencias, seleccione **Office 365 E3** y **Windows 10 Enterprise E3**.
1. En la parte inferior de la página, seleccione **Guardar**.  Verá una breve notificación en la parte superior derecha de la página que indica que las licencias se asignaron correctamente.
1. Cierre la página de asignación de licencias actualizada con la **X** de la esquina superior derecha de la pantalla.
1. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador.
1. La duración del rol de administrador de usuarios está limitada al tiempo configurado.

### <a name="review"></a>Revisar

En este laboratorio exploró la PIM.  Como administrador, configuró el usuario de Diego con privilegios de administrador de usuarios durante un tiempo determinado.  Luego, como Diego, aprendió el proceso de activación de los privilegios de administrador de usuarios y la configuración de los usuarios.  Recuerde que la PIM requiere una licencia de Azure AD Premium P2.
