---
title: ID de clic de Meta Ads de AMO
description: El ID de clic de Meta Ads de Adobe Media Optimizer que se utiliza en las integraciones de Adobe Advertising.
feature: Dimensions
exl-id: c1def73a-51b9-46bf-9dc7-0fbd46fd6e17
TQID: 'https://experienceleague.adobe.com/3J-pLiOz4QwUewRSmEFsJCg0v-PbEmksUzGKOI0hHoA'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 176
ht-degree: 3%

---

# ID de clic de Meta Ads de AMO

**[!UICONTROL ID de clic en Meta Ads de AMO]** es un identificador de clic en anuncio que se usa en las integraciones de Adobe Advertising. La dimensión se crea automáticamente al habilitar la integración de [Analytics para Advertising](https://experienceleague.adobe.com/es/docs/advertising/integrations/analytics/overview). Resulta principalmente útil como identificador de seguimiento sin procesar en lugar de como dimensión de sistema de informes legible en lenguaje natural.

## Rellene esta dimensión con datos

Esta dimensión recopila sus valores de varias formas:

* Para el tráfico de clics, los datos se recopilan del parámetro de cadena de consulta `fbclid` en la [URL de página](page-url.md), normalmente en la página a través de la cual entra el tráfico impulsado por anuncios en el sitio.
* El tráfico de clics también se puede capturar cuando la dirección URL no contiene códigos de seguimiento, pero Adobe Advertising JavaScript detecta un clic en los dos minutos anteriores.

## Elementos de dimensión

Los elementos de Dimension incluyen identificadores de clic de anuncio generados por las redes publicitarias de Meta (Facebook). La longitud de estos valores con hash puede variar, pero suelen ser cientos de caracteres. Los valores de ejemplo (truncados) incluyen:

```text
IwY2xjawP0bVtleHRuA2FlbQIxMAB[...]AVp_aem_l5TPw-muraFjBGOq8l1w0g
PAb21jcAQB1LNleHRuA2FlbQIxMQB[...]PoFocE1FH44g_aem_FNMJG5EydJ_59aBwKIf4uA
```
