---
description: 'null'
title: Prácticas recomendadas de etiquetado
uuid: d1e9bfff-9b04-4e3e-9b4e-a6e527b1b2e3
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Prácticas recomendadas de etiquetado

>[!NOTE] Recuerde que el etiquetado debe revisarse cada vez que se crea un nuevo grupo de informes o cuando se activa una nueva variable dentro de un grupo de informes existente. También es posible que tenga que revisar el etiquetado cuando se habiliten nuevas integraciones de soluciones, ya que pueden exponer nuevas variables que pueden requerir etiquetado. Una reimplementación de sus aplicaciones móviles o sitios web puede cambiar la forma en que se utilizan las variables existentes, lo que también puede requerir actualizaciones de las etiquetas.

## ID directamente e indirectamente identificables {#section_030799AA1397433FBA61A2BC60A7A750}

Antes de poder determinar las etiquetas que se deben aplicar a cada variable o campo, primero debe comprender qué tipo de ID captura en sus datos de Analytics y decidir cuáles usará para las solicitudes de privacidad de datos. La privacidad de datos amplia el ámbito de lo que se puede considerar como un ID. Los ID se dividen en dos clases generales: identificable directamente (etiqueta de identidad: I1) e identificable indirectamente (etiqueta de identidad: I2).

* **ID directamente identificable (I1)**: Asigna un nombre a la persona o proporciona un método directo para ponerse en contacto con ella. Algunos ejemplos son el nombre de alguien (incluso un nombre común como John Smith que puede ser compartido por cientos de personas), cualquiera de sus direcciones de correo electrónico o números de teléfono, etc. Una dirección postal sin nombre puede considerarse directamente identificable, aunque sólo pueda identificar un hogar o una empresa en lugar de una persona concreta de ese hogar o empresa.
* **Un ID de identificación indirecta (I2)**: No permite la identificación de una persona por sí misma, pero puede combinarse con otra información (que puede o no estar en su poder), para identificar a alguien. Algunos ejemplos son un número de lealtad del cliente o un ID utilizado por el sistema CRM de una compañía que es único para cada uno de sus clientes. De conformidad con la privacidad de datos, los ID anónimos almacenados en las cookies de seguimiento que utiliza Analytics se pueden considerar como de identificación indirecta, aunque solo pueden identificar un dispositivo, en lugar de a una persona; en un dispositivo compartido, estas cookies no pueden distinguir entre los distintos usuarios del sistema. Por ejemplo, aunque la cookie no se puede usar para encontrar un equipo que contenga la cookie, si alguien tiene acceso al equipo y encuentra la cookie, entonces puede volver a enlazar los datos de la cookie de Analytics al equipo.

   También se considera que una dirección IP es indirectamente identificable, ya que en cualquier momento dado solo puede asignarse a un solo dispositivo. Sin embargo, los ISP pueden cambiar las direcciones IP de la mayoría de los usuarios con regularidad, por lo que con el tiempo cualquiera de los usuarios puede haber utilizado una dirección IP. Tampoco es inusual que muchos clientes de un ISP o varios empleados de una empresa en la misma intranet compartan la misma dirección IP externa. Por estos motivos, Adobe no admitirá el uso de una dirección IP como el ID de una [solicitud de privacidad de datos.](/help/admin/c-data-governance/gdpr-submit-access-delete.md#submit-requests) Sin embargo, cuando se emplee un ID que aceptemos como parte de una solicitud de eliminación, también borraremos las direcciones IP ligadas a dicho ID. Debe decidir si existen otros ID que recopile que puedan pertenecer a esta categoría, de I1 o I2, pero que no sean aptos para su uso como ID distintivo en solicitudes de privacidad de datos.

Aunque su empresa recopile muchos ID distintos en sus datos de Analytics, puede optar por usar únicamente un subconjunto de dichos ID para las solicitudes de privacidad de datos. Entre las razones para esto se incluyen:

* Dentro de sus propios sistemas, puede asignar uno de los ID (por ejemplo, la dirección de correo electrónico) a un ID diferente (como el ID de CRM). Entonces, con fines de coherencia, puede decidir utilizar solo el ID de CRM a la hora de tratar las solicitudes de privacidad de datos durante el procesamiento de la privacidad de datos.
* No tiene un método para validar que alguien sea en realidad la persona asociada con el ID. Por ejemplo, puede resultar muy difícil validar que una dirección IP haya sido utilizada únicamente por una sola persona y que la persona que presenta la solicitud sea en realidad esa persona.
* Algunas ID pueden corresponder a varias personas y no se quiere arriesgar a devolver información sobre una persona a otra con la misma ID. Por ejemplo, aunque se pueda verificar que el nombre de alguien sea John Smith, es posible que no se quieran devolver todos los datos de John Smiths en el sistema.
* Otro ejemplo es un ID de dispositivo, como el ID de cookie de Analytics. Si el ID se produce en una aplicación de teléfono móvil, puede decidir que todas las interacciones que utilicen ese ID estén disponibles para el propietario del teléfono móvil. Sin embargo, si se produce en un dispositivo compartido, como un equipo doméstico o en una biblioteca o un café Internet, puede decidir que no puede distinguir entre usuarios de ese dispositivo y el riesgo de devolver datos para un usuario diferente es demasiado bueno para permitir el uso de este tipo de ID.

## Prácticas recomendadas para los ID admitidos por Analytics  {#section_B6481505FF1949498D4B4B35B780D050}

Utilice esta tabla para determinar los tipos de ID que usará para enviar solicitudes de privacidad de datos a Analytics. Una vez que conozca esta información, será más fácil determinar las demás etiquetas que debe utilizar para las variables.

<table id="table_E25612E32A03449A8E5DA00B88FCEB9E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Tipo de ID </th> 
   <th colname="col2" class="entry"> Recomendaciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID de cookies </p> 
    <ul id="ul_CB43CEA3054E490585CBF3AB46F95B5B"> 
     <li id="li_9174CB3910AF4EF8BA7165DB537765A5"> <a href="https://marketing.adobe.com/resources/help/es_ES/whitepapers/cookies/cookies_analytics.html">Cookie de Analytics (heredada)</a> </li> 
     <li id="li_7B6A9A788BBD47428315B3893FC07BC3"> <a href="https://marketing.adobe.com/resources/help/es_ES/mcvid/"> Cookie de servicio de identidad </a> (ECID), anteriormente conocido como Marketing Cloud ID (MCID) </li> 
    </ul> </td> 
   <td colname="col2"> <p>Estas cookies identifican un dispositivo o, más específicamente, un explorador para un usuario de un dispositivo. Para un dispositivo compartido en el que se utiliza un inicio de sesión común, este ID podría aplicarse a todos los usuarios del dispositivo. Adobe ha creado <a href="https://www.adobe.io/apis/cloudplatform/gdpr/services/allservices.htm">código JavaScript unificado</a> que puede colocar en su sitio web a fin de recopilar estas cookies si desea permitir que se utilicen para las solicitudes de privacidad de datos. </p> <p>Los usuarios del SDK para móviles de Adobe Analytics también tienen un Experience Cloud ID (ECID). Hay llamadas a la API dentro del SDK para leer este ID, por lo que puede mejorar su aplicación, de modo que los recopile para fines de solicitudes de privacidad de datos. </p> <p>Muchas empresas consideran que los ID de cookies de navegadores son ID de dispositivos compartidos. En consecuencia, tras consultarlo con sus equipos jurídicos, podrían optar por no permitir usarlos como ID aceptables para las solicitudes de privacidad de datos, pueden decidir devolver únicamente una cantidad de datos muy limitada cuando se utilicen dichos ID o bien pueden aceptarlos únicamente para eliminar solicitudes. </p> <p>Estas cookies tienen una etiqueta ID-DEVICE que no se puede cambiar (así como las etiquetas I2 y DEL-DEVICE). La configuración predeterminada de Adobe Analytics solo devolverá información genérica sobre el dispositivo, como el tipo de dispositivo, el sistema operativo, el navegador, etc. más la hora y las fechas en las que se visitó el sitio web al usar estos ID. Sin embargo, si opta por admitir estos ID para las solicitudes de privacidad de datos, como se explica abajo, puede añadir o eliminar etiquetas ACC-ALL para configurar el conjunto de campos exacto que desea que se devuelva en el caso de una solicitud de acceso de privacidad de datos. </p> <p>En especial si el grupo de informes corresponde a una aplicación móvil, y esta requiere credenciales de inicio de sesión, puede decidir que el Experience Cloud ID del dispositivo corresponde a un usuario específico y, por lo tanto, deseará etiquetar más de esos campos con la etiqueta ACC-ALL, incluidos los nombres de las páginas visitadas, los productos vistos, etc. </p> <p>Nota: Si especifica la opción “expandIds” en su solicitud de privacidad de datos, entonces las solicitudes siempre incluirán los ID de cookie, además de cualquier otro ID que especifique. Consulte <a href="/help/admin/c-data-governance/gdpr-id-expansion.md">Expansión de ID</a> para obtener más información. En estos casos, las visitas que solo tienen un ID de cookie, pero no otro ID, solo devolverán datos etiquetados con ACC-ALL como parte de la solicitud de acceso. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID en variables personalizadas </p> </td> 
   <td colname="col2"> <p>Algunos clientes colocan ID en <a href="https://marketing.adobe.com/resources/help/es_ES/sc/implement/props_eVars.html">variables de tráfico personalizadas (props) o variables de conversión personalizadas (eVars)</a>. Aunque que el más común es un ID de CRM, otros incluyen direcciones de correo electrónico, nombres de inicio de sesión del usuario, números de fidelidad del cliente o hash de estos valores. </p> 
    <ul id="ul_0B9492CF786046BB97E31CCF83A85FEA"> 
     <li id="li_D35B61CC6A8B485A8E09358A46D3F598">Si desea usar uno de estos ID para solicitudes de privacidad de datos, debe marcar el campo que lo contenga con la etiqueta ID-PERSON. </li> 
     <li id="li_94541340B054436297C5565F074413DC">(Mucho menos habitual). Si un ID de una de estas variables personalizadas solo identifica un dispositivo que podrían compartir varias personas, puede usar en su lugar una etiqueta ID-DEVICE. </li> 
     <li id="li_8115B999E8DA46CAB359BCF1F4A4DCAE">Estos campos también requieren etiquetas I1 o I2 y deben incluir una etiqueta DEL-PERSON o DEL-DEVICE. Normalmente, la opción PERSONA/DISPOSITIVO de la etiqueta DEL coincidirá con la opción PERSONA/DISPOSITIVO de la etiqueta de ID. </li> 
    </ul> <p> Es poco habitual que un grupo de informes tenga más de una o dos variables personalizadas que contengan ID que desearía usar con el objetivo de identificar interesados para las solicitudes de privacidad de datos. Es posible que tenga varias variables a las que se les asignen etiquetas I1 o I2, pero normalmente solo una o dos de ellas tendrían etiquetas ID-PERSON o ID-DEVICE. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de visitante personalizado </p> </td> 
   <td colname="col2"> <p>Aunque esto no se utilice de forma generalizada, Analytics también admite una implementación en la que se puede proporcionar un ID de visitante personalizado, que si está presente se utiliza en lugar de la cookie de seguimiento de Analytics heredada. Este campo tiene las etiquetas I2, ID-PERSON y DEL-PERSON. </p> <p>Muchas implementaciones obtienen este ID de un ID de CRM, por lo que solo está presente mientras alguien ha iniciado sesión en su sitio. Esto permite usar el mismo ID de Visitante personalizado en todos los dispositivos. Un inconveniente técnico es que el seguimiento que se realiza antes de que el usuario inicie sesión no puede estar vinculado al seguimiento recopilado después de haber iniciado sesión. Si, en su lugar, utiliza el ID de visitante personalizado para identificar simplemente un dispositivo, debe cambiar las etiquetas ID-PERSON y DEL-PERSON a ID-DEVICE y DEL-DEVICE, respectivamente. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Prácticas recomendadas para establecer etiquetas de eliminación {#section_08166C99B48E49218392FAC18922C10E}

>[!NOTE] Las props nunca distinguen entre mayúsculas y minúsculas. Las eVars tampoco distinguen entre mayúsculas y minúsculas, pero pueden configurarse con la ayuda del servicio de atención al cliente de Adobe para que realicen esta distinción. Si tiene una eVar que distingue entre mayúsculas y minúsculas y que contiene un ID, es su responsabilidad usar la combinación correcta de mayúsculas y minúsculas a la hora de enviar una solicitud de privacidad de datos, de modo que la combinación empleada en la solicitud coincida con la utilizada en las visitas que contengan esos ID.

Las etiquetas de eliminación DEL-DEVICE y DEL-PERSON deben usarse con moderación. Cuando se aplican a una variable que no contiene un ID que se usaba como parte de la solicitud de privacidad de datos, los recuentos (las métricas) de los informes históricos de Analytics casi siempre cambiarán.

* Se recomienda aplicar una de estas etiquetas a cualquier variable etiquetada como I1, I2 o S1. No se pueden aplicar a ninguna variable que no esté etiquetada como I1, I2 o S1.
* Las etiquetas DEL- harán que estas variables se conviertan en [anónimas](/help/admin/c-data-governance/gdpr-labels.md#data-governance-labels) (es decir, que el ID se sustituya por una cadena aleatoria con el prefijo “Privacidad de datos”). El mismo valor convertido en anónimo sustituirá a todas las instancias del valor original en todas las visitas que se hayan identificado con un ID utilizado en la solicitud. Si el valor original de este campo era uno de esos ID, las métricas de informes no cambiarán.
* Generalmente, si un campo tiene la etiqueta ID-DEVICE, también debe asignar la etiqueta DEL-DEVICE.
* Del mismo modo, si un campo tiene la etiqueta ID-PERSON, también debe asignar la etiqueta DEL-PERSON.
* Si un campo no tiene una etiqueta de ID, pero sí contiene información de identificación que desea que sea anónima, la etiqueta adecuada (DISPOSITIVO o PERSONA) depende de la implementación. Si solo usa ID de cookie para las solicitudes de privacidad de datos, debería utilizar DEL-DEVICE.
* Si utiliza ID personalizados en un campo diferente con una etiqueta ID-PERSON, y sólo desea que se borre en filas donde se produzca dicha ID, utilice DEL-PERSON.
* Si está utilizando la expansión de ID y desea que se borre todo el valor de todas las visitas en todos los dispositivos identificados, utilice DEL-DEVICE. Puede aplicar las etiquetas DEL-DEVICE y DEL-PERSON en este caso si lo prefiere, pero la etiqueta DEL-PERSON no es necesaria, ya que la expansión de ID significa que todas las filas que coincidan con un ID de persona también coincidirán con un ID de dispositivo.
* Si no va a especificar el uso de la expansión de ID, pero va a utilizar una combinación de ID de dispositivo y persona para distintas solicitudes, puede que desee especificar las etiquetas DEL-DEVICE y DEL-PERSON para variables que deben eliminarse cuando se utilice cualquier tipo de ID.
* Tenga en cuenta que si se especifica una etiqueta DEL-DEVICE o DEL-PERSON en cualquier variable que no se utilice también como ID para esa solicitud (incluso un ID expandido), los valores únicos de esa variable solo se anonimizarán en las visitas en las que se produzca un ID especificado (o expandido). Si otras visitas individuales contienen el mismo valor, no se actualizará en esas otras ubicaciones. Esto puede hacer que cambien los recuentos (métricas).

   Por ejemplo, si cuenta con tres visitas que contienen el valor “foo” en eVar7, pero solo una de ellas contiene también un ID en una variable distinta que coincide con una eliminación, entonces el valor “foo” de dicha visita se modificará por uno como “Privacidad de datos-123456789”, mientras que en las otras dos visitas permanecerá sin cambios. Un informe que incluye el número de valores únicos para eVar7 ahora mostrará un valor único más que antes. Un informe que incluye los valores principales para los eVar puede incluir “foo” con solo dos instancias (en lugar de las tres anteriores), y el nuevo valor aparecerá también como instancia única.

## Prácticas recomendadas para establecer etiquetas de acceso  {#section_AC7E216F81C141FCA6A62F8836E06EE7}

Aunque muy pocos campos tendrán alguna de las otras etiquetas, será habitual que un gran número de campos presenten etiquetas ACC. Las etiquetas de acceso adecuadas dependerán de los ID que utilice para las solicitudes de privacidad de datos.

<table id="table_A5B834CC08C641D99E2691A2361997E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Si utiliza... </th> 
   <th colname="col2" class="entry"> ...usar estas recomendaciones </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Solo ID de dispositivo </p> </td> 
   <td colname="col2"> <p>Si los únicos ID que está utilizando son los ID de cookies o los que tienen una etiqueta ID-DEVICE, sólo debe utilizar la etiqueta ACC-ALL. </p> <p>Obtendrá un par de archivos por cada solicitud de acceso, uno con una fila por cada visita coincidente con todos los campos ACC-ALL especificados y otro con un resumen de estos datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID de persona sin expansión de ID </p> </td> 
   <td colname="col2"> <p>Si solo utiliza ID personalizados que tienen la etiqueta ID-PERSON y no están ampliando el ID, debe utilizar etiquetas ACC-PERSON. Sin embargo, no es necesario cambiar las etiquetas predeterminadas ACC-ALL; estos campos se incluirán automáticamente en la solicitud de acceso. </p> <p>Obtendrá un par de archivos por cada solicitud de acceso, uno con una fila por cada visita coincidente con todos los campos ACC-DEVICE y ACC-PERSON especificados y otro con un resumen de estos datos. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID combinados o expansión de ID </p> </td> 
   <td colname="col2"> <p>Si incluye ID tanto de persona como de dispositivo en las solicitudes de privacidad de datos, o si emplea ID personalizados (ID de visitante personalizado o un ID en una prop o eVar), tendrá que prestar atención a las etiquetas ACC que utilice. Cada solicitud de acceso devolverá dos pares de archivos de datos, un par que contiene datos de las visitas que incluyeron un ID de persona coincidente y un segundo par que incluye datos de visitas que no coincidieron con un ID de persona, pero sí con un ID de dispositivo. </p> <p>Los archivos de "ID de persona" contienen datos de todas las visitas que coinciden con los ID de persona con todos los campos que tienen una etiqueta ACC-PERSON o ACC-ALL (un archivo con todas las visitas coincidentes y el otro como resumen). </p> <p>El par de archivos "ID del dispositivo" contiene solo campos que tienen una etiqueta ACC-ALL y contienen solo visitas que no contenían ningún ID de persona coincidente. Estos archivos pueden contener datos generados por otros usuarios de un dispositivo compartido, por lo que debe tener en cuenta cuidadosamente el conjunto de campos que contienen la etiqueta ACC-ALL. El etiquetado predeterminado en Analytics solo aplica esta etiqueta a los campos de información genéricos relacionados con el dispositivo (tipo de dispositivo, sistema operativo, navegador, etc.) más la fecha y hora de cada visita. </p> <p>Puede optar por recibir los conjuntos de archivos de dispositivo y persona de Adobe y, a continuación, solo compartir los archivos de persona para no compartir los datos que puedan haber generado otros usuarios de un dispositivo compartido. O bien, puede que desee combinar datos de uno o ambos conjuntos con otra información que conozca sobre el asunto de los datos y devolverla en su propio formato. </p> </td> 
  </tr> 
 </tbody> 
</table>

