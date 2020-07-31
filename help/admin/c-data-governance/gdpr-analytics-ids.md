---
description: 'null'
title: Prácticas recomendadas de etiquetado
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '2689'
ht-degree: 100%

---


# Prácticas recomendadas de etiquetado

>[!NOTE]
>
>Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que necesite revisar el etiquetado cuando se activen nuevas integraciones de la solución, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en la que se utilizan las variables existentes, las cuales también pueden necesitar la actualización de las etiquetas.

## ID directamente e indirectamente identificables {#section_030799AA1397433FBA61A2BC60A7A750}

Antes de poder determinar las etiquetas que se deben aplicar a cada variable o campo, primero debe comprender qué tipo de ID captura en sus datos de Analytics y decidir cuáles usará para las solicitudes de privacidad de datos. La privacidad de datos amplia el ámbito de lo que se puede considerar como un ID. Los ID se dividen en dos clases amplias: directamente identificables (etiqueta de identidad: I1) e indirectamente identificables (etiqueta de identidad: I2).

* **Un ID directamente identificable (I1)** especifica el nombre de la persona o proporciona un método directo de ponerse en contacto con ella. Como ejemplo podríamos mencionar el nombre de alguien (incluso uno común, como Juan Pérez, que podrían compartir cientos de personas), cualquiera de sus direcciones de correo electrónico o números de teléfono, etc. Una dirección de correo sin nombre podría considerarse como directamente identificable, aunque solo podría identificar un hogar o una empresa en lugar de una persona específica dentro de ese hogar o empresa.
* **Un ID indirectamente identificable (I2)** no permite que se determine de qué persona se trata por sí solo, pero podría combinarse con otra información (que podría tener o no en su poder) para identificar a alguien. Entre los ejemplos se incluyen un número de fidelidad de cliente o un ID empleado por el sistema de CRM de una empresa que es único para cada uno de sus clientes. De conformidad con la privacidad de datos, los ID anónimos almacenados en las cookies de seguimiento que utiliza Analytics se pueden considerar como de identificación indirecta, aunque solo pueden identificar un dispositivo, en lugar de a una persona; en un dispositivo compartido, estas cookies no pueden distinguir entre los distintos usuarios del sistema. Por ejemplo, aunque la cookie no se puede utilizar para encontrar un equipo que la contenga, si alguien tiene acceso al equipo y la localiza, entonces puede asociar los datos de la cookie de Analytics nuevamente al equipo.

   Una dirección IP también se considera indirectamente identificable, porque en cualquier momento puntual solo se puede asignar a un único dispositivo. Sin embargo, los ISP pueden cambiar las direcciones IP de la mayoría de los usuarios con regularidad (y lo hacen a menudo), de modo que a lo largo de cierto tiempo cualquiera de sus usuarios puede haber usado una dirección IP determinada. Tampoco es inusual que muchos clientes de un ISP o varios empleados de una empresa en la misma intranet compartan la misma dirección IP externa. Por estos motivos, Adobe no admitirá el uso de una dirección IP como el ID de una [solicitud de privacidad de datos.](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests) Sin embargo, cuando se emplee un ID que aceptemos como parte de una solicitud de eliminación, también borraremos las direcciones IP ligadas a dicho ID. Debe decidir si existen otros ID que recopile que puedan pertenecer a esta categoría, de I1 o I2, pero que no sean aptos para su uso como ID distintivo en solicitudes de privacidad de datos.

Aunque su empresa recopile muchos ID distintos en sus datos de Analytics, puede optar por usar únicamente un subconjunto de dichos ID para las solicitudes de privacidad de datos. Estos son algunos de los motivos para tomar esa decisión:

* Dentro de sus propios sistemas, puede asignar uno de los ID (por ejemplo, la dirección de correo electrónico) a un ID distinto (como el ID de CRM). Entonces, con fines de coherencia, puede decidir utilizar solo el ID de CRM a la hora de tratar las solicitudes de privacidad de datos durante el procesamiento de la privacidad de datos.
* Carece de un método de validar que alguien sea realmente la persona asociada a ese ID. Por ejemplo, puede resultar extremadamente difícil validar que solo una persona ha usado en todo momento una dirección IP y que quien presenta la solicitud es realmente esa persona.
* Algunos ID pueden corresponder a varias personas y puede no querer arriesgarse a devolver información sobre una persona a otra distinta con ese mismo ID. Por ejemplo, aunque pueda verificar que el nombre de una persona es Juan Pérez, es posible que no desee devolver todos los datos sobre todos los usuarios llamados Juan Pérez de su sistema.
* Otro ejemplo es un ID de dispositivo, como el ID de cookie de Analytics. Si el ID se origina en una aplicación de un teléfono móvil, puede decidir que todas las interacciones que utilicen ese ID deban estar disponibles para el propietario del teléfono móvil. No obstante, si se produce en un dispositivo compartido, como un ordenador doméstico o uno de una biblioteca o un cibercafé, puede determinar que no le es posible distinguir entre los usuarios del dispositivo en cuestión y que existe demasiado riesgo de devolver datos de un usuario distinto como para permitir el uso de este tipo de ID.

## Prácticas recomendadas para los ID admitidos por Analytics {#section_B6481505FF1949498D4B4B35B780D050}

Utilice esta tabla para determinar los tipos de ID que usará para enviar solicitudes de privacidad de datos a Analytics. Una vez que conozca esta información, le resultará más fácil determinar qué otras etiquetas debería utilizar para sus variables.

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
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://docs.adobe.com/content/help/es-ES/core-services/interface/ec-cookies/cookies-privacy.html">Cookie de Analytics (heredada)</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://docs.adobe.com/content/help/es-ES/id-service/using/home.html"> Cookie de servicio de identidad </a> (ECID), anteriormente conocido como Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Estas cookies identifican un dispositivo o, más concretamente, un navegador para el usuario de un dispositivo. En el caso de un dispositivo compartido en el que se utilicen unas credenciales de inicio de sesión comunes, este ID podría aplicarse a todos los usuarios del dispositivo. Adobe ha creado <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm">código JavaScript unificado</a> que puede colocar en su sitio web a fin de recopilar estas cookies si desea permitir que se utilicen para las solicitudes de privacidad de datos. </p> <p>Los usuarios del SDK para móviles de Adobe Analytics también tienen un Experience Cloud ID (ECID). Hay llamadas a la API dentro del SDK para leer este ID, por lo que puede mejorar su aplicación, de modo que los recopile para fines de solicitudes de privacidad de datos. </p> <p>Muchas empresas consideran que los ID de cookies de navegadores son ID de dispositivos compartidos. En consecuencia, tras consultarlo con sus equipos jurídicos, podrían optar por no permitir usarlos como ID aceptables para las solicitudes de privacidad de datos, pueden decidir devolver únicamente una cantidad de datos muy limitada cuando se utilicen dichos ID o bien pueden aceptarlos únicamente para eliminar solicitudes. </p> <p>Estas cookies tienen una etiqueta ID-DEVICE que no se puede cambiar (así como etiquetas I2 y DEL-DEVICE). La configuración predeterminada de Adobe Analytics solo devolverá información genérica sobre el dispositivo, como su tipo, el sistema operativo, el navegador, etc., además de la hora y las fechas en las que se visitara su sitio web usando estos ID. Sin embargo, si opta por admitir estos ID para las solicitudes de privacidad de datos, como se explica abajo, puede añadir o eliminar etiquetas ACC-ALL para configurar el conjunto de campos exacto que desea que se devuelva en el caso de una solicitud de acceso de privacidad de datos. </p> <p>En especial si el grupo de informes corresponde a una aplicación móvil, y esta requiere credenciales de inicio de sesión, puede decidir que el Experience Cloud ID del dispositivo corresponde a un usuario específico y, por lo tanto, deseará etiquetar más de esos campos con la etiqueta ACC-ALL, incluidos los nombres de las páginas visitadas, los productos vistos, etc. </p> <p>Nota: Si especifica la opción “expandIds” en su solicitud de privacidad de datos, entonces las solicitudes siempre incluirán los ID de cookie, además de cualquier otro ID que especifique. Consulte <a href="/help/admin/c-data-governance/gdpr-id-expansion.md">Expansión de ID</a> para obtener más información. En estos casos, las visitas que solo tienen un ID de cookie, pero no otro ID, solo devolverán los datos etiquetados ACC-ALL como parte de la solicitud de acceso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID en variables personalizadas </p> </td> 
   <td colname="col2"> <p>Algunos clientes colocan ID en <a href="https://docs.adobe.com/content/help/es-ES/analytics/implementation/vars/page-vars/evar.html">variables de tráfico personalizadas (props) o variables de conversión personalizadas (eVars)</a>. Aunque que el más común es un ID de CRM, otros incluyen direcciones de correo electrónico, nombres de inicio de sesión del usuario, números de fidelidad del cliente o hash de estos valores. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Si desea usar uno de estos ID para solicitudes de privacidad de datos, debe marcar el campo que lo contenga con la etiqueta ID-PERSON. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Mucho menos habitual). Si un ID de una de estas variables personalizadas solo identifica un dispositivo que podrían compartir varias personas, puede usar en su lugar una etiqueta ID-DEVICE. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Estos campos también precisan las etiquetas I1 o I2, y deben incluir una etiqueta DEL-PERSON o DEL-DEVICE. Normalmente, la opción PERSON/DEVICE de la etiqueta DEL coincidirá con la opción PERSON/DEVICE de la etiqueta de ID. </li> 
    </ul> <p> Es poco habitual que un grupo de informes tenga más de una o dos variables personalizadas que contengan ID que desearía usar con el objetivo de identificar interesados para las solicitudes de privacidad de datos. Puede darse el caso de que tenga diversas variables con etiquetas I1 o I2 asignadas, pero, por lo general, solo una o dos de ellas presentarían también las etiquetas ID-PERSON o ID-DEVICE. </p> </td> 
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
>Las props nunca distinguen entre mayúsculas y minúsculas. Las eVars tampoco distinguen entre mayúsculas y minúsculas, pero pueden configurarse con la ayuda del servicio de atención al cliente de Adobe para que realicen esta distinción. Si tiene una eVar que distingue entre mayúsculas y minúsculas y que contiene un ID, es su responsabilidad usar la combinación correcta de mayúsculas y minúsculas a la hora de enviar una solicitud de privacidad de datos, de modo que la combinación empleada en la solicitud coincida con la utilizada en las visitas que contengan esos ID.

Las etiquetas de eliminación DEL-DEVICE y DEL-PERSON deben usarse con moderación. Cuando se aplican a una variable que no contiene un ID que se usaba como parte de la solicitud de privacidad de datos, los recuentos (las métricas) de los informes históricos de Analytics casi siempre cambiarán.

* Se recomienda aplicar una de estas etiquetas a cualquier variable etiquetada como I1, I2 o S1. No se pueden aplicar a ninguna variable que no esté etiquetada como I1, I2 o S1.
* Las etiquetas DEL- harán que estas variables se conviertan en [anónimas](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) (es decir, que el ID se sustituya por una cadena aleatoria con el prefijo “Privacidad de datos”). El mismo valor convertido en anónimo sustituirá a todas las instancias del valor original en todas las visitas que se hayan identificado con un ID utilizado en la solicitud. Si el valor original de este campo era uno de esos ID, las métricas del informe no cambiarán.
* Por lo general, si un campo presenta la etiqueta ID-DEVICE, también debería asignarle la etiqueta DEL-DEVICE.
* Del mismo modo, si un campo presenta la etiqueta ID-PERSON, también debería asignarle la etiqueta DEL-PERSON.
* Si un campo no tiene una etiqueta de ID, pero contiene información de identificación que desea convertir en anónima, la etiqueta apropiada (DEVICE o PERSON) depende de su implementación. Si solo usa ID de cookie para las solicitudes de privacidad de datos, debería utilizar DEL-DEVICE.
* Si utiliza ID personalizados en un campo distinto con una etiqueta ID-PERSON, y solo desea que se eliminen estos datos en las filas donde aparezca ese ID, use DEL-PERSON.
* Si está usando la expansión de ID y desea que se eliminen todos los valores de todas las visitas en todos los dispositivos identificados, utilice DEL-DEVICE. Si lo prefiere, puede aplicar tanto las etiquetas DEL-DEVICE como DEL-PERSON en este caso, pero la etiqueta DEL-PERSON es innecesaria, ya que la expansión de ID supone que todas las filas que coinciden con el ID de una persona también coinciden con un ID de dispositivo.
* Si no va a especificar el uso de la expansión de ID, pero va a utilizar una mezcla de ID de dispositivo y persona para distintas solicitudes, le recomendamos especificar tanto la etiqueta DEL-DEVICE como la DEL-PERSON para las variables que se deben eliminar cuando se utiliza cualquiera de los dos tipos de ID.
* Tenga en cuenta que si se especifica una etiqueta DEL-DEVICE o DEL-PERSON en cualquier variable que no se utilice también como ID para dicha solicitud (incluida la expansión de ID), entonces los valores únicos de dicha variable solo se volverán anónimos en las visitas donde se produzca una especificación (o expansión) de ID. Si otras visitas contienen el mismo valor, no se actualizará en esas otras ubicaciones. Esto puede provocar el cambio de los recuentos (métricas).

   Por ejemplo, si cuenta con tres visitas que contienen el valor “foo” en eVar7, pero solo una de ellas contiene también un ID en una variable distinta que coincide con una eliminación, entonces el valor “foo” de dicha visita se modificará por uno como “Privacidad de datos-123456789”, mientras que en las otras dos visitas permanecerá sin cambios. Un informe que incluye el número de valores únicos para eVar7 ahora mostrará un valor único más que antes. Un informe que incluye los valores principales para los eVar puede incluir “foo” con solo dos instancias (en lugar de las tres anteriores), y el nuevo valor aparecerá también como instancia única.

## Prácticas recomendadas para establecer etiquetas de acceso {#section_AC7E216F81C141FCA6A62F8836E06EE7}

Aunque muy pocos campos tendrán alguna de las otras etiquetas, será habitual que un gran número de campos presenten etiquetas ACC. Las etiquetas de acceso adecuadas dependerán de los ID que utilice para las solicitudes de privacidad de datos.

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
   <td colname="col2"> <p>Si incluye ID tanto de persona como de dispositivo en las solicitudes de privacidad de datos, o si emplea ID personalizados (ID de visitante personalizado o un ID en una prop o eVar), tendrá que prestar atención a las etiquetas ACC que utilice. Cada solicitud de acceso devolverá dos pares de archivos de datos, un par que contiene datos de las visitas que incluyeron un ID de persona coincidente y un segundo par que incluye datos de visitas que no coincidieron con un ID de persona, pero sí con un ID de dispositivo. </p> <p>Los archivos de "ID de persona" contienen datos en todas las visitas que coinciden con los ID de persona, con todos los campos que tienen una etiqueta ACC-PERSON o ACC-ALL (un archivo con todas las visitas coincidentes y otro a modo de resumen). </p> <p>El par de archivos de ID de dispositivo solo contiene campos que presentan una etiqueta ACC-ALL e incluye únicamente visitas que no contuvieran ningún ID de persona coincidente. Estos archivos pueden contener datos generados por otros usuarios de un dispositivo compartido, por lo que se recomienda que piense detenidamente en el conjunto de campos que contienen la etiqueta ACC-ALL. El etiquetado predeterminado de Analytics solo aplica esta etiqueta a campos de información genérica relacionados con el dispositivo (tipo de dispositivo, sistema operativo, navegador, etc.), además de la fecha/hora de cada visita. </p> <p>Puede optar por recibir los conjuntos de archivos de persona y dispositivo de Adobe y, después, compartir solo los primeros, con el objetivo de no compartir datos que podrían haber generado otros usuarios de un dispositivo compartido. O puede que desee combinar los datos de uno de los pares o de ambos con otra información que conozca sobre el interesado y devolvérselos en su propio formato. </p> </td> 
  </tr> 
 </tbody> 
</table>

