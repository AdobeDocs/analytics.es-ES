---
description: Los ID que envíe no siempre abarcarán todos los datos coincidentes que Analytics pueda asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de privacidad de datos.
title: Expansión de ID
feature: Data Governance
role: Admin
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '1299'
ht-degree: 96%

---

# Expansión de ID

Los ID que envíe no siempre abarcarán todos los datos coincidentes que Analytics pueda asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de privacidad de datos. Puede solicitar esta opción con un parámetro opcional a cada solicitud de privacidad de datos que envíe junto a la solicitud de JSON:

```
"expandIds": true
```

Para obtener más información, consulte la [Documentación de la API del servicio de privacidad](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es).


| Tipo | Consideraciones |
| --- | --- |
| Expansión de ID de cookie | Muchos clientes de Analytics usaban originalmente la [cookie de Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=es) (heredada), pero ahora emplean el [servicio Experience Cloud ID (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es). Para los visitantes de su sitio web que efectuaran la visita después de la transición, solo existe el ECID. Sin embargo, para aquellos que nos visitaron por primera vez, cuando solo estaba disponible la cookie heredada, pero nos han visitado desde entonces: algunos de sus datos tienen ambas cookies. Sin embargo, los datos más antiguos solo tienen la cookie de Analytics y, en casos excepcionales, es posible que los datos más recientes solo tengan un ECID.<p>Debe asegurarse de que encuentra todos los datos de un visitante identificado a través de una cookie de Analytics (ID de visitante) o un ECID. Por tanto, si en estos momentos utiliza el ECID y antes usaba la cookie de Analytics, siempre que envíe una solicitud utilizando cualquiera de los tipos de ID, deberá incluir ambos ID en la solicitud, o bien especificar la opción `expandIds`. Cuando especifique `expandIds`, Adobe buscará otros ECID o cookies de Analytics que se correspondan con los ID de cookie que facilite. La solicitud se ampliará automáticamente para incluir los ID de cookies recién identificados. |
| Expansión de ID personalizado a ID de cookie | En sitios web de comercio electrónico, no es inusual que un visitante explore el sitio, añada artículos a su carrito y, después, inicie el proceso de pago antes de iniciar sesión en el sitio. Si el ID utilizado para identificar a los usuarios para una solicitud amparada en la privacidad de datos se almacena en una variable personalizada solo cuando el usuario tiene sesión iniciada, la actividad previa al inicio de sesión no se asociará con el ID. Gracias al ID de cookie de Analytics, los clientes pueden optar por asociar la exploración realizada antes del inicio de sesión con la compra efectuadas tras él, dado que el ID de cookie se conserva durante todo el proceso.<p>Supongamos que su implementación almacena un ID de inicio de sesión (ID de CRM, nombre de usuario, número de fidelidad, dirección de correo electrónico, etc., o un hash de cualquiera de estos valores) en una variable personalizada (prop o eVar) o un ID de visitante personalizado, y que después utiliza este ID para una solicitud de acceso amparada en la privacidad de datos. El interesado podría sorprenderse de que no se le devuelva información sobre toda su navegación como parte de una solicitud de acceso, especialmente si le han promocionado artículos vistos, pero aún no adquiridos. Por ello, el tratamiento de la privacidad de datos de Analytics admite la expansión de ID, un proceso por el cual Analytics encuentra todos los ID de cookies que se producen en la misma visita como cualquier ID personalizado y, después, amplía la solicitud para incluir también esos ID.<p>Cuando `expandIDs` se especifica junto con cualquier área de nombres que no sea un área de nombres de cookie, la solicitud se expandirá para incluir cualquier ID de cookie (ECID o cookie de Analytics), que se encuentre en las visitas que contengan cualquiera de los ID especificados. La expansión de ID de cookie, tal como se describe anteriormente, se llevará a cabo en cualquier ID de cookie que se haya encontrado recientemente.<p>Cuando se utiliza la opción `expandIDs` para una solicitud de acceso y el ID especificado tiene una etiqueta de ID-PERSON, se devuelven dos conjuntos de archivos. El primer conjunto (el conjunto de personas) contendrá datos solo de las visitas donde se encontró el ID especificado. El segundo conjunto (el conjunto de dispositivos) solo contendrá datos de las visitas de los ID expandidos, en los que el ID especificado no estaba presente. |

{style="table-layout:auto"}

## Cuándo utilizar la expansión de ID

Durante los primeros meses después de la entrada en vigor de la privacidad de datos, la gran mayoría de las solicitudes de privacidad de datos de Analytics no solicitaron la expansión de ID. Sin embargo, la determinación del valor apropiado para su organización depende de usted. Debe consultar con su equipo legal si la expansión de ID es necesaria para sus datos con los ID que utiliza y los datos que recopila dentro de Adobe Analytics.

Una consideración principal debe ser que, en un dispositivo compartido desde el que varios usuarios han visitado su sitio, el uso de la expansión de ID incluirá, en los datos devueltos por las solicitudes de acceso (en el archivo del dispositivo), datos de visitas de otros usuarios del dispositivo. Aunque haya seguido las prácticas recomendadas de etiquetado, (por ejemplo, como que no se incluyan datos privados en el archivo del dispositivo, como las páginas visitadas), este dispositivo contendrá el número de páginas visitadas y la hora de cada una de esas visitas. Puede que desee preguntarse a sí mismo: ¿me parece bien compartir esta información con alguien que podría no haber sido el visitante?

Cuando la expansión de ID *no* se utiliza para una petición DELETE: si utiliza un ID que no sea de cookie (cualquier ID distinto de ECID o de la cookie de Analytics) para identificar las visitas que deben eliminarse y ese ID tiene una etiqueta ID-DEVICE, entonces los recuentos de visitantes únicos de los informes sí cambian. Esto se debe a que solo algunas instancias de los ID de cookie se convertirán en anónimas, mientras que otras quedarán sin cambios. Si no va a especificar la expansión de ID, es recomendable que utilice un ID de cookie para las solicitudes o que utilice ID que incluyan una etiqueta ID-PERSON.

Cuando Adobe realiza la expansión de ID, puede requerir un análisis de datos completo adicional. Esto aumenta el tiempo que tarda Adobe en completar la solicitud, agregando a menudo una semana al tiempo de procesamiento.

## Otros indicadores de solicitud de privacidad de datos

Además del indicador “expandIDs”, Analytics admite otros dos que se pueden incluir como parte de una solicitud de privacidad de datos. Estas advertencias (y sus valores predeterminados) son las siguientes:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

En el futuro, el `analyticsDeleteMethod` podría admitir un valor de “purgar” además del valor predeterminado “anonimizar”. Cuando se admita, hará que se elimine toda la visita, en lugar de actualizar los valores de los campos de visita que tengan etiquetas DEL.

Además del valor predeterminado, el campo `priority` también admite un valor “bajo”. Debería especificar este valor en las solicitudes que no sean producto de una solicitud del interesado y que, por lo tanto, no se deban completar en un período de tiempo por imperativo legal.

## Usos de la API de Privacy Service

>[!IMPORTANT]
>
>Adobe no permite el uso de la [API de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es) por motivos que no sean solicitudes válidas iniciadas por el interesado. La API de Privacy Service no es una herramienta adecuada para la limpieza o reparación de datos. Cualquier uso incorrecto de la API de Privacy Service para solicitudes no iniciadas por el interesado tendrá consecuencias no deseadas. La API de Privacy Service se proporciona a los clientes de Adobe para ayudarles a completar las solicitudes de privacidad de datos, que suelen ser urgentes. Adobe no admite el uso de esta API para otros fines, y ello puede afectar a la capacidad de Adobe para proporcionar el retorno puntual de solicitudes de privacidad de datos iniciadas por los usuarios y de alta prioridad a otros clientes de Adobe. Le rogamos que no use la API de Privacy Service para otros fines, por ejemplo, higiene de los datos o borrar datos que se hayan enviado por error a grupos de visitantes grandes.

También debe tener en cuenta que cualquier información de estado de un visitante del cual se elimine una visita (actualizada o anonimizada) se restablecerá como resultado de una solicitud de eliminación de privacidad de datos. La próxima vez que el visitante vuelva a su sitio web, lo hará como visitante nuevo. Toda atribución de eVar partirá de cero, al igual que los detalles relativos al número de visitas, los referentes, la primera página visitada, etc. El resultado no es deseable en los casos en los que quiera borrar campos de datos, lo que a su vez representa uno de los motivos por los que la API de Privacy Service no es apropiada para este uso.

Póngase en contacto con el equipo de cuenta de Adobe para coordinarse con nuestro equipo de consultoría de arquitectos de ingeniería y revisar y proporcionar un nivel de esfuerzo para eliminar cualquier PII o resolver problemas de datos.
