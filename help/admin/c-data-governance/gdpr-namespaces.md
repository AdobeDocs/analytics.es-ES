---
description: A cada ID al que desee permitir búsquedas se le asigna un espacio de nombres, que es una cadena personalizada que identifica ese ID en cualquier variable en la que se utiliza en todos los grupos de informes.
seo-description: A cada ID al que desee permitir búsquedas se le asigna un espacio de nombres, que es una cadena personalizada que identifica ese ID en cualquier variable en la que se utiliza en todos los grupos de informes.
seo-title: Espacios de nombres
title: Espacios de nombres
uuid: cab 61844-3209-4980-b 14 c -6859 de 777606
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Espacios de nombres

A cada ID al que desee permitir búsquedas se le asigna un espacio de nombres, que es una cadena personalizada que identifica ese ID en cualquier variable en la que se utiliza en todos los grupos de informes.

La cadena del espacio de nombres se emplea para identificar los campos en los que desea buscar al proporcionar un ID como parte de una solicitud de RGPD. Cuando se envía una solicitud de RGPD, la solicitud incluirá una sección de JSON en la que se especifican los ID de los interesados que se utilizarán para la solicitud. Se pueden incluir varios ID como parte de una sola solicitud para un interesado. En el JSON se incluye lo siguiente:

* Un campo “namespace” que contiene la cadena del espacio de nombres.
* Un campo “type” que, en la mayoría de las solicitudes de Adobe Analytics, contiene el valor “analytics”.
* Un campo “value” que contiene el ID que Analytics debería buscar en las variables de espacio de nombres asociadas de cada uno de sus grupos de informes.

Consulte la [documentación de la API de RGPD de Experience Cloud](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md) para obtener más información.

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

It is also acceptable to use `“namespaceId”: 10` instead of or in addition to `“namespace”: “AAID”` and you may see some other Adobe products use that form.

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

## Cookie de servicio de identidad

```
{
    namespace: "ECID",
    type: "standard",
    value: "00497781304058976192356650736267671594"
}
```

El valor debe especificarse como un número decimal de 38 dígitos. Si extrae este número de los dos mcvisid\_ high/low o post\_ msvisid\_ high/low columns de una fuente de datos o de un informe Almacén de datos, debe segmentar cada uno de los números a 19 dígitos y luego concatenarlos con el valor alto primero.

It is also acceptable to use: `“namespaceId”: 4` instead of or in addition to `“namespace”: “ECID”` and you may see some other Adobe products use that form.

>[!NOTE]
>
>El ID de Experience Cloud (ECID) anteriormente se denominaba Marketing Cloud ID (MCID) y se sigue haciendo referencia a él en alguna documentación existente.
>
>Estos ID son los únicos ID admitidos por Analytics que utilizan un valor "type" distinto de "analytics".

Si el formato de la porción de valor de cualquiera de estos ID de cookie no cumple el formato descrito para el ID, la solicitud amparada en el RGPD falla y genera el error “El valor no tiene el formato correcto”.

Lo habitual es que recopile estos ID de cookie mediante el nuevo código de [JavaScript de privacidad](https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm) (vínculo a la documentación técnica), que proporcionará automáticamente todos los pares clave/valor para estos ID de JSON.

Este código de JavaScript rellena el JSON con otros pares clave/valor además de los indicados arriba (espacio de nombres, tipo, valor), pero los campos que verá arriba son los más importantes para el tratamiento del RGPD de Analytics y los únicos que tendrá que proporcionar si recopila los ID con cualquier otro método.

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

En el caso de los ID en variables de tráfico o conversión personalizadas (props o eVars), debería etiquetar la variable con ID-DEVICE o ID-PERSON y, después, asignar su propio nombre de espacio de nombres a ese tipo de ID. Consulte [Proporcionar un espacio de nombres al etiquetar una variable como ID-DEVICE o ID-PERSON](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7).

También puede ver los espacios de nombres que haya definido con anterioridad para otras variables o grupos de informes y reutilizar uno de ellos, de forma que el mismo espacio de nombres pueda utilizarse para todos sus grupos de informes que almacenan ese tipo de ID. Además, es posible asignar el mismo espacio de nombres a diversas variables dentro de un grupo de informes. Por ejemplo, algunos clientes almacenan un ID de CRM en una variable de tráfico y una de conversión (según la página, a veces se usa solo una de las dos), y podrían asignar el espacio de nombres “ID de CRM” a ambas variables.

>[!NOTE]
>
>No puede utilizar el nombre descriptivo de una variable (el nombre que se muestra en la interfaz de usuario de informes) ni el número de la variable (como evar 12) al especificar el espacio de nombres en la API GDPR, a menos que también sea el espacio de nombres especificado al aplicar la etiqueta ID-DEVICE o ID-PERSON a esta variable. Utilizar un espacio de nombres en lugar de un nombre descriptivo permite que el mismo bloque de identidad del usuario especifique la variable correcta para múltiples grupos de informes en estos casos:

* El ID se encuentra en diferentes eVars en algunos grupos de informes, o
* Los nombres descriptivos no coinciden (como cuando el nombre descriptivo se ha localizado para un grupo de informes específico)

Para obtener más información, consulte [Proporcionar un espacio de nombres al etiquetar una variable como ID-DEVICE o ID-PERSON](../../admin/c-data-governance/gdpr-labels.md#section_F0A47AF8DA384A26BD56032D0ABFD2D7).
