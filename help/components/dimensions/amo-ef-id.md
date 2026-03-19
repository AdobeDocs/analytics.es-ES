---
title: AMO EF ID
description: El ID de EF de Adobe Media Optimizer que se utiliza en las integraciones de Adobe Advertising.
feature: Dimensions
source-git-commit: 408d8db0d1e3c8301a066fe54d611ec7b8e3418a
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 4%

---

# AMO EF ID

**[!UICONTROL AMO EF ID]** es un identificador de clic en anuncio que se usa en las integraciones de Adobe Advertising. Es un token único que Adobe Advertising utiliza para asociar la actividad con un clic en línea o la exposición de un anuncio a nivel de visitante. La dimensión se crea automáticamente al habilitar la integración de [Analytics para Advertising](https://experienceleague.adobe.com/es/docs/advertising/integrations/analytics/overview).

## Rellene esta dimensión con datos

Esta dimensión recopila sus valores de varias formas:

* Para el tráfico de clics, los datos se recopilan del parámetro de cadena de consulta `ef_id` en la [URL de página](page-url.md), normalmente en la página a través de la cual entra el tráfico impulsado por anuncios en el sitio.
* El tráfico de clics también se puede capturar cuando la dirección URL no contiene códigos de seguimiento, pero Adobe Advertising JavaScript detecta un clic en los dos minutos anteriores.
* Para el tráfico de visualización admitido, Adobe Advertising complementa los valores del backend con un ID suplementario (`SDID`).

>[!NOTE]
>
>Los ID de EF distinguen entre mayúsculas y minúsculas. Si la implementación obliga al seguimiento de URL a usar minúsculas, Adobe Advertising no reconocerá el EF ID.

## Elementos de dimensión

Los elementos de Dimension incluyen identificadores de clic de anuncio generados por redes de publicidad admitidas. El formato de cadena depende de la red y el canal que lo generó.

### Anuncios de búsqueda de Google Ads

```text
{gclid}:G:{s}
```

* **`gclid`**: ID de clic de Google (GCLID).
* **`s`**: el tipo de red (`"s"` para la búsqueda).

### Anuncios de búsqueda de Microsoft Advertising

```text
{msclkid}:G:{s}
```

* **`msclkid`**: ID de clic de Microsoft (MSCLKID).
* **`s`**: el tipo de red (`"s"` para la búsqueda).

### Mostrar anuncios y anuncios de búsqueda en otros motores de búsqueda

```text
{amovid}:{ts}:{channel}
```

* **`amovid`**: el ID de visitante de Adobe Advertising, también conocido como ID de internauta.
* **`ts`**: marca de tiempo generada por Adobe Advertising.
* **`channel`**: el tipo de canal responsable del clic o la exposición:
   * **`d`**: un clic en un anuncio en pantalla de DSP (pulsación en pantalla).
   * **`i`**: impresión en un anuncio en pantalla de DSP (visualización completa).
   * **`s`**: un clic en un anuncio de búsqueda (pulsación de búsqueda).

### Ejemplos

```text
CjwKCAiAkbbMBhB2EiwANbxtbb9L573Dys0rjTDqcMo3x7tv2yEfh1RGb8exG9N892NoMqAzMBEGmhoCWxwQAvD_BwE:G:s
06207ca63ae6f4fa832197585547393c:20260301111101:i
WcmibgAAAHJK1RyY:1551968087687:d
```
