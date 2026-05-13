---
title: URL de la página
description: La URL de la página.
feature: Dimensions
exl-id: 7c0ec494-d79b-4b65-9161-bdc48485af84
TQID: https://experienceleague.adobe.com/Qek7BUR15HjFpK-XaYQ-J9fkJQiBfNi-ZoqXqaACP0A
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 224
ht-degree: 95%

---

# URL de la página

La &quot;URL de página&quot; [dimensión](overview.md) enumera las direcciones URL del sitio.

>[!IMPORTANT]
>
>Esta dimensión solo está disponible en Data Warehouse. Si desea utilizar una dimensión URL en otras soluciones de Analytics, pruebe a copiar el valor en un [eVar](evar.md) en cada visita.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de [`g` y las `-g` cadenas de consulta](/help/implement/validate/query-parameters.md) en [solicitudes de imagen (`t()`)](/help/implement/vars/functions/t-method.md). [Las llamadas de seguimiento de vínculos (`tl()`)](/help/implement/vars/functions/tl-method.md) siempre eliminan esta dimensión, aunque exista la cadena de consulta `g`.

A veces, las direcciones URL tienen más de 255 bytes. AppMeasurement utiliza el parámetro de cadena de consulta de `g` para los primeros 255 bytes de la dirección URL en las solicitudes de imagen. Si una dirección URL tiene más de 255 bytes, el resto de la dirección URL se almacena en el parámetro de cadena de consulta de `-g`. Las cadenas de consulta y protocolo de la dirección URL se incluyen en esta variable.

AppMeasurement recopila automáticamente estos datos en función de la dirección URL de la página. Puede anular el valor recopilado mediante la variable [`pageURL`](/help/implement/vars/page-vars/pageurl.md).

## Rellenar una eVar con una dirección URL

Adobe recomienda configurar una eVar en la cadena concatenada `window.location.hostname + window.location.pathname`. Esta cadena suele funcionar mejor que `window.location.href` porque omite el protocolo, las cadenas de consulta y las etiquetas de anclaje.

Si desea que la eVar coincida exactamente con la dimensión “URL de página” en Data Warehouse, puede utilizar [variables dinámicas](/help/implement/vars/page-vars/dynamic-variables.md) y establecer la eVar en `D=g` en cada visita.

## Elementos de dimensión

Los elementos de dimensión incluyen las direcciones URL de las páginas del sitio.
