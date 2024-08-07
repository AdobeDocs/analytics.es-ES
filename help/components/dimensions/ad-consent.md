---
title: Consentimiento de la plataforma de publicidad
description: Consulte la configuración de consentimiento publicitario para proveedores de publicidad de terceros.
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
source-git-commit: 5df5cffbb6abf712cb36fd807ef54b8ebaae1c73
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 3%

---

# Consentimiento de la plataforma de publicidad

La dimensión [Consentimiento de la plataforma de publicidad](overview.md) muestra si se recopila el consentimiento para enviar datos a proveedores de publicidad de terceros, como Google, Meta y otros.

Actualmente, esta dimensión se utiliza solo para Google. Debido a las regulaciones de privacidad europeas, la Ley de Mercados Digitales (DMA) de Google requiere que los datos enviados a sus servidores y recopilados en Europa indiquen si se recopila el consentimiento. Algunos clientes de Analytics envían datos de evento mediante el Adobe Advertising como eventos de conversión a Google.

En el futuro, esta dimensión se puede utilizar para admitir la codificación de información de consentimiento adicional para otros proveedores de publicidad de terceros.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de las [variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) siguientes

* `contextData.['adConsent']`

La variable de datos de contexto se rellena con valores relevantes para los campos de consentimiento de Google

* `ad_user_data` (primer carácter) y
* `ad_personalization` (segundo carácter).

Consulte [Consentimiento en la referencia de la API de Google Ads](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) para obtener más información.

Los valores posibles para cada uno de estos campos pueden ser:

| Valor | ad_user_data | ad_personalization |
|:-:|---|---|
| `Y` | Conceder consentimiento a Google para datos de usuario de publicidad. | Conceder consentimiento a Google para la personalización de anuncios. |
| `N` | Deniegue el consentimiento a Google para los datos de usuario de publicidad. | Consentimiento de entrada a Google para la personalización de anuncios. |
| `U` | No especificado. | No especificado. |

El ejemplo siguiente autoriza el uso de Google para datos de usuarios de publicidad, pero no para la personalización de anuncios:

```
contextData.['adConsent'] = "YN..."
```

Los caracteres que se encuentran más allá del primer y segundo carácter se omiten actualmente.

## Uso de los datos

Puede utilizar los datos recopilados y de consentimiento:

* Fuentes de datos: los datos del consentimiento del anuncio están disponibles mediante la `dataprivacydmaconsent` [columna](/help/export/analytics-data-feed/c-df-contents/datafeeds-reference.md).
* Informes de Data Warehouse: los datos del consentimiento del anuncio están disponibles mediante la dimensión **[!UICONTROL Consentimiento de la plataforma de publicidad]**.

Su organización determina la lógica para implementar esta variable de datos de contexto. El valor no persiste más allá de la visita en la que está establecido, por lo que debe establecer la variable de datos de contexto en cada página.

Cuando envíe datos publicitarios desde Adobe Analytics a través de Adobes Advertising como eventos de conversión a Google, consulte con el equipo de Adobe Advertising para que le ayuden con la integración.

Para obtener más información, consulte [Informes de privacidad](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/privacy-reporting.md).
