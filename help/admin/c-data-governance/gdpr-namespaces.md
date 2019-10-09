---
description: A cada ID al que desee permitir búsquedas se le asigna un espacio de nombres, que es una cadena personalizada que identifica ese ID en cualquier variable en la que se utiliza en todos los grupos de informes.
seo-description: A cada ID al que desee permitir búsquedas se le asigna un espacio de nombres, que es una cadena personalizada que identifica ese ID en cualquier variable en la que se utiliza en todos los grupos de informes.
seo-title: Espacios de nombres
title: Espacios de nombres
uuid: cab61844-3209-4980-b14c-6859de777606
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# Espacios de nombres

A cada ID al que desee permitir búsquedas se le asigna un espacio de nombres, que es una cadena personalizada que identifica ese ID en cualquier variable en la que se utiliza en todos los grupos de informes.

La cadena de espacio de nombres se utiliza para identificar los campos en los que se desea buscar al proporcionar un ID como parte de una solicitud de privacidad de datos. Cuando se envía una solicitud de privacidad de datos, la solicitud incluye una sección JSON que especifica los ID del sujeto de datos que se utilizarán para la solicitud. Se pueden incluir varios ID como parte de una sola solicitud para un interesado. En el JSON se incluye lo siguiente:

* Un campo “namespace” que contiene la cadena del espacio de nombres.
* Un campo “type” que, en la mayoría de las solicitudes de Adobe Analytics, contiene el valor “analytics”.
* Un campo “value” que contiene el ID que Analytics debería buscar en las variables de espacio de nombres asociadas de cada uno de sus grupos de informes.

Refer to the [Experience Cloud Data Privacy API documentation](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) for more details.

<!-- Meike, I converted this table to headings and text to fix a validation error. -Bob -->

## ID de cookie

Antigua cookie de rastreo de Analytics, también conocida como ID de Adobe Analytics (AAID):

```
{
   namespace: "AAID",
   type: "standard",
   value: "2CCEEAE88503384F-1188000089CA"
}
```

El valor debe especificarse como dos números hexadecimales separados por una raya. Todos los dígitos hexadecimales que sean caracteres alfabéticos deben especificarse en mayúsculas. Los valores hexadecimales no deben contener ceros a la izquierda (nótese la diferencia respecto a cuando se especificaba el mismo valor en la forma obsoleta, donde los ceros a la izquierda eran necesarios).

También se puede utilizar `“namespaceId”: 10` en lugar de o además de `“namespace”: “AAID”` y es posible que otros productos de Adobe utilicen ese formulario.

## Antigua cookie de rastreo de Analytics: forma obsoleta

```
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

Forma obsoleta:

El valor debe especificarse como dos números hexadecimales de 16 dígitos o como dos números decimales de 19 dígitos. Los números deben separarse con una raya, una raya baja o dos puntos. Si alguno de los números no tiene dígitos suficientes, es necesario añadir ceros a la izquierda.

## Cookie del servicio de identidad

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

El valor debe especificarse como un número decimal de 38 dígitos. Si está extrayendo este número de las dos columnas mcvisid\_high/low o post\_msvisid\_high/low de una fuente de datos o un informe del almacén de datos, debe añadir un relleno cero a cada uno de los dos números a 19 dígitos y, a continuación, concatenarlos primero con el valor máximo.

También se puede utilizar: `“namespaceId”: 4` en lugar de o además de `“namespace”: “ECID”` y es posible que otros productos de Adobe utilicen ese formulario.

>[!NOTE]
>
>El ID de Experience Cloud (ECID) se conocía anteriormente como Marketing Cloud ID (MCID) y todavía se hace referencia a él en alguna documentación existente.
>
>Estos ID son los únicos ID admitidos por Analytics que utilizan un valor de "tipo" distinto de "análisis".

Si el formato de la parte de valor de cualquiera de estos ID de cookies no sigue el formato descrito para ese ID, la solicitud de privacidad de datos fallará, con el error "Valor no formateado correctamente".

Lo habitual es que recopile estos ID de cookie mediante el nuevo código de [JavaScript de privacidad](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm) (vínculo a la documentación técnica), que proporcionará automáticamente todos los pares clave/valor para estos ID de JSON.

Este código JavaScript rellena el JSON con otros pares de clave/valor además de los enumerados anteriormente (espacio de nombres, tipo, valor), pero los campos enumerados arriba son los más importantes para el procesamiento de la privacidad de datos de Analytics y los únicos que debe proporcionar si recopila los ID de otra manera.

## ID de visitante personalizado

```
{
     namespace: "customVisitorID",
     type: "analytics",
     value: "<ID>"
}
```

El espacio de nombres también está predefinido para el ID de visitante personalizado.

## ID en variables personalizadas

```
{
    namespace: "Email Address",
    type: "analytics", 
    value: "john@xyz.com" }, 
{
    namespace: "CRM ID", 
    type: "analytics", 
    value: "123456-ABCD" 
}
```

Para los ID en variables de tráfico o conversión personalizadas (props o eVars), etiquete la variable con una etiqueta ID-DEVICE o ID-PERSON y asigne su propio nombre de espacio de nombres a ese tipo de ID. Consulte [Proporcionar un espacio de nombres al etiquetar una variable como ID-DEVICE o ID-PERSON.](gdpr-labels.md)

También puede ver los espacios de nombres que haya definido con anterioridad para otras variables o grupos de informes y reutilizar uno de ellos, de forma que el mismo espacio de nombres pueda utilizarse para todos sus grupos de informes que almacenan ese tipo de ID. Además, es posible asignar el mismo espacio de nombres a diversas variables dentro de un grupo de informes. Por ejemplo, algunos clientes almacenan un ID de CRM en una variable de tráfico y una de conversión (según la página, a veces se usa solo una de las dos), y podrían asignar el espacio de nombres “ID de CRM” a ambas variables.

> [!TIP] Evite utilizar el nombre descriptivo de una variable (el nombre mostrado en la interfaz de usuario de los informes) o el número de la variable (como eVar12) al especificar el espacio de nombres a la API de privacidad de datos, a menos que sea el espacio de nombres especificado al aplicar la etiqueta ID-DEVICE o ID-PERSON. El uso de un espacio de nombres en lugar de un nombre descriptivo permite que el mismo bloque de identidad de usuario especifique la variable correcta para varios grupos de informes. Por ejemplo, si el ID está en eVars diferentes en algunos grupos de informes o si los nombres descriptivos no coinciden (por ejemplo, cuando el nombre descriptivo se ha localizado para un grupo de informes específico).

> [!CAUTION] Los espacios de nombres "visitorId" y "customVisitorId" están reservados para identificar la cookie de seguimiento heredada de Analytics y el ID de visitante de cliente de Analytics. No utilice estos espacios de nombres para variables de conversión o tráfico personalizado.

Para obtener más información, consulte [Proporcionar un espacio de nombres al etiquetar una variable como ID-DEVICE o ID-PERSON.](/help/admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7)
