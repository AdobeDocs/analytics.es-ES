---
title: Estados estadounidenses
description: El estado de Estados Unidos del que procede el visitante.
feature: Dimensions
exl-id: d4506e59-c1ff-4348-912d-c1ad73278f56
TQID: https://experienceleague.adobe.com/YLZIz1-J-LVvases2X1AgNxQR1eTtqoeDoxFVCg2MV4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: d2311670-43bd-4c2e-bc98-1da2aaba9cefid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 77%

---

# Estado de EE. UU.

La [dimensión](overview.md) &quot;Estado de EE. UU.&quot; indica el estado de EE. UU. en el que se encuentra el visitante. Es similar a la dimensión [Regiones](regions.md), pero esta dimensión es específica de los Estados Unidos. El uso de esta dimensión es ideal si desea obtener una perspectiva más granular que [Países](countries.md) pero no tan granular como [Ciudades](cities.md).

## Rellene esta dimensión con datos

Esta dimensión hace referencia a las reglas de búsqueda internas de Adobe. El valor de búsqueda se basa en la dirección IP enviada con la visita. Adobe se asocia con [Digital Element](https://www.digitalelement.com/es/) para mantener búsquedas entre la dirección IP y el país.

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de Web SDK, habilita [!UICONTROL Búsqueda geográfica] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de dimensión incluyen regiones y el país en el que reside la región. Los valores de ejemplo incluyen `"California"`, `"Texas"` o `"Virginia"`. El elemento de dimensión `"Unspecified"` incluye todo el tráfico internacional fuera de los Estados Unidos.

Esta dimensión puede incluir `"AOL"`, un proveedor de servicio de acceso telefónico a Internet. A los suscriptores de este servicio se les asigna un punto de acceso. Los usuarios de AOL utilizan la dirección IP de este punto de acceso. Dado que esta dimensión se basa en la dirección IP, se utiliza la geolocalización del punto de acceso en lugar de la ubicación real del visitante.

## Diferencias entre la ubicación real y la notificada

Dado que esta dimensión se basa en la dirección IP, algunos escenarios pueden mostrar una diferencia entre la ubicación real y la ubicación registrada:

* **Direcciones IP que representan proxies corporativos**: Estos visitantes pueden aparecer como tráfico proveniente de la red corporativa del usuario, que puede ser una ubicación diferente si el usuario trabaja de forma remota.
* **Direcciones IP móviles**: La segmentación de direcciones IP móviles funciona en diferentes niveles según la ubicación y la red del dispositivo. Algunos operadores pasan el tráfico IP por puntos de presencia centralizados o regionales.
* **Usuarios de ISP satelitales**: Es difícil identificar la ubicación específica de estos usuarios, ya que normalmente parecen proceder de la ubicación del vínculo superior.
* **IP militares y gubernamentales**: Representa al personal que viaja por todo el mundo y accede a Internet a través de su ubicación local en lugar de la base u oficina en la que esté destinado.
* **Proxies que ocultan direcciones IP por motivos de privacidad**: Servicios como el Retransmisión privada de Apple ocultan la dirección IP real enviando datos de forma aleatoria a través de un intermediario o proxy. A continuación, este proxy sustituye una dirección IP diferente antes de reenviarla a Adobe.
