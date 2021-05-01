---
title: Opciones para mitigar el efecto de las limitaciones de cookies del explorador
description: Obtenga información sobre cómo mitigar el efecto de las limitaciones de cookies del explorador para mejorar la recopilación de datos para Adobe Analytics.
translation-type: tm+mt
source-git-commit: 07c76cea1f6fd64957fd4fd20bc5187976f3c14c
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 6%

---


# Opciones para mitigar el efecto de las limitaciones de cookies del explorador

Este documento explica cómo conservar la identificación persistente de visitantes entre propiedades y soluciones a medida que los exploradores principales implementan medidas de prevención del seguimiento para las cookies.

Adobe Analytics se basa en cookies de origen para registrar la actividad en el sitio de un visitante. Analytics también se basa en cookies de terceros para comprender la actividad fuera del sitio de un visitante, como la actividad en otros de sus dominios. Las cookies de terceros están bloqueadas en muchos navegadores y, en gran medida, no estarán disponibles con la próxima eliminación de la compatibilidad con Chrome (programada actualmente para 2022). Las cookies de origen están permitidas en todos los exploradores, pero tienen una caducidad limitada en Safari y otros exploradores en las medidas de prevención del seguimiento de ITP [ITP](https://webkit.org/tracking-prevention) de Apple. Para obtener más información sobre las limitaciones actuales de las cookies del explorador, consulte &quot;[Adobe Analytics y las cookies del explorador](cookies.md).

Estas limitaciones del explorador reflejan un paso más amplio desde el seguimiento anónimo de terceros hacia el uso compartido explícito de información entre usuarios y marcas en las que confían. Para admitir este movimiento, Adobe proporciona maneras para que los clientes complementen las cookies tradicionales mediante la inclusión de identificadores duraderos recopilados mediante sus relaciones de origen.

## Customer Journey Analytics y análisis entre dispositivos

[Los ](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html) análisis de Recorrido del cliente de Adobe y los  [análisis ](/help/components/cda/overview.md) entre dispositivos permiten a los usuarios incluir identificadores duraderos, como los inicios de sesión con hash, además de las cookies:

* **Análisis de canales cruzados de Recorrido** de clientes en Analysis Workspace mediante la integración con Adobe Experience Platform. Consolida los datos de clientes en línea y sin conexión disponibles en Experience Platform en el momento de la consulta, utilizando cualquier ID.

* **El** análisis entre dispositivos identifica cómo se asignan los dispositivos digitales a las personas y vincula el recorrido del usuario en cualquier ID que utilice el servicio de identidad de Adobe Experience Platform. Utiliza el gráfico de cooperación entre dispositivos de Adobe Experience Cloud, un gráfico de dispositivos privados o la vinculación basada en el campo.

## Recopilación de datos del lado del servidor

La colección del lado del servidor proporciona la flexibilidad para proporcionar su propio identificador en lugar de depender de los mecanismos del explorador para configurar cookies.

Puede importar datos del lado del servidor a Analytics mediante la [API de inserción de datos](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/data-insertion-api/index.md) o la [API de inserción de datos en lote](https://www.adobe.io/apis/experiencecloud/analytics/docs.html#!AdobeDocs/analytics-2.0-apis/master/bdia.md). Para ver una comparación de las dos API, consulte &quot;[Qué herramienta de Adobe Analytics debo usar](https://experienceleague.adobe.com/docs/analytics/admin/admin-overview/which-analytics-tool.html)&quot;.

## Más información

Para obtener información práctica sobre los pasos que su empresa puede seguir para dejar de usar cookies de terceros, consulte &quot;[Adquirir y mantener a los clientes en un mundo sin cookies con Adobe](https://business.adobe.com/solutions/cookieless.html)&quot; y la información detallada &quot;[Pensar más allá de la cookie de terceros: Su guía completa de un mundo sin cookies de terceros](https://business.adobe.com/content/dam/www/us/en/pdfs/Adobe_Thinking_Beyond_the_Third_Party_Cookie.pdf).&quot;

>[!MORELIKETHIS]
>
>[Adobe Analytics y cookies de explorador](cookies.md)
