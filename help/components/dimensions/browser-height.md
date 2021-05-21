---
title: 'Altura del explorador: Agrupado'
description: Altura de la ventana del explorador en píxeles.
exl-id: bdfd2ef5-c200-4d6e-b478-3917fca66227
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '273'
ht-degree: 100%

---

# Altura del explorador

La dimensión “Altura del explorador: agrupado” muestra la altura de la ventana del explorador, clasificada en grupos de 100 píxeles. Esta dimensión es útil cuando desea saber dónde está el “pliegue” en el sitio para los visitantes. Conocer la ubicación del pliegue permite optimizar la visualización del contenido.

Esta dimensión es diferente a la altura de la pantalla. La altura del explorador es el número de píxeles dentro del espacio visible del explorador, mientras que la altura de la pantalla es la altura de todo el monitor en píxeles. Si desea ver la diferencia entre estas dos variables en su propio equipo, abra la consola del explorador (F12 en la mayoría de los exploradores) y copie y pegue el siguiente código en la consola:

```javascript
"Browser height: " + window.innerHeight + " pixels\nScreen height: " + screen.height + " pixels";
```

La altura del explorador siempre es menor o igual a la altura de la pantalla, ya que la altura del explorador no incluye la navegación del explorador ni los bordes.

## Rellene esta dimensión con datos

Esta dimensión recupera datos de la [`bh`cadena de consulta](/help/implement/validate/query-parameters.md) en solicitudes de imagen. AppMeasurement recopila estos datos mediante la variable JavaScript `window.innerHeight` en el explorador. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), esta dimensión funciona de forma predeterminada. Si utiliza un método de recopilación de datos fuera de AppMeasurement (por ejemplo, a través de la API), asegúrese de incluir el parámetro de cadena de consulta `bh` en la primera visita individual de cada visita.

Adobe mantiene la altura del explorador durante una visita. Si la altura del explorador se ajusta a mitad de la visita, el ajuste no se registra.

## Elementos de dimensión

Los elementos de dimensión incluyen todas las alturas recopiladas del navegador, clasificadas en grupos de 100 píxeles. Por ejemplo, si la altura del explorador de una visita es `720`, se agrupa en el elemento de dimensión `700 to 799`.
