---
lab:
    title: 'Explorar la administración de riesgos internos en Microsoft 365'
    module: 'Módulo 4, lección 3: Describir las funcionalidades de las soluciones de cumplimiento de Microsoft. Describir las funcionalidades de riesgos internos de Microsoft 365'
---


# Laboratorio: Explorar la administración de riesgos internos en Microsoft 365

## Escenario del laboratorio
En este laboratorio, se familiarizará con el proceso de configurar una directiva de riesgos internos y los requisitos básicos previos para configurar y usar directivas de Administración de riesgos internos.  Nota:  Este laboratorio únicamente abordará los requisitos necesarios para configurar la Administración de riesgos internos y las opciones relativas a la creación de directivas.  Este laboratorio no incluye la tarea de desencadenar la directiva, ya que el número de eventos que tendrían que producirse para desencadenar una directiva queda fuera del ámbito de este ejercicio.


**Tiempo estimado**: 25-30 minutos.

#### Tarea 1: En esta tarea, como administrador global, habilitará los permisos para la administración de riesgos internos.  En concreto, agregará usuarios al grupo de roles de Administración de riesgos internos para asegurarse de que los usuarios designados pueden acceder y administrar las características de administración de riesgos internos.  Los permisos del grupo de roles pueden tardar hasta 30 minutos en aplicarse a los usuarios de la organización 

1. Abra Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
    
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. Debajo de Centros de administración, seleccione **Seguridad**.  Se abrirá una nueva página del explorador con la página principal del portal de Microsoft 365 Defender.  

1. En el panel de navegación izquierdo del portal de Microsoft 365 Defender, seleccione **Permisos y roles**.  Es posible que deba desplazarse hacia abajo para ver esta opción.

1. En la página Permisos y roles, debajo de **Roles de correo electrónico y colaboración**, seleccione **Roles**.

1. En la barra de búsqueda, escriba **Riesgo interno** y luego seleccione el icono de búsqueda (la lupa).  Observe los cinco roles que aparecen.  Cada uno tiene un nivel de acceso diferente.  Seleccione **Administración de riesgos internos**. 

1. En la ventana que se abre, junto a la palabra Miembros, seleccione **Editar**.

1. Para agregar miembros a este grupo de roles, seleccione **Elegir integrantes**.

1. Seleccione **+ Agregar** en la parte superior de la página.

1. En la lista de nombres, seleccione **Megan Bowen**, **Administrador MOD** y luego seleccione **Agregar** y **Aceptar** en la parte inferior de la página.

1. Compruebe que ha agregado los miembros correctos y luego seleccione **Guardar**.

1. En la parte inferior de la ventana Administración de riesgos internos, seleccione **Cerrar**.

1. Mantenga esta ventana del navegador abierta, ya que volverá a ella en una tarea posterior.


#### Tarea 2 (omítala si ha realizado la tarea Configurar el laboratorio para habilitar el registro de auditoría): Administración de riesgos internos usa los registros de auditoría de Microsoft 365 para la información y las actividades de los usuarios identificadas en las directivas y la información de los análisis. En esta tarea, habilitará la funcionalidad Búsqueda en el registro de auditoría. Nota:  Es posible que pasen varias horas después de activar la Búsqueda en el registro de auditoría antes de que pueda devolver resultados al buscar en el registro de auditoría.  Aunque pueden pasar varios horas hasta que pueda buscar en el registro de auditoría, eso no será un impedimento para completar el resto de tareas de este laboratorio

1. Seleccione la pestaña del explorador con la etiqueta **Centro de administración de Microsoft 365:Inicio**.  Si anteriormente había cerrado esta pestaña del navegador, abra Microsoft Edge, escriba **admin.microsoft.com** en la barra de direcciones e inicie sesión con sus credenciales de administrador.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del Centro de cumplimiento de Microsoft 365.  

1. En el panel de navegación izquierdo del Centro de cumplimiento de Microsoft 365, seleccione **Mostrar todo**.

1. En el panel de navegación izquierdo, en Soluciones, seleccione **Auditoría**.

1. Compruebe que la pestaña **Buscar** está seleccionada (subrayada).

1. Cuando llegue a la página Auditoría, espere entre 2 y 3 minutos.  Si Auditoría NO está habilitada, verá una barra azul en la parte superior de la página donde pone "Comenzar a registrar la actividad del usuario y del administrador".  Seleccione **Iniciar el registro de la actividad de usuarios y administradores**.  Una vez que la auditoría esté habilitada, la barra azul desaparecerá.  Si la barra azul no aparece, eso significará que la opción Auditoría ya está habilitada, y no necesitará hacer nada más.

1. Para volver a la página principal del centro de cumplimiento de Microsoft 365, seleccione **Inicio** en el panel de navegación izquierdo.

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

#### Tarea 3: En esta tarea explorará las opciones relativas a la solución Administración de riesgos internos.  La configuración de Administración de riesgos internos se aplica a todas las directivas de Administración de riesgos internos, independientemente de la plantilla que seleccione al crear una directiva. 

1. Debería encontrarse en la página principal del Centro de cumplimiento de Microsoft 365. Si no es así, abra la pestaña del explorador **Inicio: Cumplimiento de Microsoft 365**.

1. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **Administración de riesgos internos**.

1. Antes de empezar a crear una directiva, es necesario configurar algunas opciones.  En la página Administración de riesgos internos, seleccione el **icono de engranaje de Configuración** en la esquina superior derecha de la página para acceder a la configuración de Riesgos internos.  
    1. Pestaña Privacidad:  en el caso de los usuarios que realizan actividades asignadas a sus directivas de riesgos internos, esta configuración determinará si se deben mostrar los nombres reales o usar versiones anónimas para ocultar su identidad.  Seleccione **No mostrar versiones anónimas de nombres de usuario** y luego seleccione **Guardar**.  Seleccione la pestaña **Indicadores de directiva**.
    
    1. Pestaña Indicadores de directiva: una vez que se produce el evento desencadenante de una directiva, las actividades asignadas a los indicadores seleccionados se usan para determinar la puntuación de riesgo del usuario. Los indicadores de directiva seleccionados aquí se incluyen en las plantillas de directiva de riesgos internos.  Desplácese para ver todos los indicadores disponibles y cualquier tipo de información asociada. Debajo de **Indicadores de Office**, seleccione **Seleccionar todos** y **Guardar**.  Seleccione la pestaña **Plazos de la Directiva**.
    1. Pestaña Plazos de la Directiva:  los plazos que seleccione aquí entrarán en vigor para un usuario cuando desencadenen una coincidencia con una directiva de riesgos internos.   La ventana Activación determina el tiempo que las directivas detectarán activamente la actividad de los usuarios, y se desencadena cuando un usuario realiza la primera actividad que coincide con una directiva. Detección de actividad pasada: determina la retroactividad de una directiva a la hora de detectar la actividad de los usuarios, y se desencadena cuando un usuario realiza la primera actividad que coincide con una directiva.  Deje los valores predeterminados.  Seleccione la pestaña **Detecciones inteligentes**.
    1. Pestaña Detecciones inteligentes:  revise las opciones que aparecen aquí.  Observe las opciones de Configuración de dominios y su relación con los indicadores.
    1. Algunos de los demás elementos que aparecen en la lista de opciones de configuración son una versión preliminar.  Explore estas opciones a su discreción y tenga en cuenta que, dado que se trata de versiones preliminares, pueden estar sujetas a cambios.

1. Para volver a la página Información general de Administración de riesgos internos, seleccione **Administración de riesgos internos** en la esquina superior izquierda de la página, encima de la palabra "Configuración".

1. Deje esta pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

#### Tarea 4:  En esta tarea se familiarizará con el proceso de creación de una directiva

1. Debería encontrarse en la página Administración de riesgos internos.  Si aún no está en ella, abra la pestaña del explorador con la etiqueta **Administración de riesgos internos: Cumplimiento de Microsoft 365**.

1. En la página Información general de Administración de riesgos internos, seleccione la pestaña **Directivas** y luego seleccione **+ Crear**.  Configure cada una de las siguientes pestañas de Directiva.

    1. Plantilla de directiva:  en la lista de categorías, seleccione **Pérdidas de datos** y luego **Pérdidas de datos generales**.  Observe que las plantillas de las categorías pueden tener requisitos previos adicionales.  Lea los detalles asociados a esta plantilla y luego seleccione **Siguiente**.
    
    1. Nombre y descripción:  escriba un nombre, **Directivaderiesgosinternos:SC900**, y luego seleccione **Siguiente**.
    1. Usuarios y grupos:  revise el cuadro de información.  Deje la configuración predeterminada, **Incluir todos los usuarios y grupos**.  Seleccione **Siguiente**.
    1. Contenido prioritario: lea la descripción. Seleccione **Quiero especificar sitios de SharePoint, etiquetas de confidencialidad o tipos de información confidencial como contenido prioritario** y luego seleccione **Siguiente**.
        1. Sitio de SharePoint: para esta directiva de ejemplo, deje este campo en blanco y seleccione **Siguiente**.
        1. Tipos de información confidencial: para esta directiva de ejemplo, deje este campo en blanco y luego seleccione **Siguiente**. 
        1. Etiquetas de confidencialidad: seleccione **+ Agregar o editar etiquetas de confidencialidad**.  Seleccione las etiquetas que aparecen en la siguiente lista:  **Finanzas Confidencial** y **Proyecto:Falcon\Extremadamente confidencial**, seleccione **Agregar** y luego **Siguiente**.
    1. Indicadores y evento desencadenante: revise la información detallada.  La directiva se desencadena cuando el usuario realiza una actividad de filtración definida (seleccione los iconos de información de cada viñeta para obtener información más detallada) o se detecta una coincidencia con una directiva de Prevención de pérdida de datos (DLP) existente.  Dado que no ha configurado ninguna directiva DLP como parte de este ejercicio, seleccione **El usuario realiza una actividad de filtración**.  Desplácese hacia abajo para ver las opciones que se han seleccionado automáticamente.  Observe que los indicadores de directiva que habilitó en la tarea anterior están activados.   Recuerde que estos indicadores solo se activarán una vez que la directiva se desencadene, y que cualquier actividad asignada a estos indicadores se usará para calcular la puntuación de riesgo del usuario.  La opción Detección de secuencias también está habilitada.  La detección de una secuencia de actividades definida previamente sugiere un riesgo mayor.  Seleccione el icono de información para obtener información detallada sobre los indicadores requeridos.  Para realizar esta selección, es necesario seleccionar determinados indicadores e incorporar dispositivos.  Por motivos de simplicidad, y dado que no hemos incorporado dispositivos en esta cuenta empresarial, deseleccione **Seleccionar todo**.  Seleccione **Siguiente**.
    1. Umbrales de indicador:  aquí puede especificar umbrales predeterminados o personalizados asociados con los indicadores.  Recuerde que los indicadores solo se activan una vez que se produce el desencadenante de la directiva, por lo que estos umbrales no influyen en el momento en el que se desencadena esta. Seleccione **Especificar umbrales personalizados**. Al seleccionar esta opción, puede ver los valores predeterminados actuales. Deje los valores predeterminados y seleccione **Siguiente**.  
    1. Para terminar:  revise la configuración y seleccione **Enviar** y después **Listo**.

1. Ha vuelto a la pestaña Directivas de la página Administración de riesgos internos.  La directiva que acaba de crear aparecerá en la lista.  

1. En la directiva que acaba de crear, el campo "Usuarios del ámbito" representa los usuarios a los que se les están signando puntuaciones de riesgo mediante la directiva.  A los usuarios se les asigna una puntuación de riesgo cuando la directiva se desencadena, por lo que el valor que se muestra es 0.  Un administrador puede configurar una directiva para empezar a asignar puntuaciones de riesgo a usuarios específicos en base a la actividad detectada por las directivas que ha seleccionado, y esa directiva puede omitir el requisito de detectar previamente un evento desencadenante.  Para hacerlo, seleccione el círculo vacío junto al nombre de la directiva para seleccionarla, y luego seleccione la opción **Empezar a puntuar la actividad de los usuarios** que aparece encima de la tabla de directivas.  Rellene todos los campos y luego seleccione la opción **Empezar a puntuar la actividad**.  Es posible que los usuarios tarden 24 horas en aparecer en la pestaña "Usuarios". Pasado ese tiempo, podrá seleccionar los usuarios de esa pestaña para revisar las actividades detectadas.

#### Revisión
En este laboratorio, se ha familiarizado con el proceso de configurar una directiva de riesgos internos y con los requisitos básicos previos para configurar y usar directivas de administración de riesgos internos.
