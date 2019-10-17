---
description: Los ID que envíe no siempre abarcan todos los datos coincidentes que Analytics puede asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de privacidad de datos. Puede solicitar esta opción con un parámetro opcional para cada solicitud de privacidad de datos que envíe, agregado a la solicitud JSON 
seo-description: Los ID que envíe no siempre abarcan todos los datos coincidentes que Analytics puede asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de privacidad de datos. Puede solicitar esta opción con un parámetro opcional para cada solicitud de privacidad de datos que envíe, agregado a la solicitud JSON 
seo-title: Expansión de ID
title: Expansión de ID
uuid: 2672d17d-c957-4e08-8dd9-16d54bf2be18
translation-type: tm+mt
source-git-commit: 3be4e96df12d5e53bf77b1960afc229a1ac6c046

---

# Expansión de ID

Los ID que envíe no siempre abarcan todos los datos coincidentes que Analytics puede asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de privacidad de datos. Puede solicitar esta opción con un parámetro opcional para cada solicitud de privacidad de datos que envíe, que se agrega a la solicitud JSON:

```
"expandIds": true
```

Consulte la [Ejemplos de solicitudes de JSON](/help/admin/c-data-governance/gdpr-submit-access-delete.md#sample-json-request) para ver un ejemplo de cómo incluir esta opción con la solicitud. For more details, refer to the [Privacy Service API documentation](https://www.adobe.io/apis/experienceplatform/gdpr.html).

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
   <td colname="col2"> <p>Muchos clientes de Analytics utilizaban originalmente la <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external">cookie de Analytics</a> (obsoleta), pero ahora usan el <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external">servicio de identidad (ECID)</a>, antes conocido como servicio de Marketing Cloud ID (MCID). Para los visitantes de su sitio web que efectuaran la visita después de la transición, solo existe el ECID. Sin embargo, en el caso de aquellos que realizaran su visita por primera vez cuando solo estaba disponible la cookie heredada, pero hayan vuelto a visitar el sitio después: algunos de sus datos tendrán ambas cookies, pero los más antiguos solo tendrán la cookie de Analytics, mientras que, en muy pocos casos, los datos más nuevos podrían presentar únicamente un ECID. </p> <p>Debe asegurarse de que encuentra todos los datos de un visitante identificado mediante una cookie de Analytics (ID del visitante) o un ECID. Por tanto, si en estos momentos utiliza el ECID y antes usaba la cookie de Analytics, siempre que envíe una solicitud utilizando cualquiera de los tipos de ID, deberá incluir ambos ID, o bien especificar la opción expandIDs. Cuando especifique expandIDs, Adobe buscará otros ECID o cookies de Analytics que correspondan a los ID de cookie que facilite. La solicitud se ampliará automáticamente para incluir los ID de cookie recién identificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expansión de ID personalizado a ID de cookie </p> </td> 
   <td colname="col2"> <p>En sitios web de comercio electrónico, no es inusual que un visitante explore el sitio, añada artículos a su carrito y, después, inicie el proceso de pago antes de iniciar sesión en el sitio. Si el ID utilizado para identificar usuarios para una solicitud de privacidad de datos se almacena en una variable personalizada únicamente cuando el usuario ha iniciado sesión, esta actividad previa al inicio de sesión no se asociará al ID. Gracias al ID de cookie de Analytics, los clientes pueden optar por asociar la exploración realizada antes del inicio de sesión con la compra efectuadas tras él, dado que el ID de cookie se conserva durante todo el proceso. </p> <p>Supongamos que su implementación almacena un ID de inicio de sesión (ID de CRM, nombre de usuario, número de lealtad, dirección de correo electrónico, etc., o un hash de cualquiera de estos valores) en una variable personalizada (prop o eVar) o un ID de visitante personalizado, y luego utiliza este ID para una solicitud de acceso de privacidad de datos. El interesado podría sorprenderse de que no se le devuelva información sobre toda su navegación como parte de una solicitud de acceso, especialmente si le han promocionado artículos vistos, pero aún no adquiridos. </p> <p>Por lo tanto, el procesamiento de la privacidad de datos de Analytics admite la expansión de ID, donde Analytics busca todos los ID de cookies que se producen en la misma visita que cualquier ID personalizado y luego expande la solicitud para incluir también esos ID. </p> <p>Cuando se especifica expandIDs junto con cualquier área de nombres que no sea un área de nombres de cookie, la solicitud se expandirá para incluir cualquier ID de cookie (ECID o cookie de Analytics), que se encuentre en las visitas que contengan cualquiera de los ID especificados. La expansión de ID de cookie, tal como se describe anteriormente, se llevará a cabo en cualquier ID de cookie que se haya encontrado recientemente. </p> <p>Cuando se utiliza la opción expandIDs para una solicitud de acceso y el ID especificado tiene una etiqueta de ID-PERSON, se devolverán dos conjuntos de archivos. El primer conjunto (el conjunto de personas) contendrá datos solo de las visitas donde se encontró el ID especificado. El segundo conjunto (el conjunto de dispositivos) solo contendrá datos de las visitas de los ID expandidos, en los que el ID especificado no estaba presente. </p> </td> 
  </tr> 
 </tbody> 
</table>

Durante los primeros meses después de que la privacidad de datos se activara, la gran mayoría de las solicitudes de privacidad de datos de Analytics no solicitaron la expansión de ID, pero la determinación del valor adecuado para su organización depende de usted. Debe consultar con su equipo legal si la expansión de ID es necesaria para sus datos con los ID que utiliza y los datos que recopila dentro de Adobe Analytics. Una consideración esencial debe ser que, en un dispositivo compartido desde el que varios usuarios han visitado su sitio, el uso de la expansión de ID incluirá, en los datos devueltos por las solicitudes de acceso (en el archivo del dispositivo), datos de visitas de otros usuarios del dispositivo. Aunque haya seguido las prácticas recomendadas de etiquetado, como que no se incluyan datos privados en el archivo del dispositivo, como las páginas visitadas, este archivo contendrá el número de páginas visitadas y la hora de cada una de esas visitas. ¿Le parece bien compartir esta información con alguien que podría no ser el visitante?

Para una solicitud de eliminación, donde no se utiliza la expansión de ID, si utiliza un ID sin cookies (cualquier ID distinto de ECID o de la cookie de Analytics) para identificar las visitas que deben eliminarse y el ID tiene la etiqueta ID-DEVICE, el recuento de visitantes únicos en los informes cambiará, ya que solo se harán anónimas algunas instancias de los ID de cookie, mientras que otras se dejarán sin cambiar. Si no va a especificar la expansión de ID, es recomendable que utilice un ID de cookie para las solicitudes o que utilice ID que incluyan una etiqueta ID-PERSON.

Cuando Adobe realiza la expansión de ID, puede requerir un análisis de datos completo adicional, lo que aumentará (a menudo en una semana) el tiempo que Adobe tarda en completar la solicitud.

## Otros indicadores de solicitud de privacidad de datos

Además del indicador "expandedIDs", Analytics admite otros dos indicadores que se pueden pasar como parte de una solicitud de privacidad de datos. Estas advertencias (y sus valores predeterminados) son las siguientes:

```
"analyticsDeleteMethod": "anonymize"
"priority": "normal"
```

En el futuro, "analyticsDeleteMethod" puede admitir un valor de "purge" además del valor predeterminado de "anonymize". Cuando se admita, hará que se elimine toda la visita, en lugar de actualizar los valores de los campos de visita que tengan etiquetas DEL.

Además de su valor predeterminado, el campo de prioridad también admite un valor "bajo". Debería especificar este valor en las solicitudes que no sean producto de una solicitud del interesado y que, por lo tanto, no se deban completar en un plazo de 30 días por imperativo legal. Tenga en cuenta que Adobe desaconseja el uso de la API de Privacy Service por motivos distintos de las solicitudes iniciadas por el sujeto de datos. La API de Privacy Service no es una herramienta adecuada para la limpieza o reparación de datos y tendrá consecuencias no deseadas.

[!NOTE]
La API [de](https://www.adobe.io/apis/experienceplatform/gdpr.html) Privacy Service se ha proporcionado para ayudarle a cumplir con las solicitudes de privacidad de datos, que distinguen el tiempo. El uso de esta API para otros fines no es compatible con Adobe y puede afectar a la capacidad de Adobe de proporcionar respuestas oportunas de solicitudes de privacidad de datos iniciadas por el usuario y de alta prioridad para otros clientes de Adobe. Le pedimos que no utilice la API de Privacy Service para otros fines, como eliminar datos enviados accidentalmente entre grandes grupos de visitantes.

También debe tener en cuenta que cualquier visitante que tenga una visita eliminada (actualizada o anónima) como resultado de una solicitud de eliminación de la privacidad de datos tendrá su información de estado restablecida. La próxima vez que el visitante vuelva a su sitio web, lo hará como visitante nuevo. Toda atribución de eVar partirá de cero, al igual que los detalles relativos al número de visitas, los referentes, la primera página visitada, etc. Este efecto secundario no es deseable en situaciones en las que desea borrar campos de datos y resalta un motivo por el que la API de Privacy Service no es adecuada para este uso.

Póngase en contacto con su administrador de cuentas para que se coordine con nuestro equipo de consultoría encargado de la arquitectura de ingeniería. De este modo, podremos llevar a cabo una revisión más exhaustiva y establecer el nivel de actuación a la hora de subsanar cualquier problema relacionado con los datos o con PII.

