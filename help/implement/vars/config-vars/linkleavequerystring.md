---
title: linkLeaveQueryString
description: Permite la preservación de cadenas de consulta en dimensiones de seguimiento de vínculos.
translation-type: tm+mt
source-git-commit: e500332fe16887fa004858b07b59644837e183aa

---


# linkLeaveQueryString

AppMeasurement elimina las cadenas de consulta de las direcciones URL de seguimiento de vínculos de forma predeterminada. Utilice la variable linkLeaveQueryString para conservar las cadenas de consulta en las dimensiones de seguimiento de vínculos.

Para algunos vínculos de salida y de descarga, la parte importante de la dirección URL puede estar en la cadena de consulta. Por ejemplo, un vínculo de descarga como `https://example.com/download.asp?filename=myfile.exe` contiene información importante sobre el vínculo en la cadena de consulta.

Si la información de seguimiento de vínculos no está en las direcciones URL del sitio, no es necesario utilizar esta variable. La eliminación de cadenas de consulta de las direcciones URL de seguimiento de vínculos ayuda a limitar el número de valores únicos que contiene la dimensión.

La activación `linkLeaveQueryString` se aplica a todas las dimensiones de seguimiento de vínculos (incluidos vínculos personalizados, vínculos de salida y vínculos de descarga).

> [!TIP] Esta variable no afecta a las dimensiones fuera del seguimiento de vínculos. Solo afecta a los vínculos personalizados, de salida y de descarga.

## Mantener parámetros de URL en Adobe Experience Platform Launch

[!UICONTROL Mantener parámetros] de URL es una casilla de verificación debajo del [!UICONTROL acordeón Seguimiento] de vínculos al configurar la extensión de Adobe Analytics.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en Adobe Analytics.
4. Expanda el acordeón Seguimiento [!UICONTROL de] vínculos, que muestra la casilla [!UICONTROL Mantener parámetros] de URL.

Marque esta casilla si desea incluir cadenas de consulta en dimensiones de seguimiento de vínculos.

## s.linkLeaveQueryString en el editor de código personalizado AppMeasurement e Launch

La `s.linkLeaveQueryString` variable es booleana. Its default value is `false`.

* Si esta variable está configurada en `true`, las cadenas de consulta se conservan en las direcciones URL de seguimiento de vínculos.
* Si esta variable se define `false` o no, las cadenas de consulta se eliminan de las direcciones URL de seguimiento de vínculos.

```js
s.linkLeaveQueryString = true;
```

## Ejemplo

Tenga cuidado al configurar esta variable en true, ya que puede afectar a los filtros de seguimiento de vínculos como `linkInternalFilters`, `linkExternalFilters`, y `linkDownloadFiletypes`.

Considere el siguiente ejemplo como si estuviera en `adobe.com`:

```html
<script>
  s.linkInternalFilters = "adobe.com";
  s.linkLeaveQueryString = true;
</script>

<!--This link is not an exit link because the internal filter matches part of the query string -->
<a href = "example.com?r=adobe.com">Example link</a>
```
