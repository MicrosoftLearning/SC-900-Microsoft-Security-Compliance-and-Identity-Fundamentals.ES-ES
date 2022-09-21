---
ms.openlocfilehash: d2377516343cb85c279c1a2d6347c59f573d73c7
ms.sourcegitcommit: 15658ca1c7bae8a4dbaa33ab6f897070bde521b9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/12/2022
ms.locfileid: "147892202"
---
<a name="---"></a><!---
---
Laboratorio: Título: "Exploración de los grupos de seguridad de red (NSG) de Azure" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft; Módulo 1: Descripción de las funcionalidades de seguridad básicas en Azure; Unidad 6: Descripción de los grupos de seguridad de red de Azure"
---
--->

# <a name="lab-explore-azure-network-security-groups-nsgs"></a>Laboratorio: Explore Azure Network Security Groups (NSGs)

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de seguridad básicas en Azure
- Unidad: Descripción de los grupos de seguridad de red de Azure

## <a name="lab-scenario"></a>Escenario del laboratorio

En este laboratorio. Explorará la función de los grupos de seguridad de red en Azure.  Para ello, creará la VM sin ningún grupo de seguridad de red (NSG). A continuación, aprenderá el proceso de crear un NSG y de asignar la interfaz de la VM a ese NSG.  Una vez completada la configuración, observará las reglas de entrada y salida predeterminadas y creará nuevas reglas.
  
**Tiempo estimado**: 15-20 minutos

### <a name="task-1"></a>Tarea 1

En esta tarea, creará una máquina virtual de Windows 10.

1. Abrir Microsoft Edge.  En la barra de direcciones, escriba **portal.azure.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es el id. de inquilino único facilitado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.

    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Haga clic en **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.
1. En la esquina superior izquierda de la pantalla, junto a las palabras Microsoft Azure, seleccione el icono Mostrar el menú del portal (las tres líneas horizontales, también denominadas icono de hamburguesa) y luego seleccione **Todos los servicios**.  
1. En la ventana principal, en Destacado, seleccione Máquinas virtuales.  Si no ve Máquinas virtuales en la lista, escríbalo en la barra de búsqueda y luego selecciónelo en los resultados.
1. En la parte superior izquierda de la página, seleccione **+Crear** y, luego, **Azure Virtual Machine**.
1. En la pestaña Datos básicos, complete la siguiente información (si alguno de los campos no aparece en esta lista, deje la configuración predeterminada):
    1. Suscripción: compruebe que la configuración predeterminada sea Pase para Azure – Patrocinio.

    1. Grupo de recursos: seleccione **Crear nuevo**. Luego, en el campo Nombre, escriba **LabsSC900** y seleccione **Aceptar**.
    1. Nombre de las máquinas virtuales: escriba **SC900-WinVM**.
    1. Región: si el campo de región no se rellena previamente, seleccione la región más cercana a la ubicación.
    1. Imagen: en el menú desplegable, seleccione **Windows 10 Pro, versión 21H2 - Gen 2**.
    1. Tamaño: seleccione **Ver todos los tamaños** en el menú desplegable y, a continuación, **B2**. Luego, pulse **Seleccionar** en la parte inferior de la página.
    1. Nombre de usuario:  Introduzca el nombre de usuario que quiera.  Apúntelo, ya que lo necesitará para acceder a la máquina virtual.
    1. Contraseña:  Escriba una contraseña de su elección.  Apúntela, ya que la necesitará para acceder a la máquina virtual.
    1. Puertos de entrada públicos: deje el valor predeterminado, **Permitir los puertos seleccionados**.
    1. Seleccionar puertos de entrada: deje el valor predeterminado, **RDP 3389**.
    1. Licencias: seleccione **Confirmo que dispongo de una licencia válida de Windows 10 con derechos de hospedaje multiinquilino** para que aparezca una marca de verificación en el cuadro.
    1. Seleccione **Siguiente: Discos**.
1. Ahora está en la pestaña Discos para configurar la VM.  Deje el resto de los valores predeterminados y seleccione **Siguiente: Redes >** .
1. Ahora se encuentra en la pestaña Redes para configurar la máquina virtual.  En la opción Grupo de seguridad de red de NIC, seleccione **Ninguno**. Deje todas las demás opciones de configuración con su valor predeterminado.  Nota: El propósito de seleccionar Ninguno en este paso es seguir los pasos de creación de un grupo de seguridad de red desde cero, en la siguiente tarea.
1. En la parte inferior de la página, seleccione **Siguiente: Revisar y crear>** y, a continuación, una vez superada la validación, seleccione **Crear**. La implementación de la máquina virtual puede tardar varios minutos en completarse.
1. Una vez finalizada la implementación, seleccione **Ir al recurso**.
1. Ahora se encuentra en la página de SC900-VMWin.
1. En la parte superior de la página, seleccione **Conectar** y luego, en el menú desplegable, seleccione **RDP**.
1. Tenga en cuenta que no se cumple el requisito previo del puerto.  Para cumplir el requisito previo, se debe configurar una regla de seguridad de red de entrada con el puerto de destino 3389, usado por RDP.  Lo hará en la siguiente tarea, cuando cree un grupo de seguridad de red.
1. Deje esta pestaña del explorador abierta.

### <a name="task-2"></a>Tarea 2

Cree un grupo de seguridad de red, asigne la interfaz de red de la máquina virtual a ese grupo de seguridad de red y cree una nueva regla de entrada para el tráfico RDP.

1. Abra la pestaña SC900-VMWin: Microsoft Azure en su explorador.

1. En la esquina superior izquierda de la página, al lado de Microsoft Azure, seleccione el icono del menú Mostrar portal (las tres líneas horizontales también conocidas como icono de hamburguesa) y luego seleccione **Todos los servicios**.
1. En el cuadro Filtrar servicios, al lado de Todos los servicios, escriba **Grupos de seguridad de red** y, de los resultados, seleccione **Grupos de seguridad de red** (no seleccione Grupos de seguridad de red clásicos).
1. En la parte superior de la página Grupos de seguridad de red, seleccione **+ Crear**.
1. En la pestaña Datos básicos de la página Crear grupo de seguridad de red, especifique la siguiente configuración.
    1. Suscripción:  Pase para Azure: Patrocinio.

    1. Grupo de recursos:  **LabsSC900**
    1. Nombre:  **NSG-SC900**
    1. Región: deje el valor predeterminado.
    1. Seleccione **Revisar y crear** y, luego, **Crear**.
1. Una vez finalizada la implementación, seleccione **Ir al recurso**.
1. Observe las reglas de entrada y salida predeterminadas del grupo.  Aunque el grupo se ha creado y hay reglas predeterminadas para filtrar el tráfico, no hay ninguna interfaz asociada a él.
1. En el panel de navegación izquierdo de la página NSG-SC900, debajo de Configuración, seleccione **Interfaces de red**.
1. Seleccione **+ Asociar**, encima del cuadro de búsqueda.
1. En el lado derecho de la página, hay un campo para seleccionar la interfaz de red que se asociará al grupo de seguridad de red. Seleccione la flecha desplegable y, a continuación, seleccione **sc900-winvmXXX** (XXX será específico de la interfaz de red de la máquina virtual) y, a continuación, seleccione **Aceptar** en la parte inferior de la ventana.
1. Una vez que se haya asociado la interfaz al grupo, se mostrará en la lista.
1. En el panel de navegación izquierdo, seleccione **Reglas de seguridad de entrada**.
1. Las reglas de entrada predeterminadas deniegan todo el tráfico entrante no procedente de una red virtual o de un equilibrador de carga de Azure, por lo que debe configurar una regla para permitir el tráfico RDP entrante (tráfico en el puerto 3389). Recuerde que las reglas predeterminadas no se pueden quitar, pero puede reemplazarlas por reglas de prioridad más alta.
1. En la parte superior de la página, seleccione **Agregar**:
1. En la ventana Agregar regla de seguridad de entrada, especifique la siguiente configuración:
    1. Origen:  **Cualquiera**

    1. Intervalos de puertos de origen: **\***
    1. Destino:  **Cualquiera**
    1. Servicio:  **RDP**
    1. Acción:  **Permitir**
    1. Prioridad:  **300**; Nota: Las reglas con números inferiores tienen una prioridad más alta y se procesan primero.
    1. Nombre:  **AllowRDP**
1. Seleccione **Agregar**.
1. Una vez que se haya aprovisionado la regla, esta aparecerá en la lista de reglas de entrada (es posible que tenga que actualizar la pantalla).
1. Ahora compruebe que puede conectarse a la VM mediante RDP.  Seleccione el campo de búsqueda en la parte superior de la página, junto a Microsoft Azure, para ver los servicios recientes.  Seleccione **Máquinas virtuales**.
1. Seleccione la máquina virtual, **SC900-WinVM**.
1. En la parte superior de la página, seleccione **Conectar** y luego, en el menú desplegable, seleccione **RDP**.
1. Compruebe que la dirección IP está configurada en Dirección IP pública, deje el número de puerto predeterminado y seleccione **Descargar archivo DRP**.
1. Abra el archivo descargado y seleccione **Conectar**.
1. A continuación, se le pedirán las credenciales.  Escriba el nombre de usuario y la contraseña que ha usado al crear la máquina virtual.
1. Se abrirá la ventana Conexión a Escritorio remoto con el mensaje: No se puede comprobar la identidad del equipo remoto.  ¿Desea conectarse de todos modos?  Seleccione **Sí**.
1. Ahora está conectado a la VM. En este caso pudo conectarse a la VM porque la regla de tráfico de entrada que creó permite el tráfico de entrada a la VM mediante RDP.
1. Mantenga la VM abierta, la utilizará en la siguiente tarea.

### <a name="task-3"></a>Tarea 3

Las reglas de salida predeterminadas del NSG permiten el tráfico de salida de Internet, así que validará que puede conectarse a Internet.  A continuación, aprenderá el proceso de creación de una regla de salida personalizada para bloquear el tráfico saliente de Internet y probará esa regla.

1. En la VM, seleccione **Edge** para abrir el navegador.  
1. Escriba **www.bing.com** en la barra de direcciones del navegador y confirme que puede conectarse al motor de búsqueda.
1. Cierre el navegador en su VM, pero mantenga la VM abierta, porque la utilizará en los siguientes pasos.
1. Vuelva a Azure Portal, abra la pestaña SC900-VMWin: Microsoft Azure en su navegador.
1. En el panel de navegación izquierdo, debajo de Configuración, seleccione **Redes**.
1. Seleccione la pestaña **Reglas de puerto de salida**.  Verá las reglas de salida predeterminadas.  Observe la regla predeterminada "AllowInternetOutBound". Esta regla permite todo el tráfico de salida de Internet. Las regla predeterminada no se puede quitar, pero puede reemplazarla con una regla de prioridad más alta. En la parte derecha de la página, seleccione **Agregar regla de puerto de salida**.
1. En la página Agregar regla de seguridad de salida, especifique la siguiente configuración:
    1. Origen:  **Cualquiera**

    1. Intervalos de puertos de origen: **\***
    1. Destino:  **Etiqueta de servicio**
    1. Etiqueta de servicio de destino:  **Internet**
    1. Servicio:  **Personalizado** (deje el valor predeterminado).
    1. Intervalos de puertos de destino: * (asegúrese de poner un asterisco en el campo Intervalos de puerto de destino)
    1. Protocolo: **Cualquiera**
    1. Acción: **Denegar**
    1. Prioridad:  **4000**
    1. Nombre:  **DenyInternet**
1. Seleccione **Agregar**.
1. Una vez que haya aprovisionado la regla, esta aparecerá en la lista de reglas de salida.  Aunque aparezca en la lista, tardará unos minutos en surtir efecto (espere unos minutos antes de continuar con los siguientes pasos).  
1. Vuelva a su VM.
1. Abra el navegador Edge en su máquina virtual y entre en **www.bing.com**. La página no debería mostrarse.  Nota: Si puede conectarse a Internet y ha comprobado que todos los parámetros de la regla de salida están configurados correctamente, puede que sea porque la regla tarda unos minutos en surtir efecto.  Cierre el navegador, espere unos minutos y vuelva a intentarlo.
1. Cierre la conexión al escritorio remoto. Para ello, seleccione la **X** en la parte superior central de la página donde se muestra la dirección IP.  Una ventana emergente indicará que su sesión remota va a desconectarse. Seleccione **Aceptar**.
1. En esta tarea configuró correctamente una regla de salida en su NSG para bloquear el tráfico saliente de Internet.

### <a name="tear-down"></a>Desmontaje

Las máquinas virtuales son un recurso facturado y, aunque el costo de ejecutar las máquinas virtuales en esta demostración es mínimo, se recomienda que al finalizar el curso elimine el grupo de recursos que contiene la máquina virtual y los recursos asociados.

1. Abra la pestaña SC900-VMWin: Microsoft Azure en su explorador.

1. En la esquina superior izquierda de la página, seleccione **Todos los servicios**.
1. En el cuadro Filtrar servicios que aparece junto a las palabras Todos los servicios, escriba **Grupos de recursos** y luego, en los resultados, seleccione **Grupos de recursos**.
1. Seleccione **LabsSC900**.
1. En la parte superior central de la página LabsSC900, seleccione **Eliminar grupo de recursos**.
1. En la ventana que se abrirá, escriba el nombre del grupo de recursos, **LabsSC900** para confirmar la eliminación del grupo de recursos y de todos sus recursos, y luego seleccione **Eliminar** en la parte inferior de la página.
1. Eliminar todos los recursos y el grupo de recursos puede llevar varios minutos.
1. Cierre todas las pestañas abiertas del explorador.

### <a name="review"></a>Revisar

En este laboratorio, ha examinado el proceso de configuración de un grupo de seguridad de red (NSG), asociando ese grupo de seguridad de red a la interfaz de red de una máquina virtual, y agregando nuevas reglas al grupo de seguridad de red para permitir el tráfico RDP entrante y bloquear el tráfico saliente de Internet.
