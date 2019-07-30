---
description: 'Los ID que envíe no siempre abarcan todos los datos coincidentes que Analytics puede asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de RGPD. Puede solicitar esta opción con un parámetro opcional a cada solicitud de RGPD que envíe junto a la solicitud de JSON '
seo-description: 'Los ID que envíe no siempre abarcan todos los datos coincidentes que Analytics puede asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de RGPD. Puede solicitar esta opción con un parámetro opcional a cada solicitud de RGPD que envíe junto a la solicitud de JSON '
seo-title: Expansión de ID
title: Expansión de ID
uuid: 2672 d 17 d-c 957-4 e 08-8 dd 9-16 d 54 bf 2 be 18
translation-type: tm+mt
source-git-commit: aa098cbd84d773a5cc44e2771fef50d04b01a3d3

---


# Expansión de ID

Los ID que envíe no siempre abarcan todos los datos coincidentes que Analytics puede asociar al interesado. Analytics puede crear un conjunto ampliado de ID para incluir estos datos asociados en las solicitudes de RGPD. Puede solicitar esta opción con un parámetro opcional a cada solicitud de RGPD que envíe junto a la solicitud de JSON:

```
"expandIds": true
```

Consulte la [Ejemplos de solicitudes de JSON](../../admin/c-data-governance/gdpr-submit-access-delete.md#section_DB9DE6492FE740918F91D413E7BAB88F) para ver un ejemplo de cómo incluir esta opción con la solicitud. Para obtener más información, consulte la [Documentación de la API RGPD](https://www.adobe.io/apis/cloudplatform/gdpr/docs/alldocs.html#!api-specification/markdown/narrative/gdpr/use-cases/gdpr-api-overview.md).

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
   <td colname="col2"> <p>Many Analytics customers originally used the (Legacy) <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external"> Analytics Cookie </a>, but are now using the <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> Identity Service (ECID) </a>, previously known as the Marketing Cloud ID Service (MCID). Para los visitantes de su sitio web que efectuaran la visita después de la transición, solo existe el ECID. Sin embargo, en el caso de aquellos que realizaran su visita por primera vez cuando solo estaba disponible la cookie heredada, pero hayan vuelto a visitar el sitio después: algunos de sus datos tendrán ambas cookies, pero los más antiguos solo tendrán la cookie de Analytics, mientras que, en muy pocos casos, los datos más nuevos podrían presentar únicamente un ECID. </p> <p>Debe asegurarse de que encuentra todos los datos de un visitante identificado mediante una cookie de Analytics (ID del visitante) o un ECID. Por tanto, si en estos momentos utiliza el ECID y antes usaba la cookie de Analytics, siempre que envíe una solicitud utilizando cualquiera de los tipos de ID, deberá incluir ambos ID, o bien especificar la opción expandIDs. Cuando especifique expandIDs, Adobe buscará otros ECID o cookies de Analytics que correspondan a los ID de cookie que facilite. La solicitud se ampliará automáticamente para incluir los ID de cookie recién identificados. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Expansión de ID personalizado a ID de cookie </p> </td> 
   <td colname="col2"> <p>En sitios web de comercio electrónico, no es inusual que un visitante explore el sitio, añada artículos a su carrito y, después, inicie el proceso de pago antes de iniciar sesión en el sitio. Si el ID utilizado para identificar a los usuarios para una solicitud amparada en el RGPD se almacena en una variable personalizada solo cuando el usuario tiene sesión iniciada, la actividad previa al inicio de sesión no se asociará con el ID. Gracias al ID de cookie de Analytics, los clientes pueden optar por asociar la exploración realizada antes del inicio de sesión con la compra efectuadas tras él, dado que el ID de cookie se conserva durante todo el proceso. </p> <p>Supongamos que su implementación almacena un ID de inicio de sesión (ID de CRM, nombre de usuario, número de fidelidad, dirección de correo electrónico, etc., o un hash de cualquiera de estos valores) en una variable personalizada (prop o eVar) o un ID de visitante personalizado, y que después utiliza este ID para una solicitud de acceso amparada en el RGPD. El interesado podría sorprenderse de que no se le devuelva información sobre toda su navegación como parte de una solicitud de acceso, especialmente si le han promocionado artículos vistos, pero aún no adquiridos. </p> <p>Por ello, el tratamiento del RGPD de Analytics admite la expansión de ID, un proceso por el cual Analytics encuentra todos los ID de cookie que se producen en la misma visita como cualquier ID personalizado y, después, amplía la solicitud para incluir también esos ID. </p> <p>Cuando se especifica expandIDs junto con cualquier espacio de nombres que no sea un espacio de nombres de cookie, la solicitud se expandará para incluir cualquier ID de cookie (ECID o cookie de Analytics), que se encuentre en las visitas que contengan cualquiera de los ID especificados. La expansión de ID de cookie, tal como se describe anteriormente, se llevará a cabo en cualquier ID de cookie que se haya encontrado recientemente. </p> <p>Cuando se utiliza la opción expandIDs para una solicitud de acceso y el ID especificado tiene una etiqueta de ID-PERSON, se devolverán dos conjuntos de archivos. El primer conjunto (el conjunto de personas) contendrá datos solo de las visitas donde se encontró el ID especificado. El segundo conjunto (el conjunto de dispositivos) solo contendrá datos de las visitas de los ID expandidos, en los que el ID especificado no estaba presente. </p> </td> 
  </tr> 
 </tbody> 
</table>

Durante los primeros meses tras la entrada en vigor del RGPD, la inmensa mayoría de las solicitudes amparadas en el RGPD de Analytics no incluían la expansión de ID, pero de usted depende determinar el valor apropiado para su organización. Debe consultar con su equipo legal si la expansión de ID es necesaria para sus datos con los ID que utiliza y los datos que recopila dentro de Adobe Analytics. Una consideración esencial debe ser que, en un dispositivo compartido desde el que varios usuarios han visitado su sitio, el uso de la expansión de ID incluirá, en los datos devueltos por las solicitudes de acceso (en el archivo del dispositivo), datos de visitas de otros usuarios del dispositivo. Aunque haya seguido las prácticas recomendadas de etiquetado, como que no se incluyan datos privados en el archivo del dispositivo, como las páginas visitadas, este archivo contendrá el número de páginas visitadas y la hora de cada una de esas visitas. ¿Le parece bien compartir esta información con alguien que podría no ser el visitante?

Para una solicitud de eliminación, donde no se utiliza la expansión de ID, si utiliza un ID sin cookies (cualquier ID distinto de ECID o de la cookie de Analytics) para identificar las visitas que deben eliminarse y el ID tiene la etiqueta ID-DEVICE, el recuento de visitantes únicos en los informes cambiará, ya que solo se harán anónimas algunas instancias de los ID de cookie, mientras que otras se dejarán sin cambiar. Si no va a especificar la expansión de ID, es recomendable que utilice un ID de cookie para las solicitudes o que utilice ID que incluyan una etiqueta ID-PERSON.

Cuando Adobe realiza la expansión de ID, puede requerir un análisis de datos completo adicional, lo que aumentará (a menudo en una semana) el tiempo que Adobe tarda en completar la solicitud.

## Otros indicadores de solicitud RDPD

Además de la advertencia “expandIDs”, Analytics admite otras dos que se pueden incluir como parte de una solicitud de RGPD. Estas advertencias (y sus valores predeterminados) son las siguientes:

```
"analyticsDeleteMethod": “anonymize”
“priority”: “normal”
```

En el futuro, “analyticsDeleteMethod” podría admitir un valor “purge”, además del valor predeterminado “anonymize”. Cuando se admita, hará que se elimine toda la visita, en lugar de actualizar los valores de los campos de visita que tengan etiquetas DEL.

Además del valor predeterminado, el campo de prioridad también admite un valor “low”. Debería especificar este valor en las solicitudes que no sean producto de una solicitud del interesado y que, por lo tanto, no se deban completar en un plazo de 30 días por imperativo legal. Tenga en cuenta que Adobe desaconseja el uso de la API RGPD para otros fines que no sean solicitudes iniciadas por los interesados. La API RGPD no es una herramienta adecuada para borrar ni reparar datos. Asimismo, si se usa para tales fines, tendrá consecuencias no deseadas.

>[!NOTE]
>La API GDPR se ha proporcionado para ayudarle a realizar solicitudes GDPR, que dependen del tiempo. Utilizar esta API para &gt; otros propósitos no es compatible con Adobe y puede afectar a la capacidad de Adobe para proporcionar un cambio de prioridad de alta &gt; prioridad, solicitudes GDPR iniciadas por el usuario para otros clientes de Adobe. Le pedimos que no utilice la API de RGPD para &gt; otros propósitos como borrar datos que se enviaron accidentalmente a través de grandes grupos de visitantes.
>
>También debe tener en cuenta que cualquier visitante que tenga una visita eliminada (actualizada o anónima) como resultado de una solicitud GDPR &gt; de eliminación tendrá su información de estado restablecida. La próxima vez que el visitante regrese a su sitio web, será un visitante nuevo. Toda la atribución de evar comenzará nuevamente, al igual que la información como números de visitas, referentes, primera página visitada, etc. Este efecto lateral no es deseable para situaciones en las que desee borrar &gt; campos de datos y resalta un motivo por el cual la API GDPR no es apropiada para este uso.
>
>Comuníquese con el administrador de cuentas (CSM) para coordinar con nuestro equipo de asesores arquitecto de ingeniería a &gt; examinar y proporcionar un nivel de esfuerzo para eliminar cualquier PII o problema de datos.

