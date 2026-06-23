---
title: Notas de la versión de Adobe Analytics actual
description: Ver las notas de la versión actuales de Adobe Analytics
feature: Release Notes
exl-id: 97d16d5c-a8b3-48f3-8acb-96033cc691dc
TQID: 'https://experienceleague.adobe.com/yw30Yij2NBaeuWFqxD4-VH1Hysf8dxOpxHUwsFCYEw8'
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7id: fd307ce7-56f5-4ee3-af68-a7833ff6e85eid: a421fb65-2c82-457a-921c-28c46b697a39
subfeature_v2: id: d89ba969-e026-48bf-927e-e9df2f1e34f3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550ccid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d095671a-1355-40aa-8b5f-06c33c68080bid: d3cdead0-685a-4489-9250-4bb709942f66id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: 6adcad3efbe3c7f38ba8b15f835d700861fd2209
workflow-type: tm+mt
source-wordcount: 573
ht-degree: 90%

---

# Notas de la versión actuales de Adobe Analytics (junio de 2026)

**Última actualización**: 22 de junio de 2026

Estas notas de la versión abarcan el período de la versión de junio de 2026. Las versiones de Adobe Analytics funcionan con un [modelo de entrega continua](releases.md) que permite un enfoque más escalable y gradual de la implementación de funcionalidades. Por lo tanto, estas notas de la versión se actualizan varias veces al mes. Compruébelas regularmente.

## Nuevas funciones o mejoras {#features}

| Función y descripción | [Inicio del despliegue](releases.md) | [Disponibilidad general](releases.md) |
| ----------- | ---------- | ---- |
| **Lienzo del recorrido en Adobe Analytics** <br/>Lienzo del recorrido es una visualización en Analysis Workspace que le permite obtener información exhaustiva de un recorrido de usuario definido al analizar las personas que pasan o salen de un recorrido. Permite crear un gráfico flexible de nodos y flechas que representan cualquier combinación de eventos, elementos de dimensión y segmentos incluidos en el recorrido. Los datos se actualizan conforme vaya arrastrando los nodos en el lienzo o reorganizando los eventos y las condiciones del recorrido.<p>Anteriormente, el lienzo de recorrido solo estaba disponible para Customer Journey Analytics.</p><p>Para obtener más información acerca de los lienzos del recorrido, consulte [Información general de los lienzos del recorrido](/help/analyze/analysis-workspace/visualizations/journey-canvas/journey-canvas.md). </p><p>Para aprender a crear una visualización de lienzo del recorrido en Adobe Analytics, consulte [Configurar lienzo del recorrido](/help/analyze/analysis-workspace/visualizations/journey-canvas/configure-journey-canvas.md).</p> | 18 de mayo de 2026 | 5 de junio de 2026 |

### Correcciones en Adobe Analytics

**Activity Map**:
**Analysis Workspace**: AN-452009, AN-450375, AN-449870, AN-450814, AN-450698
**Clasificaciones**:
**Fuentes de datos y Data Warehouse**:
**Migración**:
**Exportaciones**:
**Report Builder**: AN-440912
**Informes**: AN-423516
**Grupos de informes**: AN-455684
**Informes programados**:
**Segmentación**:
**Otros**:


### Avisos de final de la vida útil {#eol}

| Final de la vida útil de producto o función | Fecha de incorporación o actualización | Descripción |
| --- | --- | --- |
| **Report Builder heredado** | 18 de junio de 2025 | El complemento heredado de Report Builder se eliminará en junio de 2026. Todos los usuarios deberían empezar a actualizar sus libros heredados al [nuevo Report Builder](/help/analyze/report-builder/rb-overview.md). El nuevo Report Builder está disponible para los clientes de Adobe Analytics y Customer Journey Analytics. Tiene [casi paridad de características](/help/analyze/report-builder/convert-workbooks.md#unsupported), además de muchas nuevas características convenientes y mejoras en la interfaz de usuario. Para facilitar el proceso de actualización, el nuevo Report Builder incluye una sencilla función de conversión de libros. El nuevo Report Builder solo está disponible como complemento en Microsoft Store. Muchas organizaciones requieren un proceso de aprobación interno para poder poner el complemento a disposición de los usuarios. Deje tiempo para este proceso y empiece a trabajar con su organización ahora para asegurarse de que dispone de tiempo suficiente para actualizar los libros antes de la fecha límite. |
| **API de Adobe Analytics (versión 1.4)** | 17 de julio de 2024 | El **12 de agosto de 2026**, los siguientes servicios de la API heredada de Analytics llegarán al final de su vida útil y se cerrarán, y las integraciones actuales creadas con estos servicios dejarán de funcionar:<ul><li>API de Adobe Analytics (versión 1.4)</li><li>Autenticación WSSE de Adobe Analytics</li></ul><p>Las integraciones que usan la API de Adobe Analytics (versión 1.4) deben migrarse a la [API de Adobe Analytics 2.0](https://developer.adobe.com/analytics-apis/docs/2.0/), mientras que las integraciones de WSSE deben migrarse a un protocolo de autenticación basado en OAuth en [Adobe Developer Console](https://developer.adobe.com/console).</p><p>Consulte las [preguntas frecuentes sobre el final de la vida útil de la API de Adobe Analytics 1.4](https://developer.adobe.com/analytics-apis/docs/1.4/guides/eol/) para obtener respuestas a dudas comunes y más indicaciones.</p> |


## AppMeasurement

Para obtener las últimas actualizaciones de las versiones de AppMeasurement, consulte las [notas de la versión de AppMeasurement](https://github.com/adobe/appmeasurement/releases).


>[!MORELIKETHIS]
>
>* [Notas de la versión anteriores de 2026](/help/release-notes/2026.md)
>* [Notas de la versión de Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/releases/latest.html?lang=es)
>* [Notas de la versión de los servicios de medios de streaming](https://experienceleague.adobe.com/es/docs/media-analytics/using/release-notes/release-notes)
>* Últimas actualizaciones de la versión para [productos de Adobe CX Enterprise](https://business.adobe.com/es/products/adobe-experience-cloud-products.html)
