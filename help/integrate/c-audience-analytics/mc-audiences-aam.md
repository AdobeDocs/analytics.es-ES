---
description: Adobe Audience Manager (Adobe Audience Manager) es una potente plataforma de administración de datos que le ayuda a crear perfiles de audiencia únicos a partir de integraciones de datos de origen, secundarias o de socio, y de terceros. Para los anunciantes, estos perfiles de público ayudan a definir los segmentos más valiosos que se pueden utilizar en cualquier canal digital.
solution: Experience Cloud
title: Resumen de Audience Analytics
feature: Audience Analytics
exl-id: 1665a554-8a6f-4b20-99b7-bb3c2c4bf8cc
TQID: https://experienceleague.adobe.com/WPB1fEJx1MaWpUNRCZ48ghAVyKyc5IwoGOdgQQ-tPhI
product_v2:
  - id: d0a3eab4-7b10-4d96-a71e-6c0f8e7b7c87
feature_v2:
  - id: fc7979f3-56c3-43ca-9784-f1ea3dc69c4b
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: cdd65e7e-8839-44a2-bc21-0e03623b5dd1
  - id: df401a2a-327d-468c-a5e4-b7b7ccd071a0
  - id: ebde5b41-29c9-4f5e-9ef6-1197e85409e3
  - id: fd2e3797-f2ea-4b36-a9af-52acf5e90513
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 522
ht-degree: 41%

---

# Resumen de Audience Analytics

Adobe Audience Manager (Adobe Audience Manager) es una potente plataforma de administración de datos que le ayuda a crear perfiles de audiencia únicos a partir de integraciones de datos de origen, secundarias o de socio, y de terceros. Para los anunciantes, estos perfiles de público ayudan a definir los segmentos más valiosos que se pueden utilizar en cualquier canal digital.

Con la integración de Audience Analytics, puede incorporar datos de audiencia de Adobe Audience Manager, como información demográfica (p. ej., sexo o nivel de ingresos), información psicográfica (p. ej., intereses y aficiones), datos CRM y datos de impresión publicitaria a cualquier flujo de trabajo de Analytics.


>[!BEGINSHADEBOX]

Consulte ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Audience Analytics](https://experienceleague.adobe.com/es/docs/analytics-learn/tutorials/integrations/audience-manager/audience-analytics-integrate-aam-segments-into-analytics){target="_blank"} para ver un vídeo de demostración.

>[!ENDSHADEBOX]


## Ventajas principales {#benefits}

La integración de Audience Analytics ofrece las siguientes ventajas principales:

* Supone la primera integración de productos entre una plataforma de administración de datos (DMP) y un motor de análisis.
* Los segmentos se comparten desde Adobe Audience Manager a Analytics en tiempo real para informar sobre la detección de audiencias, la segmentación y la optimización.
* Todos los segmentos de Adobe Audience Manager se comparten de forma predeterminada, lo que enriquece en gran medida los perfiles de cliente de Analytics.
* Los administradores de soluciones pueden habilitar la integración desde la interfaz de usuario, solo se requieren cambios mínimos en el código.
* Solo se comparten los segmentos que satisfacen los controles de exportación de datos de Audience Manager.

## Cómo funciona Audience Analytics {#works}

![](assets/mc-aud-dataflow.png)

1. Cada vez que un visitante llega a una de sus propiedades digitales, las visitas se recopilan y se envían a Analytics.
1. Con el [reenvío del lado del servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md), cada visita que Analytics recibe se envía automáticamente a Adobe Audience Manager en tiempo real.
1. Con la integración de Audience Analytics, para cada visita se busca en Adobe Audience Manager si el visitante pertenece a alguna audiencia y se devuelve a Analytics una lista de ID de segmento para su procesamiento en tiempo real.

Como los segmentos de Adobe Audience Manager se insertan por visita, puede estar seguro de que no le faltará ningún dato de Adobe Audience Manager sobre un visitante, y de que los datos de las visitas de dicho visitante estarán actualizados. Esta característica es mejor que un complemento de AppMeasurement, ya que los complementos solo pueden ofrecer los segmentos en la siguiente visita (y no en la visita actual).

Además, clasificamos automáticamente los ID de segmento de Adobe Audience Manager con sus nombres descriptivos para que no tengan que ver los ID alfanuméricos en los informes de Analytics.

## Requisitos previos {#prerequisites}

Asegúrese de que se cumplen los siguientes requisitos previos:

* Es cliente tanto de Audience Manager como de Adobe Analytics.
* Es administrador de Audience Manager.
* Utiliza Identity Service 1.5 o posterior.
* Los grupos de informes de Adobe Audience Manager y Adobe Analytics se asignan a la misma organización de Experience Cloud.
* Utiliza el [reenvío de lado del servidor](/help/admin/tools/manage-rs/edit-settings/general/c-server-side-forwarding/ssf.md) y tiene implementado el [módulo Gestión de público](https://experienceleague.adobe.com/docs/audience-manager/user-guide/implementation-integration-guides/integration-other-solutions/audience-management-module.html?lang=es) (sin código DIL): AppMeasurement 1.5 o posterior.

Estos requisitos previos se describen en el [flujo de trabajo de Audience Analytics](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md).
