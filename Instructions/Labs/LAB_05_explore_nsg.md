---
lab:
    title: 'Explorar los grupos de seguridad de red de Azure (NSG)'
    module: 'Módulo 3, lección 1: Describir las funcionalidades de las soluciones de seguridad de Microsoft. Describir las funcionalidades de seguridad básicas en Azure.'
---


# Laboratorio: Explorar los grupos de seguridad de red de Azure (NSG).

## Escenario del laboratorio
En este laboratorio. Explorará la función de los grupos de seguridad de red en Azure.  Para ello, creará la VM sin ningún grupo de seguridad de red (NSG).  Sin ningún NSG que filtre el tráfico, todos los puertos de la VM están expuestos a la Internet pública.  A continuación, aprenderá el proceso de crear un NSG y de asignar la interfaz de la VM a ese NSG.  Una vez configurada, probará la conexión a la máquina virtual mediante las reglas predeterminadas del grupo de seguridad de red y las reglas que va a crear.
  

**Tiempo estimado**: 15-20 minutos

#### Tarea 1:  En esta tarea, creará una máquina virtual de Windows 10.    
1.	Abra Microsoft Edge.  En la barra de direcciones, escriba **portal.azure.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.

    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.
1. En la esquina superior izquierda de la pantalla, al lado de Microsoft Azure, seleccione el icono del menú Mostrar portal (las tres líneas horizontales también conocidas como icono de hamburguesa) y luego seleccione **Todos los servicios**.  
1. En la ventana principal, en Destacado, seleccione Máquinas virtuales.  Si no ve Máquinas virtuales en la lista, escríbalo en la barra de búsqueda y luego selecciónelo en los resultados.
1. En la parte superior izquierda de la página, seleccione **+Crear** y luego seleccione **+Máquina virtual**.
1. En la pestaña Datos básicos, complete la siguiente información (si alguno de los campos no aparece en esta lista, deje la configuración predeterminada):
    1. Suscripción: compruebe que la configuración predeterminada sea Pase para Azure – Patrocinio.

    1. Grupo de recursos:  seleccione **Crear nuevo**, en el campo Nombre, escriba **LabsSC900** y luego seleccione **Aceptar**.
    1. Nombre de máquina virtual:  escriba **SC900-WinVM**.
    1. Imagen:  en el menú desplegable, seleccione **Windows 10 Pro, Versión 20H2: Generación 1**.
    1. Tamaño:  seleccione **Ver todos los tamaños** en el menú desplegable, seleccione **B2** y luego presione **Seleccionar** en la parte inferior de la página.
    1. Nombre de usuario:  escriba **UsuarioAzure**.
    1. Contraseña:  escriba **SC900AzureLabs**.
    1. Puertos de entrada públicos:  seleccione **Ninguno**.
    1. Licencia:  seleccione **Confirmo que tengo una licencia de Windows 10 elegible con derechos de hospedaje multiinquilino**, para que aparezca una marca de verificación en el cuadro.
    1. Seleccione **Siguiente: Discos**. 
1. Ahora está en la pestaña Discos para configurar la VM.  Deje el resto de valores predeterminados y seleccione **Siguiente: Redes >**.
1. Ahora se encuentra en la pestaña Redes para configurar la máquina virtual.  Complete la siguiente información (si alguno de los campos no aparece en esta lista, deje la configuración predeterminada):
    1. Grupo de seguridad de red NIC:  seleccione **Ninguno**.

    1. Seleccione **Siguiente:  Administración >**.
1. Ahora está en la pestaña Administración para configurar la VM.  Deje el resto de valores predeterminados y seleccione **Siguiente: Avanzado>**.
1. Ahora está en la pestaña Avanzado para configurar la VM.  Deje el resto de valores predeterminados y seleccione **Siguiente: Etiquetas>**.
1. Ahora está en la pestaña Etiquetas. para configurar la VM.  Deje el resto de valores predeterminados y seleccione **Siguiente: Revisar y crear>**.
1. Revise la configuración de su máquina virtual.  Algunos puntos que se deben tener en cuenta: Esta máquina virtual tiene una dirección IP pública y no cuenta con ningún grupo de seguridad de red NIC.  Desde el punto de vista de la seguridad, esto deja expuesta a la VM.  Abordaremos este problema en una de las siguientes tareas. Seleccione Crear.  La implementación de la máquina virtual puede tardar varios minutos en completarse.
1. Anote el nombre de la interfaz de red, **sc900-winvmXXX** (el XXX será específico de la interfaz de red de su máquina virtual).
1. Una vez finalizada la implementación, seleccione **Ir al recurso**.
1. Ahora se encuentra en la página de SC900-WinVM.  Anote la dirección IP pública. 
1. En la parte superior de la página, seleccione **Conectar** y luego, en el menú desplegable, seleccione **RDP**.
1. Compruebe que la dirección IP está configurada en Dirección IP pública, deje el número de puerto predeterminado y seleccione **Descargar archivo DRP**. 
1. Abra el archivo descargado y seleccione **Conectar**. 
1. A continuación, se le pedirán las credenciales.  En Nombre de usuario, escriba **UsuarioAzure**.  En Contraseña, escriba **SC900AzureLabs**. 
1. Se abrirá la ventana Conexión a Escritorio remoto con el mensaje: No se puede comprobar la identidad del equipo remoto.  ¿Desea conectarse de todos modos?  Seleccione **Sí**.
1. Se ha conectado a la máquina virtual de Windows que acaba de crear. Siga las indicaciones para completar la configuración de Windows. Aunque se ha conectado a la máquina virtual a través de RDP y de uno de los puertos RDP más utilizados, todos los puertos de esta máquina virtual están abiertos y no hay nada que filtre el tráfico. 
1. Cierre la conexión al escritorio remoto. Para ello, seleccione la **X** en la parte superior central de la página donde se muestra la dirección IP.  Una ventana emergente indicará que su sesión remota va a desconectarse. Seleccione **Aceptar**.
1. Ha vuelto a la página de SC900-WinVM en Azure Portal.  Deje esta pestaña del explorador abierta para la siguiente tarea.

#### Tarea 2:  Crear un grupo de seguridad de red y asignar la interfaz de red de la VM a ese NSG.

1. Abra la pestaña SC900-WinVM – Microsoft Azure en su navegador.

1. En la esquina superior izquierda de la página, al lado de Microsoft Azure, seleccione el icono del menú Mostrar portal (las tres líneas horizontales también conocidas como icono de hamburguesa) y luego seleccione **Todos los servicios**.
1. En el cuadro Filtrar servicios, al lado de Todos los servicios, escriba **Grupos de seguridad de red** y, de los resultados, seleccione **Grupos de seguridad de red** (no seleccione Grupos de seguridad de red clásicos).
1. En la parte superior de la página Grupos de seguridad de red, seleccione **+ Crear**.
1. En la pestaña Datos básicos de la página Crear grupo de seguridad de red, especifique la siguiente configuración.
    1. Suscripción:  Pase para Azure: Patrocinio.

    1. Grupo de recursos:  **LabsSC900.**
    1. Nombre:  **NSG-SC900.**
    1. Región:  deje el valor predeterminado **Este de EE. UU. (EE. UU)**.
    1. Seleccione **Revisar y crear** y, luego, **Crear**.
1. Una vez finalizada la implementación, seleccione **Ir al recurso**.
1. Observe las reglas de entrada y salida predeterminadas del grupo.  Aunque se creó el NSG y hay reglas predeterminadas para filtrar el tráfico, no se ha asociado ninguna interfaz al NSG, por lo que la VM aún será vulnerable con todos sus puertos expuestos a la Internet pública.
1. En el panel de navegación izquierdo de la página NSG-SC900, debajo de Configuración, seleccione **Interfaces de red**.
1. Seleccione **+ Asociar**, encima del cuadro de búsqueda.
1. En la página de asociación de la interfaz de red, seleccione **sc900-winvmXXX** (las XXX especificarán la interfaz de red de su VM).  Puesto que se está asociando la interfaz, verá un cuadro de notificación en la esquina superior derecha de la pantalla.
1. Una vez que se haya asociado la interfaz al grupo, se mostrará en la lista.
1. Gracias a la interfaz de la VM asociada al grupo de seguridad de red y las reglas predeterminadas del NSG, cualquier intento de conexión a la VM debería fallar.  
1. En la esquina superior izquierda de la página, seleccione **Todos los servicios** y, debajo de destacados, seleccione **Máquinas virtuales**.
1. En la página Máquinas virtuales, seleccione **SC900-WinVM**.
1. En la parte superior de la página **SC900-WinVM**, seleccione **Conectar** y, luego, **RDP**.
1. Compruebe que la dirección IP está configurada en Dirección IP pública, deje el número de puerto predeterminado y seleccione **Descargar archivo DRP**.
1. Abra el archivo descargado y seleccione **Conectar**.
1. Tras unos segundos en los que tratará de conectarse, verá un mensaje de error que le indicará que el escritorio remoto no puede conectarse al equipo remoto.  Seleccione **Aceptar**.

#### Tarea 3: en esta tarea, creará una regla NSG para permitir el tráfico entrante mediante RDP en el puerto 3389.  Luego probará esa regla e intentará conectarse a la VM mediante RDP. 

1. Abra la pestaña SC900-WinVM – Microsoft Azure en su navegador.

1. En el panel de navegación izquierdo, debajo de Configuración, seleccione **Redes**.
1. Si selecciona la pestaña Reglas de puerto de entrada, verá las reglas de entrada predeterminadas. Las reglas predeterminadas no se pueden quitar, pero puede reemplazarlas con reglas de prioridad más alta. En la parte derecha de la página, seleccione **Agregar regla de puerto de entrada**:
1. En la página Agregar regla de seguridad de entrada, especifique la siguiente configuración:
    1. Origen:  **Cualquiera.**

    1. Intervalos de puertos de origen: *
    1. Destino:  **Cualquiera.**
    1. Servicio:  **RDP**
    1. Acción:  **Permitir**
    1. Prioridad:  **300**; Nota: Las reglas con números inferiores tienen una prioridad más alta y se procesan primero;
    1. Nombre:  **AllowRDP**
1. Seleccione **Agregar**.
1. Una vez que haya aprovisionado la regla, esta aparecerá en la lista de reglas de entrada.
1. Ahora compruebe que puede conectarse a la VM mediante RDP.  Seleccione **Conectar** en el panel de navegación izquierdo.
1. Compruebe que la dirección IP está configurada en Dirección IP pública, deje el número de puerto predeterminado y seleccione **Descargar archivo DRP**.
1. Abra el archivo descargado y seleccione **Conectar**.
1. A continuación, se le pedirán las credenciales.  En Nombre de usuario, escriba **UsuarioAzure**.  En Contraseña, escriba **SC900AzureLabs**.
1. Se abrirá la ventana Conexión a Escritorio remoto con el mensaje: No se puede comprobar la identidad del equipo remoto.  ¿Desea conectarse de todos modos?  Seleccione **Sí**.
1. Ahora está conectado a la VM. En este caso pudo conectarse a la VM porque la regla de tráfico de entrada que creó permite el tráfico de entrada a la VM mediante RDP.
1. Mantenga la VM abierta, la utilizará en la siguiente tarea.

#### Tarea 4:  Las reglas de salida predeterminadas del NSG permiten el tráfico de salida de Internet, así que validará que puede conectarse a Internet.  A continuación, aprenderá el proceso de creación de una regla de salida personalizada para bloquear el tráfico saliente de Internet y probará esa regla.

1. En la VM, seleccione **Edge** para abrir el navegador.  
1. Escriba **https://www.bing.com** en la barra de direcciones del navegador y confirme que puede conectarse al motor de búsqueda.
1. Cierre el navegador en su VM, pero mantenga la VM abierta, porque la utilizará en los siguientes pasos.
1. Vuelva a Azure Portal, abra la pestaña SC900-WinVM – Microsoft Azure en su navegador.
1. En el panel de navegación izquierdo, debajo de Configuración, seleccione **Redes**.
1. Seleccione la pestaña **Reglas de puerto de salida**.  Verá las reglas de salida predeterminadas.  Observe la regla predeterminada "AllowInternetOutBound". Esta regla permite todo el tráfico de salida de Internet. Las regla predeterminada no se puede quitar, pero puede reemplazarla con una regla de prioridad más alta. En la parte derecha de la página, seleccione **Agregar regla de puerto de salida**.
1. En la página Agregar regla de seguridad de salida, especifique la siguiente configuración:
    1. Origen:  **Cualquiera.**

    1. Intervalos de puertos de origen:  *
    1. Destino:  **Etiqueta de servicio.**
    1. Etiqueta de servicio de destino:  **Internet.**
    1. Servicio:  **Personalizado** (deje el valor predeterminado).
    1. Intervalos de puertos de destino:  * (asegúrese de poner un asterisco en el campo de intervalos de puertos de destino)
    1. Protocolo: **Cualquiera.**
    1. Acción: **Denegar.**
    1. Prioridad:  **4000**
    1. Nombre:  **DenyInternet.**
1. Seleccione **Agregar**.
1. Una vez que haya aprovisionado la regla, esta aparecerá en la lista de reglas de salida.  Aunque aparezca en la lista, tardará unos minutos en surtir efecto (espere unos minutos antes de continuar con los siguientes pasos).  
1. Vuelva a su VM.
1. Abra el navegador Edge en su VM y entre en **https://www.bing.com**.  La página no debería mostrarse.  Nota: Si puede conectarse a Internet y ha comprobado que todos los parámetros de la regla de salida están configurados correctamente, puede que sea porque la regla tarda unos minutos en surtir efecto.  Cierre el navegador, espere unos minutos y vuelva a intentarlo.
1. Cierre la conexión al escritorio remoto. Para ello, seleccione la **X** en la parte superior central de la página donde se muestra la dirección IP.  Una ventana emergente indicará que su sesión remota va a desconectarse. Seleccione **Aceptar**.
1. En esta tarea configuró correctamente una regla de salida en su NSG para bloquear el tráfico saliente de Internet.

#### Tarea 5:  IMPORTANTE: En esta tarea eliminará el grupo de recursos y todos los recursos que contiene.   Esto es importante para evitar cargos adicionales.

1. Abra la pestaña SC900-WinVM – Microsoft Azure en su navegador.

1. En la esquina superior izquierda de la página, seleccione **Todos los servicios**.
1. En el cuadro Filtrar servicios que aparece junto a las palabras Todos los servicios, escriba **Grupos de recursos** y luego, en los resultados, seleccione **Grupos de recursos**.
1. Seleccione **LabsSC900**.
1. En la parte superior central de la página LabsSC900, seleccione **Eliminar grupo de recursos**.
1. En la ventana que se abrirá, escriba el nombre del grupo de recursos, **LabsSC900** para confirmar la eliminación del grupo de recursos y de todos sus recursos, y luego seleccione **Eliminar** en la parte inferior de la página.
1. Eliminar todos los recursos y el grupo de recursos puede llevar varios minutos.

#### Revisión

En este laboratorio aprendió el proceso de configuración de una VM con y sin grupo de seguridad de red (NSG) y vio el impacto de las reglas NSG predeterminadas.  También aprendió el proceso de creación de normas del NSG.
