---
description: Obtenga más información sobre cómo utilizar el Administrador de actividades de creación de informes para diagnosticar y corregir problemas de capacidad durante las horas de mayor actividad en la creación de informes.
title: Administrador de actividades de creación de informes
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 3c65e50bbfdbb011ef7b08d48a0ac3c87d7666b7
workflow-type: tm+mt
source-wordcount: '1892'
ht-degree: 15%

---

# Ver la actividad de creación de informes en el Administrador de actividades de informes

El [!UICONTROL Administrador de actividades de informes] permite a los administradores diagnosticar y corregir rápidamente los problemas de capacidad de creación de informes durante las horas de mayor actividad en los informes.

Para obtener más información sobre el Administrador de actividades de creación de informes, incluidas las ventajas clave y los requisitos de permisos, consulte [Información general del Administrador de actividades de creación de informes](/help/admin/admin/reporting-activity-manager/reporting-activity-overview.md).

## Ver la actividad de informes de todos los grupos de informes {#view-all-report-suites}

1. En Adobe Analytics, vaya a **[!UICONTROL Administrador]** > **[!UICONTROL Administrador de actividades de informes]**.

   Se muestra una lista de los grupos de informes base habilitados.

   ![cola de informes](assets/reporting-activity1.png) 

1. (Opcional) Puede buscar o filtrar la lista de grupos de informes:

   * Utilice el campo de búsqueda para buscar un grupo de informes específico. Empiece a escribir el nombre o ID del grupo de informes y la lista de grupos de informes se actualiza a medida que escribe.

   * Seleccione el [!UICONTROL **Filtrar**] icono ![Icono de filtro](assets/filter-icon.png) para expandir la lista de opciones de filtro. Puede filtrar por [!UICONTROL **Favoritos**] o [!UICONTROL **Estado**].

     Para marcar un grupo de informes como favorito, seleccione el icono de estrella a la izquierda del nombre del grupo de informes.

     <!-- (does this option still exist?) 1. (Optional) Select **[!UICONTROL Refresh]** at the top-right to refresh the data. -->

1. Ver información de utilización de cada grupo de informes. Puede seleccionar un encabezado de columna para ordenar la tabla por esa columna.

   Las columnas disponibles son las siguientes:

   | Elemento de la IU | Descripción |
   | --- | --- |
   | **[!UICONTROL Grupo de informes]** | El grupo de informes base cuya actividad de creación de informes está monitorizando. |
   | **[!UICONTROL Grupos de informes virtuales]** | Muestra todos los grupos de informes virtuales que se alimentan de este grupo de informes base. Los grupos de informes virtuales añaden complejidad a las solicitudes de creación de informes debido a los niveles adicionales de filtrado y segmentación aplicados. Todas las solicitudes que provienen de los grupos de informes virtuales se combinan en el grupo de informes base. |
   | **[!UICONTROL Utilización de la capacidad]** | El porcentaje de la capacidad de creación de informes del grupo de informes que se está utilizando en tiempo real. <p>**Nota** Una capacidad de uso del 100 % no sugiere necesariamente que deba empezar a cancelar inmediatamente las solicitudes de creación de informes. La capacidad de uso del 100% puede ser saludable si el tiempo de espera promedio es razonable. Por otro lado, una capacidad de uso del 100 % podría sugerir un problema si el número de solicitudes en cola también aumenta.</p> |
   | **[!UICONTROL Solicitudes en cola]** | El número de solicitudes en espera de ser procesadas. <!-- ??? --> |
   | **[!UICONTROL Tiempo de espera en cola]** | Tiempo de espera promedio antes de que las solicitudes empiecen a procesarse. <!-- ???? --> |
   | **[!UICONTROL Estado]** | Los estados posibles son: <ul><li>[!UICONTROL **Activo**] (azul): los informes se han ejecutado en el grupo de informes y se está monitorizando su actividad.</li><li>[!UICONTROL **Inactivo**] (gris): Nunca se han ejecutado informes en el grupo de informes. Este estado solo se muestra cuando se crean los grupos de informes por primera vez.</li></ul> |

   {style="table-layout:auto"}

## Ver la actividad de informes de un solo grupo de informes

1. En Adobe Analytics, seleccione [!UICONTROL **Administrador**] > [!UICONTROL **Administrador de actividades de informes**].

1. Seleccione el título vinculado del grupo de informes cuyos detalles desea ver.

   Los datos de la actividad de creación de informes se muestran para el grupo de informes seleccionado.

   <!-- Need to update this screenshot: ![report suite](assets/indiv-report-ste.png) -->

1. (Opcional) Cuando una conexión se carga por primera vez en el Administrador de actividades de creación de informes, los datos mostrados representan las métricas de utilización actuales. Para ver las métricas actualizadas después de la carga inicial, seleccione la [!UICONTROL **Actualizar**] para actualizar manualmente la página.

1. Utilice los gráficos y las tablas disponibles para comprender la actividad de creación de informes en el grupo de informes.

   * [Visualización de gráficos](#view-graphs)

   * [Ver tabla](#view-table)

### Visualización de gráficos

Los siguientes gráficos están disponibles para ayudarle a comprender mejor la actividad que se produce en el grupo de informes.

Si los gráficos no están visibles, seleccione la opción [!UICONTROL **Mostrar gráficos**] botón.

#### Gráfico de utilización {#utilization}

El gráfico Utilización muestra la utilización de los informes para el grupo de informes seleccionado durante las últimas 2 horas.

Pase el ratón sobre el gráfico para ver los puntos en el tiempo en los que el porcentaje de capacidad de uso fue mayor para ese minuto.

* **Eje X**: la capacidad de uso de creación de informes durante las últimas 2 horas.
* **Eje Y**: El porcentaje de capacidad de uso de creación de informes, por minuto.

  ![gráfico de utilización](assets/utilization-graph.png)

#### Gráfico de usuarios distintos

El gráfico Usuarios distintos muestra la actividad de creación de informes del grupo de informes seleccionado durante las últimas 2 horas.

Pase el ratón sobre el gráfico para ver los puntos en el tiempo en los que la cantidad máxima de usuarios fue mayor durante ese minuto.

* **Eje X**: la actividad de creación de informes durante las últimas 2 horas.
* **Eje Y**: el número de usuarios que han realizado solicitudes de creación de informes, por minuto.

  ![Gráfico de usuarios distintos](assets/distinct-users-graph.png)

#### Gráfico de solicitudes

El gráfico Solicitudes muestra el número de solicitudes procesadas y en cola para el grupo de informes seleccionado durante las últimas 2 horas.

Pase el ratón sobre el gráfico para ver los puntos en el tiempo en los que la cantidad máxima de solicitudes fue mayor en ese minuto.

* **Eje X**: el número de solicitudes procesadas y completadas durante las últimas 2 horas.
* **Eje Y**: El número de solicitudes procesadas (en verde) y solicitudes en cola (en púrpura), por minuto.

  ![Gráfico de usuarios distintos](assets/requests-graph.png)

#### Gráfico de colas

El gráfico En cola muestra el tiempo medio de espera de cola (en segundos) para las solicitudes de creación de informes del grupo de informes seleccionado durante las últimas 2 horas.

Pase el ratón sobre el gráfico para ver los puntos en el tiempo en los que el tiempo de espera promedio máximo fue mayor para ese minuto.

* **Eje X**: Tiempo promedio de espera en cola para solicitudes de informes durante el último lapso de tiempo de 2 horas.
* **Eje Y**: Tiempo de espera promedio (en segundos).

  ![Gráfico de usuarios distintos](assets/queueing-graph.png)

### Ver tabla {#view-table}

Al ver la tabla, tenga en cuenta lo siguiente:

* Puede elegir ver los datos eligiendo cualquiera de las siguientes pestañas en la parte superior de la tabla de datos: [!UICONTROL **Solicitud**], [!UICONTROL **Usuario**], [!UICONTROL **Proyecto**], o [!UICONTROL **Aplicación**].

* Puede buscar o filtrar la lista de conexiones:

   * Utilice el campo de búsqueda para buscar una conexión específica. Empiece a escribir el nombre o ID de la conexión y la lista de conexiones se actualizará a medida que escriba.

   * Seleccione el [!UICONTROL **Filtrar**] icono ![Icono de filtro](assets/filter-icon.png) para expandir la lista de opciones de filtro. Puede filtrar por [!UICONTROL **Estado**], [!UICONTROL **Complejidad**], [!UICONTROL **Aplicación**], [!UICONTROL **Usuario**], o [!UICONTROL **Proyecto**].

   * Puede seleccionar [!UICONTROL **Ocultar gráficos**] para mostrar solo la tabla.

![fichas de tabla](assets/report-activity-tabs.png)

#### Vista de datos por solicitud

Al seleccionar la variable [!UICONTROL **Solicitud**] , las siguientes columnas están disponibles en la tabla:

| Columna | Descripción |
| --- | --- |
| [!UICONTROL **ID de solicitud**] | Un ID único que se puede utilizar para solucionar problemas. Para copiar el ID, seleccione la solicitud y, a continuación, seleccione la opción, [!UICONTROL **Copiar ID de solicitud**]. |
| [!UICONTROL **Tiempo de ejecución**] | Cuánto tiempo lleva ejecutándose la solicitud. |
| [!UICONTROL **Hora de inicio**] | Cuando la solicitud comenzó a procesarse (según la hora local del administrador). |
| [!UICONTROL **Tiempo de espera**] | El tiempo que la solicitud ha estado esperando antes de procesarse. Este valor suele estar en &quot;0&quot; cuando hay suficiente capacidad. |
| [!UICONTROL **Aplicación**] | Las aplicaciones compatibles con el [!UICONTROL Administrador de actividades de creación de informes] son: <ul><li>IU de Analysis Workspace</li><li>Proyectos programados de Workspace</li><li>Report Builder</li><li>IU del generador: Segmento, Métricas calculadas, Anotaciones, Audiencias, etc.</li><li>Llamadas de API desde la API 1.4 o 2.0</li><li>Alertas inteligentes</li><li>Compartir vínculos con cualquiera</li><li>Cualquier otra aplicación que consulte el motor de informes de Analytics.</li></ul> |
| [!UICONTROL **Usuario**] | El usuario que inició la solicitud. <p>**Nota:** Si el valor de esta columna es [!UICONTROL **No reconocido**], esto significa que el usuario se encuentra en una empresa de inicio de sesión en la que no tiene permisos administrativos.</p> |
| [!UICONTROL **Proyecto**] | Nombres de proyectos de Workspace guardados, ID de informes de API, etc. (Los metadatos pueden variar entre distintas aplicaciones). |
| [!UICONTROL **Estado**] | Indicadores de estado: <ul><li>**Ejecución**: la solicitud está siendo procesada en este momento.</li><li>**Pendiente**: la solicitud está esperando a procesarse.</li></ul> |
| [!UICONTROL **Complejidad**] | No todas las solicitudes requieren la misma cantidad de tiempo para procesarse. La complejidad de la solicitud puede ayudar a proporcionar una idea general sobre el tiempo necesario para procesar la solicitud. <p>Entre los posibles valores están:</p> <ul><li>[!UICONTROL **Bajo**]</li><li>[!UICONTROL **Medio**]</li><li>[!UICONTROL **Alto**]</li></ul>Este valor se ve influido por los valores de las siguientes columnas:<ul><li>[!UICONTROL **Límites de mes**]</li><li>[!UICONTROL **Columnas**]</li><li>[!UICONTROL **Segmentos**]</li></ul> |
| [!UICONTROL **Límites de mes**] | El número de meses que se incluyen en una solicitud. Más límites de mes aumentan la complejidad de la solicitud. |
| [!UICONTROL **Columnas**] | El número de métricas y desgloses de la solicitud. Más columnas aumenta la complejidad de la solicitud. |
| [!UICONTROL **Segmentos**] | El número de segmentos aplicados a la solicitud. Más segmentos aumenta la complejidad de la solicitud. |

{style="table-layout:auto"}

#### Vista de datos por usuario

Al seleccionar la variable [!UICONTROL **Usuario**] , las siguientes columnas están disponibles en la tabla:

| Columna | Descripción |
| --- | --- |
| [!UICONTROL **Usuario**] | El usuario que inició la solicitud. Si el valor de esta columna es [!UICONTROL **No reconocido**], esto significa que el usuario se encuentra en una empresa de inicio de sesión en la que no tiene permisos administrativos. |
| [!UICONTROL **Número de solicitudes**] | Número de solicitudes iniciadas por el usuario. |
| [!UICONTROL **Número de proyectos**] | El número de proyectos asociados con el usuario. <!-- ??? --> |
| [!UICONTROL **Aplicación**] | Las aplicaciones compatibles con el [!UICONTROL Administrador de actividades de creación de informes] son: <ul><li>IU de Analysis Workspace</li><li>Proyectos programados de Workspace</li><li>Report Builder</li><li>IU del generador: Segmento, Métricas calculadas, Anotaciones, Audiencias, etc.</li><li>Llamadas de API desde la API 1.4 o 2.0</li><li>Alertas inteligentes</li><li>Compartir vínculos con cualquiera</li><li>Cualquier otra aplicación que consulte el motor de informes de Analytics.</li></ul> |
| [!UICONTROL **Complejidad media**] | Complejidad promedio de las solicitudes iniciadas por el usuario. <p>No todas las solicitudes requieren la misma cantidad de tiempo para procesarse. La complejidad de la solicitud puede ayudar a proporcionar una idea general sobre el tiempo necesario para procesar la solicitud.</p><p>El valor de esta columna se basa en una puntuación que viene determinada por los valores de las columnas siguientes:</p><ul><li>[!UICONTROL **Límites mensuales medios**]</li><li>[!UICONTROL **Columnas medias**]</li><li>[!UICONTROL **Segmentos medios**]</li></ul> |
| [!UICONTROL **Límites mensuales medios**] | Promedio de meses que se incluyen en las solicitudes. Más límites de mes aumentan la complejidad de la solicitud. |
| [!UICONTROL **Columnas medias**] | Número promedio de métricas y desgloses en las solicitudes incluidas. Más columnas aumenta la complejidad de la solicitud. |
| [!UICONTROL **Segmentos medios**] | El número promedio de segmentos aplicados a las solicitudes incluidas. Más segmentos aumenta la complejidad de la solicitud. |

{style="table-layout:auto"}

#### Vista de datos por proyecto

Al seleccionar la variable [!UICONTROL **Proyecto**] , las siguientes columnas están disponibles en la tabla:

| Columna | Descripción |
| --- | --- |
| [!UICONTROL **Proyecto**] | Proyecto en el que se iniciaron las solicitudes. |
| [!UICONTROL **Número de solicitudes**] | El número de solicitudes asociadas con el proyecto. |
| [!UICONTROL **Cantidad de usuarios**] | El número de usuarios asociados con el proyecto. <!-- ??? --> |
| [!UICONTROL **Aplicación**] | Las aplicaciones compatibles con el [!UICONTROL Administrador de actividades de creación de informes] son: <ul><li>IU de Analysis Workspace</li><li>Proyectos programados de Workspace</li><li>Report Builder</li><li>IU del generador: Segmento, Métricas calculadas, Anotaciones, Audiencias, etc.</li><li>Llamadas de API desde la API 1.4 o 2.0</li><li>Alertas inteligentes</li><li>Compartir vínculos con cualquiera</li><li>Cualquier otra aplicación que consulte el motor de informes de Analytics.</li></ul> |
| [!UICONTROL **Complejidad media**] | Complejidad media de las solicitudes incluidas en el proyecto. <p>No todas las solicitudes requieren la misma cantidad de tiempo para procesarse. La complejidad de la solicitud puede ayudar a proporcionar una idea general sobre el tiempo necesario para procesar la solicitud.</p><p>El valor de esta columna se basa en una puntuación que viene determinada por los valores de las columnas siguientes:</p><ul><li>[!UICONTROL **Límites mensuales medios**]</li><li>[!UICONTROL **Columnas medias**]</li><li>[!UICONTROL **Segmentos medios**]</li></ul> |
| [!UICONTROL **Límites mensuales medios**] | Promedio de meses que se incluyen en las solicitudes. Más límites de mes aumentan la complejidad de la solicitud. |
| [!UICONTROL **Columnas medias**] | Número promedio de métricas y desgloses en las solicitudes incluidas. Más columnas aumenta la complejidad de la solicitud. |
| [!UICONTROL **Segmentos medios**] | El número promedio de segmentos aplicados a las solicitudes incluidas. Más segmentos aumenta la complejidad de la solicitud. |

{style="table-layout:auto"}

#### Vista de datos por aplicación

Al seleccionar la variable [!UICONTROL **Aplicación**] , las siguientes columnas están disponibles en la tabla:

| Columna | Descripción |
| --- | --- |
| [!UICONTROL **Aplicación**] | La aplicación donde se iniciaron las solicitudes. |
| [!UICONTROL **Número de solicitudes**] | El número de solicitudes asociadas con la aplicación. |
| [!UICONTROL **Cantidad de usuarios**] | El número de usuarios asociados con la aplicación. <!--???--> |
| [!UICONTROL **Número de proyectos**] | El número de proyectos asociados con la aplicación. <!--???--> |
| [!UICONTROL **Complejidad media**] | Complejidad promedio de las solicitudes asociadas con la aplicación. <p>No todas las solicitudes requieren la misma cantidad de tiempo para procesarse. La complejidad de la solicitud puede ayudar a proporcionar una idea general sobre el tiempo necesario para procesar la solicitud.</p><p>El valor de esta columna se basa en una puntuación que viene determinada por los valores de las columnas siguientes:</p>El valor de esta columna se basa en una puntuación que viene determinada por los valores de las columnas siguientes:<ul><li>[!UICONTROL **Límites mensuales medios**]</li><li>[!UICONTROL **Columnas medias**]</li><li>[!UICONTROL **Segmentos medios**]</li></ul> |
| [!UICONTROL **Límites mensuales medios**] | Promedio de meses que se incluyen en las solicitudes. Más límites de mes aumentan la complejidad de la solicitud. |
| [!UICONTROL **Columnas medias**] | Número promedio de métricas y desgloses en las solicitudes incluidas. Más columnas aumenta la complejidad de la solicitud. |
| [!UICONTROL **Segmentos medios**] | El número promedio de segmentos aplicados a las solicitudes incluidas. Más segmentos aumenta la complejidad de la solicitud. |

{style="table-layout:auto"}

<!--

## Frequently asked questions {#faq}

| Question | Answer |
| --- | --- |
|  |  |

{style="table-layout:auto"}

-->