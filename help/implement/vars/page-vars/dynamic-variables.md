---
title: Variables dinámicas
description: Copiar variables sin aumentar la longitud de la solicitud de imagen.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 94%

---


# Variables dinámicas

Las variables dinámicas permiten copiar valores de una variable a otra sin aumentar la longitud de la solicitud de imagen. Resultan útiles a la hora de capturar los mismos datos en varias variables.

En versiones anteriores de Analytics, la longitud de solicitud de imagen era importante para evitar que los datos se truncaran. Las mejoras en AppMeasurement permiten cadenas de consulta de solicitud de imagen mucho más largas, por lo que las variables dinámicas generalmente no son necesarias.

Las variables dinámicas admiten parámetros de cadena de consulta o encabezados HTTP en una solicitud de imagen. Consulte los [parámetros de consulta de recopilación de datos](../../validate/query-parameters.md) para obtener una lista completa de los parámetros disponibles a los que hacer referencia. Consulte [Campos de solicitud estándar](https://es.wikipedia.org/wiki/Anexo:Cabeceras_HTTP) en Wikipedia para obtener una lista completa de los campos de solicitud HTTP disponibles a los que hacer referencia.

Cuando Adobe reconoce un prefijo de variable dinámica, copia automáticamente la cadena de consulta o el valor del encabezado HTTP en el grupo de informes. Esta acción se produce antes que cualquier otro procesamiento, incluidas las reglas de procesamiento y las reglas de VISTA.

>[!TIP]
>
>Tenga en cuenta los límites máximos de caracteres al copiar variables. Por ejemplo, si copia `eVar1` a `prop1`, `prop1` puede tener un valor truncado, ya que tiene un límite de 100 bytes (mientras que `eVar1` tiene un límite de 255 bytes).

## Variables dinámicas en Adobe Experience Platform Launch

Puede utilizar variables dinámicas en cualquier campo de dimensión que acepte una cadena. Los elementos de dimensión generalmente se configuran al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque el elemento de dimensión que desee.

Coloque el prefijo de variable dinámica en el campo de texto, seguido del parámetro de cadena de consulta o del encabezado HTTP al que desee hacer referencia. De forma predeterminada, el prefijo de la variable dinámica es `D=`.

## Variables dinámicas en el editor de código personalizado de AppMeasurement y Launch

Las variables dinámicas son cadenas de texto asignadas a otras variables. El prefijo de variable dinámica predeterminado es `D=`. Las variables dinámicas distinguen entre mayúsculas y minúsculas.

```js
// Copy eVar1 into eVar2. The query string parameter of eVar1 is v1.
s.eVar1 = "Example value";
s.eVar2 = "D=v1";

// Take the user agent string found in the image request HTTP header and place it in eVar1.
s.eVar1 = "D=User-Agent";

// Copy the page URL and place it in eVar1. The query string parameter of page URL is g.
s.eVar1 = "D=g";
```

>[!NOTE]
>
>Las variables dinámicas aparecen como cadenas al depurar la implementación. Los servidores de recopilación de datos de Adobe copian los valores en el servidor.
