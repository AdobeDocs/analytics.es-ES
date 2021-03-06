---
title: linkLeaveQueryString
description: Permite la conservación de cadenas de consulta en dimensiones de seguimiento de vínculos.
feature: Variables
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
source-git-commit: 9e20c5e6470ca5bec823e8ef6314468648c458d2
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 80%

---

# linkLeaveQueryString

AppMeasurement elimina las cadenas de consulta de las direcciones URL de seguimiento de vínculos de forma predeterminada. Utilice la variable `linkLeaveQueryString` para conservar las cadenas de consulta en las dimensiones de seguimiento de vínculos.

Para algunos vínculos de salida y de descarga, la parte importante de la dirección URL puede estar en la cadena de consulta. Por ejemplo, un vínculo de descarga como `https://example.com/download.asp?filename=myfile.exe` contiene información importante sobre el vínculo en la cadena de consulta.

Si la información de seguimiento de vínculos no está en las direcciones URL del sitio, no es necesario utilizar esta variable. La eliminación de cadenas de consulta de las direcciones URL de seguimiento de vínculos ayuda a limitar el número de valores únicos que contiene la dimensión.

La activación de `linkLeaveQueryString` se aplica a todas las dimensiones de seguimiento de vínculos (incluidos vínculos personalizados, vínculos de salida y vínculos de descarga).

>[!TIP]
>
>Esta variable no afecta a las dimensiones fuera del seguimiento de vínculos. Solo afecta a los vínculos personalizados, de salida y de descarga.

## Gestión de cadenas de consulta de vínculos mediante el SDK web

Las cadenas de consulta no se eliminan del campo XDM `web.webInteraction.URL`. Si desea eliminar cadenas de consulta de este campo XDM, puede editarlas mediante `onBeforeEventSend`.

## Mantener parámetros de URL con la extensión Adobe Analytics

[!UICONTROL Mantener parámetros de URL] es una casilla de verificación en el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Iniciar sesión en [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) uso de sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Mantener parámetros de URL].

Marque esta casilla si desea incluir cadenas de consulta en dimensiones de seguimiento de vínculos.

## s.linkLeaveQueryString en AppMeasurement y el editor de código personalizado de la extensión de Analytics

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
