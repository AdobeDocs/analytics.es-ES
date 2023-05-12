---
description: Obtenga más información sobre cómo utilizar el Administrador de actividades de creación de informes para diagnosticar y corregir problemas de capacidad durante las horas de mayor actividad en la creación de informes.
title: Administrador de actividades de creación de informes
feature: Admin Tools
mini-toc-levels: 3
exl-id: f638c6a9-1c2c-4936-a787-281269f95afc
source-git-commit: 646eb5aeefb17ded89a7041df6f6ad927b799f3f
workflow-type: tm+mt
source-wordcount: '954'
ht-degree: 95%

---

# Administrador de actividades de creación de informes

{{release-limited-testing}}

El [!UICONTROL Administrador de actividades de creación de informes] le permite ver la capacidad de creación de informes de cada grupo de informes de su organización. Como administrador, le ofrece una visibilidad detallada del consumo de creación de informes y le ayuda a diagnosticar y corregir problemas de capacidad durante las horas de mayor actividad de la creación de informes.

Ahora, cuando su organización alcanza el límite de solicitudes de creación de informes y experimenta una degradación en el rendimiento de los mismos, dispone de una forma de autodiagnosticar los problemas de la creación de informes sin la intervención del Servicio de atención al cliente o de ingeniería de Adobe. Puede administrar fácilmente las colas de creación de informes dentro de una sola interfaz y actuar inmediatamente para mejorar la experiencia de los usuarios. Esta herramienta:

* Le informa, en tiempo real, sobre la capacidad actual de creación de informes entre sus grupos de informes.
* Proporciona información detallada de las consultas de creación de informes sobre solicitudes de creación de informes actuales, tanto si están en cola como en curso.
* Le permite optimizar la cola de creación de informes priorizando y cancelando solicitudes de creación de informes para liberar capacidad. En otras palabras, puede preguntar en tiempo real: ¿es necesario este informe en este momento o puedo cancelarlo para darle prioridad a informes más urgentes?

## Acceso al Administrador de actividades de creación de informes

En Adobe Analytics, los administradores acceden a **[!UICONTROL Administrador]** > **[!UICONTROL Administrador de actividades de creación de informes]**.

## Permisos

Se requiere el permiso de administrador de productos de Analytics (en Adobe Admin Console) para administrar la actividad de creación de informes.

![permiso](/help/admin/admin/assets/rep-mgr-permission.png)

## Vista de la cola de informes

Al abrir la página de información general del Administrador de [!UICONTROL actividades de creación de informes], verá una lista de los grupos de informes base habilitados.

![cola de informes](/help/admin/admin/assets/reporting-activity1.png) 

| Elemento de la IU | Descripción |
| --- | --- |
| **[!UICONTROL Grupo de informes]** | El grupo de informes base cuya actividad de creación de informes está monitorizando. |
| **[!UICONTROL Grupo de informes virtuales]** | Muestra todos los grupos de informes virtuales que se alimentan de este grupo de informes base. Los grupos de informes virtuales añaden complejidad a las solicitudes de creación de informes debido a los niveles adicionales de filtrado y segmentación aplicados. Todas las solicitudes que provienen de los grupos de informes virtuales se combinan y se reducen al grupo de informes base.<p>Por ejemplo, si tiene 10 solicitudes procedentes de 5 grupos de informes virtuales, son 50 solicitudes en el grupo de informes base. De este modo, puede alcanzar la capacidad rápidamente. |
| **[!UICONTROL Capacidad de uso]** | Porcentualmente, qué parte de la capacidad de creación de informes del grupo de informes se está utilizando en tiempo real. |
| **[!UICONTROL Estado]** | Hay cuatro posibles indicadores de estado: <ul><li>**Rojo - [!UICONTROL Al límite de la capacidad]**: el grupo de informes está al límite de su capacidad de creación de informes. (100 %) </li><li>**Amarillo - [!UICONTROL Casi a plena capacidad]**: el grupo de informes corre el riesgo de alcanzar su capacidad máxima. (90 % - 99 %)</li><li>**Verde - [!UICONTROL Buen estado]**: hay suficiente capacidad de creación de informes. (0 % - 89 %)</li><li>**Gris - [!UICONTROL Estado pendiente/No habilitado]**: la capacidad de la creación de informes no está disponible.</li></ul> |

{style="table-layout:auto"}

### Otras acciones de actividades de creación de informes

* Haga clic en **[!UICONTROL Actualizar]** en la parte superior derecha para actualizar los resultados.
* Haga clic en la estrella que se encuentra la izquierda del nombre del grupo de informes para marcar como favorito este grupo de informes.
* Marque **[!UICONTROL Favoritos]** en la parte superior izquierda para mostrar sus elementos favoritos.
* En los grupos de informes, haga búsquedas por nombre o por ID en la barra de búsqueda.
* Filtre los grupos de informes por su estado.

## Vista de las actividades de creación de informes de grupos de informes individuales.

Para ver los detalles del grupo de informes que desee, haga clic en el vínculo del título.

![grupo de informes](/help/admin/admin/assets/indiv-report-ste.png)

### Gráfico de líneas {#line}

El gráfico de líneas muestra la actividad de creación de informes de un grupo de informes seleccionado durante las últimas 2 horas.

* El eje X muestra los datos de capacidad de creación de informes de las últimas 2 horas.
* El eje Y muestra la capacidad de uso de informes % por minuto para el grupo de informes seleccionado.
* Puede situarse sobre el gráfico de líneas para ver los puntos en el tiempo en los que el porcentaje de capacidad de uso representado será el % más alto para ese minuto.

   ![detalle](/help/admin/admin/assets/detail.png)

### Filtro

Puede filtrar la tabla por aplicación (consulte la lista en la tabla siguiente), por usuario y por proyecto.

![filtro](/help/admin/admin/assets/filter.png)

### Números de resumen {#summary}

![filtro](/help/admin/admin/assets/summary_numbers.png)

Los números de resumen muestran la siguiente información:

| Número de resumen | Descripción |
| --- | --- |
| [!UICONTROL Usuarios] | Número de usuarios que actualmente envían solicitudes de creación de informes a este grupo de informes. |
| [!UICONTROL Proyectos] | Proyectos de Workspace, libros de Report Builder, etc. |
| [!UICONTROL Consultas] | Número de consultas que se están ejecutando actualmente. |
| [!UICONTROL Tiempo de espera promedio] | El tiempo de espera promedio para todas las consultas en ejecución. |
| [!UICONTROL Capacidad de uso] | La capacidad de uso actual de este grupo de informes. |

{style="table-layout:auto"}

### Tabla con detalles del grupo de informes {#details}

La tabla detallada a continuación muestra los detalles del grupo de informes.

| Columna | Descripción |
| --- | --- |
| [!UICONTROL ID de consulta] | Se puede utilizar para solucionar problemas. |
| [!UICONTROL Tiempo de ejecución] | Cuánto tiempo lleva ejecutándose la consulta. |
| [!UICONTROL Tiempo de espera] | El tiempo que la consulta ha estado esperando antes de procesarse. Generalmente en &quot;0&quot; cuando hay suficiente capacidad. |
| [!UICONTROL Hora de inicio] | Cuando la consulta comenzó a procesarse (hora local del administrador). |
| [!UICONTROL Aplicación] | Las aplicaciones compatibles con el [!UICONTROL Administrador de actividades de creación de informes] son: <ul><li>IU de Analysis Workspace</li><li>Proyectos programados de Workspace</li><li>Report Builder</li><li>IU del generador: Segmento, Métricas calculadas, Anotaciones, Audiencias, etc.</li><li>Llamadas de API desde la API 1.4 o 2.0</li><li>Alertas inteligentes</li></ul> |
| [!UICONTROL Usuario] | El usuario que inició la consulta. |
| [!UICONTROL Proyecto] | Nombres de proyectos de Workspace guardados, ID de informes de API, etc. (Los metadatos pueden variar entre distintas aplicaciones). |
| [!UICONTROL Límites del mes] | ¿Cuántos límites mensuales cruza una solicitud? Esto aumenta la complejidad de la solicitud. |
| [!UICONTROL Columnas] | Número de métricas y desgloses en Workspace para medir la complejidad de la solicitud. |
| [!UICONTROL Segmentos] | Cuántos segmentos se aplican a esta solicitud. Esto aumenta la complejidad de la solicitud. |
| [!UICONTROL Estado] | Indicadores de estado: <ul><li>**Ejecución**: la solicitud está siendo procesada en este momento.</li><li>**Pendiente**: la solicitud está esperando a procesarse.</li></ul> |

{style="table-layout:auto"}

## Cancelar solicitudes de creación de informes {#cancel}

Para cancelar una solicitud

1. Marque la casilla a la izquierda de una o más **[!UICONTROL ID de consulta]** en la tabla y haga clic en **[!UICONTROL Cancelar solicitudes]** en la parte inferior.

   Puede cancelar las solicitudes de forma masiva consultando los detalles mediante [!UICONTROL Usuario], [!UICONTROL Proyecto] o [!UICONTROL Aplicación]. Las solicitudes posteriores de un proyecto, usuario o aplicación que no estaban en cola o que se estaban ejecutando en el momento de la cancelación pueden seguir apareciendo cuando se actualiza la actividad.

1. En la ventana **[!UICONTROL Cancelar x consulta]** que aparece, puede modificar el mensaje de cancelación, si es necesario.
1. Haga clic en **[!UICONTROL Continuar]**.

   ![cancelar-consulta](/help/admin/admin/assets/cancel-query.png)

Los usuarios de aplicaciones de Workspace, por ejemplo, verán aparecer el siguiente aviso en sus proyectos:

![aviso-cancelar-usuario](/help/admin/admin/assets/cancel-user-facing.png)

## Preguntas frecuentes {#faq}

| Pregunta | Respuesta |
| --- | --- |
| ¿Puedo adquirir capacidad adicional de creación de informes? | Esta capacidad estará disponible próximamente. |

{style="table-layout:auto"}
