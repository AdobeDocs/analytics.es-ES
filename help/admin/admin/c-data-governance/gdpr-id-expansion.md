---
description: Los ID que envíe no siempre abarcan todos los datos de visitas que Analytics puede asociar al sujeto de datos. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de privacidad de datos. Puede solicitar esta opción con un parámetro opcional a cada solicitud de privacidad de datos que envíe junto a la solicitud de JSON
title: Expansión de ID
feature: Data Governance
exl-id: 312a249f-e0e7-44da-bb3d-b19f1bb4c706
source-git-commit: c8e3d9bd40a427387da746c084188b5d13f45bcd
workflow-type: tm+mt
source-wordcount: '1351'
ht-degree: 33%

---

# Expansión de ID

Los ID que envíe no siempre abarcan todos los datos de visitas que Analytics puede asociar al sujeto de datos. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de privacidad de datos. Puede solicitar esta opción con un parámetro opcional a cada solicitud de privacidad de datos que envíe junto a la solicitud de JSON:

```
"expandIds": true
```

Para obtener más información, consulte la [Documentación de la API del servicio de privacidad](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es).


| Tipo | Consideraciones |
| --- | --- |
| Expansión de ID de cookie | Muchos clientes de Analytics utilizaban originalmente (heredado) [Cookie de Analytics](https://experienceleague.adobe.com/docs/core-services/interface/administration/ec-cookies/cookies-privacy.html?lang=en), pero ahora están usando la variable [Servicio de identidad de Experience Cloud (ECID)](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es). Para los visitantes de su sitio web que efectuaran la visita después de la transición, solo existe el ECID. Sin embargo, para aquellos que realizaran su visita por primera vez cuando solo estaba disponible la cookie heredada, pero hayan hecho una visita desde entonces: algunos de sus datos tienen ambas cookies. Sin embargo, los datos más antiguos solo tienen la cookie de Analytics y, en casos excepcionales, es posible que los datos más recientes solo tengan un ECID.<p>Asegúrese de encontrar todos los datos de un visitante identificado mediante una cookie de Analytics (ID de visitante) o ECID. Si actualmente utiliza el ECID y antes usaba la cookie de Analytics, siempre que envíe una solicitud utilizando cualquiera de los tipos de ID, debe incluir ambos ID en la solicitud o especificar la variable `expandIds` . Cuando especifique `expandIds`, el Adobe comprueba si hay otros ECID o cookies de Analytics que correspondan a los ID de cookie que proporcione. La solicitud se expande automáticamente para incluir estos ID de cookie recién identificados. |
| Expansión de ID personalizado a ID de cookie | En sitios web de comercio electrónico, no es inusual que un visitante explore el sitio, añada artículos a su carrito y, después, inicie el proceso de pago antes de iniciar sesión en el sitio. Si el ID utilizado para identificar a los usuarios para una solicitud de privacidad de datos se almacena en una variable personalizada solo cuando el usuario ha iniciado sesión, esta actividad previa al inicio de sesión no se asocia al ID. Gracias al ID de cookie de Analytics, los clientes pueden optar por asociar la exploración realizada antes del inicio de sesión con la compra efectuadas tras él, dado que el ID de cookie se conserva durante todo el proceso.<p>Supongamos que su implementación almacena un ID de inicio de sesión (ID de CRM, nombre de usuario, número de fidelidad, dirección de correo electrónico, etc., o un hash de cualquiera de estos valores) en una variable personalizada (prop o eVar) o un ID de visitante personalizado, y que después utiliza este ID para una solicitud de acceso amparada en la privacidad de datos. El sujeto de datos puede sorprenderse de que no se devuelva información sobre toda su navegación como parte de una solicitud de acceso, especialmente si ha promocionado artículos que se vieron pero aún no se compraron. Por ello, el tratamiento de la privacidad de datos de Analytics admite la expansión de ID, un proceso por el cual Analytics encuentra todos los ID de cookie que se producen en la misma visita como cualquier ID personalizado y, después, amplía la solicitud para incluir también esos ID.<p>When `expandIDs` se especifica junto con cualquier espacio de nombres que no sea un espacio de nombres de cookie, la solicitud se expande para incluir cualquier ID de cookie (ECID o cookie de Analytics), que se encuentre en visitas que contengan cualquiera de los ID especificados. A continuación, la expansión del ID de cookie, tal como se describe más arriba, se realiza en cualquier ID de cookie que se haya encontrado recientemente.<p>Cuando la variable `expandIDs` se utiliza para una solicitud de acceso y el ID especificado tiene una etiqueta de ID-PERSON, se devolverán dos conjuntos de archivos. El primer conjunto (el conjunto de personas) contendrá datos solo de las visitas donde se encontró el ID especificado. El segundo conjunto (el conjunto de dispositivos) solo contendrá datos de las visitas de los ID expandidos, en los que el ID especificado no estaba presente. |

{style=&quot;table-layout:auto&quot;}

## Cuándo utilizar la expansión de ID

Durante los primeros meses después de la entrada en vigor de la privacidad de datos, la gran mayoría de las solicitudes de privacidad de datos de Analytics no solicitaron la expansión de ID. Sin embargo, la determinación del valor apropiado para su organización depende de usted. Debe consultar con su equipo jurídico si es necesario ampliar los ID de sus datos con los ID que utiliza y los datos que recopila en Adobe Analytics.

Una consideración primordial podría ser: En un dispositivo compartido desde el que varios usuarios han visitado el sitio, la expansión de ID incluye datos de visitas del dispositivo de otros usuarios, en datos devueltos por solicitudes de acceso (en el archivo del dispositivo). Aunque haya seguido las prácticas recomendadas de etiquetado (por ejemplo, no se incluyen datos privados en el archivo del dispositivo, como las páginas visitadas), el archivo del dispositivo contiene el número de páginas visitadas y la hora de cada una de esas visitas. Puede que desee preguntarse a sí mismo: ¿Le parece bien compartir esta información con alguien que podría no haber sido el visitante?

Cuando la expansión de ID es *not* se utiliza para una solicitud de eliminación: si utiliza un ID que no sea de cookie (cualquier ID distinto de ECID o de la cookie de Analytics) para identificar las visitas que deben eliminarse y ese ID tiene una etiqueta ID-DEVICE, los recuentos de visitantes únicos de los informes sí cambian. Esto se debe a que solo algunas instancias de los ID de cookie se convertirán en anónimas, mientras que otras se dejarán sin cambios. Si no especifica la expansión de ID, le recomendamos que utilice un ID de cookie para las solicitudes o que utilice ID con una etiqueta ID-PERSON.

Cuando el Adobe realiza la expansión de ID, puede requerir un análisis de datos completo adicional. Esto aumenta el tiempo que tardan los Adobes en completar la solicitud, agregando a menudo una semana al tiempo de procesamiento.

## Otros indicadores de solicitud de privacidad de datos

Además del indicador “expandIDs”, Analytics admite otros dos que se pueden incluir como parte de una solicitud de privacidad de datos. Estas advertencias (y sus valores predeterminados) son las siguientes:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

En el futuro, la variable `analyticsDeleteMethod` puede admitir un valor de &quot;purge&quot; además del valor predeterminado de &quot;anonymize&quot;. Cuando se admita, hará que se elimine toda la visita, en lugar de actualizar los valores de los campos de visita que tengan etiquetas DEL.

Además del valor predeterminado, la variable `priority` también admite el valor &quot;low&quot;. Debe especificar este valor para las solicitudes que no son resultado de una solicitud del sujeto de datos y que, por lo tanto, no tienen un requisito legal que completar en un intervalo de tiempo determinado.

## Usos de la API del Privacy Service

>[!IMPORTANT]
>
>El Adobe no permite el uso del [API de Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=es) por otros motivos que no sean solicitudes válidas iniciadas por el sujeto de datos. La API de Privacy Service no es una herramienta adecuada para la limpieza o reparación de datos. Cualquier uso incorrecto de la API de Privacy Service para solicitudes no iniciadas por el sujeto de datos tendrá consecuencias no deseadas. La API de Privacy Service se proporciona a los clientes de Adobe para ayudarle a realizar las solicitudes de privacidad de datos, que suelen ser urgentes. Adobe no admite el uso de esta API para otros fines, y ello puede afectar a la capacidad de Adobe para proporcionar el retorno puntual de solicitudes de privacidad de datos iniciadas por los usuarios y de alta prioridad a otros clientes de Adobe. Le rogamos que no use la API de Privacy Service para otros fines, como la higiene de los datos o la eliminación de datos que se hayan enviado por error a grupos de visitantes grandes.

También debe tener en cuenta que cualquier información de estado de un visitante del cual se elimine una visita (actualizada o anonimizada) se restablecerá como resultado de una solicitud de eliminación de privacidad de datos. La próxima vez que el visitante vuelva a su sitio web, lo hará como visitante nuevo. Toda atribución de eVar partirá de cero, al igual que los detalles relativos al número de visitas, los referentes, la primera página visitada, etc. El resultado no es deseable en los casos en los que quiera borrar campos de datos, lo que a su vez representa uno de los motivos por los que la API de Privacy Service no es apropiada para este uso.

Póngase en contacto con su administrador de cuentas para que se coordine con nuestro equipo de consultoría encargado de la arquitectura de ingeniería. De este modo, podremos llevar a cabo una revisión más exhaustiva y establecer el nivel de actuación a la hora de eliminar cualquier PII o resolver problemas con los datos.
