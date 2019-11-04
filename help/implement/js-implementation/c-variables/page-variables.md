---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Implementación de Analytics
seo-description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
seo-title: Variables de página
solution: Analytics
subtopic: Variables
title: Variables de página
topic: Desarrollador e implementación
uuid: 2578eddd-74db-4a8a-96f2-d0289ec1826b
translation-type: tm+mt
source-git-commit: 8a96dc0587125e1b72e3146eb2f0923cecd808fb

---


# Variables de página

Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.

## browserHeight {#concept_DB87062001824369A56AA1E7969EC02A}

La variable muestra la altura de la ventana del explorador.

<!-- 
browserheight.xml
-->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

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

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

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

Hay dos maneras de rellenar la variable *`campaign`*:

* El complemento [!UICONTROL getQueryParam], usado en el archivo JavaScript, recupera un parámetro de cadena de consulta de la dirección URL. Para obtener más información sobre el complemento [!UICONTROL getQueryParam], consulte [Complementos de implementación](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

* Asigne un valor a la variable *`campaign`* en el HTML de la página web.

Con cualquiera de los métodos para rellenar la variable *`campaign`*, el tráfico del botón Atrás puede aumentar el número real de pulsaciones desde un elemento de campaña.

Por ejemplo, un visitante entra en el sitio haciendo clic en una palabra clave de búsqueda de pago. Cuando el visitante llega a la página de aterrizaje, la dirección URL contiene un parámetro de cadena de consulta que identifica el código de seguimiento de la palabra clave. Después, el visitante hace clic en un vínculo a otra página, pero inmediatamente hace clic en el botón Atrás para volver a la página de aterrizaje. Cuando el visitante llega por segunda vez a la página de aterrizaje, la dirección URL con el parámetro de cadena de consulta identifica de nuevo el código de seguimiento y se registra una segunda pulsación, aumentando incorrectamente el número de pulsaciones.

Para evitar este aumento incorrecto del número de pulsaciones, Adobe recomienda usar el complemento [!UICONTROL getValOnce] para forzar que cada pulsación de la campaña se cuente solo una vez. Para obtener más información sobre el complemento [!UICONTROL getValOnce], consulte [Complementos de implementación](../../../implement/js-implementation/plugins/impl-plugins.md#concept_021F5E4A6BD745AE91E85E7138BE930F).

**Sintaxis y valores posibles** {#section_91A141841A6D4711A1EE08A6145A301D}

```js
s.campaign="112233"
```

La variable *`campaign`* tiene las mismas limitaciones que todas las demás variables. Adobe recomienda limitar el valor a los caracteres ASCII estándar.

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

Cuando las secciones tienen uno o más niveles de subsecciones, es posible mostrar dichas secciones en la variable *`channel`* o utilizar variables separadas para identificar niveles.

**Sintaxis y valores posibles** {#section_ED90592730B64242A737F4090F1DCEE4}

```js
s.channel="value"
```

La variable *`channel`* no tiene limitaciones adicionales en sus valores.

**Ejemplos** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Problemas, preguntas y consejos** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

Si el sitio contiene varios niveles, utilice *`hierarchy`* u otra variable para designarlos. El valor *`channel`* no persiste, pero los eventos de éxito activados en la misma página se atribuyen al valor de *`channel`*.

## colorDepth {#concept_756516E181F449B996DA9CC5A53FFA3D}

La variable se utiliza para mostrar el número de bits usado para mostrar el color en cada píxel de la pantalla.

<!-- 

colordepth.xml

 -->

Por ejemplo, 32 representa 32 bits de color en la pantalla. Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en `props/eVars`, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| c | 8, 16 y 32 | 32 | Tráfico &gt; Tecnología &gt; Profundidad de color del monitor |

## connectionType {#concept_2F98ECB8BB3D490F834F274EFF02860E}

La variable, en Internet Explorer, indica si el explorador está configurado con una conexión LAN o de módem.

<!-- 

conntype.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en `props/eVars`, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| ct | lan o modem | lan | Tráfico &gt; Tecnología &gt; Tipo de conexión |

## cookiesEnabled {#concept_DF5B37E38D0D4F6DB910F419F92467ED}

La variable indica si JavaScript puede configurar una cookie de sesión de origen.

<!-- 

cookiesenabled.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en `props/eVars`, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo |
|---|---|---|
| k | Y o N | Y |

## dc {#concept_ECE6C83376704B3C84A920EFDD338A31}

(Obsoleta) La variable permite seleccionar el centro de datos al que se envían los datos.

<!-- 

dc.xml

 -->

> [!NOTE] La variable dc está obsoleta. Debe configurar *`trackingServer`para todas las implementaciones con el valor generado por el Administrador de códigos en s_code.js.*

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | 112 |

El centro de datos se identifica en la variable *`dc`* para que coincida con [!UICONTROL ActionSource].

## eVarN {#concept_74FFDDB44B5344E18ABC6F2F99DF4649}

Las variables [!UICONTROL eVar] se usan para generar informes personalizados.

<!-- 

eVarN.xml

 -->

Cuando se establece un valor en una eVar para un visitante, el valor se recuerda hasta que caduca. Cualquier evento de éxito que encuentra el visitante mientras la eVar está activa se cuenta hacia el valor eVar.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 255 bytes | V1-v75 ( [o v100 o v250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) | Conversión personalizada | "" |

**Caducidad** {#section_6DB5882B960D4660AE248B91B76883C4}

Las [!UICONTROL eVars] caducan después del período de tiempo que especifique. Cuando la eVar caduca, ya no recibe el crédito por los eventos de éxito. Las eVars también se pueden configurar para que caduquen cuando se produzcan eventos de éxito. Por ejemplo, si tiene una promoción interna que caduca el final de una visita, la promoción interna recibe el crédito solo por las compras o registros que se produzcan durante la visita en la que se activaron.

Hay dos maneras de que una eVar caduque:

* Puede configurar la eVar para que caduque después de un período de tiempo o evento especificados.
* Puede forzar la caducidad de una eVar, lo que resulta útil cuando se cambia el propósito de una variable.

Si se usa una eVar en mayo para reflejar promociones internas y caduca después de 21 días, y en junio se usa para capturar palabras clave de búsqueda interna, el 1 de junio, debe forzar la caducidad o restablecer la variable. Al hacerlo, no se incluyen los valores de la promoción interna en los informes de junio.

**Distinción entre mayúsculas y minúsculas** {#section_6E9145B7FCC2438E95BB35AAE3857412}

Las eVars no distinguen entre mayúsculas y minúsculas, pero se muestran en la escritura en mayúsculas de la primera aparición. Por ejemplo, si la primera instancia de eVar1 es "Sesión iniciada" pero todas las demás instancias se pasan como "sesión iniciada", los informes siempre mostrarán "Sesión iniciada" como valor de eVar.

**Contadores** {#section_D8403F0C175E4BC9BE4F2E794B1F4D33}

Aunque las eVars se usan habitualmente para guardar valores de cadena, también se pueden configurar para que actúen como contadores. Las eVars son útiles como contadores para contar el número de acciones que un usuario realiza antes de un evento. Por ejemplo, puede usar una eVar para capturar el número de búsquedas internas antes de la compra. Cada vez que un visitante realiza una búsqueda, la eVar debe contener un valor de '+1'. Si un visitante realiza cuatro búsquedas antes de una compra, verá una instancia con cada recuento total: 1.00, 2.00, 3.00 y 4.00. Sin embargo, solo el valor 4.00 recibe el crédito por el evento purchase (métricas de pedidos e ingresos). Solo se permiten números positivos como valores de un contador eVar.

**Subrelaciones** {#section_2BEABBBC735241F4BA42E74D19B5AEE0}

Uno de los requisitos habituales para un informe de [!UICONTROL eVar personalizado] es la posibilidad de desglosar un informe de [!UICONTROL eVar personalizado] por otro. Por ejemplo, si una eVar contiene el sexo y otra contiene el sueldo, puede preguntarse lo siguiente: de las mujeres visitantes de mi sitio, ¿cuántos ingresos generaron las mujeres que ganan más de 50.000 euros al año? Las eVars con subrelaciones completas admiten este tipo de desglose en los informes. Por ejemplo, si la eVar del sexo tiene habilitadas subrelaciones completas, todos los demás informes de eVar personalizados se pueden desglosar por sexo, y el sexo se puede desglosar por todos los demás. Para ver la relación entre dos informes, solo uno de ellos necesita tener habilitadas las subrelaciones completas. De forma predeterminada, los informes [!UICONTROL Campañas], [!UICONTROL Productos] y [!UICONTROL Categoría] están completamente subrelacionados (cualquier eVar se puede desglosar por campaña o productos).

**Sintaxis y valores posibles** {#section_BD46438B14F3488FB9AC42994C317B06}

Aunque se puede cambiar el nombre de las eVars, siempre se debe hacer referencia a ellas en el archivo JavaScript por eVarX, donde X es un número entre 1 y 75 ([ o 100 o 250](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)).

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

Las eVars se pueden configurar en [!UICONTROL Analytics &gt; Administración &gt; Grupos de informes &gt; Editar configuración &gt; Conversión &gt; Variables de conversión]. Todas las eVars se pueden configurar con un [!UICONTROL Nombre], [!UICONTROL Tipo], [!UICONTROL Asignación], [!UICONTROL Caduca después de] o [!UICONTROL Restaurar]. Cada opción de configuración se trata por separado.

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
   <td> eventos </td> 
   <td> <p>Eventos del carro de compras </p> <p>Eventos personalizados </p> </td> 
   <td> N.D. </td> 
  </tr> 
 </tbody> 
</table>

Un [!UICONTROL evento] se debe considerar un hito dentro de un sitio. Los eventos de éxito generalmente se rellenan en la página de confirmación final de un proceso, como un proceso de registro o la suscripción a un boletín. Los eventos personalizados se definen rellenando la variable de eventos con los valores literales definidos en la sección Valores posibles, a continuación.

De forma predeterminada, los eventos de éxito se configuran como eventos de *contador*. Los eventos de contador contabilizan el número de veces que se configura un evento de éxito (x+1). Los eventos también se pueden configurar como eventos *numéricos*. Los eventos numéricos permiten especificar el número que se incrementará. Esto podría ser necesario cuando se contabilizan valores dinámicos o arbitrarios, como los resultados devueltos por una búsqueda interna.

Un tipo de evento final, *moneda*, permite definir la cantidad que se sumará (similar a los eventos numéricos), pero la muestra como moneda en los informes y está sujeta a las conversiones monetarias basadas en el valor de s. *`currencyCode`* y en la configuración de moneda predeterminada para su grupo de informes. Para obtener información adicional sobre cómo usar eventos numéricos y monetarios, consulte [Productos](../../../implement/js-implementation/c-variables/page-variables.md#concept_A4007F6307E4419DAA65E1668A8FEBA2).

**Configuración de la variable** {#section_9195286C34C54B02B2598E2B856492C3}

La variable [!UICONTROL s.events] está habilitada de forma predeterminada para todas las implementaciones. Los siete eventos de conversión preconfigurados están habilitados automáticamente para todos los grupos de informes nuevos. Los nuevos eventos personalizados (event1- [event100 o event1000](../../../implement/js-implementation/c-variables/page-variables.md#concept_558663F3B8164986AB5D94128FEA7B28)) los puede habilitar un usuario con derechos de administrador en Admin Console.

**Valores posibles** {#section_18395A3BEFEB4E9F8D7B2ED0001FBE4E}

La lista siguiente muestra los posibles valores para la variable de eventos:

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

> [!NOTE] Los cambios en las jerarquías pueden conllevar cargos por servicio.

## homepage {#concept_0A3E416F1A064BA396B5FCEABFB7B0B4}

La variable, en Internet Explorer, indica si la página actual está configurada como página de inicio del usuario.

<!-- 

homepage.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

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

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| v | Y o N | Y | Tráfico &gt; Tecnología &gt; Java |

## javascriptVersion {#concept_19E2C9F87BB24E69B911C0F5873CAA90}

La variable indica la versión de JavaScript que admite el explorador.

<!-- 

javascriptVersion.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| j | 1.0, 1.1, 1.2, … 1.7 | 1.7 | Tráfico &gt; Tecnología &gt; Versión de JavaScript |

La versión H.10 y posteriores del archivo JavaScript detectan de forma precisa hasta la versión 1.7 (la última versión cuando se lanzó H.10). Las versiones anteriores del archivo JavaScript solo detectan hasta la versión 1.3

## linkName {#concept_1B2A3F56C9AD4C23A8A4331730EC2B8F}

La variable es una variable opcional utilizada en el [!UICONTROL seguimiento de vínculos] que determina el nombre de un vínculo de salida, de descarga o personalizado.

<!-- 

linkName.xml

 -->

La variable *`linkName`* no suele ser necesaria ya que el tercer parámetro de la función *`tl()`* la sustituye.

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
   <td> <p>Descargas de archivos </p> <p>Vínculos personalizados </p> <p>Vínculos de salida </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

[!UICONTROL Vínculos personalizados] hace referencia a los vínculos que envían datos de seguimiento. La variable *`linkName`* (o el tercer parámetro de la función *`tl()`*) identifica el valor que aparece en los informes de vínculos [!UICONTROL personalizados], [!UICONTROL de descarga] o [!UICONTROL de salida]. Si *`linkName`* no se rellena, la dirección URL del vínculo aparecerá en el informe.

**Sintaxis y valores posibles** {#section_C8D89834C98B4C7A858C947293C4148E}

```js
s.linkName="Link Name"
```

No existen limitaciones de *`linkName`* además de las limitaciones estándar de las variables.

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

* La variable *`linkName`* se reemplaza con el tercer parámetro en la función *`tl()`*.

* Si la variable *`linkName`* y el tercer parámetro en la función *`tl()`* están vacíos, la URL completa del vínculo (con excepción de la cadena de consulta) se verá en el informe (aunque el vínculo sea relativo).

## linkType {#concept_7695692AF5D843E3B370F6D345E32964}

La variable es una variable opcional utilizada para el seguimiento de vínculos que determina qué informe mostrará el nombre del vínculo o la dirección URL (vínculos de salida, de descarga o personalizados).

<!-- 

linkType.xml

 -->

La variable *`linkType`* no suele ser necesaria ya que el segundo parámetro de la función *`tl()`* la sustituye.

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
   <td> <p>Descargas de archivos </p> <p>Vínculos personalizados </p> <p>Vínculos de salida </p> </td> 
   <td> "" </td> 
  </tr> 
 </tbody> 
</table>

Los vínculos personalizados envían datos a Analytics. La variable *`linkType`* (o el segundo parámetro de la función *`tl()`*) se utiliza para identificar el informe en el que se mostrará el nombre del vínculo o la URL (informe de vínculos [!UICONTROL de salida], [!UICONTROL de descarga] o [!UICONTROL personalizados]).

Para los vínculos de salida y de descarga, la variable *`linkType`* se rellena automáticamente en función de si el vínculo en el que se hizo clic es de salida o de descarga. Se puede configurar un vínculo personalizado para enviar datos a cualquiera de los tres informes con esta variable o con el segundo parámetro en la función *`tl()`*. Al establecer *`linkType`* en “o”, “e” o “d”, la dirección URL *`linkName`* o del vínculo se envía respectivamente al informe Vínculos [!UICONTROL personalizados], [!UICONTROL de salida] o [!UICONTROL Descargas de archivos].

**Sintaxis y valores posibles** {#section_18DB3A8083FB4F75B970055ED336DA4E}

La sintaxis de la variable *`linkType`* depende de si utiliza XML o una cadena de consulta.

Si utiliza XML, la variable puede contener un único carácter, ya sea “o”, “e” o “d”.

```js
s.tl(this,'o','Link Name');
```

Si utiliza la cadena de consulta `pe`, debe utilizar `lnk_d`, `lnk_e` o `lnk_o`.

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

* Si no se especifica el valor de *`linkType`*, se usarán como vínculos personalizados (“o”).

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
* Cualquier variable de tráfico personalizado puede convertirse en una prop de lista. (Excepciones: [pageName](../../../implement/js-implementation/c-variables/page-variables.md#concept_5827B499DAC34B5D8445F9D9140CC328), [channel](../../../implement/js-implementation/c-variables/page-variables.md#concept_C7770B8C15724A99B10F8F468AF82D0D) y [server](../../../implement/js-implementation/c-variables/page-variables.md#concept_BF77952603BA454BAFC9A0A81D06A7D2)).

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

1. Vaya a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Grupos de informes]**
1. Seleccione el grupo de informes.
1. Haga clic en **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL Conversión]** &gt; **[!UICONTROL Lista de variables]**.

* **Nombre**: Cada valor delimitado puede contener un máximo de 255 caracteres (o menos si se utilizan caracteres multibyte). Esta es la longitud máxima de cada elemento.
* **Delimitador de valores**: carácter utilizado para separar valores en una variable de lista. Normalmente son caracteres como comas, dos puntos, barras verticales o algún otro similar.

   >[!NOTE]
   >
   >Los caracteres de bytes múltiples no se admiten como delimitadores en variables de lista. El delimitador debe ser de un solo byte.

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

Para establecer o editar las variables de lista, vaya a **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administrador]** &gt; **[!UICONTROL Grupos de informes]** &gt; **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL Conversión]** &gt; **[!UICONTROL Variables de lista]**.

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
   <th colname="col1" class="entry"> Activity Map </th> 
   <th colname="col2" class="entry"> s.list1 </th> 
   <th colname="col3" class="entry"> s.events/s.products </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Página 1 </td> 
   <td colname="col2"> <code> s.list1="value1,value2,value3"; </code> </td> 
   <td colname="col3"> (sin configurar) </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Página 2 </td> 
   <td colname="col2"> <code> s.list1="value4,value5,value6"; </code> </td> 
   <td colname="col3"> <p> <code> s.events="purchase"; </code> </p> <p> <code> s.products=";product;1;200" </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Resultado**: Todos los valores configurados en la list var1 en cualquier momento durante la visita (value1,value2,value3,value4,value5,value6) obtienen el crédito total de la compra.

## maxDelay {#concept_B355038C3B094BB68C0DC6C80F9FE5B0}

La variable s.maxDelay se usa principalmente en integraciones de DFA de Genesis para determinar el tiempo de espera al contactar con el host DFA. Si Adobe no recibe una respuesta de los servidores DFA en el período configurado en la variable  la conexión se interrumpe y los datos se procesan normalmente. Implemente esta variable si le preocupa el tiempo de respuesta de DFA en cada página. Se recomienda experimentar con este valor para determinar el tiempo de espera óptimo.

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

   Los datos de visitas de Analytics se perderían si el usuario sale de la página durante el tiempo de *`s.maxDelay`*.

* Reducir el tiempo de espera reducirá el riesgo de perder datos de visitas de Analytics, pero puede reducir la cantidad de datos de DFA que se envían con los datos de visitas.

   La pérdida de datos de integración de DFA se produce cuando el período de *`s.maxDelay`* no concede el tiempo suficiente para que el host de DFA responda.

> [!NOTE] Adobe no controla el tiempo de respuesta de DFA. Si experimenta problemas continuos incluso después de aumentar el tiempo de demora máximo a un valor razonable, consulte con el administrador de cuentas DFA de su organización.

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
   <td> Ninguna </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxis y valores posibles** {#section_FEC1B01FDD234ACEB63C0558BEEB5CBC}

**Método autoTrack:**

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
| 64 kB | pev3 | Videos; Siguiente flujo de vídeos; Anterior flujo de vídeos; Segmentos de vídeo vistos; Tiempo invertido en vídeo | Ninguna |

**Sintaxis y valores posibles** {#section_F97A2253BBD24FEBBC225F233A319F5D}

**Método autoTrack:**

Si se usa [!UICONTROL s.Media.autoTrack], no es necesario implementar la variable *`mediaName`* explícitamente. El código de AppMeasurement para JavaScript la determina automáticamente.

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
| 100 bytes | pev3 | Reproductores de vídeos | Ninguna |

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
   <td> Ninguna </td> 
  </tr> 
 </tbody> 
</table>

**Sintaxis y valores posibles** {#section_9A63266633C4427CB4A6549E4D887B85}

**Método autoTrack:**

Si se usa [!UICONTROL s.Media.autoTrack], no es necesario implementar la *`mediaName`* explícitamente. El código de AppMeasurement para JavaScript la determina automáticamente.

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
s.Media.trackEvents="event1,purchase"
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
s.Media.trackVars="prop2,events,eVar3"
```

**Problemas, preguntas y consejos** {#section_615AE1B696124B00B78F651B03813EAB}

* Incluso aunque se especifique eVar3 en [!UICONTROL trackVars], se envía con la visita multimedia.

## mobile {#concept_0CEE045F57B444138C0EAA015FC7EA70}

La variable controla el orden con el que se usan las cookies y las ID de suscriptor para identificar a los visitantes.

<!-- 

mobile.xml

 -->

Consulte [Protocolos de red móvil](../../../implement/js-implementation/c-additional-libraries/network-protocols.md#concept_2425537FC9CB45DD868B5FA2298B6CAC).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | /5/ o /1/ en la ruta de la dirección URL de la imagen | N.D. | Ninguna |

**Sintaxis y valores posibles** {#section_7F1C58090C454882BA9D3D66C9263A76}

```js
s.mobile="any_string" //subscriber id used first, produces /5/ in path of image url 
s.mobile=""  // if set to an empty string or not set at all, cookies used first, produces /1/ in path of image url 
```

**Problemas, preguntas y consejos** {#section_06CD5CB4EF1E4B9FBE3B9D1F18AAFA30}

Utilice la identificación entre visitantes para mitigar los posibles picos en el tráfico de visitantes al utilizar la variable *`s.mobile`* con la implementación de cookies de JavaScript.

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
   <td> URL de la página </td> 
  </tr> 
 </tbody> 
</table>

La variable *`pageName`* debe rellenarse con un valor que los usuarios comerciales reconozcan. En la mayoría de los casos, el valor *`pageName`* no es la dirección URL ni la ruta al archivo. Los valores habituales de *`pageName`* suelen ser “Página de inicio”, “Cierre de compra”, “Gracias por su compra” o “Registro”.

Tenga cuidado de que no aparezcan caracteres de nueva línea, guiones -em o -en u otros caracteres HTML en el nombre de la página y otras variables. Algunos exploradores envían caracteres de nueva línea pero otros no, lo que hace que los datos de Analytics se dividan en dos nombres de página aparentemente iguales. Muchos procesadores de texto y clientes de correo electrónico convertirán automáticamente un guión corto en un guión -en o -em al escribir. Como los guiones -en y -em son caracteres no permitidos en las variables de Analytics (caracteres ASCII con códigos superiores a 127), Analytics no registrará los nombres de página que contengan caracteres no permitidos y, en su lugar, mostrará la dirección URL.

Si *`pageName`* se deja en blanco, se usa la dirección URL para representar el nombre de página. Dejar *`pageName`* en blanco suele causar problemas porque la dirección URL podría no ser siempre la misma para una página (`www.mysite.com` y `mysite.com` son la misma página con direcciones URL diferentes).

**Sintaxis y valores posibles** {#section_7A61EE70F1A84D26B414404998C84BA8}

La variable *`pageName`* debe contener un identificador útil para los usuarios comerciales de Analytics.

```js
s.pageName="page_name"
```

No existen limitaciones de *`pageName`* además de las limitaciones estándar de las variables.

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

The *`pageType`* variable captures the errant URL when a 404 Error page is displayed, which allows you to quickly find broken links and paths that are no longer valid on the custom site. Configure la variable *`pageType`* en la página de error exactamente como se muestra a continuación.

No utilice la variable del nombre de página en las páginas de error 404. La variable *`pageType`* se utiliza solamente para la página de error 404.

En la mayoría de los casos, la página de error 404 es una página estática codificada. En estos casos, es importante que la referencia al archivo .JS se configure en un directorio/ruta global o relativo apropiado.

**Sintaxis y valores posibles** {#section_C1C59968226446559B05F6EE7374D525}

El único valor permitido de *`pageType`* es “errorPage”, como se muestra a continuación.

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

Para capturar otros errores del lado del servidor (como los errores ), use una prop para captar el mensaje de error y ponga `500 Error: <URL>` donde `<URL>` es la dirección URL solicitada, en la variable *`pageName`*. Este procedimiento permite usar informes de [!UICONTROL control de rutas] para ver qué rutas provocaron que los usuarios generaran errores 500. La prop explica qué mensaje de error proporciona el servidor.

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

> [!NOTE] Aunque Adobe admite valores para *`pageURL`* de hasta 64 K, algunos exploradores imponen un límite de tamaño en la dirección URL de las solicitudes de imagen. Para evitar el truncamiento de otros datos, las direcciones URL de la página superiores a 255 bytes se dividen: los primeros 255 bytes aparecen en el parámetro `g=` y los bytes restantes se muestran más adelante en la cadena de consulta, en el parámetro de consulta `-g=`.

**Sintaxis y valores posibles** {#section_22AF3BF7C2F743549967B0C760A095C0}

La variable *`pageURL`* debe ser una dirección URL válida, con un protocolo válido. El dominio será obligado a mostrarse en letra minúscula antes de rellenarse en los informes, y la cadena de consulta puede ser depurada, en función de la configuración de Analytics.

```js
s.pageURL="proto://domain/path?query_string"
```

Solo se permiten caracteres compatibles con URL en la dirección URL de la página.

> [!NOTE] Se recomienda encarecidamente que se ponga en contacto con su asesor de Adobe o con el servicio de Atención al cliente antes de utilizar la variable *`pageURL`* con fines personalizados.

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

La variable, en exploradores Netscape y Mozilla, enumera los complementos instalados en el explorador.

<!-- 

plugins.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| p | Complementos reconocidos | IE Tab Plug-in;QuickTime Plug-in 7.1.6;Mozilla Default Plug-in;iTunes Application Detector;Adobe Acrobat;ActiveTouch General Plugin Container;Shockwave Flash;Microsoft Office 2003;Java(TM) Platform SE 6 U1;Biblioteca de vínculos dinámicos del complemento Reproductor de Windows Media;Microsoft® DRM; | Tráfico &gt; Tecnología &gt; Complementos |

## Productos {#concept_A4007F6307E4419DAA65E1668A8FEBA2}

La variable se usa para rastrear productos y categorías de productos, así como precios y cantidades de compra. Los productos se suelen configurar junto con un evento de carro o un evento

<!-- 

products.xml

 -->

>[!IMPORTANT]
>
>En enero de 2016, se actualizó la lógica que establece el evento *`prodView`* automáticamente, lo que sucede cuando hay un *`product`* pero ningún *`event`*. Esta actualización puede provocar un aumento en los eventos *`prodView`*. *`prodViews`* aumentarán solo cuando:
>
>1. La variable de eventos contiene únicamente un evento no reconocido, como *`shoppingCart`* o *`cart`*, que no son eventos válidos.
   >
   >
1. La variable *`products`* no está vacía.
>
>
Un posible efecto secundario es que las eVars de comercialización activadas por los eventos *`prodView`* podrían asociarse con un *`product`* vacío, pero solo si la *`product list`* contiene únicamente un producto no válido (como un punto y coma sin producto enumerado).

La variable *`products`* realiza el seguimiento de la manera en que los usuarios interaccionan con los productos del sitio. Por ejemplo, la variable products puede realizar el seguimiento de cuántas veces se ha visto un producto, se ha agregado al carro de compras, se ha cerrado su compra y se ha comprado. También puede realizar el seguimiento de la eficacia relativa de las categorías de comercialización del sitio. Los siguientes son escenarios habituales para usar la variable products.

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
   <td> <p>La cadena de productos <span class="wintitle"></span> tiene un tamaño máximo de 64 k. </p> </td> 
   <td> Productos </td> 
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

La variable *`products`* debe configurarse junto con un evento de éxito.

**Configurar products con un evento purchase** {#section_618AAC96E7B541A7AABAA028E5F4E5C3}

El evento *`purchase`* debe configurarse en la página de confirmación final (“Gracias”) del proceso de pedido. El nombre del producto, categoría, cantidad y precio se capturan todos en la variable *`products`* campaign. Aunque la variable *`purchaseID`* no es obligatoria, es muy recomendable para evitar pedidos duplicados.

**Eventos monetarios específicos de productos** {#section_F814DF053C0D463A97DA039E6323720C}

Si un evento de moneda recibe un valor en la variable *`products`* en lugar de en la variable de eventos, solo se aplica a ese valor. Esto es útil para realizar un seguimiento de descuentos específicos del producto, envíos de productos y valores similares. Por ejemplo, si ha configurado el evento 1 para realizar un seguimiento del envío de productos, un producto con un cargo de envío de "4,50" podría parecerse a lo siguiente:

```js
s.events="event1" 
s.products="Footwear;Running Shoes;1;99.99;event1=4.50"
```

En este ejemplo, el valor de 4,50 está asociado directamente al producto "Running Shoes". Si agrega event1 al informe de productos, verá cómo aparece "4,50" en el elemento de línea "Running Shoes". Al igual que ocurre con Price, este valor debe reflejar el total de la cantidad mostrada. Si tiene 2 artículos con un cargo de envío de 4,50 cada uno, el valor de event1 debe ser "9,00".

**Eventos monetarios de todo el pedido** {#section_D06F76A8A1F8498EB1BD6D8C8B9D5BE0}

Si un evento de moneda recibe un valor en la lista de eventos en lugar de la variable *`products`*, se aplica a todos los productos de la variable *`products`*. Esto es útil para rastrear descuentos, envíos y valores similares en los pedidos sin modificar el precio del producto o rastreándolo en la lista de productos por separado.

Por ejemplo, si ha configurado event10 para que contenga descuentos en los pedidos, puede que aparezca una compra con un 10 % de descuento similar a la siguiente:

```js
s.events="purchase,event10=9.95" 
s.products="Footwear;Running Shoes;1;69.95,Running Essentials;Running Socks;10;29.50" 
s.purchaseID="1234567890"
```

En los informes de eventos monetarios, el total del informe representa el total del evento sin duplicados (en este ejemplo, la cantidad total de descuentos durante el período de informe) y no la suma de valores de evento para cada producto. Por ejemplo, aparecería "9,95" tanto para "Running Shoes" como para "Running Socks" y el total también sería "9,95".

> [!NOTE]si se especifica un valor para el mismo evento numérico/monetario en la variable *`products`* y en la variable *`events`*, se utiliza el valor de *`events`*.

**Problemas, preguntas y consejos** {#section_D38FD0B79C0347B9AB4CF1632183DA2E}

* La variable *`products`* siempre debe configurarse junto con un evento de [!UICONTROL éxito] (events). Si no se especifica un evento de [!UICONTROL éxito], el evento predeterminado es [!UICONTROL prodView].

* Elimine todas las comas y punto y comas de los nombres de producto y categoría antes de rellenar los productos.
* Elimine todos los caracteres HTML (símbolos de marca registrada, marca comercial, etc.).
* Elimine los símbolos de moneda ($) del precio.

**Ejemplos** {#section_FCC6EF43D3534ECB9A95CDB05820F564}

<table id="table_6F1334E73CE048A5AC0CC28B561C1B2D"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category2;ABC123,;ABC456" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category3;ABC123;1;10" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.products="Category;ABC123;1;10,;ABC456;2;19.98" </code> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;;;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99,;ABC123;2;19.98;event1=1.99" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping|evar2=3 Stars" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping, ;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3" </code> <p> <code> s.products="Category;ABC123;1;10;event1=1.99|event2=25;evar1=2 Day Shipping,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> s.events="event1,event2,event3=9.95" </code> <p> <code> s.products="Category;ABC123;,;ABC456;2;19.98;event1=1.99|event2=100;evar1=Ground Shipping,;;;;event3=2.9;evar3=20% off" </code> </p> </td> 
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

Siempre que se use el evento [!UICONTROL purchase] en el sitio, se debe usar la variable *`purchaseID`*.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 20 bytes | purchaseID | Conversión &gt; Compras &gt; Conversión de ingresos | "" |

Cuando un visitante compra un artículo en su sitio, *`purchaseID`* se rellena en la página "Gracias" en el mismo lugar donde se activa el evento [!UICONTROL purchase]. Si *`purchaseID`* se rellena, los productos de la página “Gracias” se contabilizan solo una vez por *`purchaseID`*. Esto resulta crítico porque muchos visitantes del sitio guardarán las páginas "Gracias" o "Página de confirmación" para sus propios fines. La variable *`purchaseID`* evita que las compras se contabilicen cada vez que se visita la página.

Además de evitar que los datos de la compra se cuenten dos veces, el *`purchaseID`*, cuando se utiliza, evita que los datos de conversión se cuenten dos veces en los informes.

**Sintaxis y valores posibles** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

El *`purchaseID`* debe tener un máximo de 20 caracteres, que deben ser ASCII estándar.

**Ejemplos** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Parámetros de configuración** {#section_1808631C96674380BF9C4A6D9A2C568E}

Ninguna

**Problemas, preguntas y consejos** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

La variable *`purchaseID`* permite contabilizar todas las variables de conversión de la página solo una vez en los informes.

## referrer {#concept_3D8E6A5D30DC4D92982EFA34D4C7F81B}

La variable puede utilizarse para restablecer la información perdida del referente.

<!-- 

referrer.xml

 -->

Las redirecciones de JavaScript y del lado del servidor generalmente se utilizan para enrutar a los visitantes hacia las ubicaciones correctas. Sin embargo, cuando se redirecciona un explorador, la dirección URL de referencia original se pierde.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 255 bytes | R | Tráfico &gt; Conversión &gt; Métodos de búsqueda | document.referrer |

Muchas empresas usan redirecciones en numerosos lugares de sus sitios web. Por ejemplo, se puede enviar a un visitante a través de una redirección desde un resultado de búsqueda de pago del motor de búsqueda. Cuando se redirecciona un explorador, generalmente el referente se pierde. La variable La variable *`referrer`* se puede utilizar para restaurar el valor original de *`referrer`* en la primera página después de una redirección. La variable *`referrer`* puede rellenarse desde el servidor o por medio de JavaScript desde la cadena de consulta.

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

La variable *`referrer`* debe parecer una dirección URL estándar e incluir un protocolo.

## resolution {#concept_8CBDDBE710744A3AA09E6B1E1519BF30}

La variable indica la resolución de la pantalla del visitante que está viendo la página web.

<!-- 

resolution.xml

 -->

Esta variable se rellena después del código de página y antes de que se ejecute *`doPlugins`*.

> [!NOTE] Esta variable solo debe leerse, nunca configurarse.

Puede leer estos valores y copiarlos en props/eVars, pero no debe modificarlos nunca. Esta variable se incorporó por primera vez con la versión H.11 del archivo JavaScript.

| Parámetro de consulta | Valor | Ejemplo | Informes afectados |
|---|---|---|---|
| s | WxH | 1680 x 1050 | Tráfico &gt; Tecnología &gt; Resolución del monitor |

## s_objectID {#concept_48B50DE6B7E546EBB4D187033F1CAF2B}

La variable es una variable global que debe configurarse en el evento [!UICONTROL onClick] de un vínculo.

<!-- 

s_objectID.xml

 -->

Si crea un ID de objeto único para un vínculo o una ubicación de vínculo en una página, se puede mejorar el seguimiento de actividades de visitante, o bien utilizar [!UICONTROL Activity Map] para informar sobre un tipo o una ubicación de vínculo en lugar de la URL del vínculo.

> [!NOTE] Se requiere un punto y coma (;) final al usar s_objectID con [Activity Map](https://marketing.adobe.com/resources/help/en_US/analytics/activitymap/activitymap-link-tracking-use-case.html).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | OID | [!UICONTROL Activity Map], [!UICONTROL ClickMap] | La dirección URL absoluta de un vínculo donde se hizo clic |

Existen tres razones comunes para utilizar *`s_objectID`*:

* Para agregar actividad de visitante que cambia a menudo durante un día.
* Para separar la actividad de vínculo que el [!UICONTROL Activity Map] combina.
* Para mejorar la precisión de los informes de datos del [!UICONTROL Activity Map].

**Agregar clics en vínculos muy dinámicos** {#section_BA730A0393B149DDBCAA272C3C23A1C5}

Si el sitio es muy dinámico y los vínculos de algunas páginas cambian a lo largo del día, *`s_objectID`* puede utilizarse para identificar la ubicación de un vínculo en la página. Si *`s_objectID`* se configura como “top left 1” o “top left 2”, que representa el primer vínculo en la parte superior izquierda de la página, por ejemplo, todos los vínculos que aparezcan en esa ubicación (o que tengan *`s_objectID`* configurado con el mismo valor) se incluyen en el mismo informe con el mapa de clics de visitantes. Si no usa *`s_objectID`*, verá el número de veces que se hizo clic en un vínculo determinado pero perderá perspectiva sobre cómo los visitantes del sitio utilizaron todos los demás vínculos de esa ubicación.

**Separar clics combinados** {#section_1AE91FB8A2D3423CBE064ACF02FEEA47}

Si la variable *`pageName`* del sitio se utiliza para mostrar la sección o plantilla que está viendo un visitante, en lugar de la página específica que el visitante está viendo, puede que desee utilizar *`s_objectID`* para separar los vínculos que aparecen en varias versiones de esa plantilla de página. Por ejemplo, si tiene una página de plantilla para todos los productos del sitio, es muy probable que en todas las páginas haya un vínculo a la página de inicio y a un cuadro de búsqueda desde esa plantilla. Si desea ver cómo se utilizan esos vínculos por producto individual (en vez de por plantilla), puede rellenar *`s_objectID`* con un valor específico de un producto, por ejemplo, "prod 123789 home page" o "prod 123789 search". Una vez finalizado, el [!UICONTROL Activity Map] informará sobre esos vínculos por producto individual.

**Mejorar la precisión de[!UICONTROL Activity Map]**{#section_08B3406821294DCCABEEB99C90CF5C52}

En algunas ocasiones, los exploradores que no sean Internet Explorer, Firefox, Netscape, Opera y Safari no se incluyen en los informes. Aunque esto suponga un porcentaje reducido, cuenta para algunos clics y otras métricas. Use *`s_objectID`* en vínculos para identificar las direcciones de los problemas de informes del navegador. A continuación se incluye un ejemplo sobre cómo actualizar los vínculos para utilizar *`s_objectID`*:

```js
<a href="/art.jsp?id=559" onClick="s_objectID='top left 1';">Article 559</a> 
<a href="/home.jsp" onClick="s_objectID='prod 123789 home page';">Home</a> 
```

**Sintaxis y valores posibles** {#section_85841DF9F06A4680953D9B2A884A1A5A}

s_objectID puede contener cualquier identificador de texto.

```js
s_objectID="unique_id" 
```

No existen limitaciones de *`s_objectID`* además de las limitaciones estándar de las variables.

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

No existen limitaciones de la variable *`server`* además de las limitaciones estándar de las variables.

**Ejemplos** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Parámetros de configuración** {#section_969DB379D5BD469FBEE8D505D3000E49}

Ninguna

**Problemas, preguntas y consejos** {#section_42A28F9B01574F38891D9D54B411D8FE}

La variable *`server`* se puede usar para mostrar qué dominios son los más populares o qué servidores sirven la mayoría de las páginas.

## state {#concept_82295D22888947BF8B1C76182C635C6C}

Las variables y son variables de conversión.

<!-- 

state.xml

 -->

Son similares a las eVars en cuando a que capturan eventos pero, a diferencia de estas, no persisten. La variable *`zip`* y *`state`* son como las eVars, que caducan inmediatamente.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 50 bytes | state | Conversión &gt; Perfil del visitante &gt; Estado de visitante | "" |

Debido a que *`state`* y *`zip`* caducan de inmediato, los únicos eventos asociados a ellas son los que se activan en la misma página en la que se rellenan. Por ejemplo: si está utilizando *`state`* para comparar las tasas de conversión por estado, debe llenar la variable *`state`* en cada página del proceso de cierre de compra. Para los sitios de conversión, Adobe recomienda usar la dirección de facturación como fuente del código postal, pero puede elegir usar la dirección de envío en su lugar (suponiendo que solo haya una dirección de envío para el pedido). Un sitio multimedia puede elegir usar *`zip`* y *`state`* para el registro o seguimiento de pulsaciones.

**Sintaxis y valores posibles** {#section_EDD1F5F9EDBC457898E61695F08C1744}

```js
s.state="state"
```

La variable *`state`* no impone ningún valor especial o restricciones de formato. No existen limitaciones de *`state`* además de las limitaciones estándar de las variables.

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

* Rellene *`state`* en todas las páginas en las que se activó un evento relevante (todas las páginas del proceso de cierre de compra).
* Las variables *`zip`* y *`state`* actúan como eVars que caducan en la vista de las páginas.

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

La variable *`timestamp`* debe tener el formato que se describe en la sección siguiente.

>[!IMPORTANT]
>
>Para poder usar la variable *`timestamp`*, el servicio de Atención al cliente debe habilitarla para el grupo de informes. Una vez habilitada, deberá establecerse de forma manual una marca de tiempo para todas las visitas que se envíen al grupo de informes desde JavaScript (con *`s.timestamp`*). De no hacerlo así, las visitas no se registrarán.
>
>Asimismo, si habilita la compatibilidad con la marca de tiempo en un grupo de informes de modo que se admita el seguimiento sin conexión, también deberá establecerse de forma manual una marca de tiempo para todas las visitas que se envíen a este grupo de informes desde JavaScript (con *`s.timestamp`*). No es posible enviar visitas con y sin marca de tiempo a un mismo grupo de informes.
>
>También se puede usar el ajuste [Marcas de hora opcionales](../../../implement/js-implementation/timestamps-overview.md#concept_1A7DF6F7BDA34467B51A6F61E08BB73F) para combinar datos con y sin marca de tiempo en el mismo grupo de informes global, enviar datos con marca de tiempo desde una aplicación móvil a un grupo de informes global, y actualizar aplicaciones para emplear marcas de tiempo sin tener que crear un nuevo grupo de informes.

**Formatos de las marcas de tiempo** {#section_C12CBCECCD7047D38EF63A5800761CE9}

Las marcas de tiempo deben tener el formato UNIX (segundos transcurridos desde el 1 de enero de 1970) o ISO-8601, con las siguientes restricciones para el formato ISO-8601 aceptado:

* La fecha y la hora deben proporcionarse separadas por una "T".
* La fecha debe ser una fecha de calendario con precisión completa (año, mes y día). . Los días de la semana y las fechas con números ordinales no son compatibles.
* La fecha puede mostrarse en formato estándar o en formato extendido (`YYYY-MM-DD` o `YYYYMMDD`), pero debe incluir las horas y los minutos. Los segundos son opcionales (`HH:MM`, `HH:MM:SS`, `HHMM`o `HHMMSS`). Los minutos y los segundos fraccionados se pueden incluir, pero la parte fraccionada se ignorará.

* Se puede especificar un huso horario opcional en formato estándar o extendido (`±HH`, `±HH:MM`, `±HH`, `±HHMM` o Z)

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
* Los datos se marcan con la hora cuando los datos sin conexión están activados en el SDK móvil (configuración predeterminada) o cuando se configura un grupo de informes para aceptar datos con marca de hora. Los datos recopilados sin conexión pueden enviarse horas o semanas después de la fecha en que se produjo el evento originalmente. Puede que estas visitas se mantengan en cola en la plataforma Analytics durante más minutos u horas que las visitas sin marca de tiempo:

   * Para los datos con marca de hora enviados en tiempo muy cercano al actual, el retraso probable es de 10 a 15 minutos.
   * Para los datos con marca de hora enviados desde ayer, el retraso probable es de aproximadamente 2 horas.
   * Para los datos con marca de hora que se envían con una antigüedad mayor que ayer, cada día agrega unas 2 horas de retraso, hasta un máximo de 48 horas.

## trackingServer {#concept_45EE91B1A99B4A37AFAEF1C0A8A6B02F}

La variable se utiliza para la implementación de cookies de origen a fin de especificar el dominio en el cual se escriben la solicitud de imagen y la cookie.

<!-- 

trackingServer.xml

 -->

Se utiliza para páginas no seguras. If *`trackingServer`* is defined, nothing goes to 2o7.net. Si *`trackingServer`* no está definida (y dc no está definido), los datos se dirigen a 112.2o7.net.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | "" |

[Aquí](https://helpx.adobe.com/analytics/kb/determining-data-center.html) podrá consultar una lista de centros de datos de Adobe.

## trackingServerSecure {#concept_28132A2606E34A2F87BEC9E7ACADC7DD}

La variable se utiliza para la implementación de cookies de origen a fin de especificar el dominio en el cual se escriben la solicitud de imagen y la cookie.

<!-- 

trackingServerSecure.xml

 -->

Se utiliza para páginas seguras. If *`trackingServerSecure`* is not defined, SSL data goes to *`trackingServer`*.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | "" |

## transactionID {#concept_FBFA55E137E644A2BD97B41E92F6AFEF}

[!UICONTROL Las fuentes de datos de integración] utilizan una [!UICONTROL ID de transacción] para enlazar los datos sin conexión a una transacción en línea (como un cliente o una compra generados en línea).

<!-- 

transactionID.xml

 -->

Cada *`transactionID`* único enviado a Adobe se registrará a fin de prepararlo para una carga de [!UICONTROL fuentes de datos] de información sin conexión sobre esa transacción. Consulte [Fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | xact | n.d. | "" |

**Habilitar el almacenamiento del ID de transacción** {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Antes de registrar los valores de *`transactionID`*, el [!UICONTROL almacenamiento del ID de transacción] debe estar habilitado para el grupo de informes seleccionado en el Administrador del grupo de informes. Esta opción se encuentra en

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

El *`transactionID`* solo puede contener caracteres alfanuméricos. Si debe registrar varias variables [!UICONTROL transactionID] para una sola visita, delimite los valores correspondientes con una coma.

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

* Si el registro de *`transactionID`* no está habilitado, los valores de *`transactionID`* se descartarán y no estarán disponibles para su uso con las [!UICONTROL fuentes de datos de integración]. Asegúrese de establecer una variable de conversión o un evento (una eVar o la variable events) en la página donde se configure *`transactionID`*. De lo contrario, no se registrarán datos para *`transactionID`*.

* Si está registrando [!UICONTROL transactionIDs] para varios sistemas, como compras y posibles clientes, asegúrese de que el valor de *`transactionID`* siempre sea único. Esto puede conseguirse agregando un prefijo a la ID, por ejemplo, lead_1234 y purchase_1234. Las [!UICONTROL Fuentes de datos de integración] no funcionan de la manera esperada (los datos de [!UICONTROL fuentes de datos] se enlazarán a los datos incorrectos) si un mismo *`transactionID`* aparece dos veces.

* De forma predeterminada, los valores de *`transactionID`* se conservan durante 90 días. Si el proceso de interacción sin conexión supera los 90 días, póngase en contacto con el Servicio de atención al cliente para ampliar el límite.

> [!NOTE] La variable *`transactionID`* puede contener cualquier carácter que no sea una coma. Debe estar en la misma ubicación donde se especifica el límite de caracteres (100 bytes). Si se utilizan caracteres de bytes múltiples, debe habilitarse la compatibilidad con caracteres de bytes múltiples para evitar problemas con caracteres imprevistos en *`transactionID`*.

## visitorID {#concept_CD273CC915CC4ABD8F52E4209FF9557E}

Los visitantes se pueden identificar mediante la variable o por dirección IP o agente de usuario.

<!-- 

visitorID.xml

 -->

El *`visitorID`* puede tener hasta 100 caracteres alfanuméricos y no debe contener guiones.

Si configura explícitamente una ID personalizada, siempre se utilizará antes de los otros métodos de ID.

Este es el orden de uso: s.visitorID &gt; s_vi &gt; s_fid &gt; IP/UA.

| ** Tamaño máximo** | ** Parámetro depurador** | ** Informes rellenados** | ** Valor predeterminado** |
|---|---|---|---|
| 100 bytes | vid | n.d. | "" |

**Sintaxis y valores posibles** {#section_5F768C7AE6824557997E92B295C09280}

```js
s.visitorID="visitor_id"
```

> [!NOTE] La variable *`visitorID`* no debe contener guiones.

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

Si *`visitorNamespace`* se usa en el archivo JavaScript, no la elimine ni la modifique. Si *`visitorNamespace`* cambia, es probable que todos los visitantes notificados a Analytics se conviertan en nuevos visitantes. El historial de visitantes se desconecta del tráfico actual y futuro. No modifique esta variable sin la autorización de un representante de Adobe.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | ns | N.D. | "" |

Analytics utiliza una cookie para identificar de manera única a los visitantes del sitio. Si *`visitorNamespace`* no se utiliza, la cookie se asocia con 2o7.net. Si se utiliza *`visitorNamespace`*, la cookie se asocia con un subdominio de 2o7.net. Todos los visitantes del sitio deberán tener las cookies asociadas con el mismo dominio o subdominio.

El motivo para usar la variable *`visitorNamespace`* es evitar la posibilidad de sobrecargar el límite de cookies de un explorador. Internet Explorer impone un límite de 20 cookies por dominio. Usando la variable *`visitorNamespace`*, las cookies de Analytics de otras empresas no entrarán en conflicto con las cookies del visitante.

**Sintaxis y valores posibles** {#section_EE247FE371784CA4B6058182181F3EA1}

El valor de *`visitorNamespace`* debe proporcionarlo Adobe y es una cadena de caracteres ASCII que no contienen comas, puntos, espacios o caracteres especiales.

```js
s.visitorNamespace="company_specific_value"
```

**Identificación de visitante en grupos de informes** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

Si no especifica un `visitorNamespace`, cada grupo de informes en su empresa recibe su propia cookie de ID de visitante como `s_vi_[random string]`. Si especifica `visitorNamespace`, se utilizará la misma cookie `s_vi` para todos los grupos de informes que envían datos al `trackingServer` especificado. Si ha implementado etiquetado de grupos múltiples, asegúrese de especificar el espacio de nombres del visitante de modo que cada grupo de informes utilice la misma cookie.

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

Las variables  y  son variables de conversión.

<!-- 

zip.xml

 -->

Son similares a las eVars en cuando a que capturan eventos pero, a diferencia de estas, no persisten. La variable *`zip`* y *`state`* son como las eVars, que caducan inmediatamente.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 50 bytes | zip | Conversión &gt; Perfil del visitante &gt; Códigos postales | "" |

Since the *`state`* and *`zip`* variables expire immediately, the only events associated with them are events fired on the same page that are populated. Por ejemplo: si está utilizando *`zip`* para comparar las tasas de conversión por código postal, debe rellenar la variable *`zip`* en cada página del proceso de cierre de compra. Adobe recomienda usar la dirección de facturación como fuente del código postal. Puede elegir usar la dirección de envío, siempre que solo haya una en el pedido. Un sitio multimedia puede elegir usar *`zip`* y *`state`* para el registro o seguimiento de pulsaciones.

**Sintaxis y valores posibles** {#section_5EDCFCAC8FC241D1B4CC777996858CD7}

```js
s.zip="zip_code"
```

La variable *`zip`* no impone ningún valor especial ni restricciones de formato. No existen limitaciones de *`zip`* además de las limitaciones estándar de las variables.

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
* Las variables *`zip`* y *`state`* actúan como eVars que caducan en la vista de las páginas.

