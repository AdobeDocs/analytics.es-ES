---
description: Obtenga información sobre cómo utilizar el administrador de actividades de informes para diagnosticar y corregir problemas de capacidad durante las horas de mayor actividad en los informes.
title: Administrador de actividades de creación de informes
feature: Admin Tools
hide: true
hidefromtoc: true
source-git-commit: 70cfad1a04d17e1007178f32af73988be503fe90
workflow-type: tm+mt
source-wordcount: '329'
ht-degree: 1%

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

## Administrar la cola de informes

Al abrir el Administrador de actividades de informes, verá una lista de los grupos de informes base. Los grupos de informes virtuales no se incluyen en esta vista.

![cola de informes](assets/reporting-activity1.png)

Los grupos de informes virtuales añaden complejidad a las solicitudes de informes debido a los niveles adicionales de filtrado y segmentación aplicados. Todas las solicitudes procedentes de los grupos de informes virtuales se combinan y se reducen al grupo de informes base. Por lo tanto, si tiene 10 solicitudes procedentes de 5 VRS, estas son 50 solicitudes en el grupo de informes de nivel base. De esta manera, puede alcanzar la capacidad rápidamente.

Esta es una vista de un VRS cuya capacidad de creación de informes se muestra en tiempo real:

![grupos de informes virtuales](assets/reporting-activity-vrs.png)

Actualice la página para cambiar los resultados.

## Repercusiones de los informes del espacio de trabajo





