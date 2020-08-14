---
title: referrer
description: Omisión del referente registrado automáticamente para una visita.
translation-type: ht
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3
workflow-type: ht
source-wordcount: '247'
ht-degree: 100%

---


# referrer

La variable `referrer` omite el referente registrado automáticamente en los informes. Esta variable es útil en situaciones en las que el referente podría perderse, como, por ejemplo, durante redirecciones o reenvíos temporales del visitante a un procesador de pagos. Esta variable ayuda a rellenar las dimensiones “Referente” y “Dominio de referencia”.

## Referente en Adobe Experience Platform Launch

Puede establecer el referente al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL Referente].

Puede establecer el referente en cualquier valor de cadena, incluidos los elementos de datos.

## “s.referrer” en el editor de código personalizado de AppMeasurement y Launch

La variable `s.referrer` es una cadena que contiene la dirección URL de la página anterior. Esta variable puede almacenar un máximo de 255 bytes. Los valores mayores a 255 bytes se truncan. AppMeasurement establece automáticamente esta variable en `document.referrer`. No es necesario configurar esta variable a menos que desee anular el valor registrado automáticamente.

```js
s.referrer = "https://example.com";
```

Evite establecer esta variable en valores que no sean URL.

## Ejemplo

Muchas empresas se ocupan de las implementaciones en torno a las redirecciones. Puede aprovechar la utilidad [`Util.getQueryParam()`](../functions/util-getqueryparam.md) para obtener el referente de la dirección URL si el sitio lo aloja. Compruebe que la dirección URL codifique los valores incluidos en la cadena de consulta.

```js
// Example if the URL is https://example.com?r=https%3A%2F%2Fexample.org
s.referrer = s.Util.getQueryParam("r");
```
