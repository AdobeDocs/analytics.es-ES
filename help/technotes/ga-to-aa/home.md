---
title: Transición de una plataforma de análisis de terceros a Adobe Analytics
description: Aprendizaje de los conceptos clave para obtener informes dirigido a usuarios familiarizados con otras plataformas, como Google Analytics.
translation-type: tm+mt
source-git-commit: 3211598c2ff43493b329a9be4fb6877ae29cf08b
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 88%

---


# Transición de una plataforma de análisis de terceros a Adobe Analytics

Esta guía presenta los tipos de informes más comunes y le ayuda a interiorizar los conceptos y flujos de trabajo principales de Adobe Analytics, haciendo especial hincapié en las similitudes y diferencias clave entre Adobe y otras herramientas populares. Esta guía está destinada a analistas familiarizados con conceptos básicos de análisis digital, pero que nunca hayan usado Adobe Analytics. La guía da por hecho que su organización tiene una implementación en funcionamiento que envía datos a los servidores de recopilación de datos de Adobe. Si su organización aún no ha configurado una implementación de Adobe Analytics, comience con la [Guía de administración de Adobe Analytics](/help/admin/admin-console/first-admin-guide.md).

Tanto Google Analytics como Adobe Analytics son plataformas potentes que permiten obtener datos valiosos sobre el rendimiento de su sitio web. Cada una de ellas tiene su propia arquitectura de procesamiento y su interfaz de usuario, lo que proporciona a cada plataforma ventajas únicas. Esta guía se ha diseñado para iniciar en Adobe Analytics a los usuarios experimentados de Google Analytics.

En Adobe Analytics, hay dos formas principales de extraer informes básicos después de iniciar sesión en Adobe Experience Cloud:

* **Reports &amp; Analytics** es el método histórico para extraer informes básicos. El menú de la izquierda proporciona una lista de informes prefabricados y permite al usuario navegar hasta el informe que desee y obtener datos. Los segmentos y las métricas proporcionan un grado de personalización aún mayor. Es posible que este diseño le resulte familiar a los usuarios que tengan experiencia con los informes de Google Analytics.
* **Analysis Workspace** es el método que se recomienda actualmente para extraer la mayoría de los informes. El menú de la izquierda permite al usuario arrastrar y soltar componentes para crear su propio informe. Permite un mayor grado de flexibilidad, por lo que se adapta perfectamente a sus necesidades específicas en materia de informes. Es posible que los usuarios con experiencia en la creación de tableros e informes personalizados de Google Analytics estén familiarizados con este diseño.

Most reports can be created in both [!UICONTROL Reports &amp; Analytics] and [!UICONTROL Analysis Workspace]. Sin embargo, algunos informes solo se pueden extraer mediante una plataforma en concreto. In most cases, Adobe recommends using [!UICONTROL Analysis Workspace], unless a specific feature is only available in [!UICONTROL Reports &amp; Analytics].

## Ruta de aprendizaje recomendada

Adobe recomienda empezar con los conceptos más básicos sobre la obtención de datos de informes:

* [Crear un informe básico en Analysis Workspace para usuarios de GA](reports/create-report.md)

Once you are familiar with components in [!UICONTROL Analysis Workspace], you can learn how to recreate most reports using the right components.

* [Creación de informes en tiempo real en Adobe Analytics](reports/realtime-reports.md)
* [Creación de informes de audiencia en Adobe Analytics](reports/audience-reports.md)
* [Creación de informes de adquisición en Adobe Analytics](reports/acquisition-reports.md)
* [Creación de informes de comportamiento en Adobe Analytics](reports/behavior-reports.md)
* [Creación de informes de conversiones en Adobe Analytics](reports/conversions-reports.md)

Después de aprender a extraer informes, comprender [las diferencias de arquitectura y procesamiento](processing-differences.md) puede ayudarle a interpretar las diferencias en los valores obtenidos en cada plataforma. También está disponible una sección de [preguntas frecuentes](faq.md).
