---
title: 'Altura del explorador: Agrupado'
description: Altura de la ventana del explorador en píxeles.
feature: Dimensions
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
TQID: https://experienceleague.adobe.com/-MSFtBJDaiG0yYL6ZdpzbPY80uFJbdxB0gyBtKAkFzY
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 273
ht-degree: 87%

---

# Altura del explorador

La [dimensión](overview.md) &quot;Altura del explorador: agrupado&quot; muestra la altura de la ventana del explorador, clasificada en grupos predefinidos. Esta dimensión es útil cuando desea saber dónde está el “pliegue” en el sitio para los visitantes. Conocer la ubicación del pliegue permite optimizar la visualización del contenido.

Esta dimensión es diferente a la altura de la pantalla. La altura del explorador es el número de píxeles dentro del espacio visible del explorador, mientras que la altura de la pantalla es la altura de todo el monitor en píxeles. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```javascript
console.log(`Browser height: ${window.innerHeight} pixels\nScreen height: ${screen.height} pixels`);
```

La altura del explorador siempre es menor o igual a la altura de la pantalla, ya que la altura del explorador no incluye la navegación del explorador ni los bordes.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`bh`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `window.innerHeight` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `bh` en la primera visita individual de cada visita.

Adobe mantiene la altura del explorador durante una visita. Si la altura del explorador se ajusta a mitad de la visita, el ajuste no se registra.

## Elementos de dimensión

Los elementos de Dimension incluyen todas las alturas recopiladas del navegador, clasificadas en grupos predefinidos. Por ejemplo, si la altura del explorador de una visita es `720`, se agrupa en el elemento de dimensión `700 to 799`.
