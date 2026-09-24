---
title: Dominio de referencia
description: Dominio general en el que se encontraba un visitante antes de hacer clic en el sitio.
feature: Dimensions
exl-id: 9e04cb62-6526-4d84-aff7-c962c0ce42b5
TQID: https://experienceleague.adobe.com/iLpQGPuxOFmhb-WCU0EEfhmGgHgeQaPgBmOETdCczGQ
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
    internal-label: Components
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '458'
ht-degree: 81%
---
# Dominio de referencia

El &quot;Dominio de referencia&quot; [dimension](overview.md) indica en qué dominios hacen clic los visitantes para llegar al sitio. Esta dimensión es útil para comprender qué sitios de terceros generan la mayor cantidad de tráfico en el suyo. Debe existir un vínculo en el sitio externo y un visitante debe hacer clic en él para que se muestre el elemento de dimensión.

>[!IMPORTANT]
>
>Debe configurar los [filtros URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) del grupo de informes para utilizar esta dimensión. Si no se configuran los filtros de URL internos, puede incluir dominios internos o evitar que aparezcan dominios externos.

El mismo informe puede mostrar diferentes resultados entre Analysis Workspace y Data Warehouse. Analysis Workspace informa del dominio de referencia de cada página individual, excluyendo los valores que coinciden con los filtros de URL internos. Data Warehouse informa solamente del primer dominio de referencia de la visita e ignora los filtros de URL internos.

## Rellene esta dimensión con datos

Adobe deriva esta dimensión del [referente](referrer.md) de cada visita, utilizando la parte de dominio de la dirección URL del referente. No hay ninguna variable que establecer. Debe configurar los [filtros URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) del grupo de informes; si no lo hace, puede incluir dominios internos o evitar que aparezcan dominios externos.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado del referente) |
| **Campo Web SDK / XDM** | Ninguno (derivado del referente) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | Visita |

Adobe persiste en el dominio de referencia de una visita. Si un visitante sale y hace clic a través de un vínculo en un dominio diferente en una sola visita, el nuevo valor se actualiza y persiste durante el resto de la visita. Si solo desea ver el valor original, consulte [Dominio de referencia original](original-referring-domain.md).

## Elementos de dimensión

Los elementos de dimensión incluyen los dominios en los que los visitantes hacen clic para llegar a su sitio. Si un hit no tiene datos de remitente del reenvío (establecidos o persistentes), se agrupa bajo el elemento de dimensión `"Typed/Bookmarked"`. Este elemento de dimensión significa que no hubo ningún valor de remitente del reenvío, como si el visitante escribiera manualmente la dirección del explorador en la barra de direcciones o hiciera clic en un marcador. El elemento de dimensión `"Typed/Bookmarked"` también aparece para redirecciones que no admiten Analytics. Consulte [Redirecciones y alias](/help/technotes/redirects.md) en la guía del usuario de Technotes.

### Elementos de dimensión que contienen `googleusercontent.com`

Los usuarios pueden ver elementos de dimensión con el dominio `googleusercontent.com`.

* **Páginas en caché**: Las arañas de Google rastrean constantemente la web y almacenan copias de páginas en caso de que se desconecten. Estas páginas en caché están disponibles junto a la mayoría de los resultados de búsqueda haciendo clic en el vínculo “En caché”. Cuando un usuario hace clic en este vínculo y visualiza el contenido que Google almacena en caché, `googleusercontent.com` es el elemento de dimensión.
* **Páginas traducidas**: Google ofrece un servicio de traducción robusto y conveniente. Al ver un sitio que utiliza este servicio, se origina desde `googleusercontent.com`. Este elemento de dimensión aparece si el usuario hace clic en un vínculo para volver al contenido original.
