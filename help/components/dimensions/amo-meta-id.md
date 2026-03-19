---
title: AMO Meta Ads Click ID
description: El ID de clic de Meta Ads de Adobe Media Optimizer que se utiliza en las integraciones de Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '165'
ht-degree: 10%

---

# AMO Meta Ads Click ID

**[!UICONTROL ID de clic en Meta Ads de AMO]** es un identificador de clic en anuncio que se usa en las integraciones de Adobe Advertising. La dimensión se crea automáticamente al habilitar la integración de [Analytics para Advertising](https://experienceleague.adobe.com/en/docs/advertising/integrations/analytics/overview). Resulta principalmente útil como identificador de seguimiento sin procesar en lugar de como dimensión de sistema de informes legible en lenguaje natural.

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
