---
description: Esta integración combina las funciones de investigación de los clientes de Qualtrics Research Suite con los abundantes datos que recopila en Adobe Analytics para crear potentes oportunidades de optimización y análisis para su organización.
subtopic: Qualtrics
title: Data Connectors de Qualtrics para Adobe Analytics
feature: Data Connectors
uuid: f1fa90b6-1b80-4da4-a39b-efb8bac1692a
exl-id: 5c1234b1-bca8-4e7a-981e-1379e88821b8
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '305'
ht-degree: 96%

---

# Data Connectors de Qualtrics para Adobe Analytics {#qualtrics-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>El 1 de agosto de 2021 finalizaremos la vida útil de la tecnología del conector de datos de Adobe. [Más información...](/help/import/data-connectors/data-connectors-eol.md)

Esta integración combina las funciones de investigación de los clientes de Qualtrics Research Suite con los abundantes datos que recopila en Adobe Analytics para crear potentes oportunidades de optimización y análisis para su organización.

Esta integración bidireccional conecta primero los datos de respuesta de las encuestas de Qualtrics con los datos del flujo de navegación del visitante. A continuación, inserta acciones y atributos de comportamiento relevantes, desde Adobe Analytics, en los informes de encuestas de Qualtrics.

## Ventajas y características principales {#key-benefits-and-features}

* Genere segmentos de usuarios basados en las respuestas que los usuarios dan a preguntas específicas en las encuestas.
* Informes de tráfico y conversión basados en los detalles de las encuestas, la pregunta y el nivel de respuesta.
* Utiliza solo 1 ListVar, 1 eVar y 1 evento para integrar encuestas de Qualtrics ilimitadas.
* Mejore los informes de calidad con hasta 5 dimensiones de conversión personalizadas, 5 dimensiones de tráfico personalizadas, 5 eventos de éxito personalizados y más de 20 métricas y dimensiones estándar con seguimiento de parte de Adobe Analytics.
* Los datos de encuestas integrados en Adobe Analytics se transfieren en “directo” a medida que se envían las respuestas. Las exportaciones a Qualtrics son diarias.

## Antes de activar este conector {#before-you-activate-this-connector}

### Requisitos previos de Adobe {#section-fd37a66150c34cd6b494d13f75e5fb0d}

* Debe ser cliente actual de Adobe Analytics.
* Debe ser un usuario administrador.
* Debe tener 1 variable de lista disponible y habilitada dentro del grupo de informes.
* Debe tener 1 variable eVar (o prop) disponible y habilitada dentro del grupo de informes.
* Debe tener 1 evento personalizado disponible dentro del grupo de informes.

### Requisitos previos de Qualtrics {#section-dbb780af47c145d7b6ae12acde3ca94c}

* Debe ser cliente de Qualtrics Research Suite.
* Debe ser un usuario con permisos para habilitar la integración de Adobe Analytics.
* Debe poder generar un token de Adobe Analytics en el área **[!UICONTROL ID de Qualtrics]** de Research Suite.
