---
demo:
  title: 'Grupos de seguridad de red (NSG) de Azure'
  module: 'Módulo 1: Descripción de las funcionalidades de seguridad básicas en Azure'
---


# <a name="demo-azure-network-security-groups-nsgs"></a>Demostración: Grupos de seguridad de red (NSG) de Azure

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de seguridad básicas en Azure
- Unidad: Descripción de los grupos de seguridad de red de Azure

## <a name="demo-scenario"></a>Escenario de la demo

En esta demostración, explorará la función de los grupos de seguridad de red en Azure y aplicará un grupo de seguridad de red a una máquina virtual creada previamente. Empezará mostrando brevemente información sobre la máquina virtual creada previamente por el host de laboratorio autorizado (ALH). A continuación, mostrará el proceso de creación del grupo de seguridad de red, mostrará las reglas de entrada y salida predeterminadas, creará una nueva regla de RDP para permitir la conexión a la máquina virtual y probarla.

### <a name="demo-part-1"></a>Demo, parte 1

En esta parte, verá algunos de los parámetros asociados a la máquina virtual que se creó para su uso con este laboratorio.

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

### <a name="demo-part-2"></a>Demo, parte 2

En esta parte creará un grupo de seguridad de red, asigne la interfaz de red de la máquina virtual a ese grupo de seguridad de red y cree una nueva regla de entrada para el tráfico RDP.

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

1. En la parte superior de la página debajo de donde dice Essentials, verá información básica sobre el grupo de seguridad de red que creó.  Dos aspectos que se han de tener en cuenta son que no hay ninguna regla de seguridad PERSONALIZADA y no hay subredes ni interfaces de red asociadas a este NSG.  Aunque no hay reglas de seguridad personalizadas, hay reglas de entrada y salida predeterminadas que se incluyen con cada NSG, como se muestra en la página.  Revise las reglas de entrada y salida. Las reglas de entrada predeterminadas deniegan todo el tráfico entrante que no procede de una red virtual o de un equilibrador de carga de Azure.  Las reglas de salida deniegan todo el tráfico saliente, excepto el tráfico entre redes virtuales y el tráfico saliente a Internet.

1. En el panel de navegación izquierdo de la página NSG-SC900, debajo de Configuración, seleccione **Interfaces de red**.
    1. Seleccione **Asociar**.
    1. En el campo para seleccionar asociaciones de interfaz de red, seleccione la **flecha desplegable**, **seleccione sc900-winvmXXX** y, a continuación, seleccione **Aceptar** en la parte inferior de la ventana. Una vez que se haya asociado la interfaz al grupo, se mostrará en la lista.

1. En el panel de navegación izquierdo, seleccione **Reglas de seguridad de entrada**. Las reglas de entrada predeterminadas deniegan todo el tráfico entrante no procedente de una red virtual o de un equilibrador de carga de Azure, por lo que debe configurar una regla para permitir el tráfico RDP entrante (tráfico en el puerto 3389). Recuerde que las reglas predeterminadas no se pueden quitar, pero puede reemplazarlas por reglas de prioridad más alta.

1. En la parte superior de la página, seleccione **Agregar**. En la ventana Agregar regla de seguridad de entrada, especifique la siguiente configuración:
    1. Origen:  **Cualquiera**
    1. Intervalos de puertos de origen: **\***
    1. Destino:  **Cualquiera**
    1. Servicio:  **RDP**
    1. Acción:  **Permitir**
    1. Prioridad:  **1000**; Nota: Las reglas con números inferiores tienen una prioridad más alta y se procesan primero.
    1. Nombre: deje el nombre predeterminado o cree su propio nombre descriptivo.
    1. Observe el signo de advertencia en la parte inferior de la página.  Usamos RDP solo para fines de prueba y para demostrar la funcionalidad del NSG.
    1. Seleccione **Agregar**.

1. Una vez que se haya aprovisionado la regla, esta aparecerá en la lista de reglas de entrada (es posible que tenga que actualizar la pantalla). En la regla recién agregada, verá un signo de advertencia.  Como se indicó anteriormente, solo usamos RDP con fines de prueba y para demostrar la funcionalidad del NSG.

### <a name="demo-part-3"></a>Demo, parte 3

Con el grupo de seguridad de red creado y asociado a la máquina virtual y la regla RDP creada, mostrará el impacto del NSG probando la conectividad RDP con la máquina virtual.

1. Abra la pestaña SC900-VMWin: Microsoft Azure en su explorador. Si ha cerrado previamente la pestaña del explorador, seleccione la barra de búsqueda azul en la parte superior de la página, seleccione Máquinas virtuales y, a continuación, seleccione la máquina virtual **SC900-WinVM**.

1. Para probar la regla de entrada, compruebe que puede conectarse a la máquina virtual mediante RDP.
    1. Seleccione **Conectar** en el panel de navegación izquierdo.
    1. Compruebe que la dirección IP está configurada en Dirección IP pública, deje el número de puerto predeterminado y seleccione **Descargar archivo DRP**.
    1. **Abra** el archivo descargado y seleccione **Conectar**.
    1. Se le pedirán las credenciales. Escriba el nombre de usuario y la contraseña que ha usado al crear la máquina virtual.  Si en la ventana se le pide un PIN además de sus credenciales, seleccione **Opciones adicionales** y luego seleccione **Usar otra cuenta**.
    1. Se abrirá la ventana Conexión a Escritorio remoto con el mensaje: No se puede comprobar la identidad del equipo remoto. ¿Desea conectarse de todos modos? Seleccione **Sí**.
    1. Ahora está conectado a la VM. Recalque ante el estudiante el hecho de que en este caso ha podido conectarse a la máquina virtual porque la regla de tráfico de salida que ha creado permite el tráfico de entrada a la máquina virtual mediante RDP.

1. Puesto que ya está en la máquina virtual, puede mostrar la conectividad saliente a Internet, que está habilitada por una de las reglas de salida predeterminadas.
    1. En la VM, seleccione **Microsoft Edge** para abrir el navegador.  Puesto que esta es la primera vez que abre Microsoft Edge, puede que aparezca una ventana emergente, seleccione **Iniciar sin los datos** y, a continuación, **Continuar sin estos datos** y, luego, seleccione **Confirmar y empezar a navegar**.
    1. Escriba **www.bing.com** en la barra de direcciones del navegador y confirme que puede conectarse al motor de búsqueda.
    1. Una vez que haya confirmado que puede acceder a www.bing.com, cierre la ventana del explorador en la máquina virtual, pero deje la máquina virtual funcionando.

1. Minimice la máquina virtual; para ello, seleccione el carácter de subrayado **_** en la pestaña azul que muestra la dirección IP de la máquina virtual. Esto le lleva de vuelta al SC900-WinVM | Página de conectar.  

### <a name="optional-demo-part-4"></a>Demostración OPCIONAL, parte 4

Si queda suficiente tiempo, es posible que quiera crear una regla de grupo de seguridad de red de salida para bloquear el tráfico saliente de Internet de la máquina virtual.

1. En el panel de navegación izquierdo, seleccione **Redes**. Debería estar en SC900-WinVM | Página de redes.

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
    1. Prioridad: **1000**
    1. Nombre: deje el nombre predeterminado o cree su propio nombre descriptivo.
    1. Seleccione **Agregar**.

1. Una vez que haya aprovisionado la regla, esta aparecerá en la lista de reglas de salida.  Aunque aparezca en la lista, tardará unos minutos en surtir efecto (espere unos minutos antes de continuar con los siguientes pasos).  

1. Vuelva a la máquina virtual (el icono de la máquina virtual debe mostrarse en la barra de tareas de la parte inferior de la página).

1. Abra el navegador Microsoft Edge en su máquina virtual y entre en **www.bing.com**. La página no debería mostrarse.  Nota: Si puede conectarse a Internet y ha comprobado que todos los parámetros de la regla de salida están configurados correctamente, puede que sea porque la regla tarda unos minutos en surtir efecto.  Cierre el navegador, espere unos minutos y vuelva a intentarlo.  Nota: Las suscripciones de Azure en el entorno de laboratorio pueden experimentar retrasos más largos que los normales.

1. Cierre la conexión al escritorio remoto. Para ello, seleccione la **X** en la parte superior central de la página donde se muestra la dirección IP.  Aparece una ventana emergente que indicará que su sesión remota va a desconectarse. Seleccione **Aceptar**.

1. Cierre todas las pestañas abiertas del explorador.

1. Como procedimiento recomendado general, es beneficioso detener o deshabilitar la máquina virtual para evitar incurrir en costos, si solo se usa con fines de demostración o prueba. Sin embargo, en este caso, no deshabilite la máquina virtual, ya que le ayudará a proporcionar los datos de administración de la posición de seguridad en la nube al realizar la demostración de Microsoft Defender for Cloud.  La máquina virtual se eliminará cuando se termine el laboratorio.

#### <a name="review"></a>Revisar

En esta demo ha realizado un recorrido por la información y la configuración asociada a un grupo de seguridad de red, incluido el proceso de asociar una interfaz al grupo; ha mostrado el funcionamiento de las reglas de entrada y salida predeterminadas y, por último, ha explicado los pasos necesarios para crear una nueva regla.
