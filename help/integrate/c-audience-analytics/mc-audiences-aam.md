---
description: Adobe Audience Manager (AAM) es una potente plataforma de administración de datos que le ayuda a crear perfiles de audiencia únicos a partir de integraciones de datos de origen, secundarias o de socio, y de terceros. Para los anunciantes, estos perfiles de audiencia ayudan a definir los segmentos más valiosos que se pueden utilizar en cualquier canal digital.
seo-description: Adobe Audience Manager (AAM) es una potente plataforma de administración de datos que le ayuda a crear perfiles de audiencia únicos a partir de integraciones de datos de origen, secundarias o de socio, y de terceros. Para los anunciantes, estos perfiles de audiencia ayudan a definir los segmentos más valiosos que se pueden utilizar en cualquier canal digital.
seo-title: Resumen de Audience Analytics
solution: Experience Cloud
title: Resumen de Audience Analytics
uuid: 86ef9391-dd6a-495f-a10e-e98bc069dde4
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# Resumen de Audience Analytics

Adobe Audience Manager (AAM) es una potente plataforma de administración de datos que le ayuda a crear perfiles de audiencia únicos a partir de integraciones de datos de origen, secundarias o de socio, y de terceros. Para los anunciantes, estos perfiles de audiencia ayudan a definir los segmentos más valiosos que se pueden utilizar en cualquier canal digital.

Cuando se establece la integración de Audience Analytics, puede incorporar datos de audiencia de AAM, como información demográfica (p. ej., sexo o nivel de ingresos), información psicográfica (p. ej., intereses y aficiones), datos CRM y datos de impresiones de publicidad en cualquier flujo de trabajo de Analytics.

## Ventajas principales {#section_94816D17283349E0BA28521BE55BB868}

La integración de Audience Analytics ofrece las siguientes ventajas principales:

* Supone la primera integración de productos entre una plataforma de administración de datos (DMP) y un motor de análisis.
* AAM comparte segmentos en tiempo real con Analytics para permitir la detección de audiencias, la segmentación y la optimización.
* De forma predeterminada, AAM comparte todos sus segmentos, lo que enriquece en gran medida los perfiles de cliente de Analytics.
* Los administradores de soluciones pueden habilitar la integración desde la interfaz de usuario, solo se requieren cambios mínimos en el código.
* Solo se comparten los segmentos que satisfacen los controles de exportación de datos de Audience Manager.

## Cómo funciona {#section_CECDF5A0FEC64264B206EFEF54F19EF2}

![](assets/mc-aud-dataflow.png)

1. Cada vez que un visitante llega a una de sus propiedades digitales, las visitas se recopilan y se envían a Analytics.
1. Con el [reenvío de servidor](/help/admin/admin/c-server-side-forwarding/ssf.md), cada visita que Analytics recibe se envía automáticamente a AAM en tiempo real.
1. A través de la integración de Audience Analytics, en cada visita se busca la pertenencia de un visitante a una audiencia en AAM y se devuelve una lista de ID de segmento a Analytics para su procesamiento en tiempo real.

Como los segmentos de AAM se insertan por visita, puede estar seguro de que no le faltará ningún dato de AAM acerca de un visitante, y de que los datos de las visitas de dicho visitante estarán actualizados. Esta característica es mejor que un complemento de AppMeasurement, ya que los complementos solo pueden ofrecer los segmentos en la siguiente visita (y no en la visita actual).

Además, clasificamos automáticamente los ID de segmento de AAM con sus nombres descriptivos, de modo que no tenga que consultar los ID alfanuméricos en los informes de Analytics.

## Requisitos previos {#section_A345DC31F7D44EAE9DC1AB53E824C0CC}

Asegúrese de que se cumplen los siguientes requisitos previos:

* Es cliente tanto de Audience Manager como de Adobe Analytics.
* Es administrador de Audience Manager.
* Utiliza Identity Service v1.5 o posterior.
* Los grupos de informes de Adobe Analytics y AAM se [asignan a la misma organización de Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).
* You use [server-side forwarding](/help/admin/admin/c-server-side-forwarding/ssf.md) and have implemented the [Audience Management module](https://marketing.adobe.com/resources/help/en_US/aam/c_profiles_audiences.html) (no DIL code) - AppMeasurement 1.5 or later.

Estos requisitos previos se describen en el flujo de trabajo [de](/help/integrate/c-audience-analytics/c-workflow/audiences-workflow.md)Audience Analytics.
