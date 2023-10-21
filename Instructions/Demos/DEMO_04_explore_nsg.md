<!---
---
Demostración: Título: "Grupos de seguridad de red (NSG) de Azure" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft; Módulo 1: Descripción de las funcionalidades de seguridad básicas en Azure; Unidad 6: Descripción de los grupos de seguridad de red de Azure"
---
--->

# Demostración: Grupos de seguridad de red (NSG) de Azure

Esta demostración está orientada al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de las soluciones de seguridad de Microsoft
- Módulo: Descripción de las funcionalidades de seguridad básicas en Azure
- Unidad: Descripción de los grupos de seguridad de red de Azure

## Escenario de la demo

En esta demostración, explorará la función de los grupos de seguridad de red en Azure y aplicará un grupo de seguridad de red a una máquina virtual creada previamente. Empezará mostrando brevemente información sobre la máquina virtual creada previamente por el host de laboratorio autorizado (ALH). A continuación, usando el grupo de seguridad de red (NSG) que se configuró como parte de la configuración previa a la demostración, mostrará los parámetros esenciales de un NSG y las reglas de entrada y salida predeterminadas. Asignará una interfaz de máquina virtual al NSG, creará una nueva regla RDP para permitir la conexión a la máquina virtual y, por último, la probará.

### Demo, parte 1

En esta parte, verá algunos de los parámetros asociados a la máquina virtual que se creó como parte de la demostración de instalación (DEMO_00_pre_demo_setup.md).

1. Abrir Microsoft Edge.  En la barra de direcciones, escriba **https://portal.azure.com** e inicie sesión con las credenciales de Azure proporcionadas por el host de laboratorio autorizado (ALH).  Esto le llevará a la página principal de servicios de Azure.

1. En el cuadro de búsqueda azul en la parte superior de la página, escriba **Virtual Machines** y seleccione **Virtual Machines** en los resultados de la búsqueda.

1. En la página Máquinas virtuales, seleccione la máquina virtual que aparece como **SC900-WinVM**.  Esta máquina virtual debe haberse creado como parte de la configuración previa a la demostración.  Si no aparece, créela ahora.

1. Ahora se encuentra en la página de SC900-WinVM.  Anote parte de la información básica sobre la máquina virtual.

1. En el panel de navegación izquierdo, seleccione **Redes**.  
    1. La vista predeterminada es para las reglas de puerto de entrada.  Tenga en cuenta que la interfaz de red de esta máquina virtual no tiene ningún grupo de seguridad de red configurado.  Lo mismo sucede si selecciona Reglas de puerto de salida.
    1. Seleccione **Reglas de seguridad vigentes** junto a donde dice Interfaz de red.  Observe que dice: "No hay ningún grupo de seguridad de red o grupo de seguridad de aplicaciones asociado a la interfaz de red".

1. Nota para el moderador: Si intenta comprobar el estado del puerto en la página de conexión, obtendrá el mensaje "No se puede comprobar".  Esto no significa necesariamente que los puertos no estén expuestos.  Como observará cuando realice la misma acción con el NSG asignado, obtendrá el mensaje "No accesible" que indica que el tráfico en ese puerto está bloqueado.


1. Deje esta pestaña del explorador abierta.

### Demo, parte 2

En esta parte, asignará una interfaz al NSG y hablará con las reglas de entrada y salida predeterminadas que muestran cómo funcionan las reglas.  Como parte de la configuración previa a la demostración, la máquina virtual debe asignar su interfaz de red a un NSG y crear una nueva regla de entrada para el tráfico RDP.

1. Abra una nueva pestaña del explorador en el Azure Portal (portal.azure.com) y, en la barra de búsqueda azul de la parte superior de la página, escriba **Grupos de seguridad de red**. En los resultados, seleccione **Grupos de seguridad de red** (no seleccione Grupos de seguridad de red clásicos).

1. Seleccione el grupo de seguridad de red creado como parte de la configuración previa a la demostración. Si no lo creó anteriormente, hágalo ahora. Seleccione **Crear grupo de seguridad de red** y especifique la siguiente configuración:
    1. Suscripción: deje el valor predeterminado (esta es la suscripción de Azure proporcionada por el host de laboratorio autorizado).
    1. Grupo de recursos:  **LabsSC900** (el mismo grupo de recursos que usa la máquina virtual).
    1. Nombre:  **NSG-SC900**
    1. Región: deje el valor predeterminado.
    1. Seleccione **Revisar y crear** y, luego, **Crear**.
    1. Una vez completada la implementación (esto sucede muy rápidamente), seleccione **Ir al recurso**.

1. En la parte superior de la página debajo de donde dice Essentials, verá información básica sobre el grupo de seguridad de red que creó.  Dos aspectos que se han de tener en cuenta son que no hay ninguna regla de seguridad PERSONALIZADA y no hay subredes ni interfaces de red asociadas a este NSG.  Aunque no hay reglas de seguridad personalizadas, hay reglas de entrada y salida predeterminadas que se incluyen con cada NSG, como se muestra en la página.  Revise las reglas de entrada y salida. Las reglas de entrada predeterminadas deniegan todo el tráfico entrante que no procede de una red virtual o de un equilibrador de carga de Azure.  Las reglas de salida deniegan todo el tráfico saliente, excepto el tráfico entre redes virtuales y el tráfico saliente a Internet.

1. En el panel de navegación izquierdo de la página NSG-SC900, debajo de Configuración, seleccione **Interfaces de red**.
    1. Seleccione **Asociar**.
    1. En el campo para seleccionar asociaciones de interfaz de red, seleccione la **flecha desplegable**, **seleccione sc900-winvmXXX** y, a continuación, seleccione **Aceptar** en la parte inferior de la ventana. Una vez que se haya asociado la interfaz al grupo, se mostrará en la lista.

1. Para devolver la máquina virtual, seleccione la pestaña del explorador de la máquina virtual.  Debería ver que ahora hay un grupo de seguridad de red asociado a la interfaz de máquina virtual.  Se muestra la tabla de reglas del puerto de entrada. Las reglas de entrada predeterminadas deniegan todo el tráfico entrante que no procede de una red virtual o de un equilibrador de carga de Azure.  Para probarlo, comprobará el estado en el puerto RDP 3389.
    1. En la parte superior de la página, seleccione **Conectar** y seleccione **Comprobar acceso** para el puerto 3389 (RDP), verá el mensaje "No accesible".  
    1. Aunque solo está probando el puerto RDP 3389, todo el tráfico de red entrante que no procede de otra red virtual o del equilibrador de carga estará bloqueado.  

1. Ahora creará una regla para permitir el tráfico entrante en el puerto RDP.  En el panel de navegación izquierdo, seleccione **Redes**. Se debe mostrar la tabla Reglas del puerto de entrada (la pestaña Reglas del puerto de entrada está subrayada).  En la parte derecha de la página, seleccione **Agregar regla de puerto de entrada**. Recuerde que las reglas predeterminadas no se pueden quitar, pero puede reemplazarlas por reglas de prioridad más alta. En la ventana Agregar regla de seguridad de entrada, especifique la siguiente configuración:
    1. Origen:  **Cualquiera**
    1. Intervalos de puertos de origen: **\***
    1. Destino:  **Cualquiera**
    1. Servicio:  **RDP**
    1. Acción:  **Permitir**
    1. Prioridad:  **1000**; Nota: Las reglas con números inferiores tienen una prioridad más alta y se procesan primero.
    1. Nombre: deje el nombre predeterminado o cree su propio nombre descriptivo.
    1. Observe el signo de advertencia en la parte inferior de la página.  Usamos RDP solo para fines de prueba y para demostrar la funcionalidad del NSG.
    1. Seleccione **Agregar**.

1. Una vez que se haya aprovisionado la regla, esta aparecerá en la lista de reglas de entrada (es posible que tenga que actualizar la pantalla).

### Demo, parte 3

Con el grupo de seguridad de red creado y asociado a la máquina virtual y la regla RDP creada, mostrará el impacto del NSG probando la conectividad RDP con la máquina virtual.

1. Abra la pestaña SC900-VMWin: Microsoft Azure en su explorador. 

1. Seleccione **Conectar** en el panel de navegación izquierdo.
    1. Puede simplemente seleccionar **comprobar el acceso**.  El estado ahora debería ser “Accesible”. Como alternativa, si tiene tiempo, puede conectarse a la máquina virtual abriendo una instancia de Conexión a Escritorio remoto en Windows.  Esta opción abrirá la máquina virtual al conectarse correctamente a ella.  A continuación se enumeran los pasos:
        1. En la barra de búsqueda de Windows, escriba **Conexión a Escritorio remoto** y seleccione **Abrir**.
        1. En el campo situado junto a donde dice **Equipo**, escriba la dirección IP pública de la máquina virtual.
        1. Una vez que escriba la dirección IP, el nombre de usuario debe aparecer debajo del campo donde escribió la dirección IP. Si no es así, expanda **Mostrar opciones** y escriba el nombre de usuario de la máquina virtual y, a continuación, seleccione **Conectar**.
        1. Se abrirá la ventana Conexión a Escritorio remoto con el mensaje: No se puede comprobar la identidad del equipo remoto. ¿Desea conectarse de todos modos? Seleccione **Sí**.
        1. Ahora está conectado a la VM. Recalque ante el estudiante el hecho de que en este caso ha podido conectarse a la máquina virtual porque la regla de tráfico de salida que ha creado permite el tráfico de entrada a la máquina virtual mediante RDP.
        1. Minimice la máquina virtual; para ello, seleccione el carácter de subrayado **_** en la pestaña azul que muestra la dirección IP de la máquina virtual. Esto le lleva de vuelta al SC900-WinVM | Página Conectar.

1. En el panel de navegación izquierdo, seleccione **Redes** y, a continuación, en la ventana principal, seleccione **Reglas del puerto de salida**.  Hable con las reglas de salida predeterminadas. Las reglas predeterminadas permiten el tráfico de red virtual saliente desde cualquier red virtual a otra red virtual y permite el tráfico saliente de Internet. Se deniega cualquier otro tipo de tráfico saliente.  No puede quitar la regla predeterminada, pero puede invalidarla mediante la creación de una regla con mayor prioridad de la misma manera en que creó la regla de entrada.

1. Si el temporizador permite y desea mostrar pasos similares para el tráfico saliente, revise la parte opcional de la demostración que se muestra a continuación.  De lo contrario, salga de la máquina virtual, pero mantenga abierta la pestaña Azure en el explorador para la siguiente demostración.

### Demostración OPCIONAL, parte 4

En esta parte, mostrará las reglas de salida de NSG actuales que permiten el tráfico saliente de Internet desde la máquina virtual.  A continuación, creará una regla para bloquear el tráfico saliente de Internet desde la máquina virtual. Por último, mostrará el impacto de la regla recién creada intentando acceder a Internet desde la máquina virtual.

1. Abra la máquina virtual que minimizó en el paso anterior. Aquí puede mostrar la conectividad saliente a Internet, que está habilitada por una de las reglas de salida predeterminadas. Una vez que se abra la máquina virtual y haya iniciado sesión como usuario, seleccione **Microsoft Edge** para abrir el explorador.  Puesto que esta es la primera vez que abre Microsoft Edge, puede que aparezca una ventana emergente, seleccione **Iniciar sin los datos** y, a continuación, **Continuar sin estos datos** y, luego, seleccione **Confirmar y empezar a navegar**.
    1. Escriba **www.bing.com** en la barra de direcciones del navegador y confirme que puede conectarse al motor de búsqueda.
    1. Una vez que haya confirmado que puede acceder a www.bing.com, cierre la ventana del explorador en la máquina virtual, pero deje la máquina virtual funcionando.

1. Minimice la máquina virtual; para ello, seleccione el carácter de subrayado **_** en la pestaña azul que muestra la dirección IP de la máquina virtual. Esto le lleva de vuelta al SC900-WinVM | Página Conectar.  

1. En el panel de navegación izquierdo, seleccione **Redes**.

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

1. Mantenga abierta la pestaña de Azure en el explorador para la siguiente demostración de Azure.

### Revisar

En esta demo ha realizado un recorrido por la información y la configuración asociada a un grupo de seguridad de red, incluido el proceso de asociar una interfaz al grupo; ha mostrado el funcionamiento de las reglas de entrada y salida predeterminadas y, por último, ha explicado los pasos necesarios para crear una nueva regla.
