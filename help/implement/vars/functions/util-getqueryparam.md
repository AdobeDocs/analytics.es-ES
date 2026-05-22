---
title: Util.getQueryParam
description: Devuelve el valor de un parámetro de cadena de consulta.
feature: Appmeasurement Implementation
exl-id: d29d6cd9-f85f-475b-a7a8-73785aa4ae7b
role: Admin, Developer
TQID: 'https://experienceleague.adobe.com/99nBiI23QwY6J6qEVKKz901Bertmkxf21YeJdKTmWbo'
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
source-wordcount: 274
ht-degree: 79%

---

# Util.getQueryParam

Los parámetros de cadena de consulta de una URL de navegador contienen con frecuencia datos importantes para Analytics. Utilice el método `Util.getQueryParam()` para recuperar datos de la cadena de consulta.

## Obtenga datos de parámetros de cadena de consulta con la extensión Adobe Analytics y la extensión Web SDK

Puede obtener datos de parámetros de cadena de consulta estableciendo valores en los elementos de datos.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Elementos de datos] y, a continuación, haga clic en el elemento de datos deseado (o cree un elemento de datos).
4. Establezca la lista desplegable [!UICONTROL Extension] en **[!UICONTROL Core]** y el [!UICONTROL Tipo de elemento de datos] en **[!UICONTROL Parámetro de cadena de consulta]**.
5. Introduzca el parámetro de cadena de consulta en el campo de texto.

El valor del parámetro de cadena de consulta se almacena en el elemento de datos. A continuación, puede hacer referencia al elemento de datos en las reglas para asignar las variables deseadas.

## s.Util.getQueryParam() en AppMeasurement y el editor de código personalizado de la extensión de Analytics

Llame al método `s.Util.getQueryParam()` para recuperar un valor de cadena de consulta de la dirección URL del explorador. Se requiere el argumento de cadena que contiene un parámetro de cadena de consulta. Este método devuelve una cadena que puede asignar a variables de Analytics:

```js
s.eVar1 = s.Util.getQueryParam("cid");
```

Un segundo argumento opcional permite especificar la cadena que se va a comprobar para buscar parámetros de cadena de consulta. De forma predeterminada, la utilidad busca la dirección URL del explorador.

```js
// Search a custom string for query string parameter
var customString = "https://example.com?q=search";

// eVar1 is set to "search"
s.eVar1 = s.Util.getQueryParam("q",customString);
```

Un tercer argumento opcional permite personalizar el delimitador de cadena de consulta. Su valor predeterminado es `&`. Puede cambiar este valor si la cadena de consulta utiliza un delimitador diferente.

```js
var customString = "https://example.com?q1=value1;q2=value2;q3=value3";

// eVar1 is set to "value2"
s.eVar1 = s.Util.getQueryParam("q2",customString,";");
```

>[!TIP]
>
>Hay un complemento similar disponible, denominado [`s.getQueryParam`](../plugins/getqueryparam.md). Este complemento contiene funciones más avanzadas, pero también es más complejo y no se incluye en AppMeasurement de forma predeterminada.
