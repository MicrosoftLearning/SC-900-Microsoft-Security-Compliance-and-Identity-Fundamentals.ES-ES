<!---
---
Configuración previa a la demostración: Título: "Configuración de la demostración"
---
--->

## Inquilinos de WWL: términos de uso

Si se le proporciona un inquilino porque está realizando un curso dirigido por un instructor, tenga en cuenta que ese inquilino está disponible únicamente como apoyo para los laboratorios prácticos del curso.

Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino usado en este curso es un inquilino de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y no sea apto para la extensión.

Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento.

## Configuración previa a la demostración del inquilino de Microsoft 365

### Habilitar el registro de auditoría de Microsoft 365

En esta tarea de configuración, habilitará la funcionalidad Registro de auditoría de Microsoft 365.  Aunque la documentación indica que el registro de auditoría está habilitado de manera predeterminada, la mayoría de los inquilinos del laboratorio no tienen habilitada esta función y pueden pasar varias horas hasta que surta efecto.  Habilitar esta función resulta útil, ya que Microsoft 365 utiliza los registros de auditoría para conseguir información sobre los usuarios y las actividades identificadas en las directivas y los análisis.

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **https://admin.microsoft.com**.

1. Inicie sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.  

1. En el panel de navegación izquierdo del Portal de cumplimiento de Microsoft Purview, seleccione **Mostrar todo**.

1. En el panel de navegación izquierdo, debajo de Soluciones, seleccione **Auditoría**.  Nota: La funcionalidad de auditoría también es accesible a través de la página principal de Microsoft 365 Defender.

1. Compruebe que la pestaña **Buscar** está seleccionada (subrayada).

1. Una vez que llegue a la página Auditoría, espere de 2 a 3 minutos.  Si Auditoría NO está habilitada, verá una barra azul en la parte superior de la página donde pone "Comenzar a registrar la actividad del usuario y del administrador".  Seleccione **Comenzar a registrar la actividad del usuario y del administrador**.  Una vez habilitada Auditoría, la barra azul desaparecerá.  Si la barra azul no aparece, eso significará que la opción Auditoría ya está habilitada, y no necesitará hacer nada más.

1. Para volver a la página principal del Portal de cumplimiento de Microsoft Purview, seleccione **Inicio** en el panel de navegación izquierdo.

### Supervisión de archivos en Microsoft Defender for Cloud

En esta configuración de la tarea, habilitará la supervisión de archivos en Microsoft Defender for Cloud Apps.

1. Abra la pestaña del explorador del Centro de administración de Microsoft 365.  Si lo cerró anteriormente, abra una nueva pestaña del explorador y, en la barra de direcciones, escriba **https://admin.microsoft.com** y, en el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.

1. En Centros de administración, seleccione **Seguridad**.  Se abrirá una nueva página del explorador con la página de bienvenida del portal de Microsoft 365 Defender.  

1. En el panel de navegación izquierdo, seleccione **Archivos**, que aparece en Aplicaciones en la nube.

1. Si aún no está habilitado, seleccione **Habilitar supervisión de archivos** y la casilla situada junto a donde dice **"Habilitar supervisión de archivos"**, después seleccione **Guardar**.  

1. En el panel de navegación izquierdo, bajo Aplicaciones en la nube, seleccione **Archivos** para volver a la página de archivos.  Si ha habilitado correctamente la supervisión de archivos, debería ver las opciones de filtro en la parte superior de la página.  Los archivos del inquilino de laboratorio preconfigurado pueden tardar algún tiempo en mostrarse.

## Configuración previa a la demostración de la suscripción de Azure Cloud Slice

Para esta configuración, está usando el entorno de Azure Cloud Slice, que es independiente del inquilino de Microsoft 365 proporcionado. Cierre sesión del inquilino de Microsoft 365 e inicie sesión con las credenciales de Azure Cloud Slice.

### Máquina virtual de Azure

Compruebe que ya se ha creado una máquina virtual. Si no es así, establézcala ahora. Usará la máquina virtual como parte de la demostración del NSG.

1. Abrir Microsoft Edge.  En la barra de direcciones, escriba **https://portal.azure.com** e inicie sesión con las credenciales de Azure proporcionadas por el host de laboratorio autorizado (ALH).  Esto le llevará a la página principal de servicios de Azure.

1. En el cuadro de búsqueda azul en la parte superior de la página, escriba **Virtual Machines** y seleccione **Virtual Machines** en los resultados de la búsqueda.

1. Si ya aparece una máquina virtual, omita los pasos siguientes; de lo contrario, deberá crear una.  Seleccione **Crear** y, a continuación, seleccione **Máquina virtual de Azure** en la lista desplegable. Configure los siguientes parámetros (si un parámetro no aparece en la lista, deje el valor predeterminado).
    1. Grupo de recursos: seleccione **Crear nuevo** y escriba **LabsSC900**, luego seleccione **Aceptar**.
    1. Nombre de la máquina virtual: escriba **SC900-WinVM**.
    1. Opciones de disponibilidad: desde el menú desplegable, seleccione **No se requiere redundancia de infraestructura**.
    1. Imagen: en la lista desplegable, seleccione **Windows 11 Pro, versión 22H2 - x64 Gen2** (o cualquier imagen de Windows 10 o Windows 11 enumerada).
    1. Tamaño: seleccione **Ver todos los tamaños** y seleccione **Standard_B1s** seleccione **Seleccionar** en la parte inferior de la página.
    1. Nombre de usuario: escriba **SC900-VM-User**
    1. Contraseña: escriba una contraseña y anótela, la necesitará más adelante.
    1. Confirmar contraseña: vuelva a escribir la contraseña.
    1. Puertos de entrada públicos: **ninguno**.
    1. Licencia: seleccione donde dice "Confirmo que dispongo de una licencia válida de Windows 10/11 con derechos de hospedaje de varios inquilinos".  Debería aparecer una marca de verificación.
    1. Seleccione **Siguiente: Discos**
    1. Tipo de disco de sistema operativo: seleccione **SSD estándar** del menú desplegable.
    1. Seleccione **Siguiente: Redes**.
    1. Grupo de seguridad de red de NIC: seleccione **Ninguno**.  Creará un NSG como parte de la demostración, así que no lo haga aquí.
    1. Elimine la dirección IP pública y la NIC cuando se elimine la máquina virtual: seleccione la casilla para que aparezca una marca de verificación.
    1. Seleccione **Revisar y crear** y, una vez superada la validación, seleccione **Crear**.
    1. Una vez completada la implementación de la máquina virtual, seleccione **Inicio** en la parte superior de la página.

1. Mantenga abierta la pestaña del explorador de Azure para continuar con la configuración previa a la demostración.

### Grupo de seguridad de red

Compruebe que ya se ha creado un NSG. Si el NSG no se ha creado, hágalo ahora, pero no asocie ninguna interfaz a él ni cree ninguna regla. Estos pasos se realizarán como parte de la demostración del NSG.

1. En la barra de búsqueda azul de la parte superior de la página, escriba **Grupos de seguridad de red**. En los resultados, seleccione **Grupos de seguridad de red** (no seleccione Grupos de seguridad de red clásicos).

1. Seleccione**Crear grupo de seguridad de red		**. En la pestaña Datos básicos del página Crear grupo de seguridad de red, especifique la siguiente configuración:
    1. Suscripción: deje el valor predeterminado (esta es la suscripción de Azure proporcionada por el host de laboratorio autorizado).
    1. Grupo de recursos: **LabsSC900**
    1. Nombre: **NSG-SC900**
    1. Región: deje el valor predeterminado.
    1. Seleccione **Revisar y crear** y, luego, **Crear**.
    1. Una vez completada la implementación (esto sucede muy rápidamente), seleccione **Ir al recurso**.

### Microsoft Defender for Cloud

El objetivo aquí es simplemente acceder a Microsoft Defender a la nube por primera vez. Esto es importante porque puede tardar hasta 24 horas en que Defender for Cloud refleje una puntuación de seguridad inicial.  

1. Abra la pestaña de inicio de Microsoft Azure en el explorador.

1. En la barra de búsqueda azul escriba **Microsoft Defender for Cloud** y, luego, en la lista de resultados, seleccione **Microsoft Defender for Cloud**.

1. Si es la primera vez que entra en Microsoft Defender for Cloud con su suscripción, es posible que llegue a la página de introducción y se le pida que actualice.  Desplácese a la parte inferior de la página y seleccione **Omitir**.  Se le dirigirá a la página de información general.

1. Todas las suscripciones tienen CSPM básico habilitado de forma predeterminada, lo que proporciona una puntuación segura, pero puede tardar hasta 24 horas en que Defender for Cloud refleje una puntuación segura inicial.

1. Seleccione **Inicio** en la parte superior de la página.

1. Mantenga abierta la pestaña del explorador si tiene previsto continuar con la configuración previa a la demostración.

### Microsoft Sentinel

Compruebe que ya se ha creado una instancia de Microsoft Sentinel. Si no es así, hágalo ahora, ya que lo necesitará como parte de la demostración en Microsoft Sentinel.

1. Abra la pestaña de inicio de Microsoft Azure en el explorador.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escriba **Microsoft Sentinel** y seleccione **Microsoft Sentinel** en los resultados de búsqueda.

1. En la página Microsoft Sentinel, seleccione **Crear Microsoft Sentinel**.

1. En la pantalla Agregar Microsoft Sentinel a una página de área de trabajo, seleccione **Crear un área de trabajo nueva**.

1. En la pestaña Datos básicos del área de trabajo Crear Log Analytics, escriba lo siguiente:
    1. Suscripción: deje el valor predeterminado.
    1. Grupo de recursos: seleccione **Crear nuevo**, luego escriba **SC900-Sentinel-RG** y seleccione **Aceptar**.
    1. Nombre: **SC900-LogAnalytics-workspace**.
    1. Región: **Este de EE. UU.**. (Se puede seleccionar una región predeterminada diferente en función de la ubicación).
    1. Seleccione **Revisar y crear** (no se configurarán etiquetas).
    1. Compruebe que escribió la información correcta y seleccione **Crear**.
    1. El área de trabajo puede tardar un minuto o dos en aparecer, si todavía no la ve, seleccione **Actualizar** y, a continuación, seleccione **Agregar**.

1. Una vez que se haya agregado la nueva área de trabajo, se mostrará la página Microsoft Sentinel | Noticias y guías, lo que indica que se ha activado la evaluación gratuita de Microsoft Sentinel.  Seleccione **Aceptar**.

### Revisar

En esta configuración, habilitó la capacidad del registro de auditoría en el inquilino de Microsoft 365 y también creó la comprobación de que una máquina virtual estaba preconfigurada en el entorno de Azure Cloud Slice. También preparó el entorno de Defender for Cloud y Microsoft Sentinel.
