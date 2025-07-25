---
title: Variables dinámicas
description: Copiar variables sin aumentar la longitud de la solicitud de imagen.
feature: Appmeasurement Implementation
exl-id: 41aab44d-01fd-45fe-892d-637d69488d98
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 78%

---

# Variables dinámicas

Las variables dinámicas permiten copiar valores de una variable a otra sin aumentar la longitud de la solicitud de imagen. Resultan útiles a la hora de capturar los mismos datos en varias variables.

En versiones anteriores de Analytics, la longitud de solicitud de imagen era importante para evitar que los datos se truncaran. Las mejoras en AppMeasurement permiten cadenas de consulta de solicitud de imagen mucho más largas, por lo que las variables dinámicas generalmente no son necesarias.

Las variables dinámicas admiten parámetros de cadena de consulta o encabezados HTTP en una solicitud de imagen. Consulte los [parámetros de consulta de recopilación de datos](../../validate/query-parameters.md) para obtener una lista completa de los parámetros disponibles a los que hacer referencia. Consulte [Campos de solicitud estándar](https://es.wikipedia.org/wiki/Anexo:Cabeceras_HTTP) en Wikipedia para obtener una lista completa de los campos de solicitud HTTP disponibles a los que hacer referencia.

Cuando Adobe reconoce un prefijo de variable dinámica, copia automáticamente la cadena de consulta o el valor del encabezado HTTP en el grupo de informes. Esta acción se produce antes que cualquier otro procesamiento, incluidas las reglas de procesamiento y las reglas de VISTA.

>[!TIP]
>
>Tenga en cuenta los límites máximos de caracteres al copiar variables. Por ejemplo, si copia `eVar1` a `prop1`, `prop1` puede tener un valor truncado, ya que tiene un límite de 100 bytes (mientras que `eVar1` tiene un límite de 255 bytes).

## Variables dinámicas que utilizan Web SDK

Utilice la asignación de secuencia de datos para enviar datos a varias variables de Analytics desde un único campo XDM.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en **[!UICONTROL Datastreams]** en el carril izquierdo.
1. Haga clic en el conjunto de datos deseado.
1. Haga clic en **[!UICONTROL Editar asignación]** a la derecha.
1. Asigne el [!UICONTROL campo Source] deseado al [!UICONTROL campo Target] deseado. Un solo campo de origen puede asignarse a cualquier número de campos de destino.

## Variables dinámicas que utilizan la extensión de Adobe Analytics

Puede utilizar variables dinámicas en cualquier campo de dimensión que acepte una cadena. Los elementos de dimensión se suelen definir al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad de etiquetas deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca la lista desplegable [!UICONTROL Extension] en Adobe Analytics y [!UICONTROL Action Type] en [!UICONTROL Set Variables].
6. Busque el elemento de dimensión deseado.

Coloque el prefijo de variable dinámica en el campo de texto, seguido del parámetro de cadena de consulta o del encabezado HTTP al que desee hacer referencia. De forma predeterminada, el prefijo de la variable dinámica es `D=`.

## Variables dinámicas en AppMeasurement y el editor de código personalizado de la extensión de Analytics

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
