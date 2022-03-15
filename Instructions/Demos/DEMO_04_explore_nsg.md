---
Demo:
  title: Grupos de seguridad de red (NSG) de Azure
  module: 'Module 3 Lesson 1: Describe the capabilities of Microsoft security solutions: Describe basic security capabilities in Azure.'
ms.openlocfilehash: 878316bb32c23e57550dddda1312af270a2fe078
ms.sourcegitcommit: 3a5280632c212b689353f3b2b0ee7c1f494ff855
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/04/2022
ms.locfileid: "138019288"
---
# <a name="demo-azure-network-security-groups-nsgs"></a>Demostración: Grupos de seguridad de red (NSG) de Azure

### <a name="demo-scenario"></a>Escenario de la demo
En esta demo, hará una demostración de la funcionalidad de un grupo de seguridad de red (NSG) en Azure.  Para ello, creará una máquina virtual (VM) sin ningún grupo de seguridad de red como parte de la configuración previa a la demo. También creará un grupo de seguridad de red sin ninguna interfaz o subred asociada.  Como parte de la demo, explicará el funcionamiento de las reglas de entrada y salida del grupo. Después, realizará el proceso de asignación de la interfaz de la máquina virtual al grupo que ha creado.  Una vez configurada, probará la conexión a la máquina virtual mediante las reglas predeterminadas del grupo de seguridad de red y las reglas que va a crear.
  

#### <a name="pre-demo-setup-part-1"></a>Configuración previa a la demostración, parte 1
 Se recomienda a los instructores que realicen este proceso **ANTES** de la clase, ya que crear una máquina virtual puede llevar varios minutos. En esta configuración, creará una máquina virtual de Windows 10.

1. Abra la pestaña **Inicio: Microsoft Azure** en su explorador.  Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba portal.azure.com y vuelva a iniciar sesión.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página que hay junto a las palabras Microsoft Azure, escriba **Máquinas virtuales** y luego seleccione **Máquinas virtuales** en los resultados de la búsqueda.  

1. En la parte superior izquierda de la página, seleccione **+Agregar** y, luego, **+Máquina virtual**.

1. En la pestaña Datos básicos, complete la siguiente información (si alguno de los campos no aparece en esta lista, deje la configuración predeterminada):
    1. **Suscripción**: compruebe que la configuración predeterminada sea Pase para Azure – Patrocinio.
    1. **Grupo de recursos**: seleccione **Crear nuevo**. Luego, en el campo Nombre, escriba **LabsSC900-RG** y seleccione **Aceptar**.
    1. **Virtual machines name**:  enter **SC900-WinVM**.
    1. **Región**: deje el valor predeterminado.
    1. **Opciones de disponibilidad**: asegúrese de seleccionar **No se requiere redundancia de la infraestructura**.  NOTA: Es muy importante que configure las opciones de disponibilidad en No se requiere redundancia de la infraestructura; de lo contrario, la demo no funcionará según lo previsto.  Para utilizar las opciones de disponibilidad se requiere un grupo de seguridad de red, y estamos creando intencionadamente la máquina virtual sin un grupo de seguridad de red.
    1. **Imagen**: en el menú desplegable, seleccione **Windows 10 Pro, versión 20H2 - Gen 1**.
    1. **Tamaño**: seleccione **Ver todos los tamaños** en el menú desplegable y, a continuación, **B2**. Luego, pulse **Seleccionar** en la parte inferior de la página.
    1. **Nombre de usuario**:  Introduzca el nombre de usuario que quiera.  Apunte este dato, ya que lo necesitará para acceder a la máquina virtual.
    1. **Contraseña**:  Escriba una contraseña de su elección.  Apunte este dato, ya que lo necesitará para acceder a la máquina virtual.
    1. **Puertos de entrada públicos**: puede dejar la configuración predeterminada (no importa lo que seleccione aquí, ya que la configuración de red reemplazará lo que haya hecho).
    1. **Licencias**: seleccione **Confirmo que dispongo de una licencia válida de Windows 10 con derechos de hospedaje multiinquilino** para que aparezca una marca de verificación en el cuadro.
    1. Seleccione **Siguiente: Discos**.

1. Ahora está en la pestaña Discos para configurar la VM.  Deje el resto de los valores predeterminados y seleccione **Siguiente: Redes >** .

1. Ahora se encuentra en la pestaña Redes para configurar la máquina virtual.  Complete la siguiente información (si alguno de los campos no aparece en esta lista, deje la configuración predeterminada):
    1. Grupo de seguridad de red de NIC: seleccione **Ninguno**.  Nota: Al seleccionar Ninguno se asegura de que la NIC no tiene un grupo de seguridad de red.  En el siguiente paso de la demo creará un grupo de seguridad de red y asignará la NIC de la máquina virtual al grupo que cree.
    1. Dado que va a utilizar los valores predeterminados para el resto de la configuración de la máquina virtual , continúe y seleccione Siguiente: **Revisar y crear>** .

1. Revise la configuración de su máquina virtual.  Algunos puntos que se deben tener en cuenta: Esta máquina virtual tiene una dirección IP pública y no cuenta con ningún grupo de seguridad de red NIC.  Desde el punto de vista de la seguridad, esto deja expuesta a la VM.  Abordaremos este problema en una de las siguientes tareas. Seleccione **Crear**.  La implementación de la máquina virtual puede tardar varios minutos en completarse.

1. Anote el nombre de la interfaz de red, **sc900-winvmXXX** (el XXX será específico de la interfaz de red de su máquina virtual).

1. Una vez finalizada la implementación, seleccione **Ir al recurso**.  Ahora se encuentra en la página de SC900-VMWin.  Anote la dirección IP pública.

1. En el panel de navegación izquierdo, seleccione **Redes** y anote la interfaz de red **sc900-winvmXXX** (el XXX será específico de la interfaz de red de su máquina virtual).  No debería haber reglas de entrada o salida asociadas a la interfaz.  

1. En la parte superior de la página, seleccione **Conectar**, puesto que es importante comprobar que puede conectarse a la máquina virtual.
    1. En la parte superior de la página, asegúrese de que **RDP** está seleccionado (subrayado).
    1. Compruebe que la dirección IP está configurada en Dirección IP pública, deje el número de puerto predeterminado y seleccione **Descargar archivo DRP**.
    1. **Abra** el archivo descargado y, en la ventana que aparece, seleccione **Conectar**.
    1. Se abrirá una ventana que le pedirá sus credenciales. Si la ventana predeterminada pide un PIN, seleccione **Opciones adicionales** y luego seleccione **Usar otra cuenta**.   A continuación, se le pedirán las credenciales.  Escriba el nombre de usuario y la contraseña que ha usado al crear la máquina virtual.
    1. Se abrirá la ventana Conexión a Escritorio remoto con el mensaje: No se puede comprobar la identidad del equipo remoto.  ¿Desea conectarse de todos modos?  Seleccione **Sí**.
    1. Se ha conectado a la máquina virtual de Windows que acaba de crear. Complete la configuración de Windows. Aunque se ha conectado a la máquina virtual a través de RDP y de uno de los puertos RDP más utilizados, todos los puertos de esta máquina virtual están abiertos y no hay nada que filtre el tráfico.  Cierre la conexión al escritorio remoto. Para ello, seleccione la **X** en la parte superior central de la página donde se muestra la dirección IP.  Una ventana emergente indicará que su sesión remota va a desconectarse. Seleccione **Aceptar**.

1. Ha vuelto a la página SC900-VMWin en Azure Portal.  Deje esta pestaña del explorador abierta para la siguiente tarea.

#### <a name="pre-demo-setup-part-2"></a>Configuración previa a la demostración, parte 2
Cree un grupo de seguridad de red, pero no asigne la interfaz de red de la máquina virtual a ese grupo.  

1. Abra la pestaña SC900-VMWin: Microsoft Azure en su explorador.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página que hay junto a las palabras Microsoft Azure, escriba **Grupo de seguridad de red** y luego seleccione **Grupos de seguridad de red** en los resultados de la búsqueda.  No seleccione Grupos de seguridad de red clásicos.

1. En la parte superior de la página Grupos de seguridad de red, seleccione **+ Crear**.

1. En la pestaña Datos básicos de la página Crear grupo de seguridad de red, especifique la siguiente configuración.
    1. Suscripción:  Pase para Azure: Patrocinio.
    1. Grupo de recursos:  **LabsSC900-RG**
    1. Nombre:  **NSG-SC900**
    1. Región: deje el valor predeterminado **Este de EE. UU. (EE. UU)**
    1. Seleccione **Revisar y crear** y, luego, **Crear**.

1. Cuando se complete la implementación, seleccione **Ir al recurso** y asegúrese de que todo está configurado correctamente.  Debería haber 3 reglas de entrada y 3 reglas de salida predeterminadas, y no debería haber subredes ni interfaces asociadas al grupo de seguridad de red.  Vuelva a la página **Inicio** de Azure Portal.  

#### <a name="demo"></a>Demostración
Explore la configuración de un grupo de seguridad de red.  En este caso, hará un recorrido por un grupo de seguridad de red existente (el que ha creado en la configuración anterior) que aún no ha sido asignado a la interfaz de una máquina virtual. Después, explicará cuál es el proceso para asociar una interfaz al grupo y crear las reglas de entrada y salida.

1. Abra la pestaña del explorador **Inicio: Microsoft Azure**.  Si anteriormente había cerrado la pestaña, abra una página del explorador y, en la barra de direcciones, escriba portal.azure.com y vuelva a iniciar sesión.

1. En el cuadro de búsqueda, en la barra azul de la parte superior de la página que hay junto a las palabras Microsoft Azure, escriba **Grupo de seguridad de red** y luego seleccione **Grupos de seguridad de red** en los resultados de la búsqueda.  No seleccione Grupos de seguridad de red clásicos.

1. En la página Grupos de seguridad de red, seleccione el grupo que ha creado en la configuración, **NSG-SC900**.

1. La pestaña **Información general** del panel de navegación izquierdo aparecerá resaltada.  Observe las reglas de entrada y salida predeterminadas del grupo. Aunque el grupo se ha creado y hay reglas predeterminadas para filtrar el tráfico, no hay ninguna interfaz asociada a él. Puede verlo en la parte superior derecha de la página, donde se muestra el texto "Asociado con: 0 subredes, 0 interfaces de red".  Para que un grupo de seguridad de red funcione, debe estar asignado a algo.  En nuestro caso, lo asignaremos a la interfaz de red de la máquina virtual que creamos previamente.

1. En el panel de navegación izquierdo de la página NSG-SC900, debajo de Configuración, seleccione **Interfaces de red**.

1. Seleccione **+ Asociar** encima del cuadro de búsqueda, y luego seleccione **sc900-winvmXXX** (el XXX será específico de la interfaz de red de su máquina virtual) en el menú desplegable y **Aceptar**. Puesto que se está asociando la interfaz, verá un cuadro de notificación en la esquina superior derecha de la pantalla. Una vez que se haya asociado la interfaz al grupo, se mostrará en la lista.

1. Vuelva a la pestaña **Información general**.  Observe que en la parte superior derecha de la página se muestra el mensaje "Asociado con: 0 subredes, 1 interfaz de red. La interfaz ya está asignada al grupo. Haga énfasis también en las reglas predeterminadas. En el caso de las reglas de entrada, solo se permitirá el tráfico procedente de otras redes virtuales de Azure y Azure Load Balancer. El rastro del tráfico de entrada a la máquina virtual será denegado. Haga hincapié también en las reglas de salida predeterminadas.  Solo se permitirá el tráfico de salida a otras redes virtuales y el tráfico de salida de Internet.  Se recomienda que, como parte de la demo, dedique un minuto a demostrar que se deniega el tráfico de entrada.
    1. En la barra de búsqueda de la parte superior de la página, escriba y seleccione **Máquinas virtuales**.
    1. En la página Máquinas virtuales, seleccione **SC900-VMWin**.
    1. En la parte superior de la página SC900-WinVM, seleccione **Conectar** y, luego, **RDP**.
    1. Compruebe que la dirección IP está configurada en Dirección IP pública, deje el número de puerto predeterminado y seleccione **Descargar archivo DRP**.
    1. **Abra** el archivo descargado y seleccione **Conectar**.
    1. Tras unos segundos en los que tratará de conectarse, verá un mensaje de error que le indicará que el escritorio remoto no puede conectarse al equipo remoto. Seleccione **Aceptar**.

1. Ahora que ha demostrado el impacto de las reglas de entrada predeterminadas del grupo de seguridad de red, querrá crear una nueva regla para permitir el tráfico RDP de entrada.  Haga énfasis en el hecho de que no pueden eliminar la reglas predeterminadas existentes; solo puede crear nuevas con una prioridad más alta.
    1. En el panel de navegación izquierdo, debajo de Configuración, seleccione **Redes**.  Se encuentra en la página Redes de la máquina virtual, y aunque puede crear una regla de entrada y otra de salida desde aquí, vuelva a la página Grupos de seguridad de red. Después de todo, ese es el tema de esta demo.  **Seleccione NSG-SC900**. Es el vínculo que aparece en medio de la ventana.

1. Ahora está en la página Información general de Grupos de seguridad de red.  Observe la información sobre el grupo de seguridad de red. En el panel de navegación izquierdo de la página Grupos de seguridad de red, debajo de Configuración, seleccione **Reglas de seguridad de entrada** y, luego, **+ Agregar** en la parte superior de la página. Comente las diferentes configuraciones de la página Agregar regla de seguridad de entrada. Se recomienda que cree la regla para permitir el tráfico RDP de entrada con la siguiente configuración:
    1. Origen: **Cualquiera**
    1. Intervalos de puertos de origen: **\***
    1. Destino: **Cualquiera**
    1. Servicio: **RDP**
    1. Acción: **Permitir**
    1. Prioridad: **300**; Nota: Las reglas con números inferiores tienen una prioridad más alta y se procesan primero. por eso la prioridad de esta nueva regla debe ser más alta que la prioridad de la regla existente que deniega todo el tráfico de entrada.
    1. Nombre: **AllowRDP**
    1. Seleccione **Agregar**.
    1. Una vez que haya aprovisionado la regla, esta aparecerá en la lista de reglas de entrada.

1. Ahora compruebe las **Reglas de seguridad de salida**.  Seleccione **+ Agregar** en la parte superior de la página y comente las diferentes configuraciones.  Mi recomendación es que cree la regla. La configuración que aparece a continuación crea una regla para denegar el tráfico de salida de Internet:
    1. Origen: **Cualquiera**
    1. Intervalos de puertos de origen: **\***
    1. Destino: **Etiqueta de servicio**
    1. Etiqueta de servicio de destino: **Internet**
    1. Servicio: **Personalizado** (deje el valor predeterminado).
    1. Intervalos de puertos de destino: **\*** (asegúrese de poner un asterisco en el campo Intervalos de puerto de destino).
    1. Protocolo: **Cualquiera**
    1. Acción: **Denegar**
    1. Prioridad: **4000** (la razón por la que debe hacer énfasis en este campo es que la prioridad debe ser más alta que la prioridad de la regla existente que permite el tráfico de salida de Internet).
    1. Nombre: **DenyInternet**
    1. Seleccione **Agregar**.
    1. Una vez que haya aprovisionado la regla, esta aparecerá en la lista de reglas de salida.

1. Ahora vuelva a su máquina virtual y pruebe las reglas.  En la parte superior de la página, seleccione **SC900-VM** encima de la opción Reglas de seguridad de salida.

1. Para probar la regla de entrada, compruebe que puede conectarse a la máquina virtual mediante RDP.
    1. Seleccione **Conectar** en el panel de navegación izquierdo.
    1. Compruebe que la dirección IP está configurada en Dirección IP pública, deje el número de puerto predeterminado y seleccione **Descargar archivo DRP**.
    1. **Abra** el archivo descargado y seleccione **Conectar**.
    1. A continuación, se le pedirán las credenciales. Escriba el nombre de usuario y la contraseña que ha usado al crear la máquina virtual.  Si en la ventana se le pide un PIN además de sus credenciales, seleccione **Opciones adicionales** y luego seleccione **Usar otra cuenta**.
    1. Se abrirá la ventana Conexión a Escritorio remoto con el mensaje: No se puede comprobar la identidad del equipo remoto. ¿Desea conectarse de todos modos? Seleccione **Sí**.
    1. Ahora está conectado a la VM. Recalque ante el estudiante el hecho de que en este caso ha podido conectarse a la máquina virtual porque la regla de tráfico de salida que ha creado permite el tráfico de entrada a la máquina virtual mediante RDP.

1. Ahora pruebe la regla de salida del grupo de seguridad de red.
    1. Abra el explorador Edge en la máquina virtual.
    1. Escriba **https://www.bing.com** . La página no debería mostrarse. Nota: Si puede conectarse a Internet y ha comprobado que todos los parámetros de la regla de salida están configurados correctamente, puede que sea porque la regla tarda unos minutos en surtir efecto. Espere unos minutos y pruebe otra vez.

1. Cierre la conexión al escritorio remoto. Para ello, seleccione la **X** en la parte superior central de la página donde se muestra la dirección IP. Una ventana emergente indicará que su sesión remota va a desconectarse. Seleccione **Aceptar**.

1. Vuelva a la página principal de Azure Portal. Para ello, seleccione **Microsoft Azure** en la barra azul de la parte superior de la página.

#### <a name="tear-down"></a>Desmontaje
**IMPORTANTE**: En esta tarea eliminará el grupo de recursos y todos los recursos que contiene.   Esto es importante para evitar cargos adicionales.

1. Abra la pestaña SC900-VMWin: Microsoft Azure en su explorador.

1. En la esquina superior izquierda de la página, seleccione **Todos los servicios**.

1. En el cuadro Filtrar servicios que aparece junto a las palabras Todos los servicios, escriba **Grupos de recursos** y luego, en los resultados, seleccione **Grupos de recursos**.

1. Seleccione **LabsSC900-RG**.

1. En la parte superior central de la página LabsSC900-RG, seleccione **Eliminar grupo de recursos**.

1. En la ventana que se abre, escriba el nombre del grupo de recursos, **LabsSC900-RG**, para confirmar la eliminación del grupo de recursos y de todos sus recursos, y luego seleccione **Eliminar** en la parte inferior de la página.

1. Eliminar todos los recursos y el grupo de recursos puede llevar varios minutos.

#### <a name="review"></a>Revisar

En esta demo ha realizado un recorrido por la información y la configuración asociada a un grupo de seguridad de red, incluido el proceso de asociar una interfaz al grupo; ha mostrado el funcionamiento de las reglas de entrada y salida predeterminadas y, por último, ha explicado los pasos necesarios para crear una nueva regla.
