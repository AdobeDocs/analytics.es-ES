---
title: Consentimiento de la plataforma de publicidad
description: Consulte la configuración de consentimiento publicitario para proveedores de publicidad de terceros.
feature: Dimensions
exl-id: bf63112d-7d20-4e35-9a59-5be21135ae51
TQID: https://experienceleague.adobe.com/Ou6-B5pFx-ku9H2iEqLN0Ly6-t01CzQUODo0poMk8Bs
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
    internal-label: Reporting
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: e0eb8757-182f-49f3-94a4-1587d16f5094
    internal-label: Personalization
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
    internal-label: Privacy
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '368'
ht-degree: 5%
---
# Consentimiento de la plataforma de publicidad

La dimensión [Consentimiento de la plataforma de publicidad](overview.md) muestra si se recopila el consentimiento para enviar datos a proveedores de publicidad de terceros, como Google, Meta y otros.

Actualmente, esta dimensión se utiliza solo para Google. Debido a las regulaciones de privacidad europeas, la Ley de Mercados Digitales (DMA) de Google requiere que los datos enviados a sus servidores y recopilados en Europa indiquen si se recopila el consentimiento. Algunos clientes de Analytics envían datos de evento a través de Adobe Advertising como eventos de conversión a Google.

En el futuro, esta dimensión se puede utilizar para admitir la codificación de información de consentimiento adicional para otros proveedores de publicidad de terceros.

## Rellene esta dimensión con datos

Esta dimensión recopila datos de la [variable de datos de contexto](/help/implement/vars/page-vars/contextdata.md) `contextData.['adConsent']`. Rellene esta variable con los valores de campo de consentimiento de Google relevantes: `ad_user_data` (primer carácter) y `ad_personalization` (segundo carácter). Consulte [Consentimiento en la referencia de la API de Google Ads](https://developers.google.com/google-ads/api/reference/rpc/v15/Consent) para obtener más información.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (establecido mediante la variable de datos de contexto `adConsent`) |
| **Campo Web SDK / XDM** | Ninguno |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | 100 bytes |
| **Persistencia** | Hit |

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

Cuando envíe datos publicitarios desde Adobe Analytics a través de Adobe Advertising como eventos de conversión a Google, póngase en contacto con el equipo de Adobe Advertising para que le ayuden con la integración.

Para obtener más información, consulte [Informes de privacidad](/help/admin/tools/manage-rs/edit-settings/privacy-reporting.md).
