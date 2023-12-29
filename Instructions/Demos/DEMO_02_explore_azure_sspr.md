<!---
---
Demostración: Título: "Autoservicio de restablecimiento de contraseña (SSPR) de Microsoft Entra" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Entra; Módulo 2: Descripción de las funcionalidades de autenticación de Microsoft Entra ID; Unidad 4: Descripción del autoservicio de restablecimiento de contraseña"
---
--->

# Demostración: Autoservicio de restablecimiento de contraseña (SSPR) de Microsoft Entra

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de Microsoft Entra
- Módulo: Descripción de las funcionalidades de autenticación de Microsoft Entra ID
- Unidad: Descripción del autoservicio de restablecimiento de contraseña

## Supuesto de demostración

En esta demo, hará un recorrido por las diferentes configuraciones asociadas a la habilitación del autoservicio de restablecimiento de contraseña.

1. Vuelva a la pestaña abierta del explorador titulada "Inicio-Centro de administración de Microsoft Entra".  Si ha cerrado previamente esa pestaña del explorador, abra Microsoft Edge e inicie sesión en **[entra.microsoft.com](https://entra.microsoft.com)** con sus credenciales de administrador de Microsoft 365.

1. En el panel de navegación izquierdo, expanda **Protección** y, a continuación, seleccione **Restablecimiento de contraseña**.

1. La pestaña Propiedades está resaltada.  En el ventana Propiedades, observe que SSPR se puede habilitar para Ninguno, Seleccionar o Todo.
    1. Coloque el cursor sobre el icono de información junto a donde pone "Autoservicio de restablecimiento de contraseña habilitado", puede elegir "Seleccionado" para restringir el restablecimiento de contraseña a un grupo limitado de usuarios, o también puede seleccionar Ninguno o Todos.
    1. Coloque el cursor sobre el icono de información junto a donde pone "Seleccionar grupo", aquí es dónde puede definir el grupo de usuarios a los que se permite restablecer sus propias contraseñas.   Debe incluir usuarios en el grupo, no puede seleccionar usuarios individualmente.  Además, si cambia el grupo, el grupo seleccionado reemplaza el grupo que aparece actualmente.  Por lo tanto, se recomienda que agregue los usuarios al grupo del SSPR.
    1. Fíjese en el cuadro de información azul claro y coméntelo a los alumnos: esta configuración solo se aplica a los usuarios finales de su organización. Los administradores siempre están habilitados para el autoservicio de restablecimiento de contraseña y deben utilizar dos métodos de autenticación para restablecer su contraseña.

1. En el panel de navegación izquierdo Restablecimiento de contraseña, seleccione Métodos de autenticación.
    1. Coloque el cursor sobre el icono de información junto a donde pone "Número de métodos necesarios para restablecer".  Señale que establece el número de métodos alternativos de identificación que un usuario de este directorio debe tener para restablecer su contraseña.   No cambie la configuración.
    1. Señale los distintos "métodos disponibles para los usuarios", incluido el punto en que SSPR admite preguntas de seguridad. Seleccione Preguntas de seguridad para mostrar las opciones para usar preguntas de seguridad. Una vez que haya terminado de comentar las opciones, vuelva atrás y seleccione Preguntas de seguridad para quitar la marca de verificación.

1. En el panel de navegación izquierdo Restablecimiento de contraseña, seleccione Registro.
    1. Mantenga el puntero sobre el icono de información junto a donde pone: "Requerir que los usuarios se registren al iniciar sesión".   Coméntelo con los usuarios.  
    1. Mantenga el puntero sobre el icono de información que aparece junto al texto "Número de días antes de que al usuario se le pida que vuelva a confirmar su información de autenticación".   Coméntelo con los usuarios.  

1. En el panel de navegación izquierdo Restablecimiento de contraseña, seleccione Notificaciones.  Señale las dos configuraciones: mantenga el puntero sobre el icono de información de la descripción.

1. Observe cómo el panel de navegación Restablecimiento de contraseña también incluye opciones para ver los registros de auditoría y Usage & insights (Uso e información).

1. Seleccione la X de la esquina superior derecha de la página. Esto le devuelve a la página principal del inquilino de Contoso.

1. Mantenga esta página del explorador abierta para la siguiente demo.

### Revisar

En esta demo, mostró las configuraciones asociadas al autoservicio de restablecimiento de contraseña.
