---
title: Detalles de canal de último contacto
description: Detalles del canal de marketing más reciente dentro de la caducidad de la participación del visitante.
feature: Dimensions
exl-id: def03267-f3e5-4772-a707-5678c45eba6d
TQID: 'https://experienceleague.adobe.com/bVZVCTQQ1tZVB0qF9fxeCU1Ec6bjcspymoyOY-AQATU'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
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
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 70%
---
# Detalles de canal de último contacto

Los informes de &quot;Detalles de canal de último contacto&quot; [dimension](overview.md) detallan el canal de marketing más reciente con el que coincide un visitante durante el periodo de participación de ese visitante (de forma predeterminada, 30 días). Esta dimensión es valiosa para comprender qué contribuyó a que el hit coincidiera con un canal de marketing. Por ejemplo: si un visitante llegó a su sitio y coincidió con el canal de marketing de “Búsqueda de pago”, puede utilizar el detalle de canal para ver qué motor de búsqueda se utilizó o qué palabra clave buscó.

## Rellene esta dimensión con datos

Esta dimensión se deriva de las reglas de procesamiento del canal de marketing, que copian valores de otras variables. La variable utilizada hace referencia al valor de canal dentro de cada [regla de procesamiento del canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Cuando un hit coincide con una regla de procesamiento de canal de marketing, la dimensión de [canal de último contacto](last-touch-channel.md) se establece en el nombre del canal y esta dimensión se establece en el valor de canal establecido en la regla. No hay ninguna variable que establecer.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado por las reglas de procesamiento del canal de marketing) |
| **Campo Web SDK / XDM** | Ninguno (derivado por las reglas de procesamiento del canal de marketing) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | n/a |

Si desea establecer esta dimensión en un valor específico, se requieren los siguientes pasos:

* Asegúrese de que el elemento de dimensión deseado esté en un atributo de hit o en una variable personalizada.
* Establezca una regla de procesamiento de canal de marketing que contenga los criterios deseados para el hit.
* Seleccione el valor desplegable que desee en [!UICONTROL Establecer el valor del canal] dentro de la regla de procesamiento del canal de marketing.
* El hit del visitante al sitio debe coincidir con los criterios descritos en la regla de procesamiento del canal de marketing.

## Elementos de dimensión

Los elementos de Dimension dependen del valor de canal enumerado en la lista desplegable de para la regla de procesamiento de canal de marketing aplicable. Por ejemplo, si establece el valor del canal en “Dirección URL de la página”, los elementos de dimensión incluyen las direcciones URL de la página en el sitio. Si establece el valor del canal en Dominio de referencia, los elementos de dimensión incluyen los dominios en los que ha hecho clic el visitante para llegar al sitio. Esta dimensión agrega todos los elementos de dimensión de detalle, independientemente del canal en el que se encuentren.

Adobe recomienda configurar los valores de canal relacionados con el canal de marketing para obtener más información sobre los detalles del canal.
