---
description: 'null'
seo-description: 'null'
seo-title: Prácticas recomendadas de etiquetado
title: Prácticas recomendadas de etiquetado
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: 21fe6a0ee434e430d77a24d060acd2ffce08e219

---


# Prácticas recomendadas de etiquetado

>[!NOTE]
>
>Recuerde que el etiquetado debe revisarse cada vez que se cree un nuevo grupo de informes o cuando se habilite una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas.

## ID directamente e indirectamente identificables {#section_030799AA1397433FBA61A2BC60A7A750}

Para poder averiguar qué etiquetas se deben aplicar a qué variables o campos, primero es necesario comprender los ID que se están capturando en los datos de Analytics y decidir qué se utilizará para las solicitudes de privacidad de datos. La privacidad de datos amplía el alcance de lo que puede considerarse un ID. Los ID se dividen en dos clases amplias: directamente identificables (etiqueta de identidad: I1) e indirectamente identificables (etiqueta de identidad: I2).

* **Un ID directamente identificable (I1)** especifica el nombre de la persona o proporciona un método directo de ponerse en contacto con ella. Como ejemplo podríamos mencionar el nombre de alguien (incluso uno común, como Juan Pérez, que podrían compartir cientos de personas), cualquiera de sus direcciones de correo electrónico o números de teléfono, etc. Una dirección de correo sin nombre podría considerarse como directamente identificable, aunque solo podría identificar un hogar o una empresa en lugar de una persona específica dentro de ese hogar o empresa.
* **Un ID indirectamente identificable (I2)** no permite que se determine de qué persona se trata por sí solo, pero podría combinarse con otra información (que podría tener o no en su poder) para identificar a alguien. Entre los ejemplos se incluyen un número de fidelidad de cliente o un ID empleado por el sistema de CRM de una empresa que es único para cada uno de sus clientes. En Privacidad de datos, los ID anónimos almacenados en las cookies de seguimiento utilizadas por Analytics pueden considerarse como identificadores indirectos, aunque solo puedan identificar un dispositivo en lugar de un individuo; en un dispositivo compartido, estas cookies no pueden distinguir entre distintos usuarios del sistema. Por ejemplo, aunque la cookie no se puede utilizar para encontrar un equipo que la contenga, si alguien tiene acceso al equipo y la localiza, entonces puede asociar los datos de la cookie de Analytics nuevamente al equipo.

   Una dirección IP también se considera indirectamente identificable, porque en cualquier momento puntual solo se puede asignar a un único dispositivo. Sin embargo, los ISP pueden cambiar las direcciones IP de la mayoría de los usuarios con regularidad (y lo hacen a menudo), de modo que a lo largo de cierto tiempo cualquiera de sus usuarios puede haber usado una dirección IP determinada. Tampoco es inusual que muchos clientes de un ISP o varios empleados de una empresa en la misma intranet compartan la misma dirección IP externa. Because of this, Adobe will not support using an IP address as the ID for a [Data Privacy request.](../../admin/c-data-governance/gdpr-submit-access-delete.md#concept_0941C076F76641FF8BF865C7C1CB916B) Sin embargo, cuando se emplee un ID que aceptemos como parte de una solicitud de eliminación, también borraremos las direcciones IP ligadas a dicho ID. Debe decidir si existen otros ID que recopile que puedan pertenecer a esta categoría, de I1 o I2, pero que no sean adecuados para utilizarse como ID distintivo para las solicitudes de privacidad de datos.

Incluso si su empresa recopila muchos ID diferentes dentro de sus datos de Analytics, puede optar por utilizar solo un subconjunto de estos ID para las solicitudes de privacidad de datos. Estos son algunos de los motivos para tomar esa decisión:

* Dentro de sus propios sistemas, puede asignar uno de los ID (por ejemplo, la dirección de correo electrónico) a un ID distinto (como el ID de CRM). A continuación, para mantener la coherencia, decide utilizar únicamente el ID de CRM para las solicitudes de privacidad de datos en el procesamiento de privacidad de datos.
* Carece de un método de validar que alguien sea realmente la persona asociada a ese ID. Por ejemplo, puede resultar extremadamente difícil validar que solo una persona ha usado en todo momento una dirección IP y que quien presenta la solicitud es realmente esa persona.
* Algunos ID pueden corresponder a varias personas y puede no querer arriesgarse a devolver información sobre una persona a otra distinta con ese mismo ID. Por ejemplo, aunque pueda verificar que el nombre de una persona es Juan Pérez, es posible que no desee devolver todos los datos sobre todos los usuarios llamados Juan Pérez de su sistema.
* Otro ejemplo es un ID de dispositivo, como el ID de cookie de Analytics. Si el ID se origina en una aplicación de un teléfono móvil, puede decidir que todas las interacciones que utilicen ese ID deban estar disponibles para el propietario del teléfono móvil. No obstante, si se produce en un dispositivo compartido, como un ordenador doméstico o uno de una biblioteca o un cibercafé, puede determinar que no le es posible distinguir entre los usuarios del dispositivo en cuestión y que existe demasiado riesgo de devolver datos de un usuario distinto como para permitir el uso de este tipo de ID.

## Prácticas recomendadas para los ID admitidos por Analytics {#section_B6481505FF1949498D4B4B35B780D050}

Utilice esta tabla para determinar los tipos de ID que utilizará al enviar solicitudes de privacidad de datos a Analytics. Una vez que conozca esta información, le resultará más fácil determinar qué otras etiquetas debería utilizar para sus variables.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID </th> 
   <th colname="col2" class="entry"> Recomendaciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de cookie </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html" format="html" scope="external">Cookie de Analytics (heredada)</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/en_US/mcvid/" format="https" scope="external"> cookie del servicio de identidad </a> (ECID), anteriormente conocida como Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Estas cookies identifican un dispositivo o, más concretamente, un navegador para el usuario de un dispositivo. En el caso de un dispositivo compartido en el que se utilicen unas credenciales de inicio de sesión comunes, este ID podría aplicarse a todos los usuarios del dispositivo. Adobe has created some <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm" format="html" scope="external"> unified JavaScript </a> that you can place on your website to collect these cookies if you want to allow them to be used for Data Privacy requests. </p> <p>Los usuarios del SDK para móviles de Adobe Analytics también tienen un Experience Cloud ID (ECID). Hay llamadas de API dentro del SDK para leer este ID, de modo que puede mejorar la aplicación para recopilarla en una solicitud de privacidad de datos. </p> <p>Muchas empresas consideran que los ID de cookies de navegadores son ID de dispositivos compartidos. Como resultado, en consulta con sus equipos legales, pueden optar por no admitir su uso como ID aceptables para las solicitudes de privacidad de datos, o pueden elegir devolver sólo una cantidad muy limitada de datos cuando estos ID se utilizan o sólo pueden aceptarlos para solicitudes de eliminación. </p> <p>Estas cookies tienen una etiqueta ID-DEVICE que no se puede cambiar (así como etiquetas I2 y DEL-DEVICE). La configuración predeterminada de Adobe Analytics solo devolverá información genérica sobre el dispositivo, como su tipo, el sistema operativo, el navegador, etc., además de la hora y las fechas en las que se visitara su sitio web usando estos ID. Sin embargo, si decide admitir estos ID para solicitudes de privacidad de datos, como se describe a continuación, puede agregar o eliminar etiquetas ACC-ALL para configurar el conjunto exacto de campos que desea que se devuelvan para una solicitud de acceso a privacidad de datos. </p> <p>En especial si el grupo de informes corresponde a una aplicación móvil, y esta requiere credenciales de inicio de sesión, puede decidir que el Experience Cloud ID del dispositivo corresponde a un usuario específico y, por lo tanto, deseará etiquetar más de esos campos con la etiqueta ACC-ALL, incluidos los nombres de las páginas visitadas, los productos vistos, etc. </p> <p>Nota:  Si especifica la opción "expandedIds" en la solicitud de privacidad de datos, las solicitudes siempre incluirán los ID de cookies, además de cualquier otro ID que especifique. Consulte <a href="../../admin/c-data-governance/gdpr-analytics-ids.md#section_D55C0722BC834118BE6F958C30AD5913" format="dita" scope="local">Expansión de ID</a> para obtener más información. En estos casos, las visitas que solo tienen un ID de cookie, pero no otro ID, solo devolverán los datos etiquetados ACC-ALL como parte de la solicitud de acceso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID en variables personalizadas </p> </td> 
   <td colname="col2"> <p>Algunos clientes colocan ID en <a href="https://marketing.adobe.com/resources/help/en_US/sc/implement/props_eVars.html" format="html" scope="external">variables de tráfico personalizadas (props) o variables de conversión personalizadas (eVars) </a>. Aunque que el más común es un ID de CRM, otros incluyen direcciones de correo electrónico, nombres de inicio de sesión del usuario, números de fidelidad del cliente o hash de estos valores. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Si desea utilizar uno de estos ID para solicitudes de privacidad de datos, debe asignar al campo que lo contiene una etiqueta ID-PERSON. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Mucho menos habitual). Si un ID de una de estas variables personalizadas solo identifica un dispositivo que podrían compartir varias personas, puede usar en su lugar una etiqueta ID-DEVICE. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Estos campos también precisan las etiquetas I1 o I2, y deben incluir una etiqueta DEL-PERSON o DEL-DEVICE. Normalmente, la opción PERSON/DEVICE de la etiqueta DEL coincidirá con la opción PERSON/DEVICE de la etiqueta de ID. </li> 
    </ul> <p> Es raro que un grupo de informes tenga más de una o dos variables personalizadas que contengan ID que desee utilizar para identificar los sujetos de datos para las solicitudes de privacidad de datos. Puede darse el caso de que tenga diversas variables con etiquetas I1 o I2 asignadas, pero, por lo general, solo una o dos de ellas presentarían también las etiquetas ID-PERSON o ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de visitante personalizado </p> </td> 
   <td colname="col2"> <p>Aunque no se utiliza de forma generalizada, Analytics también admite una implementación en la que se puede proporcionar un ID de visitante personalizado, que, en caso de estar presente, se utiliza en lugar de la cookie de seguimiento de Analytics heredada. Este campo tiene las etiquetas I2, ID-PERSON y DEL-PERSON. </p> <p>Muchas implementaciones obtienen este ID a partir de un ID de CRM, por lo que solo está presente mientras alguien tenga la sesión iniciada en su sitio. De este modo, se puede usar el mismo ID de visitante personalizado en distintos dispositivos. Un inconveniente desde el punto de vista técnico es que el seguimiento que se produce antes de que el usuario inicie sesión no se puede ligar a los datos de seguimiento que se recopilen después de iniciar sesión. Si, en su lugar, utiliza el ID del visitante personalizado simplemente para identificar un dispositivo, debe cambiar las etiquetas ID-PERSON y DEL- PERSON a ID-DEVICE y DEL- DEVICE, respectivamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prácticas recomendadas para establecer etiquetas de eliminación {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE]
>
>Las props siempre distinguen entre mayúsculas y minúsculas. Las eVars tampoco distinguen entre mayúsculas y minúsculas, pero pueden configurarse con la ayuda del servicio de atención al cliente de Adobe para que realicen esta distinción. Si tiene una eVar que distingue entre mayúsculas y minúsculas y contiene una ID, es responsabilidad suya utilizar las mayúsculas y minúsculas adecuadas al enviar una solicitud de privacidad de datos para que el caso utilizado en la solicitud coincida con el caso utilizado en las visitas que contengan estos ID.

Las etiquetas de eliminación DEL-DEVICE y DEL-PERSON deben usarse con moderación. Cuando se aplica a una variable que no contiene un ID que se utilizó como parte de la solicitud de privacidad de datos, los recuentos (métricas) en los informes históricos de Analytics casi siempre cambian.

* Se recomienda aplicar una de estas etiquetas a cualquier variable etiquetada como I1, I2 o S1. No se pueden aplicar a ninguna variable que no esté etiquetada como I1, I2 o S1.
* The DEL-labels will result in these variables being [anonymized](../../admin/c-data-governance/gdpr-labels.md#section_F3DEE591671A4B16A8E043F91C137ECB) (the ID will be replaced with a random string prefixed with "Data Privacy-"). El mismo valor convertido en anónimo sustituirá a todas las instancias del valor original en todas las visitas que se hayan identificado con un ID utilizado en la solicitud. Si el valor original de este campo era uno de esos ID, las métricas del informe no cambiarán.
* Por lo general, si un campo presenta la etiqueta ID-DEVICE, también debería asignarle la etiqueta DEL-DEVICE.
* Del mismo modo, si un campo presenta la etiqueta ID-PERSON, también debería asignarle la etiqueta DEL-PERSON.
* Si un campo no tiene una etiqueta de ID, pero contiene información de identificación que desea convertir en anónima, la etiqueta apropiada (DEVICE o PERSON) depende de su implementación. Si solo utiliza ID de cookies para solicitudes de privacidad de datos, debe utilizar DEL-DEVICE.
* Si utiliza ID personalizados en un campo distinto con una etiqueta ID-PERSON, y solo desea que se eliminen estos datos en las filas donde aparezca ese ID, use DEL-PERSON.
* Si está usando la expansión de ID y desea que se eliminen todos los valores de todas las visitas en todos los dispositivos identificados, utilice DEL-DEVICE. Si lo prefiere, puede aplicar tanto las etiquetas DEL-DEVICE como DEL-PERSON en este caso, pero la etiqueta DEL-PERSON es innecesaria, ya que la expansión de ID supone que todas las filas que coinciden con el ID de una persona también coinciden con un ID de dispositivo.
* Si no va a especificar el uso de la expansión de ID, pero va a utilizar una mezcla de ID de dispositivo y persona para distintas solicitudes, le recomendamos especificar tanto la etiqueta DEL-DEVICE como la DEL-PERSON para las variables que se deben eliminar cuando se utiliza cualquiera de los dos tipos de ID.
* Tenga en cuenta que si se especifica una etiqueta DEL-DEVICE o DEL-PERSON en cualquier variable que no se utilice también como ID para dicha solicitud (incluida la expansión de ID), entonces los valores únicos de dicha variable solo se volverán anónimos en las visitas donde se produzca una especificación (o expansión) de ID. Si otras visitas contienen el mismo valor, no se actualizará en esas otras ubicaciones. Esto puede provocar el cambio de los recuentos (métricas).

   Por ejemplo: si tiene tres visitas que contienen el valor "foo" en eVar7, pero sólo una de ellas también contiene un ID en una variable diferente que coincide con una eliminación, entonces "foo" en esa visita se modificará a un valor como "Data Privacy-123456789", mientras que permanecerá sin cambios en las otras dos visitas. Un informe que incluye el número de valores únicos para eVar7 ahora mostrará un valor único más que antes. Un informe que incluye los valores principales para los eVar puede incluir “foo” con solo dos instancias (en lugar de las tres anteriores), y el nuevo valor aparecerá también como instancia única.

## Prácticas recomendadas para establecer etiquetas de acceso {#section_AC7E216F81C141FCA6A62F8836E06EE7}

Aunque muy pocos campos tendrán alguna de las otras etiquetas, será habitual que un gran número de campos presenten etiquetas ACC. Las etiquetas de acceso correspondientes dependerán de los ID que utilice para las solicitudes de privacidad de datos.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Si utiliza... </th> 
   <th colname="col2" class="entry"> ...aplique estas recomendaciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Solo ID de dispositivo </p> </td> 
   <td colname="col2"> <p>Si los únicos ID que usa son ID de cookie o los que tienen una etiqueta ID-DEVICE, solo debe utilizar la etiqueta ACC-ALL. </p> <p>Obtendrá un par de archivos para cada solicitud de acceso, uno que contiene una fila por cada visita coincidente con todos los campos ACC-ALL especificados y otro con un resumen de estos datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de persona sin expansión de ID </p> </td> 
   <td colname="col2"> <p>Si solo usa ID personalizados que tengan la etiqueta ID-PERSON y no va a efectuar la expansión de ID, debe emplear etiquetas ACC-PERSON. Sin embargo, no hace falta que cambie las etiquetas ACC-ALL predeterminadas; estos campos se incluirán de forma automática en la solicitud de acceso. </p> <p>Obtendrá un par de archivos para cada solicitud de acceso, uno que contiene una fila por cada visita coincidente con todos los campos ACC-DEVICE y ACC-PERSON especificados y otro con un resumen de estos datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID combinados o expansión de ID </p> </td> 
   <td colname="col2"> <p>Si incluye ID de dispositivo y de persona en las solicitudes de privacidad de datos o si utiliza ID personalizados (ID de visitante personalizado o ID en una propiedad o eVar), deberá prestar atención a las etiquetas de ACC que utilice. Cada solicitud de acceso devolverá dos pares de archivos de datos, un par que contiene datos de las visitas que incluyeron un ID de persona coincidente y un segundo par que incluye datos de visitas que no coincidieron con un ID de persona, pero sí con un ID de dispositivo. </p> <p>Los archivos de "ID de persona" contienen datos en todas las visitas que coinciden con los ID de persona, con todos los campos que tienen una etiqueta ACC-PERSON o ACC-ALL (un archivo con todas las visitas coincidentes y otro a modo de resumen). </p> <p>El par de archivos de ID de dispositivo solo contiene campos que presentan una etiqueta ACC-ALL e incluye únicamente visitas que no contuvieran ningún ID de persona coincidente. Estos archivos pueden contener datos generados por otros usuarios de un dispositivo compartido, por lo que se recomienda que piense detenidamente en el conjunto de campos que contienen la etiqueta ACC-ALL. El etiquetado predeterminado de Analytics solo aplica esta etiqueta a campos de información genérica relacionados con el dispositivo (tipo de dispositivo, sistema operativo, navegador, etc.), además de la fecha/hora de cada visita. </p> <p>Puede optar por recibir los conjuntos de archivos de persona y dispositivo de Adobe y, después, compartir solo los primeros, con el objetivo de no compartir datos que podrían haber generado otros usuarios de un dispositivo compartido. O puede que desee combinar los datos de uno de los pares o de ambos con otra información que conozca sobre el interesado y devolvérselos en su propio formato. </p> </td> 
  </tr> 
 </tbody> 
</table>

