---
description: Obtenga información sobre cómo utilizar el administrador de actividades de informes para diagnosticar y corregir problemas de capacidad durante las horas de mayor actividad en los informes.
title: Administrador de actividades de creación de informes
feature: Admin Tools
mini-toc-levels: 3
hide: true
hidefromtoc: true
source-git-commit: 77b3e8a1f8ebb1459eeac83f098cab92f671efe6
workflow-type: tm+mt
source-wordcount: '464'
ht-degree: 3%

---


# Administrador de actividades de creación de informes

>[!NOTE]
>
>Esta funcionalidad se encuentra actualmente en fase de prueba beta.

El Administrador de actividades de informes le permite ver la capacidad de informes de cada grupo de informes de su organización. Como administrador, le ofrece una visibilidad detallada del consumo de los informes y le ayuda a diagnosticar y solucionar problemas de capacidad durante las horas de mayor actividad de los informes. Cuando su organización llega a la capacidad de las solicitudes de informes y experimenta una degradación en el rendimiento de los informes, ahora tiene una forma de autodiagnosticar los problemas de los informes sin intervención del servicio de atención al cliente o ingeniería de Adobe. Puede administrar fácilmente las colas de informes dentro de una sola interfaz y actuar inmediatamente &#x200B; &#x200B; para mejorar la experiencia de los usuarios. Esta herramienta:

* Le informa sobre su capacidad actual de creación de informes en sus grupos de informes.
* Proporciona información detallada de las consultas de informes sobre solicitudes de informes actuales, tanto si están en cola como en curso.
* Permite optimizar la cola de informes priorizando algunas y cancelando otras solicitudes de informes para liberar capacidad. En otras palabras, puede preguntar en tiempo real: ¿es necesario este informe en este momento o puedo cancelarlo a favor de informes más urgentes?

## Acceso al Administrador de actividades de informes

En Adobe Analytics, los administradores acceden a **[!UICONTROL Administrador]** > **[!UICONTROL Administrador de actividades de informes]**.

## Ver la cola de informes

Al abrir la página de información general de Administrador de actividades de informes , verá una lista de los grupos de informes base habilitados.

![cola de informes](assets/reporting-activity1.png)

| Elemento de la IU | Descripción |
| --- | --- |
| **[!UICONTROL Grupo de informes]** | El grupo de informes base cuya actividad de informes está monitorizando. |
| **[!UICONTROL Grupo de informes virtuales]** | Muestra todos los grupos de informes virtuales que se alimentan de este grupo de informes base. Los grupos de informes virtuales añaden complejidad a las solicitudes de informes debido a los niveles adicionales de filtrado y segmentación aplicados. Todas las solicitudes procedentes de los grupos de informes virtuales se combinan y se reducen al grupo de informes base.<p>Por ejemplo, si tiene 10 solicitudes procedentes de 5 VRS, son 50 solicitudes en el grupo de informes de nivel base. De esta manera, puede alcanzar la capacidad rápidamente. |
| **[!UICONTROL Capacidad de uso]** | En porcentaje, qué parte de la capacidad de informes del grupo de informes se está utilizando, en tiempo real. |
| **[!UICONTROL Estado]** | Cuatro posibles indicadores de estado: <ul><li>**Rojo - En Capacidad**: El grupo de informes se define como máximo en términos de capacidad de informes.</li><li>**Amarillo - Capacidad de lectura**: Este grupo de informes corre el riesgo de alcanzar su capacidad máxima.</li><li>**Verde - Todo bien**: Hay mucha capacidad de generación de informes.</li><li>**[!UICONTROL Estado pendiente]**: ?</li><li>**Gris: no disponible**: El grupo de informes no está configurado para la capacidad de generación de informes.</li></ul> |

### Informes de acciones de actividades

* Haga clic en **[!UICONTROL Actualizar]** en la parte superior derecha para actualizar los resultados.
* Haga clic en la estrella a la izquierda del nombre del grupo de informes para marcar como favorito este grupo de informes.
* Marque **[!UICONTROL Favoritos]** en la parte superior izquierda para mostrar sus favoritos.
* Busque grupos de informes por nombre o por ID en la barra de búsqueda.
* Filtre los grupos de informes por su estado.

## Ver la actividad de informes de grupos de informes individuales



