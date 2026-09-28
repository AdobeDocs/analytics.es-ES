---
title: Código de seguimiento
description: Nombre del código de seguimiento o campaña.
feature: Dimensions
exl-id: e4f70552-6946-4974-a9e2-928faf563ecd
TQID: 'https://experienceleague.adobe.com/8e9126PxGCNXJqo4a3XYTgXwrcHdf34FVwygpHXm5JI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
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
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '625'
ht-degree: 88%
---
# Código de seguimiento

La [dimensión](overview.md) “Código de seguimiento” muestra los nombres de los códigos de seguimiento en el sitio. Puede colocar vínculos con diferentes valores de parámetros de cadenas de consulta en diferentes lugares de internet. Esta dimensión puede ayudarle a entender mejor qué vínculos fueron los más exitosos a la hora de impulsar el tráfico al sitio.

Añadir cadenas de consulta de código de seguimiento es habitual en los correos electrónicos, anuncios, publicaciones en redes sociales y otros esfuerzos de marketing que utiliza su organización.

## Rellene esta dimensión con datos

AppMeasurement recopila estos datos mediante la variable [`campaign`](/help/implement/vars/page-vars/campaign.md). Esta variable generalmente obtiene su valor de una cadena de consulta utilizando el método de utilidad [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md), aunque su organización determina exactamente cómo configurarla.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`campaign`](/help/implement/vars/page-vars/campaign.md) |
| **Campo Web SDK / XDM** | [`marketing.trackingCode`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/field-groups/event/campaign-marketing-details) |
| **Parámetro de consulta** | [`v0`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<campaign>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 255 bytes |
| **Persistencia** | Configurable |

## Elementos de dimensión

Los elementos de dimensión incluyen los nombres de los códigos de seguimiento en el sitio. Su organización determina qué elementos de dimensión específicos desea utilizar. Consulte [Seguimiento de la campaña](/help/implement/use-cases/campaign-tracking.md) para obtener más información.

## Comparación de la dimensión Código de seguimiento con los canales de marketing que recopilan códigos de seguimiento

Algunos usuarios que configuran reglas de procesamiento de canal de marketing configuran una regla que toma todos los valores utilizados en la dimensión Código de seguimiento. A pesar de ser una práctica excelente, son diferentes debido a las diferencias inherentes de procesamiento y arquitectura. La siguiente lista explica por qué estos dos métodos, aunque parecidos a primera vista, pueden cambiar el comportamiento de la atribución.

### Canales anteriores en reglas de procesamiento

Las reglas de procesamiento de los canales de marketing que se encuentran más arriba en la lista pueden impedir que los hits se atribuyan a su canal de marketing de códigos de seguimiento. Por ejemplo:

1. Tiene “Redes sociales” configuradas como la primera regla y “Códigos de seguimiento” como la segunda.
2. Un usuario publica un vínculo a su sitio que contiene un código de seguimiento en un sitio de medios sociales y varios de sus amigos hacen clic en ese vínculo a su sitio.

Dado que “Redes sociales” es la primera regla de procesamiento de canales de marketing, estos usuarios atribuyen el canal de marketing “Redes sociales” y no el canal de marketing de códigos de seguimiento.

### Otros canales de marketing pueden otorgar la atribución mediante el último contacto

Cuando se trata de una dimensión Código de seguimiento estándar, no debe preocuparse por otras partes del sitio que roban la atribución. Sin embargo, con los canales de marketing, un usuario puede hacer coincidir una regla diferente y dar una atribución diferente. Por ejemplo:

1. Tiene “Códigos de seguimiento” como primer canal y “Directo” como segundo.
2. Un usuario llega al sitio inicialmente a través de un código de seguimiento, pero luego sale.
3. Al día siguiente, escriben su dirección URL en la barra de direcciones y luego realizan una compra.

En este ejemplo, el canal de marketing de códigos de seguimiento no obtendría crédito de último contacto para esa compra. En su lugar, iría al canal de marketing “Directo”.


### Diferencias de caducidad

Los canales de marketing tienen una caducidad de participación del visitante de 30 días móviles, independientemente de si hubo contacto con un canal o no. Los códigos de seguimiento tienen una caducidad basada en el momento en que se configuró la variable. Por ejemplo:

1. Tiene una caducidad de la participación del visitante de 30 días y también configuró la dimensión Código de seguimiento para que caduque a los 30 días.
2. Un usuario llega al sitio a través de un código de seguimiento. Exploran el sitio y luego se van.
3. Tres semanas después, regresan sin un código de seguimiento o canal de marketing, y luego se van de nuevo.
4. Otras dos semanas después (cinco semanas después de su visita inicial), regresan sin un código de seguimiento o canal de marketing y luego realizan una compra.

El usuario realizó una compra más allá de los 30 días, pero nunca estuvo inactivo durante más de 30 días. En este caso, vería los ingresos atribuidos al canal de marketing de códigos de seguimiento, pero no a la propia dimensión Código de seguimiento.



