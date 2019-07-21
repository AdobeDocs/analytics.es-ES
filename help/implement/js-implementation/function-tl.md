---
description: El seguimiento de las descargas de archivos y los vínculos de salida se puede realizar automáticamente en función de los parámetros configurados en el archivo de AppMeasurement para JavaScript.
keywords: Implementación de Analytics
seo-description: El seguimiento de las descargas de archivos y los vínculos de salida se puede realizar automáticamente en función de los parámetros configurados en el archivo de AppMeasurement para JavaScript.
seo-title: Función s.tl() - Seguimiento de vínculos
solution: Analytics
subtopic: Seguimiento de vínculos
title: Función s.tl() - Seguimiento de vínculos
topic: Desarrollador e implementación
uuid: f 28 f 071 a -8820-4 f 74-89 cd-fd 2333 a 21 f 22
translation-type: tm+mt
source-git-commit: acaea784c977d7ff438f84faf8af5a3c605e3cf5

---


# Función s.tl() - Seguimiento de vínculos

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

## Función s.tl() - Seguimiento de vínculos {#concept_EA13689CB8EE4F308FC89A1293046D5E}

File downloads and exit links can be automatically tracked based on parameters set in the [!DNL AppMeasurement] for JavaScript file.

Si es necesario, se puede realizar el seguimiento de estos tipos de vínculos manualmente mediante el código de vínculo personalizado. Además, el código de vínculo personalizado se puede utilizar para realizar el seguimiento de vínculos personalizados genéricos que, a su vez, se pueden usar para diversos tipos de seguimiento e informes.

## Referencia de parámetros de s.tl() {#section_DDF19EE3ACE24EFAB2D65CD4B0D7DBC4}

<!-- Meike, I converted a table within to table to this section. Please check against orginal file -Bob -->

**this**

El primer argumento siempre debe configurarse como este valor (predeterminado) o como true. El argumento hace referencia al objeto pulsado; cuando se configura como "this", hace referencia a la propiedad HREF del vínculo.

Si está implementando el seguimiento de vínculos en un objeto que no tiene propiedad HREF, siempre debe establecer este argumento en "this".

Dado que, a menudo, al hacer clic en un vínculo, el visitante sale de la página actual, se aplica una demora de 500 ms para asegurar que se envíe una solicitud de imagen a Adobe antes de que el usuario abandone la página. Esta demora solo es necesaria al abandonar la página pero, por lo general, está presente cuando se llama la función s.tl(). Si desea desactivar la demora, pase la palabra clave 'true' como el primer parámetro al llamar a la función s.tl().

**linkType**

`s.tl(this,linkType,linkName, variableOverrides, doneAction)`

linkType tiene tres posibles valores, en función del tipo de vínculo que se desea capturar. Si el vínculo no es descarga o de salida, debe elegir la opción Vínculos personalizados.

| Tipo | Valor de linkType |
|--- |--- |
| Descargas de archivos | 'd' |
| Vínculos de salida | 'e' |
| Vínculos personalizados | 'o' |

**linkName**

Puede ser cualquier valor personalizado de hasta 100 caracteres. Esto determina cómo se muestra el vínculo en el informe apropiado.

**variableOverrides**

(Opcional; pase null si no se usa) Permite cambiar los valores de la variable para esta llamada única; es similar a otras bibliotecas de [!DNL AppMeasurement].

**useForcedLinkTracking**

Esta marca se usa para deshabilitar el seguimiento de vínculos forzado para algunos exploradores. El seguimiento de vínculos forzado está habilitado de forma predeterminada para los exploradores FireFox 20+ y WebKit.

Valor predeterminado = true

Ejemplo: `s.useForcedLinkTracking& = false`

**forcedLinkTrackingTimeout**

El número máximo de milisegundos que hay que esperar para que finalice el seguimiento antes de ejecutar el parámetro doneAction que se pasó a `s.tl`. Este valor especifica el tiempo de espera máximo. Si la llamada de seguimiento de vínculos se completa antes de este tiempo de espera, el parámetro doneAction se ejecuta inmediatamente. Si nota que las llamadas de seguimiento de vínculos no se completan, es posible que tenga que aumentar este tiempo de espera.

Valor predeterminado = 250

Ejemplo: `s.forcedLinkTrackingTimeout&nbsp;=&nbsp;500`

**doneAction**

Parámetro opcional para especificar la acción de navegación que se ejecutará una vez completada la llamada de seguimiento de vínculos cuando useForcedLinkTracking está habilitada.

Sintaxis:

`s.tl(linkObject,linkType,linkName,variableOverrides,doneAction)`

doneAction: (opcional) Especifica la acción que se efectuará cuando la llamada de seguimiento de vínculos se haya enviado o cuando se haya acabado su tiempo de espera, conforme al valor especificado por:

`s.forcedLinkTrackingTimeout`

La variable doneAction puede ser la cadena 'navigate', lo que hace que el método configure `document.location` como el atributo href de linkObject . La variable doneAction también puede ser una función que permita una mayor personalización.

Si se proporciona un valor para doneAction en un evento onClick con delimitador, debe devolver false después de la llamada a `s.tl` para evitar la navegación predeterminada del explorador.

Para imitar el comportamiento predeterminado y seguir la dirección URL especificada por el atributo href, proporcione una cadena 'navigate' como doneAction .

De forma opcional, puede proporcionar su propia función para que se ocupe del evento de navegación pasando esta función como doneAction .

Ejemplos:

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a> <a href="#" onclick="s.tl(this,'o','MyLink',null,function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

**Ejemplo**

El ejemplo siguiente de una función [!UICONTROL s.tl()] utiliza la demora predeterminado de 500 ms para asegurarse de que los datos se recopilan antes de salir de la página.

```js
s.tl(this,'o','link name');
```

El ejemplo siguiente deshabilita la demora de 500 ms, si el usuario no va a salir de la página o siempre que el objeto donde se hace clic no tenga HREF.

```js
s.tl(true,'o','link name');
```

La demora de 500 ms es la demora máxima. Si la imagen solicitada se devuelve en menos de 500 ms, la demora se detiene inmediatamente. Esto permite al visitante moverse a la siguiente página o la siguiente acción dentro de la página.

Los siguientes son ejemplos de gestión de vínculos personalizados en exploradores WebKit:

```js
<a href="..." onclick="s.tl(this,'o','MyLink',null,'navigate');return false">Click Here</a>
```

```js
<a href="#"  onclick="s.tl(this,'o','MyLink',null,  
function(){if(confirm('Proceed?'))document.location=...});return false">Click Here</a>
```

>[!NOTE]
>
>Los usos del código de vínculo personalizado suelen ser muy específicos del sitio Web y de las necesidades de informes. Antes de implementar código de vínculo personalizado, póngase en contacto con el Servicio de atención al cliente o con su asesor de Adobe para averiguar cuáles son sus posibilidades y cómo puede aprovechar mejor esta función conforme a sus necesidades empresariales.

El código básico para realizar el seguimiento de un vínculo mediante código de vínculo personalizado se muestra en el siguiente ejemplo:

```js
<a href="index.html" onClick="s.tl(this,'o','Link Name')">My Page</a>
```

>[!NOTE]
>
>The [!UICONTROL s_gi] function must contain your report suite ID as a function parameter. Asegúrese de cambiar la [!DNL rsid] por la ID exclusiva de su grupo de informes.

>[!NOTE]
>
>Si no se define el parámetro del nombre del vínculo, la URL del vínculo (determinada desde el objeto "this") se utiliza como nombre del vínculo.

Las variables de [!DNL Analytics] se pueden definir como parte del código de vínculo personalizado.

## Seguimiento automático de vínculos de salida y descargas de archivos {#concept_DF078C5C1B004695B3B7C4536C99D4B2}

El archivo JavaScript se puede configurar para que rastree de manera automática las descargas de archivos y los vínculos de salida, según los parámetros que definen los tipos de archivos de las descargas de archivos y los vínculos de salida.

<!-- 

link_automatic.xml

 -->

Los parámetros que controlan el seguimiento automático son los que se mencionan a continuación:

```js
s.trackDownloadLinks=true 
s.trackExternalLinks=true 
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,doc,pdf,xls" 
s.linkInternalFilters="javascript:,mysite.com,[more filters here]" 
s.linkLeaveQueryString=false 
```

Los parámetros *`trackDownloadLinks`**`trackExternalLinks`* y determinar si está activada la descarga automática de archivos y el seguimiento de vínculos de salida. When enabled, any link with a file type matching one of the values in *`linkDownloadFileTypes`* is automatically tracked as a file download. Any link with a URL that does not contain one of the values in *`linkInternalFilters`* is automatically tracked as an exit link.

In JavaScript H.25.4 (released February 2013), automatic exit link tracking was updated to always ignore links with `HREF` attributes that start with `#`, `about:`, or `javascript:`.

## Example 1 {#section_504D163608E14B25A8B4CA9D615C6735}

The file types [!DNL jpg] and [!DNL aspx] are not included in *`linkDownloadFileTypes`* above, therefore no clicks on them are automatically tracked and reported as file downloads.

The parameter *`linkLeaveQueryString`* modifies the logic used to determine exit links. When *`linkLeaveQueryString`*=false, exit links are determined using only the domain, path, and file portion of the link URL. When *`linkLeaveQueryString`*=true, the query string portion of the link URL is also used to determine an exit link.

## Example 2 {#section_25660B64E28248A0BC982B2AF5603C0E}

Con la siguiente configuración, el ejemplo que se muestra a continuación será contabilizado como un vínculo de salida:

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=false 
 
//HTML file 
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site!</a> 
```

## Ejemplo 3 {#section_2A78D05162D640169844A7D1E9799BAA}

Con la siguiente configuración, el vínculo que se muestra no contará como vínculo de salida:

```js
//JS file  
s.linkInternalFilters="javascript:,mysite.com" 
s.linkLeaveQueryString=true 
 
//HTML  
<a href='https://othersite.com/index.html?r=mysite.com'>Visit Other Site</a> 
```

>[!NOTE]
>
>Un solo vínculo solo se puede rastrear como descarga de archivo o como vínculo de salida, con prioridad de descarga de archivo. If a link is both an exit link and file download based on the parameters *`linkDownloadFileTypes`* and *`linkInternalFilters`*, it is tracked and reported as a file download and not an exit link. La siguiente tabla resume el seguimiento automático de descargas de archivos y de vínculos de salida.

## Seguimiento manual de vínculos con el código de vínculo personalizado {#concept_7113B5D037BE4622B6934554C6D18F96}

El código de vínculo personalizado permite realizar el seguimiento de descargas de archivos, vínculos de salida y vínculos personalizados en situaciones en las que el seguimiento automático no es suficiente o no se puede aplicar.

<!-- 

link_manual.xml

 -->

Generalmente, el código de vínculo personalizado se implementa agregando un controlador de eventos [!UICONTROL onClick] a un vínculo o agregando código a una rutina existente. Se puede implementar prácticamente desde cualquier controlador de eventos o función de JavaScript.

Link Tracking consists of calling the [!DNL AppMeasurement] for JavaScript function whenever the user performs actions that generate data you want to capture. Esta función, [!UICONTROL s.tl()], se llama directamente en un controlador de eventos, como [!UICONTROL onClick] o [!UICONTROL onChange], o desde una función separada. Esta función [!UICONTROL s.tl()] tiene cinco argumentos. Los tres primeros son obligatorios:

```js
s.tl(this,linkType,linkName, variableOverrides, doneAction)
```

## Seguimiento de vínculos personalizados en los exploradores FireFox y WebKit {#section_F2B9A2A3CC1F4BB9A64456BC39FC50B9}

JavaScript H.25 incluye una actualización para garantizar que el seguimiento de vínculos se complete de forma satisfactoria en exploradores WebKit (Safari y Chrome). JavaScript H.26 incluye una actualización para garantizar que el seguimiento de vínculos se complete de forma satisfactoria en FireFox 20+.

Tras esta actualización, se realizará un seguimiento correcto de los vínculos de descarga y salida cuyo seguimiento es automático (determinado por [!DNL s.trackDownloadLinks] y [!DNL s.trackExternalLinks]). Si está realizando el seguimiento de los vínculos personalizados con las llamadas de JavaScript manuales, debe modificar cómo se realizan estas llamadas. Por ejemplo, el seguimiento de los vínculos de salida y de descarga se realiza a menudo utilizando código similar al siguiente:

```js
<a href="https://anothersite.com" onclick="s.tl(this,'e','AnotherSite',null)">
```

Internet Explorer ejecuta la llamada de seguimiento de vínculos y abre la nueva página. Otros exploradores podrían cancelar la ejecución de la llamada de seguimiento de vínculos al abrirse la nueva página. Con frecuencia, esto suele impedir que las llamadas de seguimiento de vínculos se completen.

Para solucionar este comportamiento, H.25 (lanzado en julio de 2012) incluye un método de sobrecarga de seguimiento de vínculos ([!DNL s.tl]) que obliga los exploradores a esperar a que se complete la llamada de seguimiento de vínculos. Este nuevo método ejecuta la llamada de seguimiento de vínculos y se ocupa del evento de la navegación en lugar de utilizar la acción predeterminada del explorador. Este método de sobrecarga requiere un parámetro adicional, llamado [!UICONTROL doneAction], para especificar la acción que debe realizarse cuando se completa la llamada de seguimiento de vínculos.

Para utilizar este nuevo método, actualice las llamadas a [!DNL s.tl] con un parámetro adicional [!UICONTROL doneAction], similar al siguiente:

```js
<a href="https://anothersite.com"  
onclick="s.tl(this,'e','AnotherSite',null,'navigate');return false">
```

Al hacer pasar navigate como [!UICONTROL doneAction] se refleja el comportamiento predeterminado del explorador y abre la dirección URL especificada por el atributo href cuando se completa la llamada de seguimiento.

En JavaScript H.25.4 (lanzado en febrero de 2013), se agregaron las siguientes limitaciones de ámbito a los vínculos seguidos cuando `useForcedLinkTracking` está habilitada. El seguimiento de vínculo forzado automático solo se aplica a:

* `<A>` y `<AREA>` etiquetas.
* La etiqueta debe tener un atributo `HREF`
* The `HREF` can't start with `#`, `about:`, or `javascript:`.
* The `TARGET` attribute must not be set, or the `TARGET` needs to refer to the current window ( `_self`, `_top`, or the value of `window.name`).

## Seguimiento de vínculos mediante una solicitud de imagen {#concept_FF31C8D1B3DF483D853BF0A9D637F02F}

Los vínculos pueden rastrearse sin llamar a la función s.tl() construyendo una solicitud de imagen.

<!-- 

link_img.xml

 -->

Las solicitudes de imagen se codifican agregando el parámetro "pe" al parámetro src de la solicitud de imagen, de la siguiente manera:

```
pe=[type]
```

Where `[type]` is replaced with the type of link you want to track:

* lnk_d = descarga
* lnk_e = salida
* lnk_o = personalizado

Además, se puede especificar una dirección URL de vínculo pasando la dirección URL en el parámetro pev1:

```
pev1=mylink.com
```

Se puede especificar un nombre de vínculo pasando el nombre en el parámetro pev2:

```
pev2=My%20Link
```

Por ejemplo:

```
<img src="https://collectiondomain.112.2o7.net/b/ss/reportsuite/1/H.25.3--NS/0?pe=lnk_e&pev1=othersite.com&pev2=Offsite%20Link" width="1" height="1" border="0" />
```

## Configuración de variables adicionales para descargas de archivos, vínculos de salida y vínculos personalizados {#concept_8DD06387D5234A52A6E361572FAA2DF6}

Two parameters (  and ) control which [!DNL Analytics] variables are set for file downloads, exit links, and custom links.

<!-- 

link_variables.xml

 -->

De forma predeterminada, se configuran en el archivo JS de la siguiente manera:

```js
s.linkTrackVars="None"
```

```js
s.linkTrackEvents="None"
```

El parámetro *`linkTrackVars`* debe incluir cada variable que se desea seguir con cada descarga de archivo, vínculo de salida y vínculo personalizado. The *`linkTrackEvents`* parameter should include each event you want to track with every file download, exit link, and custom link. Cuando se da uno de estos tipos de vínculo, el valor actual de cada variable se identifica como seguido.

Por ejemplo: para realizar el seguimiento de prop1, eVar1 y event1 con cada uno de los vínculos de salida, vínculos personalizados y descarga de archivos, utilice la configuración siguiente en el archivo JS global:

```js
s.linkTrackVars="prop1,eVar1,events"
```

```js
s.linkTrackEvents="event1"
```

>[!NOTE]
>
>The variable *`pageName`* cannot be set for a file download, exit link, or custom link, because each of the link types is not a page view and does not have an associated page name.

>[!NOTE]
>
>If *`linkTrackVars`* (or *`linkTrackEvents`*) is null (or an empty string), all [!DNL Analytics] variables (or events) that are defined for the current page are tracked. Es muy probable que esto aumente sin querer las instancias de cada variable, y esto debe evitarse.

## Prácticas recomendadas {#section_DA3CA596792E4BD6B5FFE89BCE0E617D}

The settings for *`linkTrackVars`* and *`linkTrackEvents`* within the JS file affect every file download, exit link, and custom link. Las instancias de cada variable y evento se pueden aumentar en situaciones en las que la variable (o el evento) se aplique a la página actual pero no a la descarga de archivo, el vínculo de salida o el vínculo personalizado en particular.

Para asegurarse de que están definidas las variables correctas con el código de vínculo personalizado, Adobe recomienda configurar *`linkTrackVars`* y *`linkTrackEvents`* dentro del código de vínculo personalizado, como se indica a continuación:

```js
<a href="index.html" onClick=" 
var s=s_gi('rsid'); 
s.linkTrackVars='prop1,prop2,eVar1,eVar2,events'; 
s.linkTrackEvents='event1'; 
s.prop1='Custom Property of Link'; 
s.events='event1'; 
s.tl(this,'o','Link Name'); 
">My Page 
```

The values of *`linkTrackVars`* and *`linkTrackEvents`* override the settings in the JS file and ensure only the variables and events specified in the custom link code are set for the specific link.

>[!NOTE]
>
>En el ejemplo anterior, el valor de prop 1 se configura dentro del propio código de vínculo personalizado. El valor de prop2 proviene del valor actual de la variable, según se ha definido en la página.

## Uso de las llamadas a funciones con código de vínculo personalizado {#concept_DB662C93B3ED415DB72C80270502BE5D}

Debido a la naturaleza compleja del código de vínculo personalizado, se puede consolidar el código dentro de una función JavaScript independiente (definida en la página o en un archivo JavaScript vinculado) y realizar llamadas a la función en el controlador de [!UICONTROL onClick].

<!-- 

link_functions.xml

 -->

For example, you could insert the following two functions in your `AppMeasurement.js` file, just below the `s_doPlugins()` function, and then use them throughout your site:

```js
/* Set Click Interaction values (with timeout - H25 code and higher*/ 

function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction',null,'navigate'); 
}
```

```js
/* Set Click Interaction values (without timeout - pre H25 code*/ 
 
function trackClickInteraction(name){ 
    var s=s_gi('rsid'); 
    s.linkTrackVars='prop42,prop35'; 
    s.prop42=name; 
    s.prop35=s.pageName; 
    s.tl(true,'o','track interaction'); 
}
```

>[!NOTE]
>
>Si es necesario, puede pasar el tipo de vínculo y el nombre del vínculo como parámetros adicionales para la función JavaScript.

Para llamar a estas funciones, use código similar al siguiente:

```
<a href=”https://www.your-site.com/some_page.php” onclick=”trackClickInteraction('this.href');”>Link Text</a>
```

## Evitar recuentos de vínculos duplicados {#section_9C3F73DE758F4727943439DED110543C}

Puede ocurrir que un vínculo se cuente dos veces si suele capturarse mediante la descarga automática de archivos o en el seguimiento de vínculos de salida.

Por ejemplo, si rastrea descargas de PDF de forma automática, el código siguiente generará un recuento de descargas duplicado:

```js
function trackDownload(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 s.tl(obj,'d','PDF Document'); 
}
```

Para asegurarse de que el vínculo no se cuenta por duplicado, use la siguiente función JavaScript modificada:

```js
<script language=JavaScript> 
function linkCode(obj) { 
 var s=s_gi('rsid'); 
 s.linkTrackVars='None'; 
 s.linkTrackEvents='None'; 
 var lt=obj.href!=null?s.lt(obj.href):""; 
 if (lt=="") { s.tl(obj,'d','PDF Document'); } 
}
```

Las dos últimas líneas del código anterior modifican el comportamiento del código de vínculo personalizado, de manera que solo se produce el comportamiento de seguimiento automático. Así se eliminan los posibles recuentos duplicados.

## Ventanas emergentes con useForcedLinkTracking {#concept_0AC4BA3A64B84CCB8D9A6021A022D1C3}

When `useForcedLinkTracking` is enabled, [!DNL AppMeasurement] overrides the default link behavior on some browsers to prevent the track link call from being canceled when the new page opens. [!DNL AppMeasurement] ejecuta esta llamada y administra el evento de navegación de forma manual, en lugar de realizar la acción predeterminada del explorador.

<!-- 

link_popups.xml

 -->

When tracking some links that open a popup window, the Chrome built-in popup blocker might prevent [!DNL AppMeasurement] from opening a popup window that would normally be allowed. To avoid this, add a `target="_blank"` attribute to calls that open a window:

```
<a href="./popup.html" target="_blank" onClick="<a href="./popup.html" onclick="s.tl(this,'o','popup',null,'navigate');javascript:window.open('./popup.html','popup','width=550,height=450'); 
return false;">
```

De este modo, el vínculo podrá rastrearse y los elementos emergentes se cargarán según lo esperado.

## Vínculos desde abreviadores de URL {#concept_CD792362A8E04448B452BE9A18772024}

De los vínculos desde servicios de abreviadores de URL (como bit.ly) no se suele realizar un seguimiento como vistas de página o referentes. Estos servicios devuelven redireccionamientos 301/302 con la dirección URL completa al explorador web, que, a su vez, envía una solicitud nueva distinta a la dirección URL completa. El referente original se conserva, ya que el abreviador ya no está en el bucle, y no hay indicación en la solicitud de que se haya usado un servicio de redireccionamiento para obtener la dirección URL.

<!-- 

link_shortener.xml

 -->

Debido a la variedad de servicios disponibles, recomendamos que pruebe las situaciones específicas que se usen en su sitio para
determinar el mecanismo de redireccionamiento del servicio.

## Variables de seguimiento de vínculos en doPlugins {#concept_B5AC1D4372AA4A7D8C7871453A4F1215}

Para facilitar la administración del seguimiento de vínculos, las siguientes variables se rellenan antes de que se ejecute la función `doPlugins`.

<!-- 

util_linkhandler.xml

 -->

En `doPlugins` puede usar los valores siguientes para modificar el comportamiento de seguimiento de los vínculos. Por ejemplo, puede anular el seguimiento o agregar otras variables a las solicitudes de seguimiento.

<table id="table_55CCF4F2BF474FD3B703C926B896B392"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variable </th> 
   <th colname="col2" class="entry"> Descripción </th> 
   <th colname="col3" class="entry"> Impacto  </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> linkType </td> 
   <td colname="col2"> <p>Contiene el tipo de vínculo determinado automáticamente, si hubiera. Se puede configurar como uno de los siguientes: </p> 
    <ul id="ul_81ACB5D00D774E86AFD22C61AD4D0E2C"> 
     <li id="li_52B6F2B124024DEFB422D1E9E97254C0">d (descarga) </li> 
     <li id="li_E842C2E64F034181A364C639C30451FD">e (salida) </li> 
     <li id="li_3263F378CE65407E81B6C5C597CED1E8">o (personalizado/otro) </li> 
    </ul> <p>Este es el parámetro <code>pe</code> en la solicitud de imagen. </p> </td> 
   <td colname="col3"> <p>Si se configura con <code>linkURL</code> o <code>linkName</code>, se envía una llamada al servidor como un vínculo de descarga, de salida o personalizado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkName </td> 
   <td colname="col2"> <p>Nombre que aparecerá en el informe de vínculos personalizados, de descarga o de salida. Se trunca a los 100 caracteres. Se puede configurar como cualquier cadena. </p> <p>Este es el parámetro <code>pev2</code> en la solicitud de imagen. </p> </td> 
   <td colname="col3"> <p> Si se configura con <code>linkType</code>, se enviará una solicitud de imagen como un vínculo de descarga, de salida o personalizado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkURL </td> 
   <td colname="col2"> <p>La dirección URL del vínculo que actúa como nombre si no existe ningún valor para linkName. Se puede establecer en cualquier cadena de URL. </p> <p>Este es el parámetro <code>pev1</code> en la solicitud de imagen. </p> </td> 
   <td colname="col3"> <p>Si se configura con <code>linkType</code>, se enviará una solicitud de imagen como un vínculo de descarga, de salida o personalizado </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> linkObject </td> 
   <td colname="col2"> <p>El objeto en el que se hace clic para obtener la referencia. Es de solo lectura. </p> </td> 
   <td colname="col3"> <p>No ejerce un impacto directo sobre la medición. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Ejemplo**

```js
function s_doPlugins(s) { 
    if (s.linkType == "d" && s.linkURL.indexOf(".aspx?f=") { 
        //special tracking for .aspx file download script 
        s.eVar11 = s.linkURL.substring(s.linkURL.lastIndexOf("?f=") + 3, s.linkURL.length); 
    } 
  
    else if (s.linkType == "o" ) { 
        // note: linkType is set to "o" only if you make a custom call 
        // to s.tl() and set the link type to "o". Automatically tracked 
        // links are set to "d" or "e" only. 
        s.eVar10 = s.LinkURL; 
    } 
}
```

## Validación de descargas de archivos, vínculos de salida y vínculos personalizados {#concept_0B43AD582D3E470899FCCB58E44D3D49}

Para validar por completo los vínculos de descarga, de salida y personalizados, Adobe recomienda utilizar un analizador de paquetes para examinar los vínculos en tiempo real.

<!-- 

downloads_validate.xml

 -->

Puesto que las descargas de archivos, los vínculos de salida y los vínculos personalizados no son vistas de páginas, no se puede utilizar la herramienta [!UICONTROL DigitalPulse Debugger] para comprobar los parámetros ni la configuración de las variables. Debe usar [analizador de paquetes](../../implement/impl-testing/packet-monitor.md#concept_490DF35E06D44234A91B5FC57C0BF258) para ver los datos de vínculos de seguimiento.
