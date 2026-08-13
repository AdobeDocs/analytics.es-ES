---
title: Idioma
description: El idioma preferido configurado para el explorador.
feature: Dimensions
exl-id: 590406a4-d336-42c7-8048-e7cd8e611d43
TQID: https://experienceleague.adobe.com/KC8nBiwUbQaE8Wi5OVKdjwP-sTijGYYMBK74M-TnOFs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 158
ht-degree: 91%

---

# Idioma

La dimensión [Idioma](overview.md) muestra los idiomas principales en los que los visitantes prefieren ver el contenido. Esta dimensión es valiosa cuando desea comprender los idiomas preferidos más frecuentes de los visitantes para ayudar en las tareas de localización.

>[!NOTE]
>
>Esta dimensión no recopila el idioma del sitio. Si desea recopilar el idioma del sitio en una dimensión, Adobe recomienda utilizar una variable personalizada, como una [eVar](evar.md).

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `Accept-Language` de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen nombres descriptivos de los idiomas preferidos de los visitantes. Los ejemplos incluyen `"English (United States)"`, `"English (United Kingom)"`, `"Chinese (China)"` y `"Spanish (Spain)"`. Si una solicitud de imagen no contiene un idioma válido en el encabezado HTTP, el elemento de dimensión es `"None"`.
