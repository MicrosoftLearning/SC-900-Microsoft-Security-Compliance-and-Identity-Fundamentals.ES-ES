---
lab:
    title: 'Explorar Microsoft Defender for Cloud'
    module: 'Módulo 3, lección 2: Describir las funcionalidades de las soluciones de seguridad de Microsoft. Describir las funcionalidades de administración de la seguridad de Azure'
---

# Laboratorio: Explorar Microsoft Defender for Cloud

## Escenario del laboratorio
En este laboratorio, recorrerá Microsoft Defender for Cloud y aprenderá cómo se puede utilizar la puntuación de seguridad de Azure para mejorar la posición de seguridad de su organización.

**Tiempo estimado**: 30 minutos

#### Tarea 1: En esta tarea hará un breve recorrido por Microsoft Defender for Cloud.
1.	Abra Microsoft Edge. En la barra de direcciones, escriba **portal.azure.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

1. En la esquina superior izquierda de la pantalla, junto a las palabras Microsoft Azure, seleccione el icono Mostrar el menú del portal (las tres líneas horizontales, también denominadas icono de hamburguesa) y luego, en el panel de navegación de la izquierda, en Favoritos, seleccione **Microsoft Defender for Cloud**.  Si no aparece bajo Favoritos, en el cuadro de búsqueda, escriba** Microsoft Defender for Cloud** y, en la lista de resultados, seleccione **Microsoft Defender for Cloud**.

1. Fíjese en la información disponible en la página de información general de Microsoft Defender for Cloud.  

1. Es posible que vea un cuadro de información azul en la parte superior de la página que indica que puede estar viendo información limitada.  Seleccione **Haga clic aquí**.
    1. Para asegurarse de que tiene una visibilidad completa del inquilino, asígnese el rol necesario.  Seleccione **Administrador de seguridad** y luego **Obtener acceso** en la parte inferior de la página.
    1. Es probable que vea el mensaje "El grupo de administración raíz no existe".  Tal y como se indica en la descripción, el sistema creará el grupo por usted.  Este proceso puede tardar hasta 15 minutos en completarse (pero normalmente tarda menos).  Una vez concedido el acceso, seleccione **Microsoft Defender for Cloud** en la esquina superior izquierda de la página, encima de donde dice Obtener permisos y luego, actualice la página de información general de Microsoft Defender for Cloud.

1. La información en la parte superior de la página incluye el número de suscripciones de Azure, el número de recursos evaluados, el número de recomendaciones activas y cualquier alerta de seguridad.  En el cuerpo principal de la página hay tarjetas que representan la Puntuación de seguridad, cumplimiento normativo, información, Azure Defender, etc.  

1. En la parte superior de la página, seleccione **Recursos evaluados**.  (Tenga en cuenta que esto equivale a haber seleccionado el Inventario en el panel de navegación izquierdo de la página de inicio de Microsoft Defender for Cloud).
    1. De esta forma irá a la página **Inventario**, que muestra su suscripción al pase para Azure.  Seleccione **Pase para Azure – Patrocinio**.
    1. La página de estado de los recursos ofrece una lista de recomendaciones.  En la lista disponible, seleccione **Debe haber más de un propietario asignado a su suscripción**.
    1. Seleccione la flecha desplegable situada junto a Pasos de corrección. Observe cómo se aportan pasos detallados de corrección junto a la opción de tomar medidas.  
    1. Seleccione **Microsoft Defender for Cloud** en la esquina superior izquierda de la pantalla para volver a la página de información general de Microsoft Defender for Cloud.

1. En la parte superior de la página, seleccione **Recomendaciones activas**.  (Tenga en cuenta que esto equivale a haber seleccionado Recomendaciones en el panel de navegación izquierdo de la página principal de Microsoft Defender for Cloud).
    1. La página de recomendaciones muestra su panel de Puntuación de seguridad.
    1. Debajo del panel de Puntuación de seguridad hay una lista de controles. Cada control de seguridad representa un riesgo de seguridad que debe mitigarse y también incluye información sobre la puntuación máxima asociada a ese control, la puntuación actual, el aumento potencial de la puntuación y el estado de los recursos.  
    1. Seleccione uno de los controles, como **Habilitar MFA**.  Seleccione uno de los subelementos, como **debe habilitarse MFA en las cuentas con permisos de propietario en su suscripción**.  En la página que se abre, verá una descripción, los pasos de corrección y los recursos afectados. Puede salir de esta página si selecciona la **X** en la esquina superior derecha de la pantalla.
    1. Puede salir de la página de recomendaciones si selecciona la **X** en la esquina superior derecha de la pantalla, para volver a la página de información general.

1. En la página principal, seleccione **Cumplimiento normativo**. La página de cumplimiento normativo ofrece una lista de controles de cumplimiento.  Bajo cada control hay un conjunto de evaluaciones que se basan en Azure Security Benchmark y ofrecen recomendaciones sobre cómo puede asegurar sus soluciones en la nube en Azure.
    1. Seleccione **IM. Administración de identidades**, luego seleccione **IM-6 Utilizar controles de autenticación fuertes**.  La lista muestra las acciones de responsabilidad del cliente que pueden tomarse para mejorar la posición de cumplimiento.
    1. Seleccione la **X** en la esquina superior derecha de la pantalla para cerrar la página y volver a la página información general de Microsoft Defender for Cloud. 
    1. Mantenga abierta la página de información general de Microsoft Defender for Cloud, la utilizará en la siguiente tarea.


#### Tarea 2: En esta tarea, navegará por la Puntuación de seguridad de Azure y explorará las recomendaciones que pueden mejorar su Puntuación de seguridad. 

1. En la página de información general de Microsoft Defender for Cloud, seleccione la tarjeta **Puntuación de seguridad**.
1. Seleccione **Pase para Azure: Patrocinio**.  Observe su Puntuación de seguridad.
1. En la página de recomendaciones, seleccione **Implementar los procedimientos recomendados de seguridad** para ampliar la lista. Observe que el estado de mantenimiento de los recursos se muestra en rojo.
1. Seleccione el elemento **Debe haber más de un propietario asignado a la suscripción**, que muestra el estado del recurso en rojo. 
1. Debajo de donde dice **Recursos afectados**, asegúrese de que la opción Recursos con estado incorrecto esté seleccionada/subrayada y luego, seleccione la suscripción a Azure de la lista.
1. En la parte superior de la página Control de acceso (IAM), seleccione **+ Agregar** y luego seleccione **Agregar asignación de roles** en el menú desplegable.
    1. En la parte izquierda de la página, seleccione **Propietario** (debería ser el primer elemento de la lista) para que la fila quede resaltada en gris y luego, seleccione **Siguiente** en la parte inferior de la página.
    1. Al lado de donde dice Miembros, seleccione **+ Seleccionar miembros**. 
    1. En la ventana Selección de miembros que se abre en la parte derecha de la pantalla, seleccione **Alex Wilber** y luego, presione **Seleccionar** en la parte inferior de la página.  
    1. En la página de asignación Agregar rol, compruebe que Alex Wilber aparezca como miembro, luego seleccione **Siguiente** seguido de **Revisar + asignar**.
    1. El estado puede tardar hasta 24 horas en actualizarse, pasadas las cuales su Puntuación de seguridad también se actualizará, dado que todos los elementos del grupo Administrar acceso y permisos se han cumplido.
    1. En la esquina superior izquierda de la página, encima de donde dice Pase para Azure, seleccione **Microsoft Defender for Cloud** para volver a la página de información general de Microsoft Defender for Cloud.
1. Mantenga esta página abierta para la siguiente tarea.


#### Tarea 3:  Recuerde que Microsoft Defender for Cloud se ofrece en dos modalidades: sin características de seguridad mejoradas (gratis) y con características de seguridad mejoradas que están disponibles a través de los planes de Microsoft Defender for Cloud. En esta tarea descubrirá cómo habilitar/deshabilitar los distintos planes de Microsoft Defender for Cloud.

1.	En la página de información general de Microsoft Defender for Cloud, seleccione **Configuración del ambiente** en el panel de navegación izquierdo.
1. Seleccione el signo mayor que **>** al lado de donde dice Grupo de raíz de inquilinos para expandirlo (no seleccione Grupo de raíz de inquilinos directamente ya que eso le dirigirá a una página diferente), luego seleccione **Pase para Azure: Patrocinio**.
1.	En la página Planes Defender, puede seleccionar Habilitar todos o seleccionar planes Defender individuales. Deje la configuración como está, con todos los planes desactivados.
1.	Ya puede cerrar la pestaña del explorador para salir de Azure Portal.


#### Revisión
En este laboratorio, recorrió Microsoft Defender for Cloud y aprendió cómo se puede utilizar la puntuación de seguridad de Azure para mejorar la posición de seguridad de su organización.
