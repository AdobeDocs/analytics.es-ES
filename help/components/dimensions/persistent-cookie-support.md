---
title: Compatibilidad con cookies persistentes
description: Determina si el visitante puede admitir cookies persistentes.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 207
ht-degree: 90%

---

# Compatibilidad con cookies persistentes

La &quot;Compatibilidad con cookies persistentes&quot; [dimension](overview.md) muestra si la visita utilizó un identificador de visitante originado en una fuente persistente. La fuente persistente más común es de una cookie, pero también puede utilizar encabezados móviles y otras fuentes.

## Rellene esta dimensión con datos

Adobe determina el valor de esta dimensión del lado del servidor en función del origen del identificador de la visita. No hay una forma de configurarlo directamente. Funciona de forma predeterminada para todas las implementaciones.

## Elementos de dimensión

* **`Enabled`**: el identificador de visitante de la visita proviene de un origen que normalmente persiste. Los ejemplos más comunes incluyen parámetros de cadena de consulta `aid`, `fid` o `mid`, ya que derivan sus valores de una cookie.
* **`Disabled`**: el identificador de visitante de la visita proviene de una fuente que Adobe no reconoce como persistente, como IP + cadena del agente de usuario. Este elemento de dimensión también incluye los ID de visitante personalizados que utilizan la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Diferencia entre “Compatibilidad con cookies” y “Compatibilidad con cookies persistentes”

* **Compatibilidad con cookies**: AppMeasurement intenta establecer una cookie genérica. El elemento de dimensión se basa en si la cookie se configuró correctamente.
* **Compatibilidad con cookies persistentes**: el elemento de dimensión se basa en si el identificador de la visita se originó a partir de una fuente persistente, como una cookie.
