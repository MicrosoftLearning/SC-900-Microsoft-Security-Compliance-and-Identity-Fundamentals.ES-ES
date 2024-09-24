<!---
---
Configuración previa a la demostración: Título: "Configuración de la demostración"
---
--->

## Inquilinos de WWL: términos de uso

Si se te proporciona un inquilino porque estás realizando un curso dirigido por un instructor, ten en cuenta que ese inquilino está disponible únicamente como apoyo para los laboratorios prácticos del curso.

Los inquilinos no deben compartirse ni usarse para otros fines que no sean los de los laboratorios prácticos. El inquilino usado en este curso es un inquilino de prueba y no se puede usar ni tener acceso a él después de que la clase haya terminado y no es apto para la extensión.

Los inquilinos no se deben convertir a suscripciones de pago. Los inquilinos obtenidos como parte de este curso siguen siendo propiedad de Microsoft Corporation y nos reservamos el derecho de acceso y recuperación en cualquier momento.

## Configuración previa a la demostración del inquilino de Microsoft 365

### Habilitación del registro de auditoría y la supervisión de archivos de Microsoft 365

En esta tarea de configuración, habilitarás las funcionalidades de registro de auditoría y supervisión de archivos de Microsoft 365.

1. Abre Microsoft Edge. En la barra de direcciones, escribe **https://admin.microsoft.com**.

1. Inicia sesión con las credenciales de administrador para el inquilino de Microsoft 365 proporcionadas por el host de laboratorio autorizado (ALH).

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, selecciona **Mostrar todo**.

1. En Centros de administración, selecciona **Seguridad**.  Se abrirá una nueva página del explorador con la página de bienvenida de Microsoft Defender.  

1. En el panel de navegación izquierdo del Portal de cumplimiento de Microsoft Purview, seleccione **Mostrar todo**.

1. En el panel de navegación izquierdo, desplázate hacia abajo y expande **Sistema**.  Selecciona **Auditoría** en la lista expandida.  Nota: la funcionalidad de auditoría también es accesible a través del portal de Microsoft Defender.

1. Una vez que llegues a la página Auditoría, espera de 1 a 2 minutos.  Si Auditoría NO está habilitada, verás una barra azul en la parte superior de la página donde pone "Comenzar a registrar la actividad del usuario y del administrador".  Selecciona **Comenzar a registrar la actividad del usuario y del administrador**.  Una vez habilitada Auditoría, la barra azul desaparecerá.  Si la barra azul no aparece, eso significará que la opción Auditoría ya está habilitada, y no necesitarás hacer nada más.

1. En el panel de navegación de la izquierda, en Sistema, selecciona **Configuración**.

1. En la página de configuración, selecciona **Aplicaciones en la nube**.   Desplázate hacia abajo y en Information Protection, selecciona **Archivos**.

1. Si aún no está habilitado, selecciona la casilla situada junto a donde dice **Habilitar supervisión de archivos** y, después, selecciona **Guardar**.  

### Configuración del rol de administrador de cumplimiento

En esta tarea de configuración, te agregarás, como administrador MOD, al grupo de roles de administrador de cumplimiento.

1. Abre una nueva pestaña de explorador Microsoft Edge y, en la barra de direcciones, escribe **https://purview.microsoft.com**. Para acceder al nuevo portal de Microsoft Purview, selecciona el cuadro situado junto a donde dice, **Acepto las condiciones de divulgación del flujo de datos y las Declaraciones de privacidad** y, después, selecciona **Introducción**.  
1. En el panel de navegación de la izquierda, selecciona **Configuración**.
1. En el panel de navegación que se abre, selecciona **Roles y ámbito** para expandir la opción y, después, selecciona **Grupos de roles**.
1. En el cuadro de búsqueda del lado derecho de la pantalla, busque el término **Cumplimiento**.  Selecciona **Administrador de cumplimiento**.
    1. Selecciona **Editar**.
    1. Selecciona **Seleccionar usuarios**.
    1. Busca Administrador MOD, selecciona el cuadro situado junto a **Administrador de MOD**. Luego, selecciona el botón **Seleccionar** situado en la parte inferior de la página.
    1. Selecciona **Siguiente**, **,Guardar** y, finalmente, **Listo**.
1. Esto concluye la configuración del inquilino de Microsoft 365, puedes cerrar las pestañas del explorador.

## Configuración previa a la demostración de la suscripción de Azure Cloud Slice

Para esta configuración, estás usando el entorno de Azure Cloud Slice, que es independiente del inquilino de Microsoft 365 proporcionado. Cierra sesión del inquilino de Microsoft 365 e inicia sesión con las credenciales de Azure Cloud Slice.

### Máquina virtual de Azure

Comprueba que ya se ha creado una máquina virtual. Si no es así, establécela ahora. Usarás la máquina virtual como parte de la demostración del NSG.

1. Abre Microsoft Edge.  En la barra de direcciones, escribe **https://portal.azure.com** e inicia sesión con las credenciales de Azure proporcionadas por el host de laboratorio autorizado (ALH).  Esto te llevará a la página principal de servicios de Azure.

1. En el cuadro de búsqueda azul en la parte superior de la página, escribe **Virtual Machines** y selecciona **Virtual Machines** en los resultados de la búsqueda.

1. Si ya aparece una máquina virtual, omite los pasos siguientes; de lo contrario, deberás crear una.  Selecciona **Crear** y, a continuación, selecciona **Máquina virtual de Azure** en la lista desplegable. Configura los siguientes parámetros (si un parámetro no aparece en la lista, deja el valor predeterminado).
    1. Grupo de recursos: selecciona **Crear nuevo**, escribe **LabsSC900** y luego selecciona **Aceptar**.
    1. Nombre de la máquina virtual: escribe **SC900-WinVM**.
    1. Opciones de disponibilidad: desde el menú desplegable, selecciona **No se requiere redundancia de infraestructura**.
    1. Tipo de seguridad: en el menú desplegable, selecciona **Estándar**.
    1. Imagen: en la lista desplegable, selecciona **Windows 11 Pro, versión 22H2 - x64 Gen2** (o cualquier imagen de Windows 10 o Windows 11 enumerada).
    1. Tamaño: selecciona **Ver todos los tamaños** y selecciona **Standard_B1s** selecciona **Seleccionar** en la parte inferior de la página.
    1. Nombre de usuario: escribe **SC900-VM-User**
    1. Contraseña: escribe una contraseña y anótala, la necesitarás más adelante.
    1. Confirmar contraseña: vuelve a escribir la contraseña.
    1. Puertos de entrada públicos: **ninguno**.
    1. Licencia: selecciona donde dice "Confirmo que dispongo de una licencia válida de Windows 10/11 con derechos de hospedaje de varios inquilinos".  Debería aparecer una marca de verificación.
    1. Selecciona **Siguiente: Discos**
    1. Tipo de disco de sistema operativo: selecciona **SSD estándar** del menú desplegable.
    1. Selecciona **Siguiente: Redes**.
    1. Grupo de seguridad de red de NIC: selecciona **Ninguno**.  Crearás un NSG como parte de la demostración, así que no lo hagas aquí.
    1. Elimina la dirección IP pública y la NIC cuando se elimine la máquina virtual: selecciona la casilla para que aparezca una marca de verificación.
    1. Selecciona **Revisar y crear** y, una vez superada la validación, selecciona **Crear**.
    1. Una vez completada la implementación de la máquina virtual, selecciona **Inicio** en la parte superior de la página.

1. Mantén abierta la pestaña del explorador de Azure para continuar con la configuración previa a la demostración.

### Grupo de seguridad de red

Comprueba que ya se ha creado un NSG. Si el NSG no se ha creado, hazlo ahora, pero no asocies ninguna interfaz a él ni crees ninguna regla. Estos pasos se realizarán como parte de la demostración del NSG.

1. En la barra de búsqueda azul de la parte superior de la página, escribe **Grupos de seguridad de red**. En los resultados, selecciona **Grupos de seguridad de red** (no selecciones Grupos de seguridad de red clásicos).

1. Selecciona **Crear grupo de seguridad de red**. En la pestaña Datos básicos del página Crear grupo de seguridad de red, especifica la siguiente configuración:
    1. Suscripción: deja el valor predeterminado (esta es la suscripción de Azure proporcionada por el host de laboratorio autorizado).
    1. Grupo de recursos: **LabsSC900**
    1. Nombre: **NSG-SC900**
    1. Región: deja el valor predeterminado.
    1. Selecciona **Revisar y crear** y, luego, **Crear**.
    1. Una vez completada la implementación (esto sucede muy rápidamente), selecciona **Ir al recurso**.

### Microsoft Defender for Cloud

El objetivo aquí es simplemente acceder a Microsoft Defender a la nube por primera vez. Esto es importante porque puede tardar hasta 24 horas en que Defender for Cloud refleje una puntuación de seguridad inicial.  

1. Abre la pestaña de inicio de Microsoft Azure en el explorador.

1. En la barra de búsqueda azul, escribe **Microsoft Defender for Cloud** y luego, en la lista de resultados, selecciona **Microsoft Defender for Cloud**.

1. Si es la primera vez que entras en Microsoft Defender for Cloud con tu suscripción, es posible que llegues a la página de introducción y se te pida que actualices.  Desplázate a la parte inferior de la página y selecciona **Omitir**.  Se te dirigirá a la página de información general.

1. Todas las suscripciones tienen CSPM básico habilitado de forma predeterminada, lo que proporciona una puntuación segura, pero puede tardar hasta 24 horas en que Defender for Cloud refleje una puntuación segura inicial.

1. Selecciona **Inicio** en la parte superior de la página.

1. Mantén abierta la pestaña del explorador si tienes previsto continuar con la configuración previa a la demostración.

### Microsoft Sentinel

Comprueba que ya se ha creado una instancia de Microsoft Sentinel. Si no es así, hazlo ahora, ya que lo necesitarás como parte de la demostración en Microsoft Sentinel.

1. Abre la pestaña de inicio de Microsoft Azure en el explorador.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página junto a Microsoft Azure, escribe **Microsoft Sentinel** y selecciona **Microsoft Sentinel** en los resultados de búsqueda.

1. En la página Microsoft Sentinel, selecciona **Crear Microsoft Sentinel**.

1. En la pantalla Agregar Microsoft Sentinel a una página de área de trabajo, selecciona **Crear un área de trabajo nueva**.

1. En la pestaña Datos básicos del área de trabajo Crear Log Analytics, escribe lo siguiente:
    1. Suscripción: deja el valor predeterminado.
    1. Grupo de recursos: selecciona **Crear nuevo**, luego escribe **SC900-Sentinel-RG** y selecciona **Aceptar**.
    1. Nombre: **SC900-LogAnalytics-workspace**.
    1. Región: **Este de EE. UU.**. (Se puede seleccionar una región predeterminada diferente en función de la ubicación).
    1. Selecciona **Revisar y crear** (no se configurarán etiquetas).
    1. Comprueba que escribiste la información correcta y selecciona **Crear**.
    1. El área de trabajo puede tardar un minuto o dos en aparecer, si todavía no la ves, selecciona **Actualizar** y, a continuación, selecciona **Agregar**.

1. Una vez que se haya agregado la nueva área de trabajo, se mostrará la página Microsoft Sentinel | Noticias y guías, lo que indica que se ha activado la evaluación gratuita de Microsoft Sentinel.  Selecciona **Aceptar**.

### Revisar

En esta configuración, habilitaste la capacidad del registro de auditoría en el inquilino de Microsoft 365 y también creaste la comprobación de que una máquina virtual estaba preconfigurada en el entorno de Azure Cloud Slice. También preparaste el entorno de Defender for Cloud y Microsoft Sentinel.
