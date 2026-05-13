---
title: Área de mercado designada (DMA) de EE.UU.
description: Área de mercado designada de la visita.
feature: Dimensions
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
TQID: https://experienceleague.adobe.com/ijUlnHJ7gP4Jq1g0SzaUVHWbiMki1rgEMd1Pz4sttmU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 321
ht-degree: 65%

---

# Área de mercado designada (DMA) de EE.UU.

La &quot;DMA de EE. UU.&quot; [dimensión](overview.md) indica el área de mercado designada (DMA) del visitante. Se basa en los mercados de medios recopilados por [Nielsen](https://www.nielsen.com/dma-regions/).

## Rellene esta dimensión con datos

Esta dimensión hace referencia a las reglas de búsqueda internas de Adobe. El valor de búsqueda se basa en la dirección IP enviada con la visita. Adobe se asocia con Nielsen para mantener búsquedas entre la dirección IP y DMA.

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de Web SDK, habilita [!UICONTROL Búsqueda geográfica] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de Dimension incluyen los códigos DMA y DMA del visitante. El código de 3 dígitos no es un código postal, sino el código DMA de Nielsen. Los valores de ejemplo incluyen `"Dallas-Ft. Worth (623)"`, `"New York (501)"` o `"Los Angeles (803)"`. El elemento de dimensión `"No Metro (0)"` incluye todo el tráfico internacional fuera de los Estados Unidos.

## Diferencias entre la ubicación real y la notificada

Dado que esta dimensión se basa en la dirección IP, algunos escenarios pueden mostrar una diferencia entre la ubicación real y la ubicación registrada:

* **Direcciones IP que representan proxies corporativos**: Estos visitantes pueden aparecer como tráfico proveniente de la red corporativa del usuario, que puede ser una ubicación diferente si el usuario trabaja de forma remota.
* **Direcciones IP móviles**: La segmentación de direcciones IP móviles funciona en diferentes niveles según la ubicación y la red del dispositivo. Algunos operadores pasan el tráfico IP por puntos de presencia centralizados o regionales.
* **Usuarios de ISP satelitales**: Es difícil identificar la ubicación específica de estos usuarios, ya que normalmente parecen proceder de la ubicación del vínculo superior.
* **IP militares y gubernamentales**: Representa al personal que viaja por todo el mundo y accede a Internet a través de su ubicación local en lugar de la base u oficina en la que esté destinado.
* **Proxies que ocultan direcciones IP por motivos de privacidad**: Servicios como el Retransmisión privada de Apple ocultan la dirección IP real enviando datos de forma aleatoria a través de un intermediario o proxy. A continuación, este proxy sustituye una dirección IP diferente antes de reenviarla a Adobe.
