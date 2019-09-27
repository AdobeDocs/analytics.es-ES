---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Implementación de análisis
seo-description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
seo-title: Variables de página
solution: Analytics
subtopic: Variables
title: Variables de página
topic: Desarrollador e implementación
uuid: 2578eddd-74db-4a8a-96f2-d0289ec1826b
translation-type: tm+mt
source-git-commit: 0dbc8ac9b416ce50f197a884bb71c6cd389cd0bb

---


# Variables de página

Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

La variable muestra la altura de la ventana del explorador.

<!-- 
browserheight.xml
-->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

**Parámetros**

<table id="table_94598A2204CF42FF9DD14D353D5C0468"> 
 <thead> 
  <tr> 
   <th class="entry"> Parámetro de consulta </th> 
   <th class="entry"> Valor </th> 
   <th class="entry"> Ejemplo </th> 
   <th class="entry"> Informes afectados </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>bh </p> </td> 
   <td> <p>Número entero positivo </p> </td> 
   <td> <p>865 </p> </td> 
   <td> <p>Tráfico &gt; Tecnología &gt; Altura del explorador </p> </td> 
  </tr> 
 </tbody> 
</table>

## browserWidth {#concept_BA0C4C2D655D41A4AEF059E21E4A55A2}

La variable muestra la anchura de la ventana del explorador.

<!-- 

browserwidth.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

**Parámetros**

<table id="table_B70F279A8CD240328520E5BD889806BD"> 
 <tbody> 
  <tr> 
   <td> <p> <b>Parámetro de consulta</b> </p> </td> 
   <td> <p> <b>Valor</b> </p> </td> 
   <td> <p> <b>Ejemplo</b> </p> </td> 
   <td> <p> <b>Informes afectados</b> </p> </td> 
  </tr> 
  <tr> 
   <td> <p>bw </p> </td> 
   <td> <p>Número entero positivo </p> </td> 
   <td> <p>1179 </p> </td> 
   <td> <p>Tráfico &gt; Tecnología &gt; Ancho del explorador </p> </td> 
  </tr> 
 </tbody> 
</table>

## campaign {#concept_C7BF7B8A69D048A6AB482052A98A91F8}

La variable identifica las campañas de marketing utilizadas para atraer visitantes a un sitio. El valor de generalmente se toma de un parámetro de cadena de consulta.

<!-- 

campaign.xml

 -->

**Parámetros**

<table id="table_A35175678B6C4D3D86287199AFBE6803"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>255 bytes </p> </td> 
   <td> <p>v0 </p> </td> 
   <td> <p>Conversión &gt; Campañas &gt; Código de seguimiento </p> </td> 
   <td> <p>"" </p> </td> 
  </tr> 
 </tbody> 
</table>

Todos los elementos de una campaña de marketing deben tener asociado un código de seguimiento único. Por ejemplo, una palabra clave de pago del motor de búsqueda puede tener un código de seguimiento 112233. Cuando alguien hace clic en la palabra clave con el código de seguimiento 112233 y es enrutado al sitio web correspondiente, la variable *`campaign`* registra el código de seguimiento.

There are two main ways to populate the *`campaign`* variable:

* El complemento [!UICONTROL getQueryParam], usado en el archivo JavaScript, recupera un parámetro de cadena de consulta de la dirección URL. Para obtener más información sobre el complemento [!UICONTROL getQueryParam], consulte [Complementos de implementación](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Assign a value to the  variable in the HTML on the Web page.*`campaign`*

With either method of populating the  variable, the Back button traffic may inflate the actual number of click-throughs from a campaign element.*`campaign`*

Por ejemplo, un visitante entra en el sitio haciendo clic en una palabra clave de búsqueda de pago. Cuando el visitante llega a la página de aterrizaje, la dirección URL contiene un parámetro de cadena de consulta que identifica el código de seguimiento de la palabra clave. Después, el visitante hace clic en un vínculo a otra página, pero inmediatamente hace clic en el botón Atrás para volver a la página de aterrizaje. Cuando el visitante llega por segunda vez a la página de aterrizaje, la dirección URL con el parámetro de cadena de consulta identifica de nuevo el código de seguimiento y se registra una segunda pulsación, aumentando incorrectamente el número de pulsaciones.

Para evitar este aumento incorrecto del número de pulsaciones, Adobe recomienda usar el complemento [!UICONTROL getValOnce] para forzar que cada pulsación de la campaña se cuente solo una vez. Para obtener más información sobre el complemento [!UICONTROL getValOnce], consulte [Complementos de implementación](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**Sintaxis y valores posibles** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

The *`campaign`* variable has the same limitations as all other variables. Adobe recomienda limitar el valor a los caracteres ASCII estándar.

**Distinción entre mayúsculas y minúsculas** {#section_112A9A0F886148B6BEF9A7C94BE0A36F}

Las eVars no distinguen entre mayúsculas y minúsculas, pero se muestran en la escritura en mayúsculas de la primera aparición. Por ejemplo, si la primera instancia de eVar1 es "Sesión iniciada" pero todas las demás instancias se pasan como "sesión iniciada", los informes siempre mostrarán "Sesión iniciada" como valor de eVar.

**Ejemplos** {#section_705A25D05F6848E29C78320247AECB5F}

```js
s.campaign="112233"
```

```js
s.campaign=s.getQueryParam('cid');
```

**Parámetros de configuración** {#section_4083F281968443169EAF8C0E8529D7BC}

Cada valor de campaign permanece activo para un usuario y recibe el crédito por las actividades y los eventos de éxito de dicho usuario hasta que caduque. La caducidad de la variable campaign se modifica en Admin Console.

**Problemas, preguntas y consejos** {#section_94B5C4BF9DE84BA3A16F9E9E9D197F0C}

* Para evitar aumentar incorrectamente el número de pulsaciones, use el complemento [!UICONTROL getValOnce] para que las pulsaciones de una campaña se cuenten solo una vez por sesión. Para obtener más información sobre el complemento [!UICONTROL getValOnce], consulte [Complementos de implementación](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Para obtener más información sobre el seguimiento de campañas de marketing y las compras por palabras clave, consulte [Campañas](https://marketing.adobe.com/resources/help/en_US/reference/campaign.html).
* Use [!DNL DigitalPulse Debugger] para ver el valor real de las campañas (v0 en el depurador). Si v0 no aparece en el depurador, no se han registrado datos de la campaña para esa página.

## canal {#concept_C7770B8C15724A99B10F8F468AF82D0D}

La variable se utiliza generalmente para identificar una sección del sitio. 

<!-- 

channel.xml

 -->

Por ejemplo: un comerciante puede tener secciones como Electrónica, Juguetes o Ropa. Un sitio de medios puede tener secciones como Noticias, Deportes o Negocios.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | CH | Contenido del sitio &gt; Secciones del sitio | "" |

Adobe recomienda rellenar la variable channel en cada página. También puede activar una correlación entre las variables *`channel`* y [!UICONTROL pageName].

When sections have one or more levels of subsections, you can show those sections in the *`channel`* variable or use separate variables to identify levels.

**Sintaxis y valores posibles** {#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

The *`channel`* variable has no extra limitations on its values.

**Ejemplos** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Problemas, preguntas y consejos** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

If your site contains multiple levels, you can use the *`hierarchy`* or another variable to designate those levels. The *`channel`* value does not persist, but the success events fired on the same page are attributed to the *`channel`* value.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

La variable se utiliza para mostrar el número de bits usado para mostrar el color en cada píxel de la pantalla.

<!-- 

colordepth.xml

 -->

Por ejemplo, 32 representa 32 bits de color en la pantalla. Esta variable se rellena después del código de página y antes de que *`doPlugins`* se ejecute.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en `props/eVars`, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| c | 8, 16 y 32 | 32 | Tráfico &gt; Tecnología &gt; Profundidad de color del monitor |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

La variable , en Internet Explorer, indica si el explorador está configurado con una conexión LAN o de módem.

<!-- 

conntype.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en `props/eVars`, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| ct | lan o modem | lan | Tráfico &gt; Tecnología &gt; Tipo de conexión |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

La variable indica si JavaScript puede configurar una cookie de sesión de origen.

<!-- 

cookiesenabled.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en `props/eVars`, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo |
|---|---|---|
| k | Y o N | Y |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

(Obsoleta) La variable permite seleccionar el centro de datos al que se envían los datos.

<!-- 

dc.xml

 -->

>[!NOTE]
>
>La variable dc está obsoleta. Debe configurar *`trackingServer`para todas las implementaciones con el valor generado por el Administrador de códigos en s_code.js.*

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | 112 |

El centro de datos se identifica en la variable *`dc`* para que coincida con [!UICONTROL ActionSource].

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

Las variables [!UICONTROL eVar] se usan para generar informes personalizados.

<!-- 

eVarN.xml

 -->

Cuando se establece un valor en una eVar para un visitante, el valor se recuerda hasta que caduca. Cualquier evento de éxito que encuentra el visitante mientras la eVar está activa se contabiliza en el valor de eVar.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 255 bytes | V1-v75 ( or v100 or v250)[](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28) | Conversión personalizada | "" |

**Caducidad** {#section_6DB5882B960D4660AE248B91B76883C4}

Las [!UICONTROL eVars] caducan después del período de tiempo que especifique. Cuando la eVar caduca, ya no recibe el crédito por los eventos de éxito. Las eVars también se pueden configurar para que caduquen cuando se produzcan eventos de éxito. Por ejemplo, si tiene una promoción interna que caduca el final de una visita, la promoción interna recibe el crédito solo por las compras o registros que se produzcan durante la visita en la que se activaron.

Hay dos maneras de que una eVar caduque:

* Puede configurar la eVar para que caduque después de un período de tiempo o evento especificados.
* Puede forzar la caducidad de una eVar, lo que resulta útil cuando se cambia el propósito de una variable.

Si se utiliza una eVar en mayo para reflejar promociones internas y caduca después de 21 días, y en junio se utiliza para capturar palabras clave de búsqueda interna, entonces el 1 de junio debe forzar la caducidad o restablecer la variable. Al hacerlo, no se incluyen los valores de la promoción interna en los informes de junio.

**Distinción entre mayúsculas y minúsculas** {#section_6E9145B7FCC2438E95BB35AAE3857412}

Las eVars no distinguen entre mayúsculas y minúsculas, pero se muestran en la escritura en mayúsculas de la primera aparición. Por ejemplo, si la primera instancia de eVar1 es "Sesión iniciada" pero todas las demás instancias se pasan como "sesión iniciada", los informes siempre mostrarán "Sesión iniciada" como valor de eVar.

**Contadores**{#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

Aunque las eVars se usan habitualmente para guardar valores de cadena, también se pueden configurar para que actúen como contadores. Las eVars son útiles como contadores para contar el número de acciones que un usuario realiza antes de un evento. Por ejemplo, puede usar una eVar para capturar el número de búsquedas internas antes de la compra. Cada vez que un visitante realiza una búsqueda, la eVar debe contener un valor de '+1'. Si un visitante realiza cuatro búsquedas antes de una compra, verá una instancia con cada recuento total: 1.00, 2.00, 3.00 y 4.00. Sin embargo, solo el valor 4.00 recibe el crédito por el evento purchase (métricas de pedidos e ingresos). Solo se permiten números positivos como valores de un contador eVar.

**Subrelaciones** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

Uno de los requisitos habituales para un informe de [!UICONTROL eVar personalizado] es la posibilidad de desglosar un informe de [!UICONTROL eVar personalizado] por otro. Por ejemplo, si una eVar contiene el sexo y otra contiene el sueldo, puede preguntarse lo siguiente: de las mujeres visitantes de mi sitio, ¿cuántos ingresos generaron las mujeres que ganan más de 50.000 euros al año? Las eVars con subrelaciones completas admiten este tipo de desglose en los informes. Por ejemplo, si la eVar del sexo tiene habilitadas subrelaciones completas, todos los demás informes de eVar personalizados se pueden desglosar por sexo, y el sexo se puede desglosar por todos los demás. Para ver la relación entre dos informes, solo uno de ellos necesita tener habilitadas las subrelaciones completas. De forma predeterminada, los informes [!UICONTROL Campañas], [!UICONTROL Productos] y [!UICONTROL Categoría] están completamente subrelacionados (cualquier eVar se puede desglosar por campaña o productos).

**Sintaxis y valores posibles** {#section_BD46438B14F3488FB9AC42994C317B06}

While eVars may be renamed, they should always be referred to in the JavaScript file by eVarX, where X is a number between 1 and 75 ( [or 100, or 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

```js
s.eVarX="value"
```

Cuando no se usan como contadores, las eVars tienen las mismas limitaciones que todas las demás variables. Si la eVar es un "contador", se espera que reciba valores numéricos como "1" o "2,5". Si se especifican más de dos decimales, el contador de eVar redondea a dos decimales. Un contador de eVar no puede contener números negativos.

**Ejemplos** {#section_B37F4B0D56734DA3AB02BB218825BA4E}

```js
s.eVar1="logged in"
```

```js
s.eVar23="internal spring promo 4"
```

**Parámetros de configuración** {#section_BD1FE63001C84D3DB69F3DEE243960B6}

eVars can be configured in Analytics &gt; Admin &gt; Report Suites &gt; Edit Settings &gt; Conversion &gt; Conversion Variables.  Todas las eVars se pueden configurar con un [!UICONTROL Nombre], [!UICONTROL Tipo], [!UICONTROL Asignación], [!UICONTROL Caduca después de] o [!UICONTROL Restaurar]. Cada opción de configuración se trata por separado.

<table id="table_5C524B71520849FA8A9A6B79A3EE77C9"> 
 <thead> 
  <tr> 
   <th class="entry"> Configuración </th> 
   <th class="entry"> Descripción </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Nombre </td> 
   <td> Permite cambiar el nombre del informe de eVar en <span class="keyword">Analytics </span>. <p>Se debe hacer referencia a la eVar como s.eVarX en el código JavaScript, independientemente del nombre que se le asigne al informe en <span class="keyword">Analytics </span>. </p> </td> 
  </tr> 
  <tr> 
   <td> Tipo </td> 
   <td> Permite mostrar si la eVar es una Cadena de texto o un Contador. </td> 
  </tr> 
  <tr> 
   <td> Asignación </td> 
   <td> Se usa para configurar qué valor de la eVar recibe el crédito por los eventos de éxito. <p>Si Asignación se configura como "Más reciente (último)", B recibe el crédito. </p> <p>Si Asignación se configura como "Valor original (primero)", A recibe el crédito. </p> <p>Si Asignación se configura como "Lineal", tanto A como B reciben el crédito por la mitad del valor de la compra. </p> </td> 
  </tr> 
  <tr> 
   <td> Caduca después de </td> 
   <td> Permite determinar si una eVar expira cuando se produzca un evento específico, como una compra, o después de un período de tiempo personalizado o predefinido. </td> 
  </tr> 
  <tr> 
   <td> Restaurar </td> 
   <td> Al seleccionar la casilla <span class="wintitle">Restaurar</span> para una eVar y hacer clic en <span class="wintitle">Guardar</span> en la parte inferior de la página, todos los valores de esa eVar caducan inmediatamente. Cuando esto sucede, solo los nuevos valores de la eVar reciben el crédito por los eventos de éxito. </td> 
  </tr> 
 </tbody> 
</table>

**Problemas, preguntas y consejos** {#section_DA6912C802E445F986C6DE4234C6C737}

* A diferencia de las variables [!UICONTROL prop], las variables eVar no pueden ser listas de valores delimitados. Si rellena una eVar con una lista de valores, por ejemplo, "uno,dos,tres,", en los informes aparecerá exactamente esa cadena.
* Los contadores de eVar no pueden contener números negativos.

## Eventos {#concept_FFD115543D54401B98FE683BD7D5B3FE}

La variable se usa para registrar eventos de éxito comunes del carro de compras, así como eventos de éxito personalizados.

<!-- 

events.xml

 -->

<table id="table_9EB9D08C80544CD68C4B1A2012440472"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Sin límite </td> 
   <td> events </td> 
   <td> <p>Eventos del carro de compras </p> <p>Eventos personalizados </p> </td> 
   <td> N.D. </td> 
  </tr> 
 </tbody> 
</table>

Un [!UICONTROL evento] se debe considerar un hito dentro de un sitio. Los eventos de éxito generalmente se rellenan en la página de confirmación final de un proceso, como un proceso de registro o la suscripción a un boletín. Los eventos personalizados se definen rellenando la variable events con los valores literales definidos en la sección Valores posibles, a continuación.

De forma predeterminada, los eventos de éxito se configuran como eventos de *contador*. Los eventos de contador contabilizan el número de veces que se configura un evento de éxito (x+1). Los eventos también se pueden configurar como eventos *numéricos*. Los eventos numéricos permiten especificar el número que se incrementará. Esto podría ser necesario cuando se contabilizan valores dinámicos o arbitrarios, como los resultados devueltos por una búsqueda interna.

Un tipo de evento final, *moneda*, permite definir la cantidad que se sumará (similar a los eventos numéricos), pero la muestra como moneda en los informes y está sujeta a las conversiones monetarias basadas en el valor de s. *`currencyCode`* y en la configuración de moneda predeterminada para su grupo de informes. For additional information on using numeric and currency events, see [Products](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**Configuración de la variable** {#section_9195286C34C54B02B2598E2B856492C3}

La variable [!UICONTROL s.events] está habilitada de forma predeterminada para todas las implementaciones. Los siete eventos de conversión preconfigurados están habilitados automáticamente para todos los grupos de informes nuevos. New custom events (event1- [event100 or event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) can be enabled by any admin-level user using the Admin Console.

**Valores posibles** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

La lista siguiente muestra los posibles valores para la variable events:

| Evento | Descripción | Informes rellenados |
|---|---|---|
| prodView | Vistas del producto | Productos |
| scOpen | Abrir o inicializar un nuevo carro de compras | Carros de compras |
| scAdd | Agregar artículos al carro de compras | Adiciones al carro de compras |
| scRemove | Eliminar artículos del carro de compras | Eliminaciones del carro de compras |
| scView | Ver el carro de compras | Vistas del carro de compras |
| scCheckout | Comienzo del proceso de cierre de compra | Cierres de compra |
| purchase | Finalización de una compra (pedido) | Pedidos |
| event1 - event1000 (event100 para producto específico) | Eventos personalizados | Eventos personalizados |

**Sintaxis y ejemplos** {#section_45A159DF00114066B8551DDEB15E084C}

Los eventos de contador se configuran colocando los eventos deseados en la variable [!UICONTROL s.events], en una lista separada por coma (si se van a pasar varios eventos).

```js
s.events="scAdd"
```

```js
s.events="scAdd,event1,event7"
```

```js
s.events="event5"
```

```js
s.events="purchase,event10"
```

En código H23 o posterior, los eventos de contador pueden tener asignados enteros mayores que uno.

```js
s.events="event1=10"
```

```js
s.events="scRemove=3,event6,event2=4"
```

Al implementar los eventos de contador con valores enteros asignados, el evento se trata como si se hubiera activado varias veces en la solicitud de imagen. Los eventos de contador no permiten decimales; se recomienda usar eventos numéricos en su lugar si esta funcionalidad es necesaria.
Los eventos numéricos y monetarios deben incluirse en la variable [!UICONTROL s.events], aunque normalmente reciben su valor numérico (por ejemplo, 24.99) en la variable [!UICONTROL s.products]. Esto permite enlazar valores numéricos y monetarios específicos con entradas de productos individuales.

**Serialización de eventos** {#section_A89488EF4471405AAFC4D6DD05E77621}

De forma predeterminada, un evento se contabiliza cada vez que se establece el evento en su sitio.

Consulte [Serialización de eventos](../../../implement/js-implementation/event-serialization.md#concept_092B638D7FEE423D91F8A57EA8E09705) para obtener más información.

**Sintaxis** {#section_8559D42D3F344AF3BB3C0125F78C4989}

```js
s.events="event1:3167fhjkah"
```

**Ejemplos** {#section_7B5B5728A59648ADB3E2548CDAD2C9D4}

```js
s.events="scAdd:003717174"
```

```js
s.events="scAdd:user228197,event1:577247280,event7:P7fhF8571"
```

## hierN {#concept_C4475D1584D544ACB4C0A573EB60FA08}

La variable ]hierarchy[!UICONTROL  determina la ubicación de una página en la jerarquía del sitio.

<!-- 

hierN.xml

 -->

Esta variable resulta muy útil para los sitios que tienen más de tres niveles en la estructura del sitio. Por ejemplo, un sitio de noticias puede tener cuatro niveles en la sección de deportes: deportes, deportes locales, béisbol y Red Sox. Si alguien visita la página de béisbol, tanto deportes como deportes locales y béisbol reflejarán esa visita.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 255 bytes | H1-H5 | Jerarquía | "" |

Hay cinco variables [!UICONTROL hierarchy] disponibles, que deben ser habilitadas por el Servicio de atención al cliente de Adobe. En el momento de habilitar hierarchy, debe decidir un delimitador para la variable y el número de niveles de la jerarquía. Por ejemplo: si el delimitador es una coma, la jerarquía de deportes puede mostrarse de la siguiente manera.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Asegúrese de que ninguno de los nombres de sección contenga un delimitador. Por ejemplo, si una de las secciones se llama "Coach Griffin, Jim", debe elegir un delimitador que no sea una coma. Cada sección de la jerarquía se limita a 255 bytes, mientras que el límite total de la variable es de 255 bytes. Después de elegir un delimitador (en el momento de crear la jerarquía), no se puede cambiar fácilmente.

Póngase en contacto con el Servicio de atención al cliente de Adobe para obtener información sobre cómo cambiar el delimitador para una jerarquía existente. Los delimitadores también pueden consistir en múltiples caracteres, como || o /|\, que es menos probable que aparezcan en una sección de jerarquía.

**Sintaxis y valores posibles** {#section_0739948A68A2420DAB1CBEA3115A5A66}

No inserte un espacio entre los delimitadores. En el siguiente ejemplo de sintaxis, N es un número entre uno y cinco.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

No use el delimitador excepto para delimitar los niveles de la jerarquía. El delimitador puede ser cualquier carácter o caracteres que elija.

**Ejemplos** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Parámetros de configuración** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

Ninguna

**Problemas, preguntas y consejos** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* El delimitador no se puede cambiar una vez configurada la jerarquía. Si debe cambiar el delimitador para su jerarquía, comuníquese con el Servicio de Atención al cliente de Adobe.
* El número de niveles no puede cambiarse una vez configurada la jerarquía.

>[!NOTE]
>
>Changes to hierarchies can result in a service charge.

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

La variable , en Internet Explorer, indica si la página actual está configurada como página de inicio del usuario.

<!-- 

homepage.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| hp | Y o N | Y | Tráfico &gt; Tecnología &gt; Página de inicio |

## javaEnabled {#concept_F24A3536F1F0453DA214B16BAA5A6F67}

La variable indica si Java está habilitado en el explorador.

<!-- 

javaEnabled.xml

 -->

Esta variable se rellena después del código de página y antes de que doPlugins se ejecute.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| v | Y o N | Y | Tráfico &gt; Tecnología &gt; Java |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

La variable indica la versión de JavaScript que admite el explorador.

<!-- 

javascriptVersion.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Tráfico &gt; Tecnología &gt; Versión de JavaScript |

La versión H.10 y posteriores del archivo JavaScript detectan de forma precisa hasta la versión 1.7 (la última versión cuando se lanzó H.10). Las versiones anteriores del archivo JavaScript solo detectan hasta la versión 1.3

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

The  variable is an optional variable used in [!UICONTROL Link Tracking] that determines the name of a custom, download, or exit link.

<!-- 

linkName.xml

 -->

The *`linkName`* variable is not normally needed because the third parameter in the *`tl()`* function replaces it.

<table id="table_4B0D1C9AADA542A59B626E077D5FC568"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 bytes </td> 
   <td> pev2 </td> 
   <td> <p>Descargas de archivos </p> <p>Vínculos personalizados </p> <p>Vínculos de salida  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Vínculos personalizados] hace referencia a los vínculos que envían datos de seguimiento. La variable *`linkName`* variable (or the third parameter in the *`tl()`* function) is used to identify the value that appears in the [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report. If *`linkName`* is not populated, the URL of the link appears in the report.

**Sintaxis y valores posibles** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

There are no limitations on *`linkName`* outside of the standard variable limitations.

**Ejemplos** {#section_5F68766210184E82A23D2A6ECD80BA0B}

```js
s.linkName="Nav Bar Home Link"
```

```js
s.linkName="Partner Link to A.com"
```

**Parámetros de configuración** {#section_F15FF429FC274F708D50DF79D4668EA3}

Ninguna

**Problemas, preguntas y consejos** {#section_170A78452A7340B5B229713AC1FB71FA}

* The *`linkName`* variable is replaced by the third parameter in the *`tl()`* function.

* If the *`linkName`* variable and the third parameter in the *`tl()`* function are blank, the full URL of the link (with the exception of the query string) appears in the report (even if the link is relative).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

La variable es una variable opcional utilizada para el seguimiento de vínculos que determina qué informe mostrará el nombre del vínculo o la dirección URL (vínculos de salida, de descarga o personalizados).

<!-- 

linkType.xml

 -->

The *`linkType`* variable is not normally needed because the second parameter in the *`tl()`* function replaces it.

<table id="table_3D1A2FC1CECD4709BE2F9E32AC2DC730"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Un carácter </td> 
   <td> pe=[lnk_o|lnk_d|lnk_e] </td> 
   <td> <p>Descargas de archivos </p> <p>Vínculos personalizados </p> <p>Vínculos de salida  </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Los vínculos personalizados envían datos a Analytics. The *`linkType`* variable (or the second parameter in the *`tl()`* function) is used to identify the report in which the link name or URL appears ( [!UICONTROL Custom], [!UICONTROL Download], or [!UICONTROL Exit Links] report).

For exit and download Links, the  variable is automatically populated depending on whether the link clicked is an exit or download link. *`linkType`* A custom link may be configured to send data to any of the three reports with this variable or with the second parameter in the *`tl()`* function. By setting  to 'o,' 'e,' or 'd,' the  or link URL is sent to the Custom Links, Exit Links, or File Downloads report respectively.*`linkType`**`linkName`*

**Sintaxis y valores posibles** {#section_18DB3A8083FB4F75B970055ED336DA4E}

The *`linkType`* variable syntax depends on whether you use XML or a query string.

Si utiliza XML, la variable puede contener un único carácter, ya sea “o”, “e” o “d”.

```js
s.tl(this,’o’,’Link Name’);
```

If you are using the query-string `pe`, you need to use `lnk_d`, `lnk_e`, or `lnk_o`.

**Ejemplos** {#section_242B5DFFD1C9462A9A8EB1556B2E3160}

```js
<a href="index.html" onClick=" 
 var s=s_gi('rsid'); **see note below on the rsid** 
 s.tl(this,'o','Link Name'); 
 ">My Page</a> 
```

**Parámetros de configuración** {#section_59738AD1B5E94294B8D36F4E772DEDB3}

Ninguna

**Problemas, preguntas y consejos** {#section_F0D01DDE3FDA486C987162DA50A79C45}

* If  is not specified, custom links ('o') is assumed.*`linkType`*

## props de lista {#concept_83ED74232225431F83A796E22FFC75B4}

Las props de lista son una lista delimitada de valores que se pasan a una variable y, a continuación, se incluyen en los informes como elementos de línea individuales. Las props de lista generalmente se implementan en páginas que contienen valores seleccionables por el usuario como, por ejemplo, elementos enumerados con casillas de verificación o botones de opción. Resultan útiles para aquellos casos en los que desea definir varios valores en una variable sin enviar varias solicitudes de imagen.

<!-- 

list_props.xml

 -->

**Consideraciones**

* Las props de lista solo se activan en variables de tráfico ( [props](../../../implement/js-implementation/c-variables/page-variables.md#concept_0F10FA2DE69B4029A31EA5E9313AA254)).
* No se puede habilitar el control de rutas ni las correlaciones para las props de lista.
* Analytics proporciona visitas y visitantes únicos prácticamente en todos los informes, incluidos los informes de props de lista.
* Las clasificaciones son compatibles con las props de lista. 
* Cualquier variable de tráfico personalizado puede convertirse en una prop de lista. (Excepciones: [pageName](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328), [channel](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D)y [server](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2)).

* Cuando se definen valores duplicados en la misma solicitud de página, no se anula la duplicación de instancias.

Una prop puede cambiarse a una prop de lista en la página Herramientas de administración &gt; Grupo de informes &gt; Variables de tráfico al habilitar la compatibilidad de lista y luego seleccionar un delimitador. Los delimitadores habituales son: dos puntos, punto y coma, coma o barra vertical. Técnicamente puede ser cualquiera de los primeros 127 caracteres ASCII.

**Ejemplos de implementación** {#section_A3DD7293A8BB4807B42BFB1F73BE11AC}

Cuando solicite la activación de props de lista, indique el delimitador que desea usar. Después de que la *`s.prop`* que elija se active, se pueden configurar múltiples valores en la variable tal como se muestra en los ejemplos siguientes:

Una prop de lista delimitada por una barra vertical que pasa dos valores:

```js
s.prop1="Banner ad impression|Sidebar impression"
```

Una prop de lista delimitada por una coma que pasa varios valores:

```js
s.prop2="cerulean,vermilion,saffron"
```

Las props de lista también se pueden enviar con un único valor:

```js
s.prop3="Single value"
```

El delimitador puede cambiarse en cualquier momento. No obstante, la implementación debe coincidir con el nuevo delimitador. Si no se usa el delimitador correcto, el valor de la prop de lista se tratará en los informes como un solo elemento de línea concatenado.

Como una prop de lista sigue siendo una variable de tráfico, está sujeta a las limitaciones de dichas variables. Las props de lista se limitan a 100 bytes de datos y se ven afectadas por la configuración de la distinción entre mayúsculas y minúsculas.

## Variable de lista {#concept_AC42F2D69B674C02A484137CE5B4E687}

También se conoce como List Var. Similar a cómo funcionan las props de lista, las variables de lista permiten incluir varios valores dentro de la misma solicitud de imagen. Actúan de modo similar a las eVars, las cuales persisten más allá de la solicitud de imagen en la que se definieron. Puede usar estas variables para ver la causa y el efecto de varios elementos de una única página como, por ejemplo, listas de productos, listas de preferencias, listas de perfeccionamiento de búsqueda o listas de anuncios en pantalla.

<!-- 

listN.xml

 -->

**Consideraciones**

* Las variables de lista recuerdan sus valores específicos mediante referencia a la cookie VisitorID del explorador del visitante.
* Se almacena un límite de 250 valores máximos una vez por visitante. Si se exceden los 250 valores por visitante, se utilizan los últimos 250 valores. La caducidad de estos valores está basada en la caducidad configurada para la variable.
* Cada valor delimitado puede contener un máximo de 255 caracteres (o menos si se utilizan caracteres multibyte). Esta es la longitud máxima de cada elemento.
* No existe ningún límite para el número de caracteres dentro de esta variable. La única excepción a esta limitación es que los exploradores Internet Explorer antiguos imponen una limitación de 2083 caracteres en todas las solicitudes URL.
* Hay disponible un total de tres variables de lista por grupo de informes.
* El uso de variables de lista requiere el código H23 o superior.
* Las variables de lista pueden clasificarse.
* Si se definen valores duplicados en la misma solicitud de imagen, las variables de lista anulan la duplicación de todas las instancias de esos valores.
* El mayor detalle con el que se pueden segmentar las variables de lista es por visita (o vista de página). Si tiene una variable de lista con tres valores en la misma solicitud de imagen, las reglas de segmentación que coincidan con uno de los valores enviarán los tres al informe. Por el contrario, si una regla de conversión definida coincide con un único valor, se excluyen los tres valores.

**Configuración** {#section_8CADFF581D2447518BA3F7F79B2D80A9}

Puede acceder a la configuración en Admin Console y actualizarla sin tener que involucrar al Servicio de atención al cliente de Adobe:

1. Go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]**
1. Seleccione el grupo de informes.
1. Click  **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

* **Nombre**: Cada valor delimitado puede contener un máximo de 255 caracteres (o menos si se utilizan caracteres multibyte). Esta es la longitud máxima de cada elemento.
* **Delimitador de valores**: carácter utilizado para separar valores en una variable de lista. Normalmente son caracteres como comas, dos puntos, barras verticales o algún otro similar.

   >[!NOTE]
   >
   >Multi-byte characters are not supported as delimiters in List Vars. El delimitador debe ser de un solo byte.

* **Caducidad**: similar a la caducidad de eVar, determina la cantidad de tiempo que puede transcurrir entre la variable de lista y el evento de conversión para que se relacionen.

   * **A nivel de vista de página o visita**: Los eventos de éxito más allá de la vista de página o la visita no se vincularán con ningún valor que haya dentro de la variable de lista.
   * **En función de un período de tiempo como día, semana, mes, etc.**: Los eventos de éxito que no entren dentro del período de tiempo especificado no se vincularán a ningún valor que haya dentro de la variable de lista. También se puede definir un número de días personalizado.
   * **Eventos de conversión específicos**: Cualquier otro evento de éxito que se active después del evento específico designado no se vinculará con ningún valor que haya dentro de la variable de lista.
   * **Nunca**: Puede transcurrir cualquier cantidad de tiempo entre la variable de lista y el evento de éxito.

* **Asignación**: Esta opción determina cómo dividirán los eventos de éxito el crédito entre los valores:

   * **Total**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el total del crédito por los eventos de éxito.
   * **Lineal**: Todos los valores de variable definidos antes de la caducidad de la variable obtienen el crédito dividido entre los eventos de conversión.
   * Los valores de variable no se sobrescriben nunca; se suman a los valores que obtienen el crédito por los eventos de éxito.

* **Valores máximos**: Designa el número de valores activos permitidos para esta variable de lista. Por ejemplo, si se establece en 3, solo se guardarán los últimos 3 valores capturados y se descartarán todos los capturados con anterioridad. Tenga en cuenta que si se envían varios valores para la misma variable de lista en la misma visita y se ha restringido el uso de los valores máximos, todos los valores adquirirán la misma marca de tiempo y no puede garantizarse qué valor se guardará.

   Se almacena un límite de 250 valores máximos una vez por visitante. Si se exceden los 250 valores por visitante, se utilizan los últimos 250 valores. La caducidad de estos valores está basada en la caducidad configurada para la variable.

   La opción Valores máximos resulta muy útil para limitar la atribución a un número específico de valores. Por ejemplo, si una variable de lista se establece en "A,B,C" en la primera página de una visita y en "X,Y,Z" en la página siguiente, la atribución se distribuye a estos seis valores en función de la asignación. Si desea limitar la atribución a "X,Y,Z" exclusivamente, puede establecer los valores máximos en tres.

To set up or edit List Vars, go to  **[!UICONTROL Analytics]** &gt; **[!UICONTROL Admin]** &gt; **[!UICONTROL Report Suites]** &gt; **[!UICONTROL Edit Settings]** &gt; **[!UICONTROL Conversion]** &gt; **[!UICONTROL List Variables]** .

**Ejemplos de implementación** {#section_564AFE6A2F524BFEB372EC0F7FEBA656}

En cada uno de los ejemplos siguientes se utiliza una coma como delimitador de valores.

**Definir un valor único en una variable de lista:**

```js
s.list1="Cat";
```

**Pasar varios valores:**

```js
s.list2="Tabby,Persian,Siamese"; 
s.list1="Product 1,Product 2,Product 3";
```

**Atribuir ingresos a una variable de lista:**

```js
//Define this code on the landing page: 
s.list3="Top Banner Ad,Side Bar Ad,Internal Campaign 1"; 
 
//Have these variables fire on the purchase confirmation page: 
s.products=";Kitten;1;50" 
s.events="purchase";
```

Este resultado mostraría tres elementos de línea con 50 dólares de ingresos cada uno. (Top Banner Ad; Side Bar Ad; and Internal Campaign 1). Tenga en cuenta que el total para este informe anula la duplicación de los ingresos, por lo que el total también reflejaría 50 dólares.

**Atribuir ingresos a una variable de lista que se configuró varias veces durante una visita:**

**Asignación**: Total

**Caducidad**: Visita

<table id="table_09E1879B44624A858555449E2DC74E69"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Página </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Página 1 </td> 
   <td colname="col2"> <code> s.list1=”value1,value2,value3”; </code> </td> 
   <td colname="col3"> (sin configurar) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página 2 </td> 
   <td colname="col2"> <code> s.list1=”value4,value5,value6”; </code> </td> 
   <td colname="col3"> <p> <code> s.events=”purchase”; </code> </p> <p> <code> s.products=”;product;1;200” </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Resultado**: Todos los valores configurados en la list var1 en cualquier momento durante la visita (value1,value2,value3,value4,value5,value6) obtienen el crédito total de la compra.

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

La variable s.maxDelay se usa principalmente en integraciones de DFA de Genesis para determinar el tiempo de espera al contactar con el host DFA. Si Adobe no recibe una respuesta de los servidores DFA en el período configurado en la variable   la conexión se interrumpe y los datos se procesan normalmente. Implemente esta variable si le preocupa el tiempo de respuesta de DFA en cada página. Se recomienda experimentar con este valor para determinar el tiempo de espera óptimo.

<!-- 

maxDelay.xml

 -->

**Ejemplo de implementación**

```
s.maxDelay="750";
```

**Propiedades**

* Esta variable es una métrica de evento opcional que se rellena mediante el código JavaScript implementado en el sitio.
* Si el host DFA no responde en el tiempo especificado, se ejecuta el evento designado para Timeout (que se asigna mediante el asistente para la integración con Genesis).
* Esta variable solo puede contener un valor numérico.
* La cantidad de tiempo especificada se mide en milisegundos.
* Al aumentar el tiempo de espera se recopilan más datos de DFA, pero también aumenta el riesgo de perder datos de visitas de Analytics.

   Losing Analytics hit data would occur when the user navigates away from the page during the *`s.maxDelay`* period.

* Reducir el tiempo de espera reducirá el riesgo de perder datos de visitas de Analytics, pero puede reducir la cantidad de datos de DFA que se envían con los datos de visitas.

   La pérdida de datos de integración de DFA se produce cuando el *`s.maxDelay`* período no admite tiempo suficiente para que el host de DFA responda.

>[!NOTE]
>
>Adobe does not have control over DFA's response time. Si experimenta problemas continuos incluso después de aumentar el tiempo de demora máximo a un valor razonable, consulte con el administrador de cuentas DFA de su organización.

## mediaLength {#concept_F52B1670122C4461824223E525307060}

La variable especifica la longitud total del contenido multimedia que se está reproduciendo.

<!-- 

mediaLength.xml

 -->

<table id="table_B1AE8A9DF9D545C2965CDB2DB6C2969B"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Sin tamaño máximo para la solicitud pev3 completa; el tamaño se limita a la longitud de dirección URL máxima del explorador. </td> 
   <td> pev3 </td> 
   <td> Tiempo invertido en vídeo; <p>Segmentos de vídeo vistos </p> </td> 
   <td> Ninguno. </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxis y valores posibles** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

** Método autoTrack: **

Si se usa [!UICONTROL s.Media.autoTrack], no es necesario implementar la variable [!UICONTROL mediaLength] explícitamente. El código de AppMeasurement para JavaScript la determina automáticamente.

**Método de seguimiento manual:**

Sintaxis:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valores posibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Ejemplos** {#section_048B2D31BB584647A5D335AE94E5A599}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3= [Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Problemas, preguntas y consejos** {#section_1CEDC78FEF4940E9BC02A2AF1EE2FB01}

* Debe llamar a los métodos de seguimiento de contenido multimedia únicamente si no puede realizar el seguimiento del reproductor mediante [!UICONTROL s.Media.autoTrack] = true.
* Si no realiza el seguimiento mediante [!UICONTROL autoTrack], asegúrese de configurar la longitud en segundos.

## mediaName {#concept_A4CB1782DE244C23BA6CBB5E806DDE6A}

Esta variable especifica el nombre del vídeo o elemento multimedia.

<!-- 

mediaName.xml

 -->

Solo está disponible mediante la [!UICONTROL API de inserción de datos] y la [!UICONTROL fuente de datos de procesamiento completo].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 64 kB | pev3 | Videos; Siguiente flujo de vídeos; Anterior flujo de vídeos; Segmentos de vídeo vistos; Tiempo invertido en vídeo | Ninguno. |

**Sintaxis y valores posibles** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**Método autoTrack:**

Si se usa [!UICONTROL s.Media.autoTrack], no es necesario implementar la variable *`mediaName`explícitamente.* El código de AppMeasurement para JavaScript la determina automáticamente.

**Método de seguimiento manual:**

Sintaxis:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

```js
s.Media.close(mediaName)
```

Valores posibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

**Ejemplos** {#section_4B9584265B1A47289818141B2A88021D}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
s.Media.close("de_bofr_1045Making_400k")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]  
  
```

```js
Possible pev3 Values: 
  pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 
  11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32  
  
```

**Problemas, preguntas y consejos** {#section_941A445BB52E4063B0F6920E61BB90DE}

* Debe llamar a los métodos de seguimiento de contenido multimedia únicamente si no puede realizar el seguimiento del reproductor mediante [!UICONTROL s.Media.autoTrack] = true.
* Esta variable se almacena como variable TEXT de mySQL al contrario que VARCHAR(100).

## mediaPlayer {#concept_1932756C093B4B2FBA0484E5A58EF927}

Esta variable especifica el reproductor que se utiliza para reproducir un vídeo o elemento multimedia.

<!-- 

mediaPlayer.xml

 -->

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | pev3 | Reproductores de vídeos | Ninguno. |

**Sintaxis y valores posibles** {#section_EAA55A3A45B5405F903E3BE6ACAB143F}

**Método autoTrack:**

```js
s.Media.playerName = "My Custom Player Name"  //configure player name in global JavaScript or ActionSource
```

**Método de seguimiento manual:**

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName)
```

Valores posibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

**Ejemplos** {#section_64967E1333D542CCB6CF62F0A1E0EF88}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers] 
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32
```

**Problemas, preguntas y consejos** {#section_0020E031338F4A4880B9AC5B9A85BEF5}

Debe llamar a los métodos de seguimiento de contenido multimedia únicamente si no puede realizar el seguimiento del reproductor mediante s.Media.autoTrack = true.

## mediaSession {#concept_19E6C850C3244CB6973140709BDCB0B9}

Esta variable especifica los segmentos de un vídeo o elemento multimedia consumidos.

<!-- 

mediaSession.xml

 -->

<table id="table_8681473270FE44DFBBCCC0FBA6737104"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 255 bytes </td> 
   <td> pev3 </td> 
   <td> Tiempo invertido en vídeo <p>Segmentos de vídeo vistos </p> </td> 
   <td> Ninguno. </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxis y valores posibles** {#section_9A63266633C4427CB4A6549E4D887B85}

**Método autoTrack:**

Si se usa [!UICONTROL s.Media.autoTrack], no es necesario implementar la *`mediaName`explícitamente.* El código de AppMeasurement para JavaScript la determina automáticamente.

**Método de seguimiento manual:**

Sintaxis:

```js
s.Media.open(mediaName,mediaLength,mediaPlayerName) 
```

```js
s.Media.play(mediaName,mediaOffset)
```

```js
s.Media.stop(mediaName,mediaOffset)
```

Valores posibles:

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

**Ejemplos** {#section_3446EC37E017407FA3F43C9BDAEA0B85}

```js
s.Media.open("de_bofr_1045Making_400k", "414","Windows Media Player 11.0.5721.5230") 
```

```js
s.Media.play("de_bofr_1045Making_400k", "0")
```

```js
s.Media.play("de_bofr_1045Making_400k", "414")
```

```js
Resulting pev3 parameter syntax: pev3=[Asset Name]--**--[Total length of asset]--**--[Player name]--**--[Total seconds consumed]--**--[Timestamp]--**--[Chronological record of all starts and stops along with accompanying markers]
```

```js
Possible pev3 Values: pev3=de_bofr_1045Making_400k--**--414--**--Windows Media Player 11.0.5721.5230--**--288--**--1207893838--**--S0E0S0E256S0E32 
```

**Problemas, preguntas y consejos** {#section_1BCEB037AB724B6EBE87420BD3604B88}

Debe llamar a los métodos de seguimiento de contenido multimedia únicamente si no puede realizar el seguimiento del reproductor mediante [!UICONTROL s.Media.autoTrack] = true.

## Media.trackEvents {#concept_B1C5FF6C437949EBA5D52040AC6BB6D9}

La variable identifica qué eventos deben enviarse con una visita multimedia.

<!-- 

media_trackEvents.xml

 -->

Solo es aplicable con JavaScript y [!UICONTROL ActionSource].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | s.Media.trackEvents="None" |

**Sintaxis y valores posibles** {#section_66A978EF56914BEAAE73359A268A1B4A}

Nombres de evento como event1 o purchase.

**Ejemplos** {#section_140A55D80EA24011954F9383CF312237}

```js
s.Media.trackEvents=”event1,purchase”
```

**Problemas, preguntas y consejos** {#section_030B11C64EE84D46A85CA550DB732D28}

Asegúrese de rellenar [!UICONTROL trackVars] con "events" siempre que se rellene esta variable.

## Media.trackVars {#concept_4350CA9A892148AE93C8133AB3B4BEA4}

La variable identifica qué variables deben enviarse con una visita multimedia.

<!-- 

media_trackVars.xml

 -->

Solo es aplicable con JavaScript y [!UICONTROL ActionSource].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | s.Media.trackVars="None" |

**Sintaxis y valores posibles** {#section_7374684A7EB34AE685E8C40A66CFD289}

Nombres de variables como [!UICONTROL propN], *`eVarN`*, *`events`*, *`channel`*, etc.

**Ejemplos** {#section_48653222ABA14AB0A3C4471659971FAA}

```js
s.Media.trackVars=”prop2,events,eVar3”
```

**Problemas, preguntas y consejos** {#section_615AE1B696124B00B78F651B03813EAB}

* Incluso aunque se especifique eVar3 en [!UICONTROL trackVars], se envía con la visita multimedia.

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

La variable controla el orden con el que se usan las cookies y las ID de suscriptor para identificar a los visitantes.

<!-- 

mobile.xml

 -->

See [Mobile network protocols](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | /5/ o /1/ en la ruta de la dirección url de la imagen | N.D. | Ninguno. |

**Sintaxis y valores posibles** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Problemas, preguntas y consejos** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Utilice la identificación entre visitantes para mitigar los posibles picos en el tráfico de visitantes al utilizar la *`s.mobile`* variable con la implementación de cookies de JavaScript.

## pageName {#concept_5827B499DAC34B5D8445F9D9140CC328}

La variable contiene el nombre de cada una de las páginas del sitio.

<!-- 

pageName.xml

 -->

<table id="table_0D09BAEC2FFD43F7905ED3649B3F8E05"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 100 bytes </td> 
   <td> pageName </td> 
   <td> <p>Páginas </p> <p>Rutas </p> </td> 
   <td> Dirección URL de la página </td> 
  </tr> 
 </tbody> 
</table>

La variable *`pageName`* debe rellenarse con un valor que los usuarios comerciales reconozcan. En la mayoría de los casos, el *`pageName`* valor no es la dirección URL ni la ruta al archivo. Common *`pageName`* values include names such as "Home Page," "Checkout," "Purchase Thank you," or "Registration."

Tenga cuidado de que no aparezcan caracteres de nueva línea, guiones -em o -en u otros caracteres HTML en el nombre de la página y otras variables. Algunos exploradores envían caracteres de nueva línea pero otros no, lo que hace que los datos de Analytics se dividan en dos nombres de página aparentemente iguales. Muchos procesadores de texto y clientes de correo electrónico convertirán automáticamente un guión corto en un guión -en o -em al escribir. Como los guiones -en y -em son caracteres no permitidos en las variables de Analytics (caracteres ASCII con códigos superiores a 127), Analytics no registrará los nombres de página que contengan caracteres no permitidos y, en su lugar, mostrará la dirección URL.

If *`pageName`* is left blank, the URL is used to represent the page name. Leaving *`pageName`* blank is often problematic because the URL may not always be the same for a page `www.mysite.com` and `mysite.com` are the same page with different URLs).

**Sintaxis y valores posibles** {#section_7A61EE70F1A84D26B414404998C84BA8}

The *`pageName`* variable should contain a useful identifier for business users of Analytics.

```js
s.pageName="page_name"
```

There are no limitations on *`pageName`* outside of the standard variable limitations.

**Ejemplos** {#section_8BB4F86F84E246A08B72DEC47FFC0765}

```js
s.pageName="Search Results" 
```

```js
s.pageName="Standard Offer List"
```

**Parámetros de configuración** {#section_58CBC68C805344A999EB47455FEBA8D5}

Los administradores tienen la posibilidad de cambiar el nombre de página visible en Analytics con la [!UICONTROL Herramienta de asignación de nombres a páginas], lo que resulta potencialmente peligroso y podría afectar negativamente a los informes. Póngase en contacto con el Servicio de atención al cliente de Adobe antes de usar la herramienta [!UICONTROL Nombrar páginas].

**Problemas, preguntas y consejos** {#section_BB41DC9682C34385B9CAA80D5257C113}

Asegúrese de que *`pageName`* no contenga caracteres ilegales.

## pageType {#concept_F67870238EF74491B5D3909A33CDB985}

La variable solo se usa para designar una página de error 404 Página no encontrada.

<!-- 

pageType.xml

 -->

<table id="table_0492B136E9D14070A6CA49ED534BCA4C"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> 20 bytes </td> 
   <td> pageType </td> 
   <td> Rutas &gt; Páginas &gt; Páginas <p>No encontrado </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

La variable *`pageType`* captura la dirección URL errante cuando se muestra una página de error 404, lo que permite encontrar rápidamente los vínculos rotos y las rutas que ya no son válidas en el sitio personalizado. Configure la *`pageType`* variable en la página de error exactamente como se muestra a continuación.

No utilice la variable del nombre de página en las páginas de error 404. La variable *`pageType`* se utiliza solamente para la página de error 404.

En la mayoría de los casos, la página de error 404 es una página estática codificada. En estos casos, es importante que la referencia al archivo .JS se configure en un directorio/ruta global o relativo apropiado.

**Sintaxis y valores posibles** {#section_C1C59968226446559B05F6EE7374D525}

El único valor permitido de *`pageType`* es "errorPage", como se muestra a continuación.

```js
s.pageType="errorPage"
```

**Ejemplos** {#section_6CE22FCB835B4A19B633B7F67E73A115}

```js
s.pageType="errorPage"
```

**Parámetros de configuración** {#section_3B304A6D3A6C48F2BE90B4DA92A39DDB}

Ninguna

**Problemas, preguntas y consejos** {#section_943681AB01FE47BEAC72E93CB60C53C8}

To capture other server-side errors (such as 500 errors), use a prop to capture the error message and put "`500 Error: <URL>`" where `<URL>` is the URL requested, in the *`pageName`* variable. Este procedimiento permite usar informes de [!UICONTROL control de rutas] para ver qué rutas provocaron que los usuarios generaran errores 500. La prop explica qué mensaje de error proporciona el servidor.

## pageURL {#concept_A15F710CD0174297A2286BF3E7452113}

La variable anula la dirección URL real de la página.

<!-- 

pageURL.xml

 -->

En casos excepcionales, la dirección URL de la página no es la dirección URL que se desearía registrar en Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Sin límite* </td> 
   <td> <p>G </p> </td> 
   <td> Tráfico &gt; Segmentación &gt; Páginas más populares </td> 
   <td> URL de la página </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Although Adobe allows *`pageURL`* values up to 64k, some browsers impose a size limit on the URL of image requests. To prevent truncation of other data, page URLs longer than 255 bytes are split, with the first 255 bytes appearing in the `g=` parameter, with the remaining bytes appearing later in the query sting in the `-g=` query parameter.

**Sintaxis y valores posibles** {#section_22AF3BF7C2F743549967B0C760A095C0}

The *`pageURL`* variable must be a valid URL, with a valid protocol. El dominio será obligado a mostrarse en letra minúscula antes de rellenarse en los informes, y la cadena de consulta puede ser depurada, en función de la configuración de Analytics.

```js
s.pageURL="proto://domain/path?query_string"
```

Solo se permiten caracteres compatibles con URL en la dirección URL de la página.

>[!NOTE]
>
>Se recomienda encarecidamente que se ponga en contacto con su asesor de Adobe o con el Servicio de atención al cliente antes de utilizar la *`pageURL`* variable con fines personalizados.

**Ejemplos** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**Parámetros de configuración** {#section_A8F77DAD88164528ACC5C16C066B47DF}

Ninguna

## plugins {#concept_B570F04FEDA34EB7A9826687FE633953}

La variable , en exploradores Netscape y Mozilla, enumera los complementos instalados en el explorador.

<!-- 

plugins.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| p | Complementos reconocidos | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Biblioteca de vínculos dinámicos del complemento Reproductor de Windows Media;Microsoft® DRM; | Tráfico &gt; Tecnología &gt; Complementos |

## informe de productos {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

La variable se usa para rastrear productos y categorías de productos, así como precios y cantidades de compra. Los productos se suelen configurar junto con un evento de carro o un evento 

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>In January of 2016, we updated the logic that sets the *`prodView`* event automatically, which happens when there is a *`product`* but no *`event`*. Esta actualización puede provocar un aumento en los eventos *`prodView`.* *`prodViews`* aumentarán solo cuando:
>
>1. The events variable contains nothing but an unrecognized event, such as *`shoppingCart`* or *`cart`*, which are not valid events.
   >
   >
1. La variable *`products`no está vacía.*
>
>
A possible side effect is that merchandising eVars triggered by *`prodView`* events could be associated with an empty *`product`*, but only if the *`product list`* contains only an invalid product (such as a semicolon with no product listed).

The *`products`* variable tracks how users interact with products on your site. Por ejemplo, la variable products puede realizar el seguimiento de cuántas veces se ha visto un producto, se ha agregado al carro de compras, se ha cerrado su compra y se ha comprado. También puede realizar el seguimiento de la eficacia relativa de las categorías de comercialización del sitio. Los siguientes son escenarios habituales para usar la variable products.

La variable *`products`* siempre debe configurarse junto con un evento de éxito.

<table id="table_D5A11AFDDD364D0993D387906343DDF3"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> <p>La cadena " <span class="wintitle"> products </span>" tiene un tamaño máximo de 64 k. </p> </td> 
   <td> products </td> 
   <td> Productos <p>Categorías (opcional) </p> <p>Ingresos (opcional) </p> <p>Unidades (opcional) </p> <p>Eventos personalizados (opcional) </p> <p>eVars (opcional) </p> </td> 
   <td> " " </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxis** {#section_ABA3682985E540E6AA67A510176CCFFC}

```js
"Category;Product;Quantity;Price;eventN=X[|eventN2=X2];eVarN=merch_category[|eVarN2=merch_category2]"
```

| Campo | Definición |
|---|---|
| Categoría | Contiene la categoría de producto asociada. En la versión 15, los productos se pueden asociar a varias categorías, lo que pone fin a la limitación existente en la versión 14. Si anteriormente no registraba una categoría de producto, ahora le recomendamos que empiece a rellenar este campo para los grupos de informes presentes en la versión 15. |
| Producto | (Requerido) Identificador usado para realizar el seguimiento de un producto. Este identificador se utiliza para rellenar el informe [!UICONTROL Productos]. Asegúrese de usar el mismo identificador en todo el proceso de cierre de la compra. |
| Cantidad | Número de unidades compradas. Este campo se debe configurar con un evento [!UICONTROL purchase] para que se registre. |
| Precio | Hace referencia al coste combinado de la cantidad total comprada (unidades x precio unitario individual), no al precio individual. Este campo se debe configurar con un evento [!UICONTROL purchase] para que se registre. |
| Eventos | Eventos monetarios asociados al producto especificado. Consulte [Eventos monetarios específicos de productos](../../../implement/js-implementation/c-variables/page-variables.md#section_F814DF053C0D463A97DA039E6323720C) y [Eventos monetarios de todo el pedido](../../../implement/js-implementation/c-variables/page-variables.md#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0). |
| eVars | Valores eVar de comercialización asociados a un producto específico. Consulte [Variables de comercialización](/help/components/c-variables/c-merch-variables/var-merchandising.md). |

Los valores incluidos en la variable *`products`* se basan en el tipo de evento que esté registrando. El delimitador de categoría/producto (;) es necesario como marcador de posición cuando se omite la categoría. Solo se requieren otros delimitadores en caso de que sea necesario distinguir el parámetro que se está incluyendo, como se muestra en los ejemplos de esta página.

**Configurar products con eventos que no son purchase** {#section_D5E689D4AAE941EC851CA9B98328A4DE}

The *`products`* variable must be set in conjunction with a success event.

**Configurar products con un evento purchase** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

The *`purchase`* event should be set on the final confirmation ("Thank You!") del proceso de pedido. El nombre del producto, categoría, cantidad y precio se capturan todos en la variable *`products`* variable. Although the *`purchaseID`* variable is not required, it is strongly recommended in order to prevent duplicate orders.

**Eventos monetarios específicos de productos** {#section_F814DF053C0D463A97DA039E6323720C}

Si un evento de moneda recibe un valor en la *`products`* variable en lugar de en la variable events, sólo se aplica a ese valor. Esto es útil para realizar un seguimiento de descuentos específicos del producto, envíos de productos y valores similares. Por ejemplo, si ha configurado el evento 1 para realizar un seguimiento del envío de productos, un producto con un cargo de envío de "4,50" podría parecerse a lo siguiente:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

En este ejemplo, el valor de 4,50 está asociado directamente al producto "Running Shoes". Si agrega event1 al informe de productos, verá cómo aparece "4,50" en el elemento de línea "Running Shoes". Al igual que ocurre con Price, este valor debe reflejar el total de la cantidad mostrada. Si tiene 2 artículos con un cargo de envío de 4,50 cada uno, el valor de event1 debe ser "9,00".

**Eventos monetarios de todo el pedido** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

Si un evento de moneda recibe un valor en la lista de eventos en lugar de la *`products`* variable, se aplica a todos los productos de la *`products`* variable. Esto es útil para rastrear descuentos, envíos y valores similares en los pedidos sin modificar el precio del producto o rastreándolo en la lista de productos por separado.

Por ejemplo, si ha configurado event10 para que contenga descuentos en los pedidos, puede que aparezca una compra con un 10 % de descuento similar a la siguiente:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

En los informes de eventos monetarios, el total del informe representa el total del evento sin duplicados (en este ejemplo, la cantidad total de descuentos durante el período de informe) y no la suma de valores de evento para cada producto. Por ejemplo, aparecería "9,95" tanto para "Running Shoes" como para "Running Socks" y el total también sería "9,95".

>[!NOTE]
>
>si se especifica un valor para el mismo evento numérico/monetario en la *`products`* variable y en la *`events`* variable, se utiliza el valor del *`events`* .

**Problemas, preguntas y consejos** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* The *`products`* variable should always be set in conjunction with a [!UICONTROL success] event (events). Si no se especifica un evento de [!UICONTROL éxito], el evento predeterminado es [!UICONTROL prodView].

* Elimine todas las comas y punto y comas de los nombres de producto y categoría antes de rellenar los productos.
* Elimine todos los caracteres HTML (símbolos de marca registrada, marca comercial, etc.).
* Elimine los símbolos de moneda ($) del precio.

**Ejemplos** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category;ABC123” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category2;ABC123,;ABC456” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category3;ABC123;1;10” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products=”Category;ABC123;1;10,;ABC456;2;19.98” </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2,event3” </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events=”event1,event2,event3=9.95” </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

## propN {#concept_0F10FA2DE69B4029A31EA5E9313AA254}

Las variables de propiedad ([!UICONTROL props]) se usan para generar informes personalizados en el [!UICONTROL módulo de tráfico].

<!-- 

propN.xml

 -->

Las variables de propiedad se pueden utilizar como contadores (para contabilizar el número de veces que se envía una vista de página), para informes de rutas o en informes de correlación.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | c1 - c75 | Tráfico personalizado | "" |

**Sintaxis y valores posibles** {#section_4D3013AF2979426B9589CA2BB9D254CD}

```js
s.propN="value"
```

No existen limitaciones en las variables de [!UICONTROL propiedad] aparte de las limitaciones estándar de las variables.

**Ejemplos** {#section_FFBB916DA9F44B668D5FAB7C511F6182}

```js
s.prop2="editorial" 
```

```js
s.prop15="toy category"
```

**Parámetros de configuración** {#section_25FDEB6ECA8242A2A44EE540C083078A}

Póngase en contacto con el Servicio de atención al cliente de Adobe para obtener información sobre cómo mostrar las métricas [!UICONTROL Visita], [!UICONTROL Visitante] y [!UICONTROL Ruta] para las variables [!UICONTROL prop].

## purchaseID {#concept_21937434E63F413CB469007623B933AE}

 se usa para evitar que un pedido se cuente varias veces en los informes.

<!-- 

purchaseID.xml

 -->

Whenever the [!UICONTROL purchase] event is used on your site, you should use the *`purchaseID`* variable.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 20 bytes | purchaseID | Conversión &gt; Compras &gt; Conversión de ingresos | "" |

Cuando un visitante compra un artículo en su sitio, *`purchaseID`* se rellena en la página "Gracias" en el mismo lugar donde se activa el evento [!UICONTROL purchase]. If the *`purchaseID`* is populated, the products on the "Thank You" page are counted only once per *`purchaseID`*. Esto resulta crítico porque muchos visitantes del sitio guardarán las páginas "Gracias" o "Página de confirmación" para sus propios fines. La variable *`purchaseID`* evita que las compras se contabilicen cada vez que se visita la página.

Además de evitar que los datos de la compra se cuenten dos veces, el *`purchaseID`*, cuando se utilizan, evita que todos los datos de conversión se cuenten dos veces en los informes.

**Sintaxis y valores posibles** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

The *`purchaseID`* must be 20 characters or fewer, and be standard ASCII.

**Ejemplos** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Parámetros de configuración** {#section_1808631C96674380BF9C4A6D9A2C568E}

Ninguna

**Problemas, preguntas y consejos** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

The *`purchaseID`* variable allows all conversion variables on the page to be counted only once in reports.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

La variable puede utilizarse para restablecer la información perdida del referente.

<!-- 

referrer.xml

 -->

Las redirecciones de JavaScript y del lado del servidor generalmente se utilizan para enrutar a los visitantes hacia las ubicaciones correctas. Sin embargo, cuando se redirecciona un explorador, la dirección URL de referencia original se pierde. 

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 255 bytes | R | Tráfico &gt; Conversión &gt; Métodos de búsqueda | document.referrer |

Muchas empresas usan redirecciones en numerosos lugares de sus sitios web. Por ejemplo, se puede enviar a un visitante a través de una redirección desde un resultado de búsqueda de pago del motor de búsqueda. Cuando se redirecciona un explorador, generalmente el referente se pierde. La variable se puede utilizar *`referrer`* para restaurar el valor original *`referrer`* en la primera página después de una redirección. The *`referrer`* may be populated server-side, or via JavaScript from the query string.

Para que Analytics registre un referente, debe estar "bien formado", lo que significa que debe seguir el formato URL estándar, con un protocolo y una ubicación apropiados.

**Sintaxis y valores posibles** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

Solamente debe haber valores compatibles con URL en *`referrer`*. Asegúrese de que la cadena tenga codificación URL (sin espacios).

**Ejemplos** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**Parámetros de configuración** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

Ninguna

**Problemas, preguntas y consejos** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

The *`referrer`* must look like a standard URL and include a protocol.

## resolution {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

La variable indica la resolución de la pantalla del visitante que está viendo la página web.

<!-- 

resolution.xml

 -->

This variable is populated after the page code and before *`doPlugins`* is run.

>[!NOTE]
>
>Esta variable solo debe leerse y nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| s | WxH | 1680 x 1050 | Tráfico &gt; Tecnología &gt; Resolución del monitor |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

The  variable is a global variable that should be set in the [!UICONTROL onClick] event of a link.

<!-- 

s_objectID.xml

 -->

By creating a unique object ID for a link or link location on a page, you can either improve visitor activity tracking or use [!UICONTROL Activity Map] to report on a link type or location, rather than the link URL.

>[!NOTE]
>
>A trailing semicolon (;) is required when using s_objectID with [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | La dirección URL absoluta de un vínculo donde se hizo clic |

Existen tres razones comunes para utilizar *`s_objectID`*:

* Para agregar actividad de visitante que cambia a menudo durante un día.
* To separate link activity that [!UICONTROL Activity Map] combines.
* To improve the accuracy of [!UICONTROL Activity Map] data reporting.

**Agregar clics en vínculos muy dinámicos** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

Si el sitio es muy dinámico y los vínculos de algunas páginas cambian a lo largo del día, *`s_objectID`* puede utilizarse para identificar la ubicación de un vínculo en la página. Si *`s_objectID`* se configura en "top left 1" o "top left 2", que representa el primer vínculo en la parte superior izquierda de la página, por ejemplo, todos los vínculos que aparezcan en esa ubicación (o que *`s_objectID`* se hayan configurado en el mismo valor) se informan junto con el mapa de clics de visitantes. If you don't use *`s_objectID`*, you see the number of times that a specific link was clicked, but you lose insight into how all the other links in that location were used by visitors to your site.

**Separar clics combinados** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

Si la *`pageName`* variable del sitio se utiliza para mostrar la sección o plantilla que está viendo un visitante, en lugar de la página específica que el visitante está viendo, puede que desee utilizar *`s_objectID`* para separar los vínculos que aparecen en varias versiones de esa plantilla de página. Por ejemplo, si tiene una página de plantilla para todos los productos del sitio, es muy probable que en todas las páginas haya un vínculo a la página de inicio y a un cuadro de búsqueda desde esa plantilla. Si desea ver cómo se utilizan esos vínculos por producto individual (en vez de por plantilla), puede rellenar *`s_objectID`* con un valor específico de un producto, por ejemplo, "prod 123789 home page" o "prod 123789 search". Once completed, [!UICONTROL Activity Map] reports on those links at an individual product basis.

**Mejorar la precisión[!UICONTROL de Activity Map]**{#section_08B3406821294DCCABEEB99C90CF5C52}

En algunas ocasiones, los exploradores que no sean Internet Explorer, Firefox, Netscape, Opera y Safari no se incluyen en los informes. Aunque esto suponga un porcentaje reducido, cuenta para algunos clics y otras métricas. Use *`s_objectID`* within links to uniquely identify the addresses the browser reporting issue. A continuación se incluye un ejemplo sobre cómo actualizar los vínculos para utilizar *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Sintaxis y valores posibles** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID puede contener cualquier identificador de texto.

```js
s_objectID="unique_id" 
```

No existen limitaciones en *`s_objectID`* aparte de las limitaciones estándar de las variables.

**Ejemplos** {#section_33F119D532CA4ACAA3426253C42030BB}

```js
s_objectID="top left 2" 
```

```js
s_objectID="prod 123789 search"
```

**Parámetros de configuración** {#section_95396657D55B41ECB66B83D0534EA827}

Ninguna

## server {#concept_BF77952603BA454BAFC9A0A81D06A7D2}

La variable se usa para mostrar el dominio de una página web (para mostrar a qué dominios vienen los usuarios) o el servidor que atiende la página (para una referencia rápida del balance de carga).

<!-- 

server.xml

 -->

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | server | Servidores | "" |

Si su sitio tiene más de un dominio que sirve el mismo contenido, la variable *`server`* se puede usar para realizar el seguimiento de cuál de esos dominios están usando los visitantes. El siguiente código JavaScript rellenará el dominio de la página en la variable server.

```js
s.server=window.location.hostname
```

Si utiliza la variable server como guía rápida del balance de carga, podría colocar un nombre o número de servidor en la variable server. Veamos el siguiente ejemplo:

```js
s.server="server 14"
```

Aunque el informe [!UICONTROL Servidores más populares] puede usarse como referencia rápida del balance de carga, no es una medida precisa de la carga del servidor. Por ejemplo, el tráfico del botón atrás no aumenta la carga del servidor, pero aparece en los informes. El informe no muestra qué servidores están sirviendo las imágenes o las grandes descargas.

**Sintaxis y valores posibles** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

There are no limitations on the *`server`* variable outside of the standard variable limitations.

**Ejemplos** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Parámetros de configuración** {#section_969DB379D5BD469FBEE8D505D3000E49}

Ninguna

**Problemas, preguntas y consejos** {#section_42A28F9B01574F38891D9D54B411D8FE}

The *`server`* variable can be used to show which domains are most popular or which servers are serving the most pages.

## state {#concept_82295D22888947BF8B1C76182C635C6C}

The  and  variables are conversion variables.

<!-- 

state.xml

 -->

Son similares a las eVars en cuando a que capturan eventos pero, a diferencia de estas, no persisten. La variable *`zip`* and *`state`* variables are like eVars that expire immediately.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 50 bytes | state | Conversión &gt; Perfil del visitante &gt; Estado de visitante | "" |

Because the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events that are fired on the same page on which they are populated. For example, if you are using *`state`* to compare conversion rates by state, you should populate the *`state`* variable on every page of the checkout process. Para los sitios de conversión, Adobe recomienda usar la dirección de facturación como fuente del código postal, pero puede elegir usar la dirección de envío en su lugar (suponiendo que solo haya una dirección de envío para el pedido). Un sitio multimedia puede elegir usar  *`zip`* and *`state`* for registration or ad click-through tracking.

**Sintaxis y valores posibles** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

The *`state`* variable does not impose any special value or format restrictions. There are no limitations on *`state`* outside of the standard variable limitations.

**Ejemplos** {#section_D181B163F79A41D199CA4C70765E583F}

```js
s.state="california" 
```

```js
s.state="prince edward island"
```

**Parámetros de configuración** {#section_DB0D6DC3F4764AC59C11B10D27D2806C}

Ninguna

**Problemas, preguntas y consejos** {#section_02F1620D0BB14AA6A838966FDB9A234F}

* Populate *`state`* on every page that a relevant event is fired (such as each page of the checkout process).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

## timestamp {#concept_D997A2FF4D134C80A614C0BC7A4D7507}

Esta variable permite personalizar la marca de tiempo de una visita de forma similar a las bibliotecas de AppMeasurement para otras plataformas.

<!-- 

timestamp.xml

 -->

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 4 bytes | Fecha/Hora | No se notifica directamente. | Configurado por los servidores de recopilación de datos. |

**Sintaxis** {#section_1DF752B1202C4412A301AC7CC10874DF}

```js
s.timestamp="UNIX or ISO-8601 format timestamp"
```

The *`timestamp`* variable must be in the format explained in the next section.

>[!IMPORTANT]
>
>Your report suite must be timestamp-enabled by Customer Care before you can use the *`timestamp`* variable. After timestamp support is enabled, all hits sent to this report suite from JavaScript must have a timestamp manually set (using *`s.timestamp`*) or the hits will not be recorded.
>
>Asimismo, si habilita la compatibilidad con la marca de tiempo en un grupo de informes de modo que se admita el seguimiento sin conexión, también deberá establecerse de forma manual una marca de tiempo para todas las visitas que se envíen a este grupo de informes desde JavaScript (con *`s.timestamp`*). No es posible enviar visitas con y sin marca de tiempo a un mismo grupo de informes.
>
>También se puede usar el ajuste [Marcas de hora opcionales](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F) para combinar datos con y sin marca de tiempo en el mismo grupo de informes global, enviar datos con marca de tiempo desde una aplicación móvil a un grupo de informes global, y actualizar aplicaciones para emplear marcas de tiempo sin tener que crear un nuevo grupo de informes.

**Formatos de las marcas de tiempo** {#section_C12CBCECCD7047D38EF63A5800761CE9}

Las marcas de tiempo deben tener el formato UNIX (segundos transcurridos desde el 1 de enero de 1970) o ISO-8601, con las siguientes restricciones para el formato ISO-8601 aceptado:

* La fecha y la hora deben proporcionarse separadas por una "T".
* La fecha debe ser una fecha de calendario con precisión completa (año, mes y día). . Los días de la semana y las fechas con números ordinales no son compatibles.
* The date can be in standard or extended format ( `YYYY-MM-DD` or `YYYYMMDD`), but they must include the hour and minute. Los segundos son opcionales ( `HH:MM`, `HH:MM:SS`, `HHMM`o `HHMMSS`). Los minutos y los segundos fraccionados se pueden incluir, pero la parte fraccionada se ignorará.

* An optional time zone can be specified in standard or extended format ( `±HH`, `±HH:MM`, `±HH`, `±HHMM`, or Z)

Las marcas de tiempo UNIX siguen siendo compatibles (segundos transcurridos desde el 1 de enero de 1970).

**Ejemplos** {#section_FA19C53D70DE4CF2AF259A5B968B84C3}

```js
s.timestamp=Math.round((new Date()).getTime()/1000);
```

```js
s.timestamp="2012-04-20T12:49:31-0700";
```

La siguiente lista contiene ejemplos de marcas de tiempo con el formato ISO-8601 válidas:

```
2013-01-01T12:30:05+06:00 
2013-01-01T12:30:05Z 
2013-01-01T12:30:05 
2013-01-01T12:30
```

**Parámetros de configuración** {#section_5275D206F2CB4009B3681E8C4457124A}

El Servicio de atención al cliente debe habilitar un grupo de informes para que acepte marcas de tiempo personalizadas antes de poder usar esta variable. Una vez habilitadas las marcas de tiempo personalizadas, todas las visitas que se envíen al grupo de informes deben contener una marca de tiempo o descartarse.

**Problemas, preguntas y consejos** {#section_EFDE8F67D13C4775A461E0B00D30AFD7}

* Las marcas de tiempo se usan principalmente para realizar el seguimiento de datos sin conexión en plataformas móviles. Las marcas de tiempo personalizadas suelen estar deshabilitadas a menos que estén recopilando datos de aplicaciones web y sin conexión en el mismo grupo de informes.
* Los datos se marcan con la hora si los datos sin conexión están habilitados en el SDK móvil (configuración predeterminada) o en cualquier momento en el que un grupo de informes se configure para aceptar datos con marca de hora. Puede que los datos recogidos sin conexión en dispositivos móviles se envíen horas o semanas después de la fecha en la que se produjeron. Puede que estas visitas se mantengan en cola en la plataforma Analytics durante más minutos u horas que las visitas sin marca de tiempo:

   * Para los datos con marca de hora de envío muy cerca de la hora actual, el retraso probable es de 10-15 minutos.
   * Para los datos con marca de hora de envío de ayer, el retraso probable es de unas dos horas.
   * Para los datos con marca de hora de envío anterior a ayer, cada día añade aproximadamente una hora de retraso, hasta los 15 días, cuando el retraso se detiene.

* Los datos de sesión con marca de tiempo habilitada se conservan por un período máximo de 92 días.

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

La variable se utiliza para la implementación de cookies de origen a fin de especificar el dominio en el cual se escriben la solicitud de imagen y la cookie.

<!-- 

trackingServer.xml

 -->

Se utiliza para páginas no seguras. Si *`trackingServer`* está definida, ningún dato se dirige a 2o7.net. If *`trackingServer`* is not defined (and dc is not defined), data goes to 112.2o7.net.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | "" |

[Aquí](https://helpx.adobe.com/analytics/kb/determining-data-center.html) podrá consultar una lista de centros de datos de Adobe.

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

La variable se utiliza para la implementación de cookies de origen a fin de especificar el dominio en el cual se escriben la solicitud de imagen y la cookie.

<!-- 

trackingServerSecure.xml

 -->

Se utiliza para páginas seguras. Si *`trackingServerSecure`* no está definida, los datos SSL se dirigen a *`trackingServer`*.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | "" |

## transactionID {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

[!UICONTROL Las fuentes de datos de integración] utilizan una [!UICONTROL ID de transacción] para enlazar los datos sin conexión a una transacción en línea (como un cliente o una compra generados en línea).

<!-- 

transactionID.xml

 -->

Each unique *`transactionID`* sent to Adobe is recorded in preparation for a [!UICONTROL Data Sources] upload of offline information about that transaction. Consulte [Fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | xact | n.d. | "" |

**Habilitar almacenamiento** de ID de transacción {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Before *`transactionID`* values are recorded, [!UICONTROL Transaction ID Storage] must be enabled for the report suite selected in the Report Suite Manager. Esta opción se encuentra en

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

Para ver si *`transactionID Storage`* está habilitado para un grupo de informes, vaya a

```
Analytics > Admin > Data Sources > Manage
```

**Sintaxis y valores posibles** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

The *`transactionID`* should contain only alphanumeric characters. Si debe registrar varias variables [!UICONTROL transactionID] para una sola visita, delimite los valores correspondientes con una coma.

**Ejemplos** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Problemas, preguntas y consejos** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* Si *`transactionID`* la grabación no está habilitada, *`transactionID`* los valores se descartarán y no estarán disponibles para su uso con las fuentes [!UICONTROL de datos de]integración. Make sure to set a conversion variable or event (an eVar or the events variable) on the page where *`transactionID`* is set. De lo contrario, no se registrarán datos para *`transactionID`*.

* Si está registrando [!UICONTROL transactionIDs] para varios sistemas, como compras y posibles clientes, asegúrese de que el valor de *`transactionID`* siempre sea único. Esto puede conseguirse agregando un prefijo a la ID, por ejemplo, lead_1234 y purchase_1234. [!UICONTROL Integration Data Sources] do not function as expected ( [!UICONTROL Data Source] data will tie to the wrong data) if a unique *`transactionID`* is seen twice.

* De forma predeterminada, *`transactionID`* los valores se recuerdan durante 90 días. Si el proceso de interacción sin conexión supera los 90 días, póngase en contacto con el Servicio de atención al cliente para ampliar el límite.

>[!NOTE]
>
>The *`transactionID`* variable can contain any character other than a comma. Debe estar en la misma ubicación donde se especifica el límite de caracteres (100 bytes). Si se utilizan caracteres de bytes múltiples, debe habilitarse la compatibilidad con caracteres de bytes múltiples para evitar problemas con caracteres imprevistos en *`transactionID`*.

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

Los visitantes se pueden identificar mediante la variable o por dirección IP o agente de usuario.

<!-- 

visitorID.xml

 -->

The *`visitorID`* can be up to 100 alpha-numeric characters and must not contain a hyphen.

Si configura explícitamente una ID personalizada, siempre se utilizará antes de los otros métodos de ID.

Este es el orden de uso: s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** Tamaño máximo** | ** Parámetro depurador** | ** Informes rellenados** | ** Valor predeterminado** |
|---|---|---|---|
| 100 bytes | vid | n.d. | "" |

**Sintaxis y valores posibles** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

>[!NOTE]
>
>The *`visitorID`* variable should not contain a hyphen.

**Ejemplos** {#section_F7F07FEFAC3644A5A084D166ACE1315E}

```js
s.visitorID="abc123"
```

**Parámetros de configuración** {#section_582B376FE55C4BCA8F978E0F62B5DB54}

Ninguna

## visitorNamespace {#concept_8369DDB3830C4BF2905F1CFC8C8B0D92}

La variable se usa para identificar el dominio con el que se configuran las cookies.

<!-- 

visitorNamespace.xml

 -->

If *`visitorNamespace`* is used in your JavaScript file, do not delete or alter it. If *`visitorNamespace`* changes, all visitors reported in Analytics may become new visitors. El historial de visitantes se desconecta del tráfico actual y futuro. No modifique esta variable sin la autorización de un representante de Adobe.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | ns | N.D. | "" |

Analytics utiliza una cookie para identificar de manera única a los visitantes del sitio. If *`visitorNamespace`* is not used, the cookie is associated 2o7.net. If *`visitorNamespace`* is used, the cookie is associated with a sub-domain of 2o7.net. Todos los visitantes del sitio deberán tener las cookies asociadas con el mismo dominio o subdominio.

El motivo para usar la variable *`visitorNamespace`* es evitar la posibilidad de sobrecargar el límite de cookies de un explorador. Internet Explorer impone un límite de 20 cookies por dominio. Usando la variable *`visitorNamespace`*, las cookies de Analytics de otras empresas no entrarán en conflicto con las cookies del visitante.

**Sintaxis y valores posibles** {#section_EE247FE371784CA4B6058182181F3EA1}

The value of *`visitorNamespace`* must be provided by Adobe and is a string of ASCII characters that don't contain commas, periods, spaces, or special characters.

```js
s.visitorNamespace="company_specific_value"
```

**Identificación de visitante en grupos de informes** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

If you do not specify a `visitorNamespace`, each report suite in your company receives its own visitor ID cookie written as `s_vi_[random string]`. Si especifica `visitorNamespace`, se utilizará la misma cookie `s_vi` para todos los grupos de informes que envían datos al `trackingServer` especificado. Si ha implementado etiquetado de grupos múltiples, asegúrese de especificar el espacio de nombres del visitante de modo que cada grupo de informes utilice la misma cookie.

**Ejemplos** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Parámetros de configuración** {#section_1128A2531ECC43DFA6749ECC21F050A2}

Ninguna

## zip {#concept_C1DF93083553410DA36EAB61FBFDF69A}

Las variables y son variables de conversión.

<!-- 

zip.xml

 -->

Son similares a las eVars en cuando a que capturan eventos pero, a diferencia de estas, no persisten. La variable *`zip`* and *`state`* variables are like eVars that expire immediately.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 50 bytes | zip | Conversión &gt; Perfil del visitante &gt; Códigos postales | "" |

Como las variables *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. For example, if you are using *`zip`* to compare conversion rates by Zip Code, you should populate *`zip`* on every page of the checkout process. Adobe recomienda usar la dirección de facturación como fuente del código postal. Puede elegir usar la dirección de envío, siempre que solo haya una en el pedido. Un sitio multimedia puede elegir usar  *`zip`* and *`state`* for registration or ad click-through tracking.

**Sintaxis y valores posibles** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

The *`zip`* variable does not impose any value or format restrictions. There are no limitations on *`zip`* outside of the standard variable limitations.

**Ejemplos** {#section_F25C0D0CC3C04B81892A662CD605C593}

```js
s.zip="92806"
```

```js
s.zip="92806-4115"
```

**Parámetros de configuración** {#section_7987084EECC34DD38B643B94F82385CA}

Ninguna

**Problemas, preguntas y consejos** {#section_E86774D5CE8B40EFA36353CDEE3A84D0}

* Rellene [!UICONTROL zip] en todas las páginas en las que se activó un evento relevante (todas las páginas del proceso de cierre de compra).
* The *`zip`* and *`state`* variables act like eVars that expire on the Page View.

