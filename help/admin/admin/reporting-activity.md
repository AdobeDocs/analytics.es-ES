---
description: Obtenga información sobre cómo utilizar el administrador de actividades de informes para diagnosticar y corregir problemas de capacidad durante las horas de mayor actividad en los informes.
title: Administrador de actividades de creación de informes
feature: Admin Tools
mini-toc-levels: 3
source-git-commit: 1f42ca083346f673f6685ca43f361b19c644975d
workflow-type: tm+mt
source-wordcount: '919'
ht-degree: 7%

---


# Administrador de actividades de creación de informes

>[!NOTE]
>
>Esta funcionalidad se encuentra actualmente en fase de prueba beta.

La variable [!UICONTROL Administrador de actividades de informes] le permite ver la capacidad de creación de informes de cada grupo de informes de su organización. Como administrador, le ofrece una visibilidad detallada del consumo de los informes y le ayuda a diagnosticar y solucionar problemas de capacidad durante las horas de mayor actividad de los informes.

Cuando su organización llega a la capacidad de las solicitudes de informes y experimenta una degradación en el rendimiento de los informes, ahora tiene una forma de autodiagnosticar los problemas de los informes sin intervención del servicio de atención al cliente o ingeniería de Adobe. Puede administrar fácilmente las colas de informes dentro de una sola interfaz y actuar inmediatamente &#x200B; &#x200B; para mejorar la experiencia de los usuarios. Esta herramienta:

* Le informa, en tiempo real, sobre su capacidad actual de creación de informes en sus grupos de informes.
* Proporciona información detallada de las consultas de informes sobre solicitudes de informes actuales, estén en cola o en curso.
* Permite optimizar la cola de informes priorizando algunas y cancelando otras solicitudes de informes para liberar capacidad. En otras palabras, puede preguntar en tiempo real: ¿es necesario este informe en este momento o puedo cancelarlo a favor de informes más urgentes?

## Acceso al Administrador de actividades de informes

En Adobe Analytics, los administradores acceden a **[!UICONTROL Administrador]** > **[!UICONTROL Administrador de actividades de informes]**.

## Permisos

Para administrar la actividad de creación de informes, necesita permisos de administración del sistema de Analytics. El acceso del administrador de productos no es suficiente.

## Ver la cola de informes

Al abrir el [!UICONTROL Actividad de informes] Página de información general del administrador, verá una lista de los grupos de informes base habilitados.

![cola de informes](assets/reporting-activity1.png)

| Elemento de la IU | Descripción |
| --- | --- |
| **[!UICONTROL Grupo de informes]** | El grupo de informes base cuya actividad de informes está monitorizando. |
| **[!UICONTROL Grupo de informes virtuales]** | Muestra todos los grupos de informes virtuales que se alimentan de este grupo de informes base. Los grupos de informes virtuales añaden complejidad a las solicitudes de informes debido a los niveles adicionales de filtrado y segmentación aplicados. Todas las solicitudes procedentes de los grupos de informes virtuales se combinan y se reducen al grupo de informes base.<p>Por ejemplo, si tiene 10 solicitudes procedentes de 5 VRS, son 50 solicitudes en el grupo de informes de nivel base. De esta manera, puede alcanzar la capacidad rápidamente. |
| **[!UICONTROL Capacidad de uso]** | En porcentaje, qué parte de la capacidad de informes del grupo de informes se está utilizando, en tiempo real. |
| **[!UICONTROL Estado]** | Cuatro posibles indicadores de estado: <ul><li>**Rojo - [!UICONTROL A la capacidad]**: El grupo de informes se define como máximo en términos de capacidad de informes. (100%) </li><li>**Amarillo - [!UICONTROL Capacidad de lectura]**: Este grupo de informes corre el riesgo de alcanzar su capacidad máxima. (90 % - 99 %)</li><li>**Verde - [!UICONTROL Todo bien]**: Hay mucha capacidad de generación de informes. (0 % - 89 %)</li><li>**Gris [!UICONTROL Estado pendiente/No habilitado]**: Capacidad de los informes no disponible.</li></ul> |

{style=&quot;table-layout:auto&quot;}

### Otras acciones de actividades de informes

* Haga clic en **[!UICONTROL Actualizar]** en la parte superior derecha para actualizar los resultados.
* Haga clic en la estrella a la izquierda del nombre del grupo de informes para marcar como favorito este grupo de informes.
* Marque **[!UICONTROL Favoritos]** en la parte superior izquierda para mostrar sus favoritos.
* Busque grupos de informes por nombre o por ID en la barra de búsqueda.
* Filtre los grupos de informes por su estado.

## Ver la actividad de informes de grupos de informes individuales

Haga clic en el vínculo de título de un grupo de informes para el que desee ver los detalles.

![grupo de informes](assets/indiv-report-ste.png)

### Gráfico de líneas

El gráfico de líneas muestra la actividad de informes del grupo de informes seleccionado durante las últimas 2 horas.

* El eje x muestra los datos de capacidad de informes de las últimas 2 horas.
* El eje Y muestra el tiempo de espera promedio para una consulta, en segundos.
* Puede situarse sobre el gráfico de líneas para ver los puntos en el tiempo y el tiempo de espera promedio para ese instante.

   ![detalle](assets/detail.png)

### Filtro

Puede filtrar la tabla por aplicación (consulte la lista en la tabla siguiente), por usuario y por proyecto.

![filtro](assets/filter.png)

### Números de resumen

![filtro](assets/summary_numbers.png)

Los números de resumen muestran la siguiente información:

| Número de resumen | Descripción |
| --- | --- |
| [!UICONTROL Usuarios] | Cuántos usuarios están enviando solicitudes de informes actualmente a este grupo de informes. |
| [!UICONTROL Proyectos] | Proyectos de Workspace, libros de Report Builder, etc. |
| [!UICONTROL Consultas] | Número de consultas que se están ejecutando actualmente. |
| [!UICONTROL Tiempo de espera promedio] | El tiempo de espera promedio para todas las consultas en ejecución. |
| [!UICONTROL Capacidad de uso] | La capacidad de uso actual de este grupo de informes. |

{style=&quot;table-layout:auto&quot;}

### Tabla

La tabla detallada a continuación muestra los detalles del grupo de informes.

| Columna | Descripción |
| --- | --- |
| [!UICONTROL ID de consulta] | Se puede utilizar para solucionar problemas. |
| [!UICONTROL Tiempo de ejecución] | Cuánto tiempo lleva ejecutándose la consulta. |
| [!UICONTROL Tiempo de espera] | El tiempo que la consulta ha estado esperando antes de procesarse. Generalmente en &quot;0&quot; cuando hay suficiente capacidad. |
| [!UICONTROL Hora de inicio] | Cuando la consulta comenzó a procesarse (hora local del administrador). |
| [!UICONTROL de asistencia al cliente] | Las aplicaciones compatibles con la variable [!UICONTROL Administrador de actividades de informes] son: <ul><li>IU de Analysis Workspace</li><li>Proyectos programados de Workspace</li><li>Report Builder</li><li>IU del generador: Segmento, Métricas calculadas, Anotaciones, Audiencias, etc.</li><li>Llamadas de API desde la API 1.4 o 2.0</li><li>Alertas inteligentes</li></ul> |
| [!UICONTROL Usuario] | El usuario que inició la consulta. |
| [!UICONTROL Proyecto] | Nombres de proyectos de Workspace guardados, ID de informes de API, etc. (Los metadatos pueden variar entre distintas aplicaciones). |
| [!UICONTROL Límites del mes] | ¿Cuántos límites mensuales cruza una solicitud? Esto aumenta la complejidad de la solicitud. |
| [!UICONTROL Columnas] | Número de métricas y desgloses en Workspace para medir la complejidad de la solicitud. |
| [!UICONTROL Segmentos] | Cuántos segmentos se aplican a esta solicitud. Esto aumenta la complejidad de la solicitud. |
| [!UICONTROL Estado] | Indicadores de estado: <ul><li>**Ejecución**: La solicitud se está procesando actualmente.</li><li>**Pendiente**: La solicitud está esperando a procesarse.</li></ul> |

{style=&quot;table-layout:auto&quot;}

## Cancelar solicitudes de informes

Para cancelar una solicitud

1. Marque la casilla a la izquierda de una o más **[!UICONTROL ID de consulta]** en la tabla y haga clic en **[!UICONTROL Cancelar solicitudes]** en la parte inferior.
1. En el **[!UICONTROL Cancelar x consulta]** que aparece, puede modificar el mensaje de cancelación, si es necesario.
1. Haga clic en **[!UICONTROL Continuar]**.

   ![cancel-query](assets/cancel-query.png)

Los usuarios de aplicaciones de Workspace, por ejemplo, verán aparecer el siguiente aviso en sus proyectos:

![cancel-user-notice](assets/cancel-user-facing.png)


## Preguntas frecuentes

| Pregunta | Respuesta |
| --- | --- |
| ¿Puedo adquirir capacidad de informes adicional? | Esta capacidad estará disponible próximamente. |

{style=&quot;table-layout:auto&quot;}
