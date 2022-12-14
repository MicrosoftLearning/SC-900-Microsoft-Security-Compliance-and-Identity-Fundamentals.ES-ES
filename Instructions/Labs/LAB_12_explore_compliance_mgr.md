<a name="---"></a><!---
---
Laboratorio: Título: "Exploración del portal de cumplimiento y el administrador de cumplimiento de Microsoft Purview" Ruta de aprendizaje/Módulo/Unidad: "Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft; Módulo 2: Descripción de las funcionalidades de administración de cumplimiento en Microsoft Purview; Unidad 2: Descripción del portal de cumplimiento de Microsoft Purview"
---
--->

# <a name="lab-explore-the-microsoft-purview-compliance-portal--compliance-manager"></a>Laboratorio: Explorar el Portal de cumplimiento de Microsoft Purview y el Administrador de cumplimiento

Este laboratorio está orientado al siguiente contenido de Learn:

- Ruta de aprendizaje: Descripción de las funcionalidades de cumplimiento de Microsoft
- Módulo: Descripción de las funcionalidades de administración de cumplimiento en Microsoft Purview
- Unidad: Descripción del portal de cumplimiento de Microsoft Purview

## <a name="lab-scenario"></a>Escenario del laboratorio

En este laboratorio explorará la página principal del Portal de cumplimiento de Microsoft Purview y explorará las diferentes formas en las que las funcionalidades del Administrador de cumplimento pueden ayudar a las organizaciones a mejorar su posición de cumplimiento.

**Tiempo estimado**: 30-45 minutos

### <a name="task-1"></a>Tarea 1

Explore la página principal del Portal de cumplimiento de Microsoft Purview y aprenda a personalizar la vista de tarjeta y el panel de navegación.

1. Abrir Microsoft Edge. En la barra de direcciones, escriba **admin.microsoft.com**.
1. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (donde ZZZZZZ es el id. de inquilino único proporcionado por el proveedor de servicios de hospedaje de laboratorios) y seleccione **Siguiente**.
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**. Esto le llevará a la página del Centro de administración de Microsoft 365.
1. En el panel de navegación izquierdo del Centro de administración de Microsoft 365, seleccione **Mostrar todo**.
1. En Centros de administración, seleccione **Cumplimiento**.  Se abrirá una nueva página del explorador con la página principal del portal de cumplimiento de Microsoft Purview.  
1. La sección de tarjetas de la página principal le muestra de un vistazo la posición de cumplimiento de su organización, las soluciones disponibles para esta, y mucho más.
1. Desplácese hacia abajo en la ventana principal para ver las diferentes tarjetas. Es posible modificar las tarjetas disponibles en la pantalla principal y su posición para ajustarlas a las preferencias de cada administrador.  
1. Al situar el cursor del ratón sobre la barra de título de cualquier tarjeta, la barra se vuelve gris.  Cuando vea que el cursor se convierte en un icono en forma de cruz, podrá mover la tarjeta a la ubicación que desee.
1. En la barra de título de cada tarjeta, verá también unos puntos suspensivos que muestran las acciones que puede realizar.  Seleccione los puntos suspensivos en el Catálogo de soluciones y seleccione **Quitar**.
1. Para agregar tarjetas, seleccione **+ Agregar tarjetas**.  Se abre la ventana Agregar tarjetas a la página principal.  Sitúe el cursor del ratón sobre la tarjeta que aparece en esta ventana y arrástrela a la ubicación de su pantalla principal en la que desea situarla.
1. Como administrador de cumplimiento, puede haber un conjunto de soluciones que administre para nuestra organización y, como tal, tal vez quiera que solo esas soluciones aparezcan en el panel de navegación que vea. Para personalizar sus preferencias, seleccione **Personalizar la navegación**.  
1. En la ventana con la etiqueta Personalizar el panel de navegación, observe cómo puede seleccionar los elementos que quiere que aparezcan en el panel de navegación y anular la selección de los elementos que no quiera ver. Para estos laboratorios, mantenga todos los elementos seleccionados y presione **Guardar** en la parte inferior de la ventana.  
1. Deje abierta la pestaña del explorador.

### <a name="task-2"></a>Tarea 2

Obtenga información sobre la postura de cumplimiento de su organización mediante el Administrador de cumplimiento

1. En el panel de navegación izquierdo del Portal de cumplimiento de Microsoft Purview, seleccione **Administrador de cumplimiento**.  Como alternativa, puede seleccionar Administrador de cumplimiento desde la barra de título de la tarjeta Administrador de cumplimiento.

1. En la parte superior de la página Administrador de cumplimiento, asegúrese de que la opción **Información general** está seleccionada (subrayada). Desplácese hacia abajo para ver toda la información disponible en la página.  Entre la información de esta página se incluye la puntuación de cumplimiento, los puntos y los puntos administrados por Microsoft que ha obtenido.   Verá las acciones de mejora clave, las soluciones que afectan a su puntuación y un desglose de la puntuación de cumplimiento por categorías.

1. En la parte superior de la página Información general, seleccione **Acciones de mejora**.  Son las acciones que pueden mejorar la puntuación de cumplimiento de la organización. Tenga en cuenta que, a medida que se llevan a cabo acciones de mejora, los puntos pueden tardar hasta 24 horas en actualizarse.  Observe los filtros disponibles.

1. En la lista de acciones de mejora, seleccione **Habilitar el autoservicio de restablecimiento de contraseña**.  Revise la información disponible para la acción de mejora.  En el lado izquierdo de la ventana se proporciona información general breve sobre la implementación, el estado de prueba, etc. A la derecha de la información general, tiene una página de detalles desde la cual puede seleccionar su implementación, las pruebas, los estándares y los requisitos normativos relacionados, y documentos. Cada una de estas pestañas proporciona información más detallada para la acción de mejora.

1. Para salir de esta acción de mejora, seleccione **Acciones de mejora** en la ruta de navegación de la parte superior izquierda de la página.  Ahora ha vuelto a la página Acciones de mejora.

1. Seleccione **Soluciones** en la parte superior de la página. En esta página verá cómo influyen las soluciones en su puntuación y el margen de mejora de cada una.

1. En la parte superior de la página, seleccione **Evaluaciones**. En esta página verá la línea base de protección de datos de Microsoft 365.  Se trata de la evaluación predeterminada base que proporciona Microsoft en el Administrador de cumplimiento para Microsoft 365.  Esta evaluación de la línea base incluye un conjunto de controles para las normativas y los estándares clave para la protección y el gobierno de datos general. El Administrador de cumplimiento resulta más útil a medida que agrega sus propias evaluaciones para satisfacer las necesidades particulares de su organización.

1. Seleccione **Línea base de protección de datos**.  En el lado izquierdo de la página se muestra información general que incluye detalles e información.  Expanda **Acerca de** y revise la descripción sobre la línea base de protección de datos de Microsoft 35.  En el lado derecho de la página, observe la información disponible en la pestaña progreso y para las acciones de mejora. En la parte superior de la página hay pestañas que puede seleccionar para ver información más detallada sobre los controles, las acciones de mejora y las acciones de Microsoft. Puede explorarlas si así lo desea. 

1. En la parte superior izquierda de la página, encima de donde se indica Línea de base de protección de datos para Microsoft 365 (la ruta de navegación), seleccione **Evaluación** para volver a la pestaña evaluaciones del Administrador de cumplimiento.  

1. En la parte superior de la página, seleccione **Plantillas de evaluación**.  En esta página se enumeran las plantillas disponibles y están organizadas por Plantillas incluidas y plantillas Premium (es posible que tenga que desplazarse hacia abajo o expandir la lista para verlas).  Puede crear evaluaciones para su organización mediante una plantilla ya existente o crear una nueva plantilla.
    1. En la lista de plantillas incluidas, seleccione cualquier plantilla. En la parte superior derecha de la página, seleccione **+ Crear evaluación**.  Aquí puede ver los pocos pasos y fragmentos de información necesarios para crear una evaluación a partir de una plantilla existente: identifique el producto para la evaluación, asígnele el nombre de la evaluación y asígnelo a un grupo.  Seleccione Cancelar en la parte inferior de la página.

1. Cierre todas las pestañas abiertas del explorador.

### <a name="review"></a>Revisar

En este laboratorio exploró la página principal del Portal de cumplimiento de Microsoft Purview y explorará las diferentes formas en las que las funcionalidades del Administrador de cumplimento pueden ayudar a las organizaciones a mejorar su posición de cumplimiento.
