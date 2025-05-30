---
description: A cada ID al que desee permitir búsquedas se le asigna un área de nombres, que es una cadena personalizada que identifica ese ID en cualquier variable en la que se utiliza en todos los grupos de informes.
title: Espacios de nombres
feature: Data Governance
role: Admin
exl-id: 421572c2-2789-48bc-b530-d48216799724
source-git-commit: 79f650a7168e0cc44194445f3164a3f981e39a91
workflow-type: ht
source-wordcount: '896'
ht-degree: 100%

---

# Espacios de nombres

A cada ID al que desee permitir búsquedas se le asigna un área de nombres, que es una cadena personalizada que identifica ese ID en cualquier variable en la que se utiliza en todos los grupos de informes.

La cadena del área de nombres se emplea para identificar los campos en los que desea buscar al proporcionar un ID como parte de una solicitud de privacidad de datos. Cuando se envía una solicitud de privacidad de datos, esta incluirá una sección de JSON en la que se especifican los ID de los interesados que se utilizarán para la solicitud. Se pueden incluir varios ID como parte de una sola solicitud para un interesado. En el JSON se incluye lo siguiente:

* Un campo “namespace” que contiene la cadena del área de nombres.
* Un campo “type” que, en la mayoría de las solicitudes de Adobe Analytics, contiene el valor “analytics”.
* Un campo “value” que contiene el ID que Analytics debería buscar en las variables de área de nombres asociadas de cada uno de sus grupos de informes.

Consulte la [documentación de la API de privacidad de datos de Experience Cloud](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es) para obtener más información sobre la [lista de espacio de nombres de identidad estándar](https://experienceleague.adobe.com/es/docs/experience-platform/privacy/api/appendix#standard-namespaces). Consulte [Crear un trabajo de acceso o eliminación](https://experienceleague.adobe.com/es/docs/experience-platform/privacy/api/privacy-jobs#access-delete) para una solicitud de muestra.

## ID de cookie

Antigua cookie de rastreo de Analytics, también conocida como ID de Adobe Analytics (AAID):

```json
{
   "namespace": "AAID",
   "type": "standard",
   "value": "2CCEEAE88503384F-1188000089CA"
}
```

El valor debe especificarse como dos números hexadecimales separados por una raya. Todos los dígitos hexadecimales que sean caracteres alfabéticos deben especificarse en mayúsculas. Los valores hexadecimales no deben contener ceros a la izquierda (nótese la diferencia respecto a cuando se especificaba el mismo valor en la forma obsoleta, donde los ceros a la izquierda eran necesarios).

También puede utilizar `"namespaceId": 10` en lugar de o además de `"namespace": "AAID"` y es posible que vea otros productos de Adobe usar ese formulario.

## Antigua cookie de seguimiento de Analytics: forma obsoleta

```json
{
   "namespace": "visitorId",
   "type": "analytics",
   "value": "2cceeae88503384f-00001188000089ca"
}
```

El valor debe especificarse como dos números hexadecimales de 16 dígitos o como dos números decimales de 19 dígitos. Los números deben separarse con una raya, una raya baja o dos puntos. Si alguno de los números no tiene dígitos suficientes, es necesario añadir ceros a la izquierda.

## Cookie del servicio de identidad

```json
{
   "namespace": "ECID",
   "type": "standard",
   "value": "00497781304058976192356650736267671594"
}
```

El valor debe especificarse como un número decimal de 38 dígitos. Si obtiene este número de las dos columnas mcvisid\_high/low or post\_msvisid\_high/low de una fuente de datos o de un informe de Data Warehouse, debe completar con ceros los dos números hasta que tengan 19 dígitos y después concatenarlos, poniendo primero el valor alto.

También se puede utilizar `"namespaceId": 4` en lugar de o además de `"namespace": "ECID"` y es posible que vea que otros productos de Adobe utilizan ese formulario.

>[!NOTE]
>
>Experience Cloud ID (ECID) se conocía antes como Marketing Cloud ID (MCID) y aún se hace referencia a él con ese nombre en partes de la documentación publicada.
>
>Estos ID son los únicos que Analytics admite cuyo valor de “type” es distinto de “analytics”.

Si el formato de la porción de valor de cualquiera de estos ID de cookie no cumple con el formato descrito para el ID, la solicitud amparada en la privacidad de datos falla y genera el error “El valor no tiene el formato correcto”.

Lo habitual es que recopile estos ID de cookie mediante el nuevo código de [JavaScript de privacidad](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) (vínculo a la documentación técnica), que proporcionará automáticamente todos los pares clave/valor para estos ID de JSON.

Este código de JavaScript rellena el JSON con otros pares clave/valor además de los indicados arriba (área de nombres, tipo, valor), pero los campos que verá arriba son los más importantes para el tratamiento de la privacidad de datos de Analytics y los únicos que tendrá que proporcionar si recopila los ID con cualquier otro método.

## ID de visitante personalizado

```json
{
    "namespace": "customVisitorID",
    "type": "analytics",
    "value": "<ID>"
}
```

El área de nombres también está predefinido para el ID de visitante personalizado.

## ID en variables personalizadas

```json
{
"namespace":"Email Address",
"type": "analytics", 
"value": "john@xyz.com" 
}, 
{
    "namespace": "CRM ID", 
    "type": "analytics",
    "value": "123456-ABCD" 
}
```

En el caso de los ID en variables de tráfico o conversión personalizadas (props o eVars), etiquete la variable con ID-DEVICE o ID-PERSON y, después, asignar su propio nombre de área de nombres a ese tipo de ID. Consulte [Proporcionar un área de nombres al etiquetar una variable como ID-DEVICE o ID-PERSON.](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md)

También puede ver los áreas de nombres que haya definido con anterioridad para otras variables o grupos de informes y reutilizar uno de ellos, de forma que el mismo área de nombres pueda utilizarse para todos sus grupos de informes que almacenan ese tipo de ID. Además, es posible asignar el mismo área de nombres a diversas variables dentro de un grupo de informes. Por ejemplo, algunos clientes almacenan un ID de CRM en una variable de tráfico y una de conversión (según la página, a veces se usa solo una de las dos), y podrían asignar el área de nombres “ID de CRM” a ambas variables.

>[!TIP]
>
>No puede utilizar un nombre descriptivo de una variable (el nombre mostrado en la interfaz de usuario de generación de informes) o el número de la variable (como eVar12) cuando especifica el área de nombres en la API de privacidad de datos, a menos que también sea el área de nombres especificado al aplicar la etiqueta ID-DEVICE o ID-PERSON. Utilizar un área de nombres en lugar de un nombre descriptivo permite que el mismo bloque de identidad del usuario especifique la variable correcta para múltiples grupos de informes. Por ejemplo, si el ID está en eVars diferentes en algunos grupos de informes o si los nombres descriptivos no coinciden (como cuando el nombre descriptivo se ha localizado para un grupo de informes específico).

>[!CAUTION]
>
>Las áreas de nombres `visitorId` y `customVisitorId` están reservadas para identificar la cookie de seguimiento heredada de Analytics y el ID de visitante del cliente de Analytics. No utilice estas áreas de nombres para variables de conversión o tráfico personalizado.

Para obtener más información, consulte [Proporcionar un área de nombres al etiquetar una variable como ID-DEVICE o ID-PERSON.](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md)
