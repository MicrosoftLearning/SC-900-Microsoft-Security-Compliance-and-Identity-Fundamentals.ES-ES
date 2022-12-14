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

En este laboratorio, explorará la función de los grupos de seguridad de red en Azure.  Para ello, creará un grupo de seguridad de red (NSG) y asignará el NSG a la interfaz de una máquina virtual (VM) existente previamente.  Una vez completada la configuración, observará las reglas de entrada y salida predeterminadas, creará nuevas reglas y las probará.  En este laboratorio, la máquina virtual que usará con el grupo de seguridad de red se crea automáticamente, por lo que primero verá parte de la información asociada a esa máquina virtual.
  
**Tiempo estimado**: 30-45 minutos

### <a name="task-1"></a>Tarea 1

En esta tarea, verá algunos de los parámetros asociados a la máquina virtual que se ha creado para su uso con este laboratorio.

1. Abrir Microsoft Edge.  En la barra de direcciones escriba **portal.azure.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana Inicio de sesión, escriba el nombre de usuario proporcionado por el proveedor de hospedaje de laboratorio y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Si aparece un mensaje para preguntarle si quiere mantener iniciada la sesión, seleccione **Sí**.

1. En la parte superior de la página, debajo de donde pone Servicios de Azure, seleccione **Máquina virtuales**.  Si no aparece, en el cuadro de búsqueda, en la barra azul de la parte superior de la página que hay junto a las palabras Microsoft Azure, escriba **Máquinas virtuales** y luego seleccione **Máquinas virtuales** en los resultados de la búsqueda.

1. En la página Máquinas virtuales, seleccione la máquina virtual que aparece como **SC900-WinVM**.

1. Ahora se encuentra en la página de SC900-WinVM.  Observe el nombre del grupo de recursos, LabsSC900, en el que reside la máquina virtual.

1. En la parte superior de la página, seleccione **Conectar** y luego, en el menú desplegable, seleccione **RDP**. Tenga en cuenta que no se cumple el requisito previo del puerto.  Para cumplir el requisito previo, se debe configurar una regla de seguridad de red de entrada con el puerto de destino 3389, usado por RDP.  Lo hará en la siguiente tarea, cuando cree un grupo de seguridad de red.

1. En el panel de navegación izquierdo, seleccione **Redes**.  
    1. La vista predeterminada es para las reglas de puerto de entrada.  Tenga en cuenta que la interfaz de red de esta máquina virtual no tiene ningún grupo de seguridad de red configurado.  Lo mismo sucede si selecciona Reglas de puerto de salida.
    1. Seleccione **Reglas de seguridad vigentes** junto a donde dice Interfaz de red.  Observe que dice: "No hay ningún grupo de seguridad de red o grupo de seguridad de aplicaciones asociado a la interfaz de red".
1. Deje esta pestaña del explorador abierta.

### <a name="task-2"></a>Tarea 2

En esta tarea, creará un grupo de seguridad de red, asignará la interfaz de red de la máquina virtual a ese grupo de seguridad de red y creará una nueva regla de entrada para el tráfico RDP.

1. Abra la pestaña SC900-VMWin: Microsoft Azure en su explorador.

1. En la barra de búsqueda azul de la parte superior de la página, escriba **Grupos de seguridad de red**. En los resultados, seleccione **Grupos de seguridad de red** (no seleccione Grupos de seguridad de red clásicos).

1. En la parte superior de la página Grupos de seguridad de red, seleccione **+ Crear**.

1. En la pestaña Datos básicos de la página Crear grupo de seguridad de red, especifique la siguiente configuración.
    1. Suscripción: deje el valor predeterminado (esta es la suscripción de Azure proporcionada por el host de laboratorio autorizado).
    1. Grupo de recursos:  **LabsSC900**
    1. Nombre:  **NSG-SC900**
    1. Región: deje el valor predeterminado.
    1. Seleccione **Revisar y crear** y, luego, **Crear**.

1. Una vez finalizada la implementación, seleccione **Ir al recurso**.

1. En la parte superior de la página debajo de donde dice Essentials, verá información básica sobre el grupo de seguridad de red que creó.  Dos aspectos que se han de tener en cuenta son que no hay ninguna regla de seguridad personalizada y no hay subredes ni interfaces de red asociadas a este NSG.  Aunque no hay reglas de seguridad personalizadas, hay reglas de entrada y salida predeterminadas que se incluyen con cada NSG, como se muestra en la página.  Revise las reglas de entrada y salida. Las reglas de entrada predeterminadas deniegan todo el tráfico entrante que no procede de una red virtual o de un equilibrador de carga de Azure.  Las reglas de salida deniegan todo el tráfico saliente, excepto el tráfico entre redes virtuales y el tráfico saliente a Internet.

1. En el panel de navegación izquierdo de la página NSG-SC900, debajo de Configuración, seleccione **Interfaces de red**.
    1. Seleccione **Asociar**.
    2. En el campo para las asociaciones de interfaz de red, seleccione la **flecha desplegable**, seleccione **sc900-winvmXXX** y, a continuación, seleccione **Aceptar** en la parte inferior de la ventana. Una vez que se haya asociado la interfaz al grupo, se mostrará en la lista.

1. En el panel de navegación izquierdo, seleccione **Reglas de seguridad de entrada**.

1. Las reglas de entrada predeterminadas deniegan todo el tráfico entrante no procedente de una red virtual o de un equilibrador de carga de Azure, por lo que debe configurar una regla para permitir el tráfico RDP entrante (tráfico en el puerto 3389). Recuerde que las reglas predeterminadas no se pueden quitar, pero puede reemplazarlas por reglas de prioridad más alta.

1. En la parte superior de la página, seleccione **Agregar**. En la ventana Agregar regla de seguridad de entrada, especifique la siguiente configuración:
    1. Origen:  **Cualquiera**
    1. Intervalos de puertos de origen: **\***
    1. Destino:  **Cualquiera**
    1. Servicio:  **RDP**
    1. Acción:  **Permitir**
    1. Prioridad:  **1000**. Nota: Las reglas con números inferiores tienen una prioridad más alta y se procesan primero.
    1. Nombre: deje el nombre predeterminado o cree su propio nombre descriptivo.
    1. Observe el signo de advertencia en la parte inferior de la página.  Usamos RDP solo para fines de prueba y para demostrar la funcionalidad del NSG.
    1. Seleccione **Agregar**.

1. Una vez que se haya aprovisionado la regla, esta aparecerá en la lista de reglas de entrada (es posible que tenga que actualizar la pantalla). En la regla recién agregada, verá un signo de advertencia.  Como se indicó anteriormente, solo usamos RDP con fines de prueba y para demostrar la funcionalidad del NSG. Seleccione la regla recién agregada.

### <a name="task-3"></a>Tarea 3

En esta tarea, probará la regla de NSG de entrada recién creada para confirmar que puede establecer una conexión de escritorio remoto (RDP) con la máquina virtual.  Una vez dentro de la máquina virtual, comprobará la conectividad saliente a Internet desde la máquina virtual.

1. Abra la pestaña SC900-VMWin: Microsoft Azure en su explorador. Si ha cerrado previamente la pestaña del explorador, seleccione la barra de búsqueda azul en la parte superior de la página, seleccione Máquinas virtuales y, a continuación, seleccione la máquina virtual **SC900-WinVM**.

1. En la parte superior de la página, seleccione **Conectar** y, a continuación, seleccione **RDP**.

1. Compruebe que la dirección IP está configurada en Dirección IP pública, deje el número de puerto predeterminado y seleccione **Descargar archivo DRP**.

1. En la ventana emergente que aparece, seleccione **Abrir archivo**.

1. Se abre una ventana Conexión a Escritorio remoto; seleccione **Conectar**.

1. Se le pedirán las credenciales.  Escriba el nombre de usuario y la contraseña (consulte la pestaña recursos del panel de instrucciones del laboratorio).

1. Se abrirá la ventana Conexión a Escritorio remoto con el mensaje: No se puede comprobar la identidad del equipo remoto.  ¿Desea conectarse de todos modos?  Seleccione **Sí**.

1. Ahora está conectado a la máquina virtual. En este caso pudo conectarse a la VM porque la regla de tráfico de entrada que creó permite el tráfico de entrada a la VM mediante RDP.

1. Al cabo de unos segundos, en la pantalla de bienvenida verá una ventana para elegir la configuración de privacidad del dispositivo; seleccione **Aceptar**.  En la ventana Redes, seleccione **No**.

1. Una vez que la máquina virtual esté en funcionamiento, pruebe la conectividad saliente a Internet desde la máquina virtual.
    1. En la máquina virtual, seleccione **Microsoft Edge** para abrir el explorador.  Puesto que esta es la primera vez que abre Microsoft Edge, puede que aparezca una ventana emergente, seleccione **Iniciar sin los datos** y, a continuación, **Continuar sin estos datos** y, luego, seleccione **Confirmar y empezar a navegar**.
    1. Escriba **www.bing.com** en la barra de direcciones del navegador y confirme que puede conectarse al motor de búsqueda.
    1. Una vez que haya confirmado que puede acceder a www.bing.com, cierre la ventana del explorador en la máquina virtual, pero deje la máquina virtual funcionando.

1. Minimice la máquina virtual; para ello, seleccione el carácter de subrayado **_** en la pestaña azul que muestra la dirección IP de la máquina virtual. Esto le lleva de vuelta al SC900-WinVM | Página Conectar. 

1. En el panel de navegación izquierdo, seleccione **Redes**.

1. Deje la pestaña del explorador abierta, porque la utilizará en la siguiente tarea.

### <a name="task-4"></a>Tarea 4

En la tarea anterior, ha confirmado que podía establecer una conexión RDP a la máquina virtual. Una vez en la máquina virtual, también ha confirmado que podía establecer una conexión saliente a Internet.  El tráfico saliente a Internet se ha permitido porque las reglas de salida predeterminadas para el grupo de seguridad de red permiten el tráfico saliente a Internet.  En esta tarea, realizará un recorrido por el proceso de creación de una regla de salida personalizada para bloquear el tráfico saliente a Internet y probará esa regla.

1. Debería estar en SC900-WinVM | Página Redes. Si ha cerrado previamente la pestaña del explorador, seleccione la barra de búsqueda azul en la parte superior de la página, seleccione Máquinas virtuales, luego seleccione la máquina virtual **SC900-WinVM** y, por último, seleccione **Redes**.

1. Seleccione la pestaña **Reglas de puerto de salida**. Verá las reglas de salida predeterminadas.  Observe la regla predeterminada "AllowInternetOutBound". Esta regla permite todo el tráfico de salida de Internet. Las regla predeterminada no se puede quitar, pero puede reemplazarla con una regla de prioridad más alta. En la parte derecha de la página, seleccione **Agregar regla de puerto de salida**.

1. En la página Agregar regla de seguridad de salida, especifique la siguiente configuración:
    1. Origen:  **Cualquiera**
    1. Intervalos de puertos de origen: **\***
    1. Destino:  **Etiqueta de servicio**
    1. Etiqueta de servicio de destino:  **Internet**
    1. Servicio:  **Personalizado** (deje el valor predeterminado).
    1. Intervalos de puertos de destino: * (asegúrese de poner un asterisco en el campo Intervalos de puerto de destino)
    1. Protocolo: **Cualquiera**
    1. Acción: **Denegar**
    1. Prioridad: **1000**
    1. Nombre: deje el nombre predeterminado o cree su propio nombre descriptivo.
    1. Seleccione **Agregar**.

1. Una vez que haya aprovisionado la regla, esta aparecerá en la lista de reglas de salida.  Aunque aparezca en la lista, tardará unos minutos en surtir efecto (espere unos minutos antes de continuar con los siguientes pasos).  

1. Vuelva a la máquina virtual (el icono de la máquina virtual debe mostrarse en la barra de tareas de la parte inferior de la página).

1. Abra el navegador Microsoft Edge en su máquina virtual y entre en **www.bing.com**. La página no debería mostrarse.  Nota: Si puede conectarse a Internet y ha comprobado que todos los parámetros de la regla de salida están configurados correctamente, puede que sea porque la regla tarda unos minutos en surtir efecto.  Cierre el navegador, espere unos minutos y vuelva a intentarlo.  Nota: Las suscripciones de Azure en el entorno de laboratorio pueden experimentar retrasos más largos que los normales.

1. Cierre la conexión al escritorio remoto. Para ello, seleccione la **X** en la parte superior central de la página donde se muestra la dirección IP.  Aparece una ventana emergente que indicará que su sesión remota va a desconectarse. Seleccione **Aceptar**.

1. Cierre todas las pestañas abiertas del explorador.

### <a name="review"></a>Revisar

En este laboratorio, ha examinado el proceso para configurar un grupo de seguridad de red (NSG), asociar ese grupo de seguridad de red a la interfaz de red de una máquina virtual y agregar nuevas reglas al grupo de seguridad de red para permitir el tráfico RDP entrante y bloquear el tráfico saliente a Internet.
