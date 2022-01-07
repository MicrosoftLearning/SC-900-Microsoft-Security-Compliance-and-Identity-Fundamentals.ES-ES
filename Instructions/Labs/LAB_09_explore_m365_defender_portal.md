---
lab:
    title: 'Explorar el portal de Microsoft 365 Defender'
    module: 'Módulo 3, lección 5: Describir las funcionalidades de las soluciones de seguridad de Microsoft. Describir las funcionalidades de administración de seguridad de Microsoft 365'
---


# Laboratorio: Explorar el portal de Microsoft 365 Defender

## Escenario del laboratorio
En este laboratorio explorará el portal de Microsoft 365 Defender. Para ello, realizará un recorrido por el contenido mostrado en la página de aterrizaje. También examinará las opciones del panel de navegación que ofrecen un acceso rápido a una funcionalidad integrada en la solución de detección y respuesta ampliadas (XDR) de Microsoft: Microsoft Defender para punto de conexión, y Microsoft Defender para Office 365 (correo electrónico y colaboración).  Por último, también descubrirá cómo puede Puntuación de seguridad de Microsoft contribuir a mejorar la posición de seguridad de una organización.


**Tiempo estimado**: 10-15 minutos.

#### Tarea 1:  Explorar la página de aterrizaje de Microsoft 365 Defender

1. Abra Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.

1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
   
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.

1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Seguridad**.  Si no ve Seguridad en la lista, seleccione **Mostrar todo** y luego seleccione **Seguridad**.  Se abrirá una nueva página del explorador con la página principal del portal de Microsoft 365 Defender.  

1. Si esta es la primera vez que visita el portal de Microsoft 365 Defender, es posible que vea una ventana emergente para realizar un paseo introductorio.  Se recomienda que realice el paseo.  Seleccione **Realizar un paseo introductorio**.  Lea la descripción que aparece en las diferentes ventanas emergentes y luego seleccione **Siguiente**. Continúe el paseo hasta llegar al final y luego seleccione **Listo**.

1. El panel de navegación de la izquierda proporciona vínculos/acceso a la información que forma parte de la solución Extended Detection and Response (XDR) de Microsoft, que incluye incidentes y alertas, búsqueda, centro de acción, análisis de amenazas, puntuación segura y más.  También incluye un acceso rápido a Microsoft Defender para punto de conexión (los vínculos que aparecen debajo de Punto de conexión) y Microsoft Defender para Office 365 (los vínculos que se encuentran debajo de Correo electrónico y colaboración).  Para explorar estas opciones, seleccione uno de los vínculos.   Para volver a la página principal del portal de Microsoft 365 Defender, seleccione **Inicio** en el panel de navegación izquierdo.  Nota: Es posible que no se muestre una gran cantidad de información en estas pestañas, ya que no hay dispositivos conectados y es posible que no haya amenazas o alertas activas.

1. En la página principal del portal de Microsoft 365 Defender se muestran muchas de las tarjetas comunes que necesitan los equipos de seguridad. La composición de las tarjetas y los datos depende del rol de usuario. Desplácese por la página para ver el conjunto de tarjetas predeterminado para su rol de administrador global.

1. Las tarjetas mostradas pueden personalizarse según sus preferencias.  Seleccione **+ Agregar tarjetas**. Se abre una ventana que indica que ya tiene todas las tarjetas en su página principal.  Para cerrar la ventana seleccione la **X** en la esquina superior derecha de la ventana.

1. Seleccione los puntos suspensivos de la parte superior derecha de una de las tarjetas para mostrar una lista de las acciones adicionales que puede realizar.  

1. También puede mover las tarjetas. Mantenga el puntero del ratón sobre la barra de título de cualquiera de las tarjetas. Cuando el cursor se convierta en un icono en forma de cruz, seleccione la tarjeta y muévala a la ubicación que desee.

1. Si selecciona el título de una tarjeta, obtendrá información adicional sobre ese tema. Profundizará en esto en la próxima tarea.  Mantenga la ventana del explorador abierta.

#### Tarea 2: En esta tarea, descubrirá cómo puede Puntuación de seguridad de Microsoft contribuir a mejorar la posición de seguridad de una organización

1. Vaya a la página principal del portal de Microsoft 365 Defender y seleccione **Puntuación de seguridad de Microsoft** en la barra de título de la tarjeta (el texto se volverá azul).  Otra opción para hacerlo es seleccionar **Puntuación de seguridad** en el panel de navegación izquierdo.

1. Se abrirá la página Puntuación de seguridad de Microsoft en la pestaña Información general.  Puntuación de seguridad de Microsoft es una medición de la posición de seguridad de una organización. La Puntuación de seguridad de su organización se muestra en forma de porcentaje y desglosada por categoría junto al número de puntos que ha alcanzado del número total de puntos posibles. Seleccione **Incluir**, al lado de donde dice Su puntuación segura.  Se abrirá una pequeña ventana que le permitirá incluir la puntuación alcanzable, la planificada y la de la licencia actual en el desglose de la puntuación segura de su organización.  Seleccione de nuevo **Incluir** para cerrar la ventana.

1. La página Información general también incluye las principales acciones de mejora, una comparación de puntuaciones, el historial y recursos adicionales.

1. Seleccione **Acciones de mejora** en la parte superior de la página.  Observe la información disponible en la tabla para cada elemento, la cual incluye el impacto de la puntuación y los puntos obtenidos.  

1. Para ver información detallada, seleccione uno de los elementos de la lista.  Seleccione **Requerir MFA para roles administrativos**.  Seleccione **Editar estado y plan de acción**  En la ventana que se abre, observe las opciones de estado disponibles. Seleccione la **X** de la esquina superior derecha para cerrar la ventana.

1. En la parte inferior de la página, seleccione **Administrar en Microsoft Azure**.  Se abre una nueva pestaña en el explorador que le lleva directamente a la página Directivas de acceso condicional.  Si ha completado el ejercicio del laboratorio Acceso condicional, debería ver la directiva en la lista. Vuelva a la pestaña Puntuación de seguridad de Microsoft en su navegador. Esto le permitirá volver a la página Acciones de mejora para requerir MFA para roles administrativos. En la esquina superior derecha de la ventana, seleccione la **X** para cerrar esta ventana y volver a la página Acciones de mejora.

1. Seleccione la pestaña **Historial** en la parte superior de la página.  Es posible que algunas actividades muestren puntos negativos.  Como se describe en el campo Actividad, esto puede deberse a que se ha quitado uno de los elementos porque ya no era relevante.  Seleccione uno de los elementos de la tabla del historial.  Se abrirá una página detallada del elemento seleccionado.  Explore las opciones disponibles.  Para salir de la página de detalles y volver al Historial, seleccione la **X** de la esquina superior derecha de la página.

1. En la parte superior de la página, seleccione **Métricas y tendencias**.  Observe la información disponible.  En la esquina superior derecha de la página, seleccione el **icono de calendario**.  Puede restringir la vista a un intervalo de fechas personalizado.  Para filtrar la vista por identidad, dispositivos o aplicaciones, seleccione el **icono de filtro**.  Cierre la ventana y seleccione **Inicio** en el panel de navegación izquierdo para volver a la página principal de Microsoft 365 Defender.

1. Cierre la página del explorador.

#### Revisión
En este laboratorio ha examinado el portal de Microsoft 365 Defender. Para ello, ha realizado un recorrido por el contenido mostrado en la página de aterrizaje y ha explorado las opciones del panel de navegación que ofrecen un acceso rápido a una funcionalidad integrada en la solución de detección y respuesta ampliadas (XDR) de Microsoft, Microsoft Defender para punto de conexión y Microsoft Defender para Office 365 (correo electrónico y colaboración).  Por último, ha descubierto cómo puede Puntuación de seguridad de Microsoft contribuir a mejorar la posición de seguridad de una organización.
