---
title: linkURL
description: Omitir la URL del vínculo generado automáticamente que AppMeasurement utiliza en las llamadas de seguimiento de vínculos.
exl-id: 15d6e423-d9fc-4f84-ad39-0bd91399cde4
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '115'
ht-degree: 100%

---

# linkURL

Cada vez que se envía una llamada de seguimiento de vínculos a Adobe, los servidores de recopilación de datos detectan automáticamente la dirección URL. Utilice la variable `linkURL` para anular la dirección URL detectada.

## URL de vínculo en Adobe Experience Platform Launch

No hay un campo específico en Launch para utilizar esta variable. Utilice el editor de código personalizado siguiendo la sintaxis de AppMeasurement.

## s.linkURL en el editor de código personalizado de AppMeasurement y Launch

La variable `s.linkURL` es una cadena que contiene la dirección URL del explorador cuando se hizo clic en el vínculo. Esta variable no rellena ninguna dimensión disponible en los informes.

```js
s.linkURL = "https://example.com";
```

Si no se establece el tercer argumento del método [tl()](../functions/tl-method.md), se utiliza la variable `linkURL` en su lugar.
