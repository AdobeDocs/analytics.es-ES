---
title: Opciones para mitigar el efecto de las limitaciones de cookies del explorador
description: Obtenga información sobre cómo mitigar el efecto de las limitaciones de cookies del explorador para mejorar la recopilación de datos para Adobe Analytics.
source-git-commit: 6c354a343648162ce2951c52a70a688970e1304d
workflow-type: tm+mt
source-wordcount: '516'
ht-degree: 5%

---


# Opciones para mitigar el efecto de las limitaciones de cookies del explorador

Este documento analiza las opciones para preservar la identificación de visitantes persistentes en todas las propiedades y soluciones a medida que los exploradores principales implementan medidas de prevención de seguimiento para las cookies.

Adobe Analytics se basa en cookies de origen para registrar la actividad en el sitio de un visitante. Analytics también se basa en cookies de terceros para comprender la actividad fuera del sitio de un visitante, como la actividad en otros de sus dominios. Las cookies de terceros están bloqueadas en muchos navegadores y, en gran medida, no estarán disponibles con la próxima eliminación de la compatibilidad con Chrome (programada actualmente para 2022). Las cookies de origen están permitidas en todos los exploradores, pero tienen una caducidad limitada en Safari y otros exploradores en las medidas de prevención del seguimiento de ITP [ITP](https://webkit.org/tracking-prevention) de Apple. Para obtener más información sobre las limitaciones actuales de las cookies del explorador, consulte [Adobe Analytics y las cookies del explorador](cookies.md).

Estas limitaciones del explorador reflejan un paso más amplio desde el seguimiento anónimo de terceros hacia el uso compartido explícito de información entre usuarios y marcas en las que confían. Para admitir este movimiento, Adobe proporciona maneras para que los clientes complementen las cookies tradicionales mediante la inclusión de identificadores duraderos recopilados mediante sus relaciones de origen.

## Customer Journey Analytics y análisis entre dispositivos

[Los ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) análisis de Recorrido del cliente de Adobe y los  [análisis ](/help/components/cda/overview.md) entre dispositivos permiten a los usuarios incluir identificadores duraderos, como los inicios de sesión con hash, además de las cookies. Esto le permite comprender el recorrido del cliente entre dispositivos y, en el caso del Customer Journey Analytics, entre canales en línea y sin conexión:

* **El** análisis del Recorrido del cliente se basa en Adobe Experience Platform y proporciona la flexibilidad para combinar datos en línea y sin conexión en Analysis Workspace, en función de cualquier ID de cliente común. Puede especificar qué ID desea utilizar para un análisis determinado y explorar los datos en Analysis Workspace. Los clientes de Analytics Select, Prime y Ultimate pueden adquirir este producto como complemento.

* **El** análisis entre dispositivos es una mejora de la versión tradicional de Adobe Analytics que permite a los clientes utilizar identificadores alternativos para los visitantes. Esta funcionalidad le permite pasar de una vista centrada en el dispositivo a una vista centrada en la persona. El análisis entre dispositivos está disponible para los clientes de Analytics Ultimate.

## Recopilación de datos del lado del servidor

La colección del lado del servidor proporciona la flexibilidad para proporcionar su propio identificador en lugar de depender de los mecanismos del explorador para configurar cookies.

Puede enviar datos al servidor de Analytics mediante la [API de inserción de datos](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) o la [API de inserción masiva de datos](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). La API de inserción de datos en lote se recomienda para las nuevas implementaciones del lado del servidor. Para ver una comparación de las dos API, consulte &quot;[Qué herramienta de Adobe Analytics debo usar](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)&quot;.

## Más información

Para obtener información práctica sobre los pasos que su empresa puede seguir para dejar de usar cookies de terceros, consulte [Adquirir y mantener a los clientes en un mundo sin cookies con Adobe](https://business.adobe.com/solutions/cookieless.html) y el [Pensamiento detallado más allá de la cookie de terceros: Su guía completa de un mundo sin cookies de terceros](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
[Adobe Analytics y cookies de explorador](cookies.md)>
>
