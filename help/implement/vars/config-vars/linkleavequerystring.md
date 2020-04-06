---
title: linkLeaveQueryString
description: Permite la conservación de cadenas de consulta en dimensiones de seguimiento de vínculos.
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# linkLeaveQueryString

AppMeasurement elimina las cadenas de consulta de las direcciones URL de seguimiento de vínculos de forma predeterminada. Use the `linkLeaveQueryString` variable to preserve query strings in link tracking dimensions.

Para algunos vínculos de salida y de descarga, la parte importante de la dirección URL puede estar en la cadena de consulta. Por ejemplo, un vínculo de descarga como `https://example.com/download.asp?filename=myfile.exe` contiene información importante sobre el vínculo en la cadena de consulta.

Si la información de seguimiento de vínculos no está en las direcciones URL del sitio, no es necesario utilizar esta variable. La eliminación de cadenas de consulta de las direcciones URL de seguimiento de vínculos ayuda a limitar el número de valores únicos que contiene la dimensión.

La activación de `linkLeaveQueryString` se aplica a todas las dimensiones de seguimiento de vínculos (incluidos vínculos personalizados, vínculos de salida y vínculos de descarga).

>[!TIP] Esta variable no afecta a las dimensiones fuera del seguimiento de vínculos. Solo afecta a los vínculos personalizados, de salida y de descarga.

## Mantener parámetros de URL en Adobe Experience Platform Launch

[!UICONTROL Keep URL Parameters] es una casilla de verificación bajo el [!UICONTROL Link Tracking] acordeón al configurar la extensión de Adobe Analytics.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Go to the [!UICONTROL Extensions] tab, then click the [!UICONTROL Configure] button under Adobe Analytics.
4. Expanda el [!UICONTROL Link Tracking] acordeón, que muestra la [!UICONTROL Keep URL Parameters] casilla de verificación.

Marque esta casilla si desea incluir cadenas de consulta en dimensiones de seguimiento de vínculos.

## s.linkLeaveQueryString en el editor de código personalizado de AppMeasurement y Launch

La variable `s.linkLeaveQueryString` es booleana. Su valor predeterminado es `false`.

* Si esta variable tiene el valor `true`, las cadenas de consulta se conservan en las direcciones URL de seguimiento de vínculos.
* Si esta variable tiene el valor `false` o no está definida, las cadenas de consulta se eliminan de las direcciones URL de seguimiento de vínculos.

```js
s.linkLeaveQueryString = true;
```

## Ejemplo

Tenga cuidado al configurar esta variable como true, ya que puede afectar a los filtros de seguimiento de vínculos como [`linkInternalFilters`](linkinternalfilters.md), [`linkExternalFilters`](linkexternalfilters.md) y [`linkDownloadFiletypes`](linkdownloadfiletypes.md).

Se utilizará el siguiente ejemplo como si estuviera en `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
