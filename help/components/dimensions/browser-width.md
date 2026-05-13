---
title: 'Anchura del explorador: Agrupado'
description: Anchura de la ventana del explorador en píxeles.
feature: Dimensions
exl-id: f0cb28b6-260b-4c3d-bbf8-17fae7ef22a0
TQID: https://experienceleague.adobe.com/f9AknIwL-9ZMJ8tnGMxpUNmlkQiFmbjI3gtlP3KZtSQ
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 274
ht-degree: 81%

---

# Anchura del explorador

La [dimensión](overview.md) &quot;Anchura del explorador: agrupado&quot; muestra la anchura de la ventana del explorador, clasificada en grupos predefinidos. Esta dimensión es útil cuando desea comprender la amplitud con la que los visitantes ven el contenido. Comprender la anchura con la que se visualiza el contenido generalmente puede permitirle optimizar ese contenido.

Esta dimensión es diferente al ancho de la pantalla. La anchura del explorador es el número de píxeles dentro del espacio del explorador visible, mientras que la anchura de la pantalla es el ancho de todo el monitor en píxeles. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```javascript
console.log(`Browser width: ${window.innerWidth} pixels\nScreen width: ${screen.width} pixels`);
```

El ancho del explorador siempre es menor o igual al ancho de la pantalla, ya que el ancho del explorador no incluye barras de desplazamiento ni bordes.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`bw`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `window.innerWidth` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `bw` en la primera visita individual de cada visita.

Adobe mantiene la anchura del navegador para una visita. Si la anchura del explorador se ajusta a mitad de la visita, el ajuste no se registra.

## Elementos de dimensión

Los elementos de Dimension incluyen todas las anchuras recopiladas del navegador, clasificadas en grupos predefinidos. Por ejemplo, si la anchura del explorador de una visita es `1280`, se agrupa en el elemento de dimensión `1200 to 1299`.
