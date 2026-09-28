---
title: Dominio de referencia original
description: El primer dominio de referencia en el que se encontraba un visitante antes de hacer clic en el sitio.
feature: Dimensions
exl-id: 6b9ac662-a79a-477b-8612-7980da7cfadd
TQID: 'https://experienceleague.adobe.com/G-se6LH33gMTt8ttrP5RBzL85m335ujtbiSm6EjLGuU'
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
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '365'
ht-degree: 72%
---
# Dominio de referencia original

El &quot;Dominio de referencia original&quot; [dimension](overview.md) indica el primer dominio de referencia en el que un visitante hizo clic para llegar al sitio. Una vez configurado, contiene el mismo valor para toda la duración de ese ID de visitante. Esta dimensión es útil para comprender qué sitios de terceros generan tráfico al sitio originalmente.

>[!IMPORTANT]
>
>Debe configurar los [filtros URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) del grupo de informes para utilizar esta dimensión. Si no se configuran los filtros de URL internos, puede incluir dominios internos o evitar que aparezcan dominios externos.

## Rellene esta dimensión con datos

Adobe deriva esta dimensión del primer [referente](referrer.md) del visitante, usando la parte de dominio de esa dirección URL de referente. No hay ninguna variable que establecer. Debe configurar los [filtros URL internos](/help/admin/tools/manage-rs/edit-settings/general/internal-url-filter-admin.md) del grupo de informes; si no lo hace, puede incluir dominios internos o evitar que aparezcan dominios externos.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado del primer referente del visitante) |
| **Campo Web SDK / XDM** | Ninguno (derivado del primer referente del visitante) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | Visitante |

Si un visitante sale y hace clic en un vínculo de un dominio diferente en cualquier momento, el nuevo valor no se registra. Para ver nuevos valores, consulte [Dominio de referencia](referring-domain.md).

## Elementos de dimensión

Los elementos de dimensión incluyen los dominios en los que los visitantes hacen clic para llegar a su sitio. Si un hit no tiene datos de remitente del reenvío (establecidos o persistentes), se agrupa bajo el elemento de dimensión `"None"`. Este elemento de dimensión significa que no hubo ningún valor de remitente del reenvío, como si el visitante escribiera manualmente la dirección del explorador en la barra de direcciones o hiciera clic en un marcador.

## Comparar el dominio de referencia con el dominio de referencia original

El dominio de referencia puede cambiar entre visitas. Por ejemplo, un visitante llega a su sitio a través de `google.com` y una semana después llega a su sitio a través de `twitter.com`. Finalmente, realizan una compra en el sitio. Si se utiliza el dominio de referencia como dimensión con atribución de último contacto, `twitter.com` obtiene crédito por la compra. Si utiliza el dominio de referencia original como dimensión, `google.com` obtiene crédito por la compra independientemente del modelo de atribución.

El dominio de referencia original nunca cambia durante toda la duración de un ID de visitante determinado.
