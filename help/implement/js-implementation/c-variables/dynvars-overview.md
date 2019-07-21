---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de Analytics
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
seo-title: Variables dinámicas
solution: Analytics
subtopic: Variables
title: Variables dinámicas
topic: Desarrollador e implementación
uuid: 1 c 6 db 083-570 e -4 bc 4-858 d -84 cf 46 e 7 bec 8
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Variables dinámicas

Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.

Las variables dinámicas se utilizan al capturar los mismos datos (por ejemplo, códigos de seguimiento de campaña) en varias variables al mismo tiempo. Esta es una práctica habitual en casos en los que diferentes informes proporcionan importantes métricas únicas. Por ejemplo, la captura de palabras clave de búsqueda interna en una variable [!UICONTROL Conversión personalizada] y en una variable [!UICONTROL Tráfico personalizado] permite visualizar las métricas [!UICONTROL Ingresos] y [!UICONTROL Visitantes únicos semanales] asociadas, respectivamente, a estas palabras clave..

Las variables dinámicas también son útiles para ver datos bajo distintas condiciones de informes. Un código de seguimiento de campaña puede capturarse en varias eVars con distintas configuraciones de asignación y caducidad de cookies. Esto permite a los usuarios elegir el modo en que desean atribuir métricas de conversión a estas campañas. 

>[!NOTE]
>
>Las variables dinámicas no se admiten junto con cookies (s_ cc, s_ sq, s_ fid, s_ vi y cualquier cookie configurada por un complemento). You can not use `D=<cookie value>`.

Una ventaja importante de las variables dinámicas es la capacidad de capturar cadenas largas de datos en distintas variables sin que sea necesario pasar la cadena larga repetidamente. Algunos exploradores limitan la longitud máxima de las solicitudes GET de HTTP (incluida la solicitud de imagen de Adobe). El uso de variables dinámicas garantiza que todos los datos se capturan reduciendo la longitud de las solicitudes a los servidores de Adobe cuando los datos están duplicados en varias variables. .

En la solicitud de imagen de Adobe que se produce en la vista de página, si está utilizando variables dinámicas para copiar el valor de [!UICONTROL Tráfico personalizado ] en [!UICONTROL Conversión personalizada ], debería ver `v1=D=c1`1=1. Si eVar1 recibió un valor previamente en la solicitud, los servidores de Adobe copian dinámicamente el valor de [!UICONTROL Tráfico personalizado 1] en [!UICONTROL Conversión personalizada 1] durante el procesamiento de los datos. Como resultado, el valor pasado originalmente usando [!UICONTROL Tráfico personalizado 1] también aparece en los informes de [!UICONTROL Conversión personalizada 1].

Dynamic variables are passed by setting a variable to the desired value and then setting other variables to `D=[variable abbreviation]`. For abbreviations for each variable, see [Data Collection Query Parameters](../../../implement/js-implementation/data-collection/query-parameters.md). Las variables dinámicas pueden extraer datos de las ubicaciones siguientes:

* Otras variables de cadena de consulta
* Encabezados HTTP (excepto el encabezado HTTP Cookie)

Para crear una variable dinámica, agregue un prefijo especial al principio del valor. El prefijo predeterminado es "D=". Existen dos métodos para marcar variables dinámicas:

* Con el prefijo predeterminado D= (por ejemplo: s.prop1="D=User-Agent").
* En implementaciones que no son de JavaScript, puede definirse un prefijo personalizado con el parámetro de cadena de consulta "D". For example, if the query-string parameter is `"&D=$"`, you can create a dynamic variable with the following command: `s.prop1="$User-Agent"` .

La abreviatura de variable utilizada debe coincidir con el nombre del parámetro de la variable pasado en la solicitud de imagen. Algunas variables tienen varios parámetros aceptados que se utilizan en casos distintos. For example, `pageName=` and `gn=` both pass the page name, but the latter is most often used in mobile and hard-coded implementations. If the image request uses `pageName=` to pass the page name, then `D=pageName` is acceptable but `D=gn` is not. If the image request uses `gn=`, then `D=gn` is acceptable, but `D=pageName` is not.

La información siguiente se aplica a las variables dinámicas:

* Las variables dinámicas trabajan con todas las versiones del código de AppMeasurement.
* Las variables dinámicas distinguen mayúsculas de minúsculas.
* Las variables dinámicas admiten cadenas literales entre comillas.
* La sustitución de las variables dinámicas tiene lugar antes de procesar las reglas, los datos de VISTA y otros elementos.
* El prefijo "D=" de las variables dinámicas debe situarse al principio del valor de la variable y no en mitad de este. For example, use `c2='D="test7"+User-Agent'` rather than `c2='"test7"+D=User-Agent'` .

* Al igual que con todas las técnicas de implementación, Adobe recomienda encarecidamente realizar pruebas exhaustivas de las implementaciones de variables dinámicas en un entorno de desarrollo antes de su implementación en producción. Como las cadenas completas que se copian no están visibles en las herramientas de depuración del lado del cliente, revise los informes de Analytics que se vean afectados para confirmar que la implementación se ha realizado correctamente.
* Cuando copie valores entre variables con distintas longitudes máximas, tenga en cuenta que si copia un valor que exceda la longitud máxima de la variable de destino, se provocará un truncamiento. Por ejemplo, las variables [!UICONTROL Tráfico personalizado] tienen un límite de 100 caracteres y las variables [!UICONTROL Conversión personalizada] tiene un límite de 255 caracteres. Si copia un valor de 150 caracteres desde s.eVar1 a s.prop1 utilizando variables dinámicas, este valor quedará truncado en el informe [!UICONTROL Tráfico personalizado] en los 100 caracteres. 

## Ejemplos de variables dinámicas {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

Ejemplos de variables dinámicas que se pueden usar en Analytics.

En la solicitud de imagen de Adobe que se produce en la vista de página, si está utilizando variables dinámicas para copiar el valor de [!UICONTROL Tráfico personalizado ] en [!UICONTROL Conversión personalizada ], debería ver `v1=D=c1`1=1. Si eVar1 recibió un valor previamente en la solicitud, los servidores de Adobe copian dinámicamente el valor de [!UICONTROL Tráfico personalizado 1] en [!UICONTROL Conversión personalizada 1] durante el procesamiento de los datos. Como resultado, el valor pasado originalmente usando [!UICONTROL Tráfico personalizado 1] también aparece en los informes de [!UICONTROL Conversión personalizada 1].

Note that the `D=[variable]` value should be in quotes. El código de Analytics tratará esto como una cadena. Se aplicará la codificación URL a la cadena cuando se pase a Analytics (como podrá comprobar si visualiza la solicitud en DigitalPulse Debugger o una utilidad similar). Esto es normal. Adobe's servers recognize the `D=[variable]` construction and will copy the appropriate value when they encounter this string.

>[!NOTE]
>
>Al utilizar la solicitud de imagen para rastrear vínculos, debe definirse el tipo de vínculo (download = lnk_ d, exit = lnk_ e o custom link = lnk_ o), como hace URL/nombre del vínculo (pev 2). Links require manual implementation by inserting code within the `<a href>` tag.

>[!NOTE]
>
>Las variables dinámicas no se admiten junto con cookies (s_ cc, s_ sq, s_ fid, s_ vi y cualquier cookie configurada por un complemento). You can not use `D=<cookie value>`.

<table id="table_A25D5EA2A8C446F5A55AB32955B9848C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ejemplo de JavaScript </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. evar 1 = "D = pagename" </code>
  </td> 
   <td colname="col2"> <p>Captura el valor de pageName en eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop 1 =' D = v 2 + ": " + c 2 ' &amp; amp; nbsp; </code>
  </td> 
   <td colname="col2"> <p>Concatena eVar2:prop2 en prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop 1 = s. evar 1 = "D = g" &amp; amp; nbsp; </code>
  </td> 
   <td colname="col2"> <p>Pasa la dirección URL de la página a prop1 y eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. evar 1 = "D = v 0" </code>
  </td> 
   <td colname="col2"> <p>Captura la campaña en eVar 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">s. prop 1 =' D = User-Agent + "; - " + Accept-Language ' </code>
  </td> 
   <td colname="col2"> <p>Concatena los encabezados de aceptar idioma y agente de usuario en prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>s. prop 1 = "D = User-Agent" </code>
  </td> 
   <td colname="col2"> <p>Captura el agente de usuario en prop1. </p> </td> 
  </tr> 
 </tbody> 
</table>

<table id="table_DD0B7F0648054E01A5F98CDF18D745E4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Ejemplo de solicitud de imagen </th> 
   <th colname="col2" class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">/b/ss/rsid/? gn = Home &amp; D = ~ ~ &amp; c 1 = ~ ~ v 0 /b/ss/rsid/? gn = Home &amp; D = ~ ~ &amp; c 1 = ~ ~ campaign /b/ss/rsid/? gn = Home &amp; c 1 = D % 3 dv 0% 3 d is /b/ss/rsid/? gn = Home &amp; c 1 = % 5 b % 5 bv 0% 5 d % 5 d % 5 b </code>
  </td> 
   <td colname="col2"> <p>Cuatro modos de establecer prop1 en una campaña. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>/b/ss/rsid/? gn = Home &amp; D = ~ ~ &amp; c 2 = ~ ~ x-up-subno </code>
  </td> 
   <td colname="col2"> <p> Extrae el encabezado x-up-subno de prop2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>c 1 = D % 3 duser-Agent </code>
  </td> 
   <td colname="col2"> <p> Convierte prop1 en una variable dinámica que se rellena con el encabezado HTTP User-Agent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c 1 = D % 3 D % 22 test % 22 </code>
  </td> 
   <td colname="col2"> <p> Convierte prop1 en una variable dinámica que se rellena con la cadena “test”. Resulta mucho más útil si se usa junto con la concatenación con el operador +. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; c 1 = D % 3 D % 22 US % 3 A % 20% 22% 2 buser-Agent </code>
  </td> 
   <td colname="col2"> <p> Convierte prop1 en una variable dinámica que se rellena con el encabezado User-Agent y el prefijo “UA:” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">&amp; vid = D % 3 DX-TM-ANTID </code>
  </td> 
   <td colname="col2"> <p> Este ejemplo busca un encabezado único en este caso, X-TM-ANTID. </p> </td> 
  </tr> 
 </tbody> 
</table>
