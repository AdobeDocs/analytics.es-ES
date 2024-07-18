---
title: Opciones para mitigar el efecto de las limitaciones de cookies del explorador
description: Obtenga información sobre cómo mitigar el efecto de las limitaciones de cookies del explorador para mejorar la recopilación de datos para Adobe Analytics.
feature: Data Configuration and Collection
exl-id: 81cf3f0c-4871-435d-bcc9-bcff5c682f05
role: Admin
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: tm+mt
source-wordcount: '515'
ht-degree: 100%

---

# Opciones para mitigar el efecto de las limitaciones de cookies del explorador

Este documento analiza las opciones para preservar la identificación de visitantes persistentes en todas las propiedades y soluciones a medida que los exploradores principales implementan medidas de prevención de seguimiento para las cookies.

Adobe Analytics se basa en cookies de origen para registrar la actividad en el sitio de un visitante. Analytics también se basa en cookies de terceros para comprender la actividad fuera del sitio de un visitante, como la actividad en otros de sus dominios. Las cookies de terceros están bloqueadas en muchos exploradores y, en gran medida, no estarán disponibles con la próxima eliminación de la compatibilidad con Chrome (programada, por ahora, para finales de 2024). Las cookies de origen están permitidas en todos los exploradores, pero tienen una caducidad limitada en Safari y en otros exploradores con las medidas de [prevención del seguimiento de ITP](https://webkit.org/tracking-prevention) de Apple. Para obtener más información sobre las limitaciones actuales de las cookies del explorador, consulte [Adobe Analytics y las cookies del explorador](cookies.md).

Estas limitaciones del explorador reflejan un paso más amplio desde el seguimiento anónimo de terceros hacia el uso compartido explícito de información entre usuarios y marcas en las que confían. Para admitir este movimiento, Adobe proporciona maneras para que los clientes complementen las cookies tradicionales mediante la inclusión de identificadores duraderos recopilados mediante sus relaciones de origen.

## Customer Journey Analytics y análisis entre dispositivos

[Adobe Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es) y [Cross-Device Analytics](/help/components/cda/overview.md) permiten a los usuarios incluir identificadores duraderos, como los inicios de sesión con hash, además de las cookies. Esto le permite comprender el recorrido del cliente entre dispositivos y, en el caso de Customer Journey Analytics, entre canales en línea y sin conexión:

* **Customer Journey Analytics** se basa en Adobe Experience Platform y proporciona la flexibilidad para combinar datos en línea y sin conexión en Analysis Workspace, en función de cualquier ID de cliente común. Puede especificar qué ID desea utilizar para un análisis determinado y explorar los datos en Analysis Workspace. Los clientes de Analytics Select, Prime y Ultimate pueden adquirir este producto adicional.

* **Cross-Device Analytics** ofrece una mejora de la versión tradicional de Adobe Analytics que permite a los clientes utilizar identificadores alternativos para los visitantes. Esta funcionalidad le permite pasar de una vista centrada en el dispositivo a una vista centrada en la persona. Cross-Device Analytics está disponible para los clientes de Analytics Ultimate.

## Recopilación de datos del lado del servidor

La recopilación del lado del servidor proporciona la flexibilidad para proporcionar su propio identificador en lugar de depender de los mecanismos del explorador para configurar las cookies.

Puede enviar datos del lado del servidor de Analytics mediante la [API de inserción de datos](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) o la [API de inserción de datos por lotes](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). La API de inserción de datos por lotes se recomienda para las nuevas implementaciones del lado del servidor. Para ver una comparación de las dos API, consulte “[Qué herramienta de Adobe Analytics debo usar](/help/analyze/get-started/which-analytics-tool.md)”.

## ID de dispositivo de origen (FPID) con SDK web

Con el SDK web de Adobe Experience Platform, puede optar por establecer y administrar sus propios identificadores de dispositivo en lugar de los Experience Cloud ID (ECID) generados por Adobe. Estos se denominan ID de dispositivos de origen (FPID). Obtenga más información [aquí](https://experienceleague.adobe.com/docs/experience-platform/edge/identity/first-party-device-ids.html?lang=es).

## Más información

Para obtener información práctica sobre los pasos que su empresa puede seguir para dejar de usar cookies de terceros, consulte [Adquirir y mantener clientes en un mundo sin cookies con Adobe](https://business.adobe.com/es/solutions/cookieless.html) y el artículo detallado [Más allá de las cookies de terceros: uía completa para un mundo sin cookies de terceros](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).

>[!MORELIKETHIS]
>
>[Cookies de Adobe Analytics y de explorador](cookies.md)
