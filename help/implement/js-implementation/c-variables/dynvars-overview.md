---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
subtopic: Variables
title: Variables dinámicas
topic: Developer and implementation
uuid: 1c6db083-570e-4bc4-858d-84cf46e7bec8
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Variables dinámicas

Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.

Las variables dinámicas se utilizan al capturar los mismos datos (por ejemplo, códigos de seguimiento de campaña) en varias variables al mismo tiempo. Esta es una práctica habitual en casos en los que diferentes informes proporcionan importantes métricas únicas. Por ejemplo, la captura de palabras clave de búsqueda interna en una variable [!UICONTROL Conversión personalizada] y en una variable [!UICONTROL Tráfico personalizado] permite visualizar las métricas [!UICONTROL Ingresos] y [!UICONTROL Visitantes únicos semanales] asociadas, respectivamente, a estas palabras clave..

Las variables dinámicas también son útiles para ver datos bajo distintas condiciones de informes. Un código de seguimiento de campaña puede capturarse en varias eVars con distintas configuraciones de asignación y caducidad de cookies. Esto permite a los usuarios elegir el modo en que desean atribuir métricas de conversión a estas campañas.

> [!NOTE] No se admiten variables dinámicas junto con cookies (s_cc, s_sq, s_fid, s_vi ni las cookies establecidas por un complemento). No puede usar `D=<cookie value>`.

Una ventaja importante de las variables dinámicas es la capacidad de capturar cadenas largas de datos en distintas variables sin que sea necesario pasar la cadena larga repetidamente. Algunos exploradores limitan la longitud máxima de las solicitudes GET de HTTP (incluida la solicitud de imagen de Adobe). El uso de variables dinámicas garantiza que todos los datos se capturan reduciendo la longitud de las solicitudes a los servidores de Adobe cuando los datos están duplicados en varias variables..

En la solicitud de imagen de Adobe que se produce en la vista de página, si está utilizando variables dinámicas para copiar el valor de [!UICONTROL Tráfico personalizado ] en [!UICONTROL Conversión personalizada ], debería ver `v1=D=c1`1=1. Si eVar1 recibió un valor previamente en la solicitud, los servidores de Adobe copian dinámicamente el valor de [!UICONTROL Tráfico personalizado 1] en [!UICONTROL Conversión personalizada 1] durante el procesamiento de los datos. Como resultado, el valor pasado originalmente usando [!UICONTROL Tráfico personalizado 1] también aparece en los informes de [!UICONTROL Conversión personalizada 1].

Las variables dinámicas se pasan mediante la configuración de una variable en el valor deseado y la posterior configuración de otras variables en `D=[variable abbreviation]`. Para obtener las abreviaciones de cada variable, consulte [Parámetros de consulta de recopilación de datos](/help/implement/js-implementation/data-collection/query-parameters.md). Las variables dinámicas pueden extraer datos de las ubicaciones siguientes:

* Otras variables de cadena de consulta
* Encabezados HTTP (excepto el encabezado HTTP Cookie)

Para crear una variable dinámica, agregue un prefijo especial al principio del valor. El prefijo predeterminado es "D=". Existen dos métodos para marcar variables dinámicas:

* Con el prefijo predeterminado D= (por ejemplo: s.prop1="D=User-Agent").
* En implementaciones que no son de JavaScript, puede definirse un prefijo personalizado con el parámetro de cadena de consulta "D". Por ejemplo, si el parámetro de cadena de consulta es `"&D=$"`, puede crear una variable dinámica con el comando siguiente: `s.prop1="$User-Agent"`.

La abreviatura de variable utilizada debe coincidir con el nombre del parámetro de la variable pasado en la solicitud de imagen. Algunas variables tienen varios parámetros aceptados que se utilizan en casos distintos. Por ejemplo, tanto `pageName=` como `gn=` pasan el nombre de la página, pero el último se usa más a menudo en implementaciones móviles y codificadas (hard-coded). Si la solicitud de imagen usa `pageName=` para pasar el nombre de página, se aceptará `D=pageName` pero no `D=gn`. Si la solicitud de imagen usa `gn=`, se aceptará `D=gn` pero no `D=pageName`.

La información siguiente se aplica a las variables dinámicas:

* Las variables dinámicas trabajan con todas las versiones del código de AppMeasurement.
* Las variables dinámicas distinguen mayúsculas de minúsculas.
* Las variables dinámicas admiten cadenas literales entre comillas.
* La sustitución de las variables dinámicas tiene lugar antes de procesar las reglas, los datos de VISTA y otros elementos.
* El prefijo "D=" de las variables dinámicas debe situarse al principio del valor de la variable y no en mitad de este. Por ejemplo, utilice `c2='D="test7"+User-Agent'` en lugar de `c2='"test7"+D=User-Agent'`.

* Al igual que con todas las técnicas de implementación, Adobe recomienda encarecidamente realizar pruebas exhaustivas de las implementaciones de variables dinámicas en un entorno de desarrollo antes de su implementación en producción. Como las cadenas completas que se copian no están visibles en las herramientas de depuración del lado del cliente, revise los informes de Analytics que se vean afectados para confirmar que la implementación se ha realizado correctamente.
* Cuando copie valores entre variables con distintas longitudes máximas, tenga en cuenta que si copia un valor que exceda la longitud máxima de la variable de destino, se provocará un truncamiento. Por ejemplo, las variables [!UICONTROL Tráfico personalizado] tienen un límite de 100 caracteres y las variables [!UICONTROL Conversión personalizada] tiene un límite de 255 caracteres. Si copia un valor de 150 caracteres desde s.eVar1 a s.prop1 utilizando variables dinámicas, este valor quedará truncado en el informe [!UICONTROL Tráfico personalizado] en los 100 caracteres.

## Ejemplos de variables dinámicas {#section_5CE4468D978540FBA384B9D6477C92EC}

<!-- 

dynvars_examples.xml

 -->

Ejemplos de variables dinámicas que se pueden usar en Analytics.

En la solicitud de imagen de Adobe que se produce en la vista de página, si está utilizando variables dinámicas para copiar el valor de [!UICONTROL Tráfico personalizado ] en [!UICONTROL Conversión personalizada ], debería ver `v1=D=c1`1=1. Si eVar1 recibió un valor previamente en la solicitud, los servidores de Adobe copian dinámicamente el valor de [!UICONTROL Tráfico personalizado 1] en [!UICONTROL Conversión personalizada 1] durante el procesamiento de los datos. Como resultado, el valor pasado originalmente usando [!UICONTROL Tráfico personalizado 1] también aparece en los informes de [!UICONTROL Conversión personalizada 1].

Recuerde que el valor `D=[variable]` debe entrecomillarse. El código de Analytics tratará esto como una cadena. Se aplicará la codificación URL a la cadena cuando se pase a Analytics (como podrá comprobar si visualiza la solicitud en DigitalPulse Debugger o una utilidad similar). Esto es normal. Los servidores de Adobe reconocen la construcción `D=[variable]` y copiarán el valor apropiado cuando se encuentren con esta cadena.

> [!NOTE] Cuando se usa la solicitud de imagen para realizar el seguimiento de vínculos, debe definirse el tipo de vínculo (descarga=lnk_d, salida=lnk_e o personalizado=lnk_o), como hace URL/nombre del vínculo (pev2). Los vínculos requieren una implementación manual mediante la inserción de código en la etiqueta `<a href>`.

> [!NOTE] No se admiten variables dinámicas junto con cookies (s_cc, s_sq, s_fid, s_vi ni las cookies establecidas por un complemento). No puede usar `D=<cookie value>`.

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
    <code class="syntax javascript">
      s.eVar1="D=pageName" 
    </code> </td> 
   <td colname="col2"> <p>Captura el valor de pageName en eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1='D=v2+":"+c2'&amp;nbsp; 
    </code> </td> 
   <td colname="col2"> <p>Concatena eVar2:prop2 en prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1=s.eVar1="D=g"&amp;nbsp; 
    </code> </td> 
   <td colname="col2"> <p>Pasa la dirección URL de la página a prop1 y eVar1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.eVar1="D=v0" 
    </code> </td> 
   <td colname="col2"> <p>Captura la campaña en eVar 1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      s.prop1='D=User-Agent+" ;- "+Accept-Language' 
    </code> </td> 
   <td colname="col2"> <p>Concatena los encabezados de aceptar idioma y agente de usuario en prop1. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      s.prop1="D=User-Agent" 
    </code> </td> 
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
    <code class="syntax javascript">
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~v0 /b/ss/rsid/?gn=Home&amp;D=~~&amp;c1=~~campaign /b/ss/rsid/?gn=Home&amp;c1=D%3dv0%3d&nbsp;is /b/ss/rsid/?gn=Home&amp;c1=%5b%5bv0%5d%5d%5b
    </code> </td> 
   <td colname="col2"> <p>Cuatro modos de establecer prop1 en una campaña. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      /b/ss/rsid/?gn=Home&amp;D=~~&amp;c2=~~x-up-subno 
    </code> </td> 
   <td colname="col2"> <p> Extrae el encabezado x-up-subno de prop2. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code>
      c1=D%3DUser-Agent 
    </code> </td> 
   <td colname="col2"> <p> Convierte prop1 en una variable dinámica que se rellena con el encabezado HTTP User-Agent. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;c1=D%3D%22test%22 
    </code> </td> 
   <td colname="col2"> <p> Convierte prop1 en una variable dinámica que se rellena con la cadena “test”. Resulta mucho más útil si se usa junto con la concatenación con el operador +. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;c1=D%3D%22US%3A%20%22%2BUser-Agent 
    </code> </td> 
   <td colname="col2"> <p> Convierte prop1 en una variable dinámica que se rellena con el encabezado User-Agent y el prefijo “UA:” </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> 
    <code class="syntax javascript">
      &amp;vid=D%3DX-TM-ANTID 
    </code> </td> 
   <td colname="col2"> <p> Este ejemplo busca un encabezado único en este caso, X-TM-ANTID. </p> </td> 
  </tr> 
 </tbody> 
</table>
