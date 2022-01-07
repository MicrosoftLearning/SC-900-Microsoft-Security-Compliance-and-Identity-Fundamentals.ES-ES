---
lab:
    title: 'Explorar la autenticación de Azure AD con el autoservicio de restablecimiento de contraseña de Azure AD'
    module: 'Módulo 2, lección 2: Describir las funcionalidades de las soluciones de administración de identidades y acceso de Microsoft: Describir los distintos métodos de autenticación de Azure AD'
---

# Laboratorio: Explorar la autenticación de Azure AD con el autoservicio de restablecimiento de contraseña de Azure AD

## Escenario del laboratorio

En este laboratorio, como administrador, aprenderá el proceso para habilitar el autoservicio de restablecimiento de contraseña. Cuando el SSPR esté habilitado, asumirá el rol de un usuario y pasará por el proceso de registrarse en el SSPR y también de restablecer su contraseña.  Por último, como administrador, podrá ver los registros de auditoría y los datos de uso e información del SSPR.

**Tiempo estimado**: 15-20 minutos


#### Tarea 1:  En esta tarea, como administrador, agregará un usuario existente, Adele Vance, al grupo SSPRSecurityUsers.  También deberá restablecer la contraseña del usuario para que pueda iniciar sesión por primera vez, como usuario, y registrarse en el SSPR.

1. Abra Microsoft Edge.

2. En la barra de direcciones, escriba **portal.azure.com** e inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

3. Seleccione **Azure Active Directory**.  

4. En el panel de navegación izquierdo, seleccione **Grupos**.

5. Se mostrará una lista de grupos existentes. En el campo Buscar grupos, escriba **SSPR**, a continuación, en los resultados de la búsqueda, seleccione **SSPRSecurityGroupUsers**.  Le llevará a la configuración de este grupo.

6. En el panel de navegación izquierdo, seleccione **Miembros**.

7. En la parte superior de la página, seleccione **+ Agregar miembros**.  

8. En el cuadro de búsqueda, escriba **Adele**.  Cuando el usuario **Adele Vance** aparezca debajo del cuadro de búsqueda, selecciónelo y pulse **Seleccionar** en la parte inferior de la página.

9. Cierre la ventana SSPRSecurityUsers con la **X** de la esquina superior derecha de la pantalla.

10. Para volver a la página Active Directory, seleccione **Contoso** en la esquina superior izquierda de la pantalla, justo encima de Grupos y volverá a la página Contoso Azure Active Directory.

11. En el panel de navegación izquierdo, seleccione **Usuarios**.

12. Seleccione **Adele Vance** de la lista de usuarios.

13. Seleccione **Restablecer contraseña** en la parte superior de la página. Como no ha iniciado sesión previamente como Adele Vance, deberá restablecer la contraseña.

14. Cuando se abra la ventana de restablecimiento de contraseña, seleccione **Restablecer contraseña**.  IMPORTANTE: Anote la nueva contraseña, la necesitará en una tarea posterior para poder acceder como usuario.

15. Cierre la ventana de restablecimiento de contraseña con la **X** de la esquina superior derecha de la página.

16. Cierre la ventana Adele Vance con la **X** de la esquina superior derecha de la página.

17. Cierre la ventana Usuarios con la **X** de la esquina superior derecha de la página.

18. Mantenga abierta la ventana Contoso Overview, la usará en la siguiente tarea.

#### Tarea 2: En esta tarea, como administrador, aprenderá a configurar el restablecimiento de contraseña para los usuarios, incluida la configuración de los tipos de métodos de autenticación a utilizar.

1. Vaya a la pestaña de Microsoft Azure: Contoso que hay abierta en su explorador. Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba portal.azure.com y seleccione Azure Active Directory.  Debería haber iniciado sesión como administrador en Azure Portal; si no es así, vuelva a iniciar sesión.

2. En el panel de navegación izquierdo, seleccione **Restablecer contraseña**.  

3. Se mostrarán las propiedades para el autoservicio de restablecimiento de contraseñas.  Asegúrese de que el **autoservicio de restablecimiento** está **seleccionado** para el grupo que aparece en la lista, el **SSPRSecurityUsers**.  Coloque el cursor sobre el icono de información junto a "seleccionar grupo" y observe lo que dice: "Defina el grupo de usuarios a los que se permite restablecer sus propias contraseñas". Debe incluir usuarios en el grupo. No puede seleccionar usuarios de forma individual.  Además, si cambia el grupo, el grupo que seleccione reemplazará al grupo que aparezca en la lista en ese momento.  Por lo tanto, se recomienda que simplemente agregue los usuarios al grupo del SSPR.  Por último, observe el cuadro de información azul: "Esta configuración solo se aplica a los usuarios finales de su organización. Los administradores siempre están habilitados para el autoservicio de restablecimiento de contraseña y deben utilizar dos métodos de autenticación para restablecer su contraseña".

5. En el panel de navegación izquierdo de restablecimiento de contraseña, seleccione **Métodos de autenticación**.

6. En Número de métodos requeridos para el restablecimiento, seleccione **1**. Observe el cuadro de información de la pantalla.

7. Observe los diferentes métodos disponibles para los usuarios.  **Correo electrónico** y **Teléfono móvil (solo SMS)** ya deberían estar marcados; si no es así, selecciónelos.

8. En el panel de navegación izquierdo de restablecimiento de contraseña, seleccione **Registro**.  

9. Asegúrese de que la opción Exigir a los usuarios que se registren al iniciar sesión esté establecida a **Sí**.  Deje el Número de días antes de que se solicite a los usuarios que vuelvan a confirmar su información de autenticación, en el valor predeterminado 180.   Observe el cuadro de información de la página.

10. En el panel de navegación izquierdo de restablecimiento de contraseña, seleccione **Notificaciones**.  

11. Asegúrese de que la opción Notificar a los usuarios los restablecimientos de contraseña esté establecida a **Sí**.  Deje la configuración Notificar a todos los administradores cuando otros administradores restablezcan su contraseña en No.

12. Observe que el panel de navegación de Restablecimiento de contraseña también incluye opciones para ver registros de auditorías y Uso e información.

13. Para **Cerrar sesión** de todas las pestañas del navegador, haga clic en el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla. A continuación, cierre todas las ventanas del navegador.


#### Tarea 3:  En esta tarea, como el usuario Adele Vance, aprenderá el proceso de registro para el autoservicio de restablecimiento de contraseña.  Esta tarea requiere que tenga acceso a un dispositivo móvil donde pueda recibir mensajes de texto o una cuenta de correo electrónico personal a la que pueda acceder.
 
1. Abra Microsoft Edge.

2. En la barra de direcciones escriba **login.microsoftonline.com**.

3. Inicie sesión como Adele Vance.
    1. En la ventana Inicio de sesión escriba **AdedleV@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es su ID de inquilino única ofrecida por su proveedor de hospedaje de laboratorio) y luego seleccione **Siguiente**.
    1. Escriba la contraseña que anotó en la tarea anterior. Seleccione **Iniciar sesión**.
    1. Si se le pregunta si quiere mantener la sesión iniciada, seleccione **Sí**

4. Como no ha iniciado sesión previamente como Adele Vance, se le solicitará que restablezca su contraseña..  Escriba su contraseña antigua.  Como contraseña nueva escriba **SC900-Lab**. Escriba **SC -900** en el campo para confirmar la contraseña.  Seleccione **Iniciar sesión**. Nota: Utilizamos esta contraseña solo para porque es práctica para el laboratorio. Como procedimiento recomendado, normalmente se utiliza una contraseña más segura.

5. Aparecerá una ventana emergente que indica que se requiere más información.  Esto se debe a que, como miembro del grupo SSPRSecurityUsers, la configuración requiere que sus miembros se registren cuando inician sesión. Seleccione el botón **Siguiente**.  Nota:  Una alternativa a que los usuarios hagan el registro por sí mismos es que los administradores configuren directamente los métodos de autenticación cuando agregan a un usuario. Esto requiere que los administradores conozcan y establezcan los números de teléfono y las direcciones de correo electrónico que utilizan los usuarios para realizar el autoservicio de restablecimiento de contraseña, y para restablecer la contraseña de un usuario.

6. Se abrirá la página "Garantizar la seguridad de la cuenta".  La ventana que aparece es para el método de autenticación por teléfono, si no tiene un dispositivo móvil con usted que pueda recibir mensajes de texto, pase al siguiente paso.  Se le solicita que escriba un número de teléfono. Asegúrese de que la opción **Enviarme un código por mensaje de texto** esté activada.   Escriba un número de teléfono donde pueda recibir un código de texto y seleccione el **botón Siguiente**.  Se abrirá una nueva ventana que indica que se acaba de enviar un código al teléfono que escribió.  Escriba el código que recibió y seleccione **Siguiente**. Se abrirá una ventana de confirmación que muestra su método de inicio de sesión predeterminado.  Seleccione **Listo**.  

7. Omita este paso si pudo configurar el SSPR con su número de teléfono móvil.  También puede configurar un método diferente como se muestra en la parte inferior izquierda de la ventana.  Si elige configurar un método diferente, seleccione **Quiero configurar otro método**, aparecerá una ventana emergente que le pregunta ¿Qué método quiere usar?  En el menú desplegable, seleccione su método preferido, **Correo electrónico**, y luego seleccione el botón **Confirmar**.  Escriba la dirección de correo electrónico que desea utilizar y seleccione **Siguiente**.  Se abrirá una nueva ventana que indica que se acaba de enviar un código al correo electrónico que escribió.  Acceda al correo electrónico para conseguir el código.  Escriba el código que recibió y seleccione **Siguiente**. Se abrirá una ventana de confirmación que muestra su método de inicio de sesión predeterminado.  Seleccione **Listo**.

8. Ahora puede completar su inicio de sesión. Debería estar en la página principal de Azure Portal.  Si su tiempo de inicio de sesión expira, simplemente vuelva a escribir la contraseña, SC900-Lab.

9. Cierre sesión en Azure Portal y cierre la ventana del explorador. 

#### Tarea 4 (opcional): En esta tarea, como el usuario Adele Vance, aprenderá el proceso de restablecimiento de su contraseña.

1. Abra Microsoft Edge.

2. En la barra de direcciones escriba login.microsoftonline.com.

3. Inicie sesión como Adele Vance, escriba el correo electrónico **AdeleV@WWLxZZZZ.onmicrosoft.com** (donde ZZZZZZ es su ID de inquilino única ofrecida por su proveedor de hospedaje de laboratorio) y seleccione el botón **Siguiente**. Quizás se abra una ventana para elegir una cuenta, si es así, seleccione la cuenta de Adele Vance.

4. En la ventana Escribir contraseña, seleccione **He olvidado mi contraseña**. 

5. Se abrirá la ventana Volver a su cuenta.   Compruebe que el correo electrónico de Adele Vance, AdeleV@WWLxZZZZ.onmicrosoft.com, aparece en el cuadro de correo electrónico o nombre de usuario.  Si no es así, escríbalo.  

6. En el cuadro vacío, escriba los caracteres que aparecen en la imagen o las palabras del audio. Cuando los haya escrito, seleccione **Siguiente**.

7. La pantalla muestra Volver a su cuenta y Verificación, paso 1 > elegir una contraseña nueva. Deje el valor predeterminado **Enviar mensaje de texto a mi teléfono móvil.**  Se le solicitará que escriba su número de teléfono.  Cuando lo haya escrito, seleccione el **botón Texto**.  Si durante el registro seleccionó el correo electrónico, la ventana Volver a su cuenta indicará que recibirá un correo electrónico con un código de verificación en su dirección de correo electrónico alternativa.  Seleccione **Correo electrónico**. 

8. Escriba el código de verificación y presione **Siguiente**.

9. En la siguiente pantalla se le solicitará que escriba y confirme su contraseña nueva.  Escríbalos y seleccione el botón **Finalizar**.

10. Verá un mensaje en la pantalla que indica que la contraseña se ha restablecido.  Seleccione **haga clic aquí** para iniciar sesión con la contraseña nueva.

11. En el cuadro de información sobre la cuenta, seleccione **AdeleV@WWLxZZZZZZ.onmicrosoft.com**, escriba su contraseña nueva y, luego seleccione el botón **Iniciar sesión**.  Si se le pregunta si desea mantener la sesión iniciada, seleccione **No**.

12. Ahora debería estar en Azure Portal.

13. Para cerrar la sesión seleccione el icono de usuario junto a la dirección de correo electrónico en la esquina superior derecha de la pantalla y seleccione **Cerrar sesión**. A continuación, cierre todas las ventanas del navegador

#### Tarea 5 (opcional):  En esta tarea, como administrador, verá brevemente los registros de auditoría y los datos de uso e información asociados al restablecimiento de contraseñas.

1. Abra Microsoft Edge.

2. En la barra de direcciones escriba **portal.azure.com** 

3. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

4. Seleccione **Azure Active Directory**.  

5. En el panel de navegación izquierdo, seleccione **Restablecer contraseña**.

6. En el panel de navegación izquierdo, seleccione **Registros de auditoría**.  Observe la información y los filtros disponibles.  Observe también que se pueden descargar los registros.  

7. Seleccione **Descargar**.  Observe que al descargar puede elegir los formatos de archivo CSV o JSON.  Cierre la ventana con la **X** de la esquina superior derecha de la pantalla.

8. En el panel de navegación izquierdo, seleccione **Uso e información**.

9. Observe la información disponible sobre el registro.  Observe que estos datos pueden tardar en actualizarse, incluso después actualizar, por lo que puede que aún no se reflejen los datos de registro o uso de la tarea anterior.

10. En la parte superior de la página, seleccione **Uso** para ver el número de autoservicios de restablecimiento de contraseña y desbloqueos de cuentas por método.  Observe que estos datos pueden tardar en actualizarse, incluso después actualizar, por lo que puede que aún no se reflejen los datos de uso de la tarea anterior.

11. Cierre las pestañas abiertas del explorador.


#### Revisión
En este laboratorio, como administrador, aprendió el proceso para habilitar el autoservicio de restablecimiento de contraseña. Cuando habilitó el SSPR, asumió el rol de un usuario y pasó por el proceso de registrarse en el SSPR y también de restablecer su contraseña.  Por último, como administrador, aprendió dónde acceder a los registros de auditoría y a los datos de uso e información del SSPR.
