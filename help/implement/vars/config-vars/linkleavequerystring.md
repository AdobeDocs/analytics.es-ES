---
title: linkLeaveQueryString
description: Permite la conservación de cadenas de consulta en dimensiones de seguimiento de vínculos.
feature: Appmeasurement Implementation
exl-id: 266f7d9c-803d-4dbe-95a1-282230012878
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/HI9yasKxMWctqoHOlZfkvMEWo1tDa3UWuWo22Bl3jFM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 331
ht-degree: 84%

---

# linkLeaveQueryString

AppMeasurement elimina las cadenas de consulta de las direcciones URL de seguimiento de vínculos de forma predeterminada. Utilice la variable `linkLeaveQueryString` para conservar las cadenas de consulta en las dimensiones de seguimiento de vínculos.

Para algunos vínculos de salida y de descarga, la parte importante de la dirección URL puede estar en la cadena de consulta. Por ejemplo, un vínculo de descarga como `https://example.com/download.asp?filename=myfile.exe` contiene información importante sobre el vínculo en la cadena de consulta.

Si la información de seguimiento de vínculos no está en las direcciones URL del sitio, no es necesario utilizar esta variable. La eliminación de cadenas de consulta de las direcciones URL de seguimiento de vínculos ayuda a limitar el número de valores únicos que contiene la dimensión.

La habilitación de `linkLeaveQueryString` se aplica a todas las dimensiones de seguimiento de vínculos (incluidos vínculos personalizados, vínculos de salida y vínculos de descarga).

>[!TIP]
>
>Esta variable no afecta a las dimensiones fuera del seguimiento de vínculos. Solo afecta a los vínculos personalizados, de salida y de descarga.

## Administrar cadenas de consulta de vínculos mediante Web SDK

Las cadenas de consulta no se eliminan del campo XDM `web.webInteraction.URL`. Si desea eliminar las cadenas de consulta de este campo XDM, puede editarlo mediante `onBeforeEventSend`.

## Mantener parámetros de URL con la extensión Adobe Analytics

[!UICONTROL Mantener parámetros de URL] es una casilla de verificación en el acordeón de [!UICONTROL Seguimiento de vínculos] al configurar la extensión de Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en Adobe Analytics.
4. Expanda el acordeón de [!UICONTROL Seguimiento de vínculos], que muestra la casilla [!UICONTROL Mantener parámetros de URL].

Marque esta casilla si desea incluir cadenas de consulta en dimensiones de seguimiento de vínculos.

## s.linkLeaveQueryString en el editor de código personalizado de la extensión de AppMeasurement

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
