---
lab:
    title: 'Explorar Microsoft Sentinel'
    module: 'Módulo 3, lección 3: Describir las funcionalidades de las soluciones de seguridad de Microsoft. Describir las funcionalidades de seguridad de Microsoft Sentinel'
---


# Laboratorio: Explorar Microsoft Sentinel 

## Escenario del laboratorio
En este laboratorio, recorrerá el proceso de creación de una instancia de Microsoft Sentinel.  También configurará los permisos para garantizar el acceso a los recursos que se implementarán para admitir Microsoft Sentinel.  Una vez realizada esta configuración básica, seguirá los pasos para conectar Microsoft Sentinel a sus orígenes de datos, utilizará los análisis integrados para recibir notificaciones de cualquier cosa sospechosa y, por último, explorará la funcionalidad de automatización.  

  

**Tiempo estimado**: 30-45 minutos.

#### Tarea 1:  Crear una instancia de Microsoft Sentinel.

1. Abra Microsoft Edge. En la barra de direcciones, escriba **portal.azure.com**.

2. Inicie sesión con sus credenciales de administrador.
    1. En la ventana de inicio de sesión, escriba **admin@WWLxZZZZZZ.onmicrosoft.com** (la ZZZZZZ es su id. de inquilino único proporcionado por su proveedor de servicios de hospedaje de laboratorios) y luego seleccione **Siguiente**.
    
    1. Escriba la contraseña de administrador que debería haberle proporcionado su proveedor de servicios de hospedaje de laboratorios. Seleccione **Iniciar sesión**.
    1. Cuando aparezca un mensaje para preguntarle si quiere mantener la sesión iniciada, seleccione **Sí**.

3. En la esquina superior izquierda de la pantalla, junto a las palabras Microsoft Azure, seleccione el icono Mostrar el menú del portal (las tres líneas horizontales, también denominadas icono de hamburguesa) y luego seleccione **Todos los servicios**.  

4. En el cuadro de servicios de filtrado, escriba **Microsoft Sentinel** y luego, seleccione **Microsoft Sentinel** de la lista.

5. En la página de Microsoft Sentinel, seleccione **Crear Microsoft Sentinel**.

6. En la página Agregar Microsoft Sentinel a un área de trabajo, seleccione **Crear una nueva área de trabajo**.

7. En la pestaña Aspectos básicos de Crear un área de trabajo de Log Analytics, escriba lo siguiente:
    1. Suscripción:  **Pase para Azure: Patrocinio.**
   
    1. Grupo de recursos: seleccione **Crear nuevo**. Luego, en el campo Nombre, escriba **SC900-ResourceGroup** y seleccione **Aceptar**.
    1. Nombre: **SC900-LogAnalytics-workspace**.
    1. Región: **Este de EE. UU.** (Dejar este valor predeterminado)
    1. Seleccione **Siguiente: Plan de tarifas >**

8. Para el Plan de tarifas, deje los valores predeterminados: **Pago por uso (por GB 2018)**, y seleccione **Siguiente: Etiquetas >**.

9. Para las Etiquetas, puede dejar este en blanco y después seleccionar **Revisar y crear**.

10. Compruebe la información que ha escrito y luego seleccione **Crear**.

11. Si la nueva área de trabajo no aparece en la lista, seleccione **Actualizar** y luego **Agregar**.

12. Una vez agregada la nueva área de trabajo, se mostrará la página de | Noticias y guías de Microsoft Sentinel.  Tenga en cuenta los tres pasos que se muestran en la página Empezar.

13. Deje esta página abierta, porque la utilizará en la siguiente tarea.

#### Tarea 2:  Una vez que haya creado la instancia de Microsoft Sentinel, deberá asegurarse de que tiene el acceso necesario a los recursos que se implementan para admitir Microsoft Sentinel.  En esta tarea deberá ir a la página de control de acceso (IAM) para el grupo de recursos que creó con la instancia de Microsoft Sentinel, verá los roles disponibles y se asignará a sí mismo (administrador de MOD) el rol necesario. La asignación de un rol al grupo de recursos garantizará que el rol se aplique a todos los recursos que se implementan para admitir Microsoft Sentinel.

1. En la página de Microsoft Sentinel, en la esquina superior izquierda, encima de donde dice Microsoft Sentinel, seleccione **Todos los servicios**.

2. En el cuadro Filtrar servicios, escriba Grupos de recursos y luego, en la lista que aparece, seleccione **Grupos de recursos**.

3. En la página Grupos de recursos, seleccione el grupo de recursos que creó con Microsoft Sentinel, **SC900-ResourceGroup**.

4. En la página SC900-ResourceGroup, seleccione **Control de acceso (IAM)** en el panel de navegación izquierdo.

5. En la página Control de acceso, seleccione **Ver mi acceso**.  Observe que el rol actual es Administrador de seguridad.  Para cerrar la ventana de Asignaciones de administrador MOD, seleccione la **X** en la esquina superior derecha de la ventana.

6. En la página Control de acceso, seleccione **+Agregar** y después seleccione **Agregar asignación de roles**.

7. Se abre la ventana Agregar asignación de roles.  Seleccione la flecha desplegable en el campo Seleccionar rol para mostrar los roles disponibles.  Para este laboratorio, seleccione **Propietario**.  NOTA:  El procedimiento recomendado es asignar los privilegios mínimos necesarios para el rol.  Como referencia, revise los permisos en Microsoft Sentinel:  https://docs.microsoft.com/es-es/azure/sentinel/roles

8. En la lista de usuarios que aparece, seleccione **Administrador MOD**.

9. Seleccione **Guardar** en la parte inferior de la página.

10. En la página Control de acceso, seleccione **Ver mi acceso** para confirmar que se ha agregado el rol y luego cierre la ventana. Para ello, seleccione la **X** en la esquina superior derecha de esta.

11. Vuelva a la página de Azure Todos los servicios. Para ello, seleccione la opción **Todos los servicios** en la esquina superior izquierda de la página, encima de las palabras Grupos de recursos.

#### Tarea 3:  En esta tarea, recorrerá el proceso de conectar Microsoft Sentinel a su origen de datos para comenzar a recopilar datos. Nota: Es posible que el estado Conectado de un conector tarde algo de tiempo en aparecer (pueden ser unos 30 minutos, aunque depende del inquilino).

1. En el cuadro de servicios de filtrado de la página Todos los servicios, escriba **Microsoft Sentinel** y luego, seleccione **Microsoft Sentinel** de la lista de resultados. 

2. En la página de Microsoft Sentinel, seleccione el área de trabajo que creó con la instancia de Microsoft Sentinel, **SC900-LogAnalytics-workspace**.

3. El primer paso con Microsoft Sentinel es poder recopilar datos. En el panel de navegación izquierdo, seleccione **Conectores de datos**, que se muestran en Configuración.

4. En la página Conectores de datos, desplácese hacia abajo en la ventana principal para ver la amplia lista de conectores disponibles. En el cuadro de búsqueda de la página Conectores de datos, escriba **Azure** y seleccione **Azure Active Directory** en la lista.

5. Se abrirá la ventana de conectores de Azure Active Directory.  Seleccione **Abrir página del conector**.

6. En la página del conector de Azure Active Directory, revise la descripción y observe el contenido relacionado,el cual incluye libros, consultas y plantillas de reglas de análisis.  

7. La pestaña de instrucciones de la ventana principal proporciona los requisitos para que Microsoft Sentinel se integre con Azure Active Directory.   En Configuración, seleccione **Registros de inicio de sesión** y luego seleccione Aplicar cambios (puede seleccionar varios conectores).

8. En la pestaña Siguientes pasos, vea la lista de libros recomendados.   En Libros recomendados, seleccione **Registros de inicio de sesión de Azure** (puede seleccionar varios libros adicionales).

9. En la página Libros y con la pestaña Plantillas seleccionada (subrayada), seleccione **Registros de inicio de sesión en Azure**. 

10. En la ventana Registros de inicio de sesión de Azure AD que se abre, revise la descripción y seleccione **Ver plantilla**.  Para salir de la plantilla, seleccione la **X** en la esquina superior derecha de la ventana.  Seleccione **Guardar** en la parte inferior de la página y después seleccione **Aceptar** para guardar el libro en la ubicación predeterminada.

11. En la esquina superior izquierda de la página de Libros, encima de donde dice Libros, seleccione **Microsoft Sentinel**. Esto le llevará de nuevo a la página Conectores de datos de Microsoft Sentinel.

12. En la parte superior de la página Conectores de datos, debería aparecer uno conectado, de forma que se refleje que está ahora conectado a Azure Active Directory.

13. En el panel de navegación izquierdo, seleccione **Libros**.

14. En la página Libros, seleccione la pestaña **Mis libros**, sobre el cuadro de búsqueda.  El libro que acaba de guardar aparecerá en la lista y estará disponible para que pueda ver y supervisar sus datos.

15. Deje esta página abierta, porque la utilizará en la siguiente tarea.

#### Tarea 4:  En esta tarea aprenderá paso a paso a usar una plantilla de regla de análisis integrada para crear una regla que le permita recibir una notificación cuando se produzca algo sospechoso

1. En el panel de navegación izquierdo, seleccione **Análisis**.

2. La página Análisis mostrará las reglas activas (la detección avanzada de ataques de varias etapas estará habilitada de forma predeterminada) y le dará acceso a las plantillas de reglas.  Seleccione la pestaña **Plantillas de reglas**.  Observe la lista de plantillas disponibles y las diferentes formas de filtrar la lista.  Gracias a las alertas analíticas integradas en el área de trabajo de Microsoft Sentinel, recibirá una notificación cuando ocurra algo sospechoso.

3. En la barra de búsqueda, escriba **Azure Portal**.  Seleccione **Intentos de inicio de sesión fallidos en Azure Portal**.  

4. En la ventana que se abre, lea la descripción y revise la información asociada con la plantilla.  Seleccione **Crear regla** en la parte inferior de la página.

5. En el Asistente de reglas de análisis, revise la información y luego seleccione **Siguiente: Establecer la lógica de la regla >**.

6. En la página Establecer la lógica de la regla, definirá la lógica de la nueva regla de análisis. La plantilla mostrará alguna lógica y configuración predeterminada.  Desplácese por la página para ver las opciones disponibles.  Deje los valores predeterminados. Seleccione **Siguiente: Configuración de incidentes (versión preliminar)>**.

7. Mediante la configuración de Incidentes, las alertas de Microsoft Sentinel pueden agruparse en un Incidente que debe investigarse. Puede configurar si las alertas desencadenadas mediante esta regla de análisis deben generar incidentes.  Deje la configuración predeterminada y seleccione **Siguiente: Respuesta automática >**.

8. En la pestaña Respuesta automatizada, observe cómo puede agregar un cuaderno de estrategias para automatizar la respuesta.  Del mismo modo, puede crear una regla de automatización de incidentes.  Seleccione **+ Agregar** nueva en Automatización de incidentes.  Se abrirá una ventana para crear una nueva regla de automatización.  Cualquier regla de automatización que cree en esta página se desencadenará mediante la regla de análisis que está creando. Observe que puede agregar condiciones y configurar acciones para la regla.   Seleccione **Cancelar** para salir de la ventana.

9. Seleccione **Siguiente: Revisar>** para revisar todos los detalles relacionados con la regla y basados en la plantilla seleccionada. En este punto, puede elegir crear la regla (deberá seleccionar **Crear**) o salir sin crear la regla (para lo que deberá seleccionar la **X** que aparece en la esquina superior derecha de la página).

10. Deje esta página abierta, porque la utilizará en la siguiente tarea.

#### Tarea 5:  En la tarea anterior ha creado una regla de análisis para recibir alertas sobre actividades sospechosas.  La opción de automatizar la respuesta a un incidente en base a una regla específica se encuentra integrada en ese asistente,  pero también puede crear reglas de automatización directamente desde la opción Configuración de automatización

1. En el panel de navegación izquierdo, seleccione **Automatización**.  

2. Seleccione **+ Crear**. En el menú desplegable, puede seleccionar agregar tanto un nuevo cuaderno de estrategias como una nueva regla.  Seleccione **Agregar nueva regla**.  

3. Se abrirá una ventana para crear una nueva regla de automatización.  Tenga en cuenta que puede agregar condiciones y establecer acciones para la regla.  La única diferencia es que la primera condición es asociar la regla o reglas de análisis a las que desea aplicar esta regla de automatización.  Esta opción se deshabilitó en la tarea anterior porque la automatización se estaba configurando para la regla específica.  Seleccione **Cancelar** para salir de la ventana Crear nueva regla de automatización.

4. Deje esta página abierta, porque la utilizará en la siguiente tarea.


#### Tarea 6:  Eliminar un grupo de recursos de Microsoft Sentinel.  Microsoft Sentinel se factura en función del volumen de datos ingeridos para su análisis en Microsoft Sentinel. Aunque la cantidad de datos ingeridos como resultado de este laboratorio es mínima, se recomienda eliminar el grupo de recursos de Microsoft Sentinel cuando haya terminado de explorar las características de las funcionalidades de Microsoft Sentinel.

1. En la página de Microsoft Sentinel, en la esquina superior izquierda, encima de donde dice Microsoft Sentinel, seleccione **Todos los servicios**.

2. En el cuadro Filtrar servicios, escriba Grupos de recursos y luego, en la lista que aparece, seleccione **Grupos de recursos**.

3. En la página Grupos de recursos, seleccione el grupo de recursos que creó con Microsoft Sentinel, **SC900-ResourceGroup**.

4. En la parte superior central de la página, seleccione **Eliminar grupo de recursos**.  Revise la advertencia.  Escriba el nombre del grupo de recursos, **SC900-ResourceGroup**, y luego seleccione **Eliminar** en la parte inferior de la página.  Eliminar el grupo llevará varios minutos.

5. Una vez que haya comprobado que el grupo de recursos se ha eliminado, cierre la página del explorador. 


#### Revisión

En este laboratorio, recorrió el proceso de creación de una instancia de Microsoft Sentinel.  También configuró los permisos para garantizar el acceso a los recursos asociados con su instancia de Microsoft Sentinel.  Una vez creada su instancia de Microsoft Sentinel, siguió los pasos para conectar Microsoft Sentinel a sus orígenes de datos, utilizó los análisis integrados para recibir notificaciones de cualquier cosa sospechosa y, por último, exploró la funcionalidad de automatización. Finalizó la laboratorio con el borrado del grupo de recursos asociado a la instancia de Microsoft Sentinel que creó.
