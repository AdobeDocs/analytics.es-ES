---
description: 'Los ID que envíe no siempre abarcan todos los datos coincidentes que Analytics puede asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de privacidad de datos. Puede solicitar esta opción con un parámetro opcional a cada solicitud de privacidad de datos que envíe junto a la solicitud de JSON '
title: Expansión de ID
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Expansión de ID

Los ID que envíe no siempre abarcan todos los datos coincidentes que Analytics puede asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de privacidad de datos. Puede solicitar esta opción con un parámetro opcional a cada solicitud de privacidad de datos que envíe junto a la solicitud de JSON:

```
"expandIds": true
```

Consulte la [Ejemplos de solicitudes de JSON](/help/admin/c-data-governance/gdpr-submit-access-delete.md#sample-json-request) para ver un ejemplo de cómo incluir esta opción con la solicitud. Para obtener más información, consulte la [Documentación de la API del servicio de privacidad](https://www.adobe.io/apis/experienceplatform/gdpr.html).

<table id="table_A10CA8DC8C1643CF84A4DF30A6740D51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo </th> 
   <th colname="col2" class="entry"> Consideraciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Expansión de ID de cookie </p> </td> 
   <td colname="col2"> <p>Muchos clientes de Analytics utilizaban originalmente la <a href="https://marketing.adobe.com/resources/help/es_ES/whitepapers/cookies/cookies_analytics.html">cookie de Analytics</a> (obsoleta), pero ahora usan el <a href="https://marketing.adobe.com/resources/help/es_ES/mcvid/">servicio de identidad (ECID)</a>, antes conocido como servicio de Marketing Cloud ID (MCID). Para los visitantes de su sitio web que visitaron por primera vez después de la transición, sólo existe el ECID. Sin embargo, para aquellos que visitaron por primera vez cuando solo estaba disponible la cookie heredada, pero que desde entonces han visitado: algunos de sus datos tendrán ambas cookies, pero los datos antiguos solo tendrán la cookie de Analytics y, en casos excepcionales, los datos más recientes solo pueden tener un ECID. </p> <p>Debe asegurarse de que encuentra todos los datos de un visitante identificado mediante una cookie de Analytics (ID del visitante) o un ECID. Por lo tanto, si actualmente utiliza el ECID y ha utilizado anteriormente la cookie de Analytics, siempre que envíe una solicitud con cualquier tipo de ID, debe incluir ambos ID en la solicitud o especificar la opción expandedIds. Cuando especifique expandIDs, Adobe buscará otros ECID o cookies de Analytics que correspondan a los ID de cookie que facilite. La solicitud se ampliará automáticamente para incluir estos ID de cookies recién identificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expansión de ID personalizado a ID de cookie </p> </td> 
   <td colname="col2"> <p>En los sitios Web de comercio electrónico, es común que un visitante navegue por el sitio, agregue cosas al carro y luego inicio el proceso de cierre de compra antes de ingresar al sitio. Si el ID utilizado para identificar a los usuarios para una solicitud amparada en la privacidad de datos se almacena en una variable personalizada solo cuando el usuario tiene sesión iniciada, la actividad previa al inicio de sesión no se asociará con el ID. Gracias al ID de cookie de Analytics, los clientes pueden optar por asociar la exploración realizada antes del inicio de sesión con la compra efectuadas tras él, dado que el ID de cookie se conserva durante todo el proceso. </p> <p>Supongamos que su implementación almacena un ID de inicio de sesión (ID de CRM, nombre de usuario, número de fidelidad, dirección de correo electrónico, etc., o un hash de cualquiera de estos valores) en una variable personalizada (prop o eVar) o un ID de visitante personalizado, y que después utiliza este ID para una solicitud de acceso amparada en la privacidad de datos. El interesado podría sorprenderse de que no se le devuelva información sobre toda su navegación como parte de una solicitud de acceso, especialmente si le han promocionado artículos vistos, pero aún no adquiridos. </p> <p>Por ello, el tratamiento de la privacidad de datos de Analytics admite la expansión de ID, un proceso por el cual Analytics encuentra todos los ID de cookie que se producen en la misma visita como cualquier ID personalizado y, después, amplía la solicitud para incluir también esos ID. </p> <p>Cuando se especifica expandIDs junto con cualquier área de nombres que no sea un área de nombres de cookie, la solicitud se expandirá para incluir cualquier ID de cookie (ECID o cookie de Analytics), que se encuentre en las visitas que contengan cualquiera de los ID especificados. La expansión de ID de cookie, como se describe más arriba, se realizará en cualquier ID de cookie que se encuentre recientemente. </p> <p>Cuando se utiliza la opción expandIDs para una solicitud de acceso y el ID especificado tiene una etiqueta de ID-PERSON, se devolverán dos conjuntos de archivos. El primer conjunto (el conjunto de personas) contendrá datos solo de las visitas donde se encontró el ID especificado. El segundo conjunto (el conjunto de dispositivos) contendrá datos solo de las visitas de los ID expandidos, donde el ID especificado no estaba presente. </p> </td> 
  </tr> 
 </tbody> 
</table>

Durante los primeros meses tras la entrada en vigor de la privacidad de datos, la inmensa mayoría de las solicitudes amparadas en la privacidad de datos de Analytics no incluían la expansión de ID, pero de usted depende determinar el valor apropiado para su organización. Debe consultar con su equipo legal si es necesario ampliar el ID para sus datos con los ID que utiliza y los datos recopilados en Adobe Analytics. Una consideración primordial debe ser que, en un dispositivo compartido, desde el que varios usuarios han visitado el sitio, la expansión de ID incluirá datos de visitas de otros usuarios del dispositivo en datos devueltos por solicitudes de acceso (en el archivo del dispositivo). Aunque haya seguido las prácticas recomendadas en el etiquetado, de modo que no se incluyan datos privados en el archivo del dispositivo, como páginas visitadas, el archivo del dispositivo contendrá la cantidad de páginas visitadas y las horas de cada una de esas visitas. ¿Está bien si comparte esta información con alguien que puede no haber sido el visitante?

Para una solicitud de eliminación, donde no se utiliza la expansión de ID, si utiliza un ID que no sea de cookie (cualquier ID que no sea la cookie ECID o Analytics) para identificar las visitas que deben eliminarse y ese ID tiene una etiqueta ID-DEVICE, los recuentos de visitantes únicos en los informes cambiarán, ya que solo algunas instancias de los ID de cookies serán anónimas, mientras que otras permanecerán sin cambios. Si no especifica la expansión de ID, se recomienda usar un ID de cookie para las solicitudes o ID con una etiqueta ID-PERSON.

Cuando Adobe realiza la expansión de ID, puede requerir un análisis de datos completo adicional, lo que aumentará el tiempo que Adobe tarda en completar la solicitud, agregando con frecuencia una semana al tiempo de procesamiento.

## Otros indicadores de solicitud de privacidad de datos

Además del indicador “expandIDs”, Analytics admite otros dos que se pueden incluir como parte de una solicitud de privacidad de datos. Estas advertencias (y sus valores predeterminados) son las siguientes:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

En el futuro, “analyticsDeleteMethod” podría admitir un valor “purge”, además del valor predeterminado “anonymize”. Cuando se admita, hará que se elimine toda la visita, en lugar de actualizar los valores de los campos de visita que tengan etiquetas DEL.

Además del valor predeterminado, el campo de prioridad también admite un valor “low”. Debería especificar este valor en las solicitudes que no sean producto de una solicitud del interesado y que, por lo tanto, no se deban completar en un plazo de 30 días por imperativo legal. Tenga en cuenta que Adobe desaconseja el uso de la API del servicio de privacidad para otros fines que no sean solicitudes iniciadas por los interesados. La API del servicio de privacidad no es una herramienta adecuada para borrar ni reparar datos. Asimismo, si se usa para tales fines, tendrá consecuencias no deseadas.

>[!NOTE]La [API del servicio de privacidad](https://www.adobe.io/apis/experienceplatform/gdpr.html) sirve para ayudarle a realizar las solicitudes de privacidad de datos, que suelen ser urgentes. Adobe no admite el uso de esta API para otros fines, y ello puede afectar a la capacidad de Adobe para proporcionar el retorno puntual de solicitudes de privacidad de datos iniciadas por los usuarios y de alta prioridad a otros clientes de Adobe. Le rogamos que no use la API del servicio de privacidad para otros fines, por ejemplo, para borrar datos que se hayan enviado por error a grupos de visitantes grandes.

También debe tener en cuenta que cualquier información de estado de un visitante del cual se elimine una visita (actualizada o anonimizada) se restablecerá como resultado de una solicitud de eliminación de privacidad de datos. La próxima vez que el visitante regrese a su sitio web, será un nuevo visitante. Toda atribución de eVar partirá de cero, al igual que los detalles relativos al número de visitas, los referentes, la primera página visitada, etc. Este efecto colateral no es deseable en los casos en los que quiera borrar campos de datos, lo que a su vez representa uno de los motivos por los que la API del servicio de privacidad no es apropiada para este uso.

Póngase en contacto con su administrador de cuentas para que se coordine con nuestro equipo de consultoría encargado de la arquitectura de ingeniería. De este modo, podremos llevar a cabo una revisión más exhaustiva y establecer el nivel de actuación a la hora de subsanar cualquier problema relacionado con los datos o con PII.

