---
description: Variables de configuración establecidas en appmeasurement. js.
keywords: Implementación de Analytics
seo-description: Variables de configuración definidas en appmeasurement. js para Adobe Analytics
seo-title: Variables de configuración
solution: Analytics
subtopic: Variables
title: Variables de configuración
topic: Desarrollador e implementación
uuid: a 19484 b 6-e 350-4 c 12-b 4 d 6-a 31 c 79 a 42 db 0
translation-type: tm+mt
source-git-commit: 696e7ed6dc6648cf523bc81e6cd40c7a06115484

---


# Variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. Las variables de configuración más comunes que suelen configurarse en el principal appmeasurement. js de JavaScript global. Estas variables se pueden configurar en el código y los vínculos de nivel de página de Analytics cuando corresponda.

Not all of these variables appear in the code by default when you generate code through the **[!UICONTROL Admin Tool]** &gt; **[!UICONTROL Code Manager]**. Puede que algunas de estas variables de configuración no sean aplicables a las necesidades de implementación del sitio.

Algunos de los objetivos de usar estas variables de configuración son:

* Seguir varios sitios o dominios.
* Usar cualquier moneda en compras.
* Capturar datos en idiomas indiferentes.
* Seguimiento de vínculos (cantidad de archivos descargados, vínculos a sitios externos).
* Seguir vínculos personalizados con un fin determinado.

>[!NOTE]
>
>[!DNL AppMeasurement] requiere que todas las variables de configuración se establezcan antes de la llamada inicial a la función de seguimiento `t()`. If configuration variables are set after the call to `t()`, unexpected results may occur. To ensure proper data collection, all configuration variables must be above the `doPlugins` function.

## s.account {#concept_685A5C832A6C40619ACB5920925785DC}

<!--
s_account.xml
-->

La variables determina el grupo de informes donde se almacenan los datos y se crean los informes sobre ellos.

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. La ID del grupo de informes viene determinada por Adobe.

**Parámetros**

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| 40 bytes | En la ruta de URL | N.D. | N.D. |

Cada ID de grupo de informes debe coincidir con el valor creado en [!DNL Admin Console]. Cada ID de grupo de informes debe tener 40 bytes o menos, pero la suma de todos los grupos (es decir, la lista separada por comas completa) no tiene límite. 

El grupo de informes es el nivel más fundamental de segmentación en los informes. Puede configurar todos los grupos de informes que permita el contrato. Cada grupo de informes hace referencia a un conjunto de tablas dedicadas que se rellenan en los servidores de recopilación de Adobe. Un grupo de informes se identifica mediante la variable `s_account` en el código JavaScript.

En [!DNL Analytics], el cuadro desplegable del sitio en la esquina superior izquierda de los informes muestra el grupo de informes actual. Cada grupo de informes tiene un identificador único denominado ID de grupo de informes. La variable `s_account` contiene una o más ID del grupo de informes al que se envían los datos. Adobe debe proporcionar o aprobar el valor de la ID del grupo de informes, que es invisible para los usuarios de [!DNL Analytics], antes de que pueda utilizarla. Cada ID de grupo de informes tiene asociado un "nombre descriptivo" que se puede cambiar en la sección de grupos de informes de [!DNL Admin Console].

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). You can declare the `s_account` variable on the HTML page, which is a common practice when the value of `s_account` may change from page to page. Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of `s_account` also appears in the domain, before 112.2o7.net. El valor en la ruta es el único valor que determina el grupo de informes de destino. El texto en negritas que sigue muestra el grupo de informes al que se envían los datos, según aparecerá en el depurador. Consulte [DigitalPulse Debugger](../../../implement/impl-testing/debugger.md#concept_B26FFE005EDD4E0FACB3117AE3E95AA2).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

**Sintaxis y valores posibles** {#section_3BE913DF26D848AEB4CB5B0A6CE7F0CA}

La ID del grupo de informes es una cadena alfanumérica de caracteres ASCII, de no más de 40 bytes de longitud. El único carácter no alfanumérico permitido es un guión. No se permite ningún espacio, punto, coma u otro signo de puntuación. La variable `s_account` puede contener varios grupos de informes, y todos ellos recibirán datos de esa página.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

All values of `s_account` must be provided or approved by Adobe.

**Ejemplos** {#section_16580A9101B64560A58C7745397FB42F}

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

**Configuración de la variable en Analytics** {#section_7DFB2CCF02F045AFB1AD4F376638393B}

Adobe [!DNL Customer Care] puede cambiar el nombre descriptivo asociado a cada ID de grupo de informes. Este nombre descriptivo se puede ver en [!DNL Analytics], en el cuadro desplegable del sitio situado en la parte superior izquierda de la pantalla.

**Problemas, preguntas y consejos** {#section_BFFDA5C0AF31442494B0E02F0925CF93}

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Utilice [!DNL DigitalPulse Debugger] para determinar los grupos de informes de destino.

* En algunos casos, se puede utilizar [!DNL VISTA] para modificar el grupo de informes de destino. Se recomienda utilizar [!DNL VISTA] para volver a enrutar o copiar los datos en otro grupo de informes cuando se utilizan cookies de origen o si el sitio tiene más de 20 grupos de informes activos.

* Always declare `s_account` inside the JS file or just before it is included.

## s.dynamicAccountSelection {#concept_FAD499DB357148DB8BD74F08093D3E35}

La variable permite seleccionar dinámicamente el grupo de informes en función de la dirección URL de cada página.

>[!NOTE]
>
>`dynamicAccountSelection` no funciona con el seguimiento de vínculos personalizados.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | False |

>[!NOTE]
>
>Both `dynamicAccountList` and `dynamicAccountMatch` are ignored if the `dynamicAccountSelection` variable is not declared or set to 'false.'

**Sintaxis y valores posibles** {#section_36E5D0E2170345F5A652B44CE85DFED1}

```js
s.dynamicAccountSelection=[true|false]
```

Solo se permiten 'true' y 'false' como valores de *`dynamicAccountSelection`*.

**Ejemplos** {#section_E8CE8BA62C7545889531495E2521663D}

```js
s.dynamicAccountSelection=true
```

```js
s.dynamicAccountSelection=false
```

**Parámetros de configuración** {#section_F052FA38144B4F84B015A263A8E711CF}

Ninguna

**Problemas, preguntas y consejos** {#section_62F0B0895BC84A05840AEEED0643DE60}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Utilice siempre [!DNL DigitalPulse Debugger] para determinar qué grupo de informes recibe los datos de cada página.

## s.dynamicAccountList {#concept_19715BA0AD4D41748E0C4A4A6B71AB51}

<!-- 
dynamicAccountList.xml
-->

[!DNL AppMeasurement] para JavaScript puede seleccionar dinámicamente el grupo de informes al que envía los datos. La variable contiene las reglas que se utilizarán para determinar el grupo de informes de destino.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | "" |

Esta variable se usa junto con las variables *`dynamicAccountSelection`* y *`dynamicAccountMatch`* variables. The rules in *`dynamicAccountList`* are applied if *`dynamicAccountSelection`* is set to 'true,' and they apply to the section of the URL specified in *`dynamicAccountMatch`*.

If none of the rules in *`dynamicAccountList`* matches the URL of the page, the report suite identified in `s_account` is used. Las reglas enumeradas en esta variable se aplican con un orden de izquierda a derecha. Si la dirección URL de la página coincide con más de una regla, se usa la regla situada más a la izquierda para determinar el grupo de informes. Como resultado, las reglas más genéricas deben situarse a la derecha de la lista.

In the following examples, the page URL is `www.mycompany.com/path1/?prod_id=12345` and `dynamicAccountSelection` is set to *true* and `s_account` is set to `mysuitecom.`

| Valor de DynamicAccountList | Valor de DynamicAccountMatch | Grupo de informes que recibirá los datos |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1, mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom, mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

**Sintaxis y valores posibles** {#section_7360E4354ED345E8BAAE210DBD58A7EC}

`dynamicAccountList` La variable es una lista separada por punto y coma de pares = valor pares (reglas). Cada parte de la lista debe contener los siguientes elementos:

* una o varias ID de grupo de informes (separadas por coma)
* un signo igual
* uno o varios filtros de URL (separados por coma)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

En la cadena solo deben usarse caracteres ASCII estándar (sin espacios).

**Ejemplos** {#section_49936D14EF6D45859B666C9E7A4CBA9E}

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

**Parámetros de configuración** {#section_9F99CD741BC7449B8CCC108094B2EB85}

Ninguna

**Problemas, preguntas y consejos** {#section_3E10534FCC05457AB67147BB480C8BB3}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* Si la dirección URL de la página coincide con varias reglas, se usa la regla situada más a la izquierda.
* Si no coincide ninguna regla, se usa el grupo de informes predeterminado.
* Si su página se guarda en el disco duro de otra persona o se traduce mediante un motor de traducción web (como las páginas traducidas de Google), la selección de cuentas dinámicas probablemente no funcionará. Para un seguimiento más preciso, rellene el lado del servidor de la variable `s_account`.
* `dynamicAccountSelection` Las reglas solo se aplican a la sección de la dirección URL especificada en `dynamicAccountMatch`.

* When using dynamic account selection, be sure to update *`dynamicAccountList`* every time you obtain a new domain.
* Use [!DNL DigitalPulse Debugger] cuando trate de identificar el grupo de informes de destino. The `dynamicAccountSelection` variable always overrides the value of `s_account`.

## s.dynamicAccountMatch {#concept_718171E602214CCC9905C749708BBE52}

<!-- 
dynamicAccountMatch.xml
-->

La variable utiliza el objeto DOM para recuperar la sección de la dirección URL donde se aplican todas las reglas de 

This variable is only valid when *`dynamicAccountSelection`* is set to 'True.' Como el valor predeterminado es [!DNL window.location.host], esta variable no es necesaria para que [!UICONTROL selección de cuentas dinámicas] funcione. For additional information, see [dynamicAccountList](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_19715BA0AD4D41748E0C4A4A6B71AB51).

The rules found in `dynamicAccountList` are applied to the value of `dynamicAccountMatch`. If `dynamicAccountMatch` only contains [!DNL window.location.host] (default), the rules in `dynamicAccountList` apply only to the domain of the page.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | window.location.host |

**Sintaxis y valores posibles** {#section_95CD81972C22419B80A921CA137D3841}

The `dynamicAccountMatch` variable is usually populated by the Adobe consultant who provides the AppMeasurement for JavaScript file. Sin embargo, los valores indicados a continuación se pueden aplicar en cualquier momento.

```js
s.dynamicAccountMatch=[DOM object]
```

| Descripción | Valor |
|---|---|
| Dominio (predeterminado) | window.location.host |
| Ruta | window.location.pathname |
| Cadena de consulta | (window.location.search?window.location.search:"?") |
| Dominio y ruta | window.location.host+window.location.pathname |
| Ruta y cadena de consulta | window.location.pathname+(window.location.search?window.location.search:"?") |
| Dirección URL completa | window.location.href |

**Ejemplos** {#section_924687CCE255421AA2223A3D4B8B6A30}

```js
s.dynamicAccountMatch=window.location.pathname
```

```js
s.dynamicAccountMatch=window.location.host+window.location.pathname
```

**Parámetros de configuración** {#**section_43BCE13B1ADD4D418DF7CBB9DD7A6472}

Ninguna

**Problemas, preguntas y consejos** {#section_EF9B2977BC21497D8C5EEB9BAD731E17}

* Dynamic account selection is not supported by [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8).
* When pages are saved to a hard drive, [!DNL window.location.host] is empty, causing those page views to be sent to the default report suite (in `s_account`).

* Cuando se traduce una página con un motor de traducción web, como Google, la [!UICONTROL selección de cuentas dinámicas] no funciona como está previsto. Para un seguimiento más preciso, rellene el lado del servidor de la variable [!UICONTROL s_account ].

## s.dynamicVariablePrefix {#concept_38C1F2452DDB47FCA8F458BE1398E276}

<!-- 
dynamicVariablePrefix.xml
-->

La variable permite a la implementación marcar variables que deben rellenarse de forma dinámica.

Las cookies, los encabezados de solicitud y parámetros de cadena de consulta de imagen se pueden rellenar dinámicamente.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | D= | Cualquiera | D= |

**Sintaxis y valores posibles** {#section_D0669899567F46B6A081C7661362BA81}

```js
s.prop1="D=User-Agent”
```

O USE MARCAS PERSONALIZADAS PARA VARIABLES DINÁMICAS

```js
s.dynamicVariablePrefix=".."
```

**Ejemplos** {#section_DD148560F9E8416EBCF159194FA427AC}

```js
s.prop1="D=User-Agent”
```

O USE MARCAS PERSONALIZADAS PARA VARIABLES DINÁMICAS

```js
s.dynamicVariablePrefix=".."
```

```js
s.prop1="..User-Agent"
```

**Problemas, preguntas y consejos** {#section_6889908FBD78488D955F67DDB17617B1}

* Se pueden usar variables dinámicas para reducir significativamente la longitud total de la dirección URL copiando valores en otras variables.
* Se pueden usar variables dinámicas para recopilar datos de encabezados y cookies que no están disponibles de otra forma para la recopilación de datos.

## s.charSet {#concept_E65B9A8F75C3482C87D0D455805F89BD}

<!-- 
charset.xml
-->

Analytics utiliza la propiedad charset, que normalmente se define en el archivo JavaScript, para convertir los datos entrantes a UTF -8 para almacenamiento e informes por Analytics.

>[!Note:] La propiedad charset es necesaria al enviar datos a un grupo de informes multibyte y nunca debe utilizarse con un grupo de informes estándar. Si se configura la propiedad charSet con un grupo de informes ISO estándar, es posible que aparezcan variables truncadas o que se produzca una conversión de caracteres inesperada.

El valor de la propiedad charSet debe coincidir con la codificación de la página web de la etiqueta meta o el encabezamiento http, aunque la sintaxis no sea exactamente la misma. Aunque la etiqueta meta puede utilizar un alias para la codificación, el valor de charSet debe utilizar el nombre preferido (u oficial) de la codificación.

La tabla siguiente contiene algunas de las codificaciones más comunes con su nombre preferido y alias.

| Nombre preferido | Alias |
|--- |--- |
| ISO-8859-1 | ISO_8859-1, CP819, latin1 |
| ISO-8859-2 | ISO_8859-2, latin2 |
| ISO-8859-5 | ISO_8859-5, cyrillic |
| Big5 | Big-5 |
| Shift_JIS | SJIS |

Dado que existen numerosos alias y codificaciones, comuníquese con el consultor de implementación o con el Servicio de atención al cliente de Adobe para confirmar el valor correcto de charset si no aparece en la tabla anterior.

If a site has different web encodings on different pages, or a single JavaScript file is used for multiple sites, the charSet property can be set to a default value in the JavaScript file and then reset on specific pages as needed to override the default; for example, `s.charSet="UTF-8"` or `s.charSet="SJIS"`.

Cualquier valor no vacío del parámetro charSet hará que los datos se conviertan a UTF-8 para su almacenamiento. Todos los caracteres del rango 128–255 se convertirán a la secuencia de dos bytes de UTF-8 correspondiente y se almacenarán. Estos caracteres no se mostrarán correctamente en un grupo de informes estándar. Por lo tanto, la propiedad charSet no se debe utilizar nunca con un grupo de informes estándar.

Del mismo modo, si el parámetro charSet tiene un valor vacío, evitará el proceso de conversión de datos y todos los caracteres del rango 128–255 se almacenarán como bytes simples. Estos caracteres no se mostrarán correctamente en los grupos de informes multibyte, dado que los códigos de byte simple de estos caracteres no son válidos en UTF-8. Por lo tanto, el parámetro charSet siempre se debe utilizar con un grupo de informes multibyte. Además, se debe usar el valor correcto en relación con la codificación de la página web.

If the *`charSet`* variable contains an incorrect value, the data in all other variables are translated incorrectly. If JavaScript variables on your pages (e.g. *`pageName`*, [!UICONTROL prop1], or *`channel`*) contain only ASCII characters, *`charSet`* does not need to be defined. However, if the variables on your pages contain non-ASCII characters, the *`charSet`* variable must be populated.

**Parámetros**

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N.D. | CE | N.D. | "" |

**Sintaxis y valores posibles** {#section_EBC2176067A04D9E814CF78A86DC80FA}

```js
s.charSet="character_set"
```

**Ejemplos** {#section_406DE0A2B58441DB8512F5B3BE5D9CB5}

```js
s.charSet="ISO-8859-1"
```

```js
s.charSet="SJIS"
```

## s.currencyCode {#concept_CE216F1610E2499D8178DB9A8EB97C63}

<!-- 
currencycode.xml
-->

La variable determina la tasa de conversión que se aplicará a los ingresos.

Todos los importes monetarios se almacenan en la moneda que elija. Si esa moneda es la misma que la especificada en *`currencyCode`* o *`currencyCode`* está vacía, no se aplica ninguna conversión.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N.D. | cc | Conversión &gt; Compras &gt; Ingresos Todos los informes de conversión con los ingresos o los valores monetarios | "USD" |

Si su sitio permite que los visitantes compren en diferentes monedas, debe usar la variable *`currencyCode`* para asegurarse de que los ingresos se almacenan en la moneda apropiada. For example, if the base currency for your report suite is USD, and you sell an item for 40 Euros, you should populate the *`currencyCode`* with "EUR" on the HTML page. En cuanto la recopilación de datos recibe los datos, usa la tasa de conversión actual para convertir los 40 euros en su equivalente en USD.

Se recomienda rellenar la variable *`currencyCode`* en la página HTML en lugar del archivo JavaScript si vende en varias monedas. If you want to use your own conversion rates rather than the conversion rates used by Adobe, set the *`currencyCode`* to equal the base currency of your report suite. Después, convierta todos los ingresos antes de enviarlos a [!DNL Analytics].

La conversión monetaria se aplica tanto a los eventos de ingresos como monetarios. Estos son eventos que se usan para sumar valores similares a los ingresos, como los impuestos y el envío. Los eventos de ingresos y monetarios se especifican en la cadena de productos. Para obtener más información sobre los productos, consulte [events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). Para obtener más información sobre cómo se administran las monedas, consulte [Compatibilidad con múltiples monedas](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/).

**Sintaxis y valores posibles** {#section_7CD68F08AB4848EE9B0D19DCC3F1BECE}

```js
s.currencyCode="currency_code"
```

Solo se admiten los códigos de moneda enumerados en [Compatibilidad con múltiples monedas](https://marketing.adobe.com/resources/help/en_US/whitepapers/currency/).

**Ejemplos** {#section_D55ED45369544C8AAA02B3193752636C}

```js
s.currencyCode="GBP"
```

```js
s.currencyCode="EUR"
```

**Parámetros de configuración** {#section_D05E29F545A04958B1C0A82248BCA1B0}

Adobe [!DNL Customer Care] puede cambiar la configuración predeterminada de su grupo de informes. Cuando se cambia la moneda base de un grupo de informes, los ingresos existentes en el sistema no se convierten. Los valores de ingresos nuevos se convertirán convenientemente.

**Problemas, preguntas y consejos** {#section_08A80A87B54A4861905953A6FA61FF8F}

* If you notice surprisingly large amounts of revenue in reports, ensure that the *`currencyCode`* variable and base currency of the report suite are set correctly.
* The *`currencyCode`* variable is not persistent, meaning that the variable must be passed in the same image request as any revenue or other currency-related metrics.
* No deben usarse eventos monetarios con otros fines que no sean monetarios. Si necesita contar valores arbitrarios o dinámicos que no son monetarios, use el tipo de evento [!UICONTROL numérico].
* Si la variable *`currencyCode`* está vacía, no se aplica ninguna conversión.

## s.cookieDomain {#concept_6164C39CF8BE4737A7EF1DE5A8376C1B}

<!-- 
cookiedomain.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set.

Commonly, `s.cookieDomainPeriods` is used to generate `s.cookieDomain` from `window.location.hostnam`e. Instead of using `s.cookieDomainPeriods`, you can explicitly set `s.cookieDomain` to what you want to use in your implementation. Por ejemplo, podría establecer cookies en el nombre de página completo mediante:

`s.cookieDomain = window.location.hostname;`

## s.cookieDomainPeriods {#concept_F17A59C7D8F54F5897AD40980B6725EB}

<!-- 
cookiedomainperiods.xml
-->

The  variable determines the domain on which the [!DNL Analytics] cookies `s_cc` and `s_sq` are set by determining the number of periods in the domain of the page URL. Algunos complementos también usan esta variable para determinar el dominio correcto donde se configurará la cookie del complemento.

The default value for *`cookieDomainPeriods`* is "2". This is the value that is used if *`cookieDomainPeriods`* is omitted. For example, using the domain `www.mysite.com`, *`cookieDomainPeriods`* should be "2". For `www.mysite.co.jp`, *`cookieDomainPeriods`* should be "3".

If *`cookieDomainPeriods`* is set to "2" but the domain contains three periods, the JavaScript file attempts to set cookies on the domain suffix.

For example, if setting *`cookieDomainPeriods`* to "2" on the domain `www.mysite.co.jp`, the `s_cc` and `s_sq` cookies are created on the domain `co.jp`. Como `co.jp` no es un dominio válido, casi todos los exploradores rechazan estas cookies. Como consecuencia, se pierden los datos del mapa de clics de visitantes y el informe [!UICONTROL Perfil del visitante] &gt; [!UICONTROL Tecnología] &gt; [!UICONTROL Cookies] indica que casi el 100 % de los visitantes rechazan las cookies.

Si *`cookieDomainPeriods`* se establece en "3" pero el dominio solo contiene dos puntos, el archivo JavaScript establece las cookies en el subdominio del sitio. For example, if setting *`cookieDomainPeriods`* to "3" on the domain `www2.mysite.com`, the `s_cc` and `s_sq` cookies are created on the domain `www2.mysite.com`. When a visitor goes to another subdomain of your site (such as `www4.mysite.com`), all cookies set with `www2.mysite.com` cannot be read.

>[!NOTE]
>
>Do not include additional subdomains as part of *`cookieDomainPeriods`*. For example, `store.toys.mysite.com` would still have *`cookieDomainPeriods`* set to "2". Esta definición de variable configura correctamente las cookies en el dominio raíz, [!DNL mysite.com]. Setting *`cookieDomainPeriods`* to "3" in this example would set cookies on the domain [!DNL toys.mysite.com], which has the same implications as the prior example.

See also [s.fpCookieDomainPeriods](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_0A25BD152B0744989E7C662A95448274).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | CDP | Afecta a varios informes ya que controla el modo de almacenamiento y gestión de la ID de visitante.  | "2" |

>[!NOTE]
>
>Algunos servicios informáticos de nube se consideran dominios de nivel superior, que no permiten que se escriban cookies. (For example, `compute.amazonaws.com`, `*.herokuapp.com`, `*.googlecode.com`, and so on.) Si implementa en esos servicios, podría verse afectado por la configuración de privacidad de Analytics que elimina a los usuarios que han bloqueado todas las cookies si no cuenta con su propio dominio configurado (por ejemplo, si está probando la implementación). En este caso, cualquier visita para la que el sistema haya determinado que las cookies están deshabilitadas, no son funcionales o no son accesibles queda fuera y se excluye de los informes.

**Ejemplos** {#section_4218BE29FA5E49F58975A2094329B268}

Configuración manual de la variable:

```js
s.cookieDomainPeriods = "3";
```

Algunos ejemplos para configurar dinámicamente la variable si su archivo JavaScript principal aloja ambos tipos:

```js
document.URL.indexOf(".co.") > 0 ? s.cookieDomainPeriods = "3" : s.cookieDomainPeriods = "2";
```

```js
s.cookieDomainPeriods = "2"; 
var d=window.location.hostname; 
if(d.indexOf(".co.uk") > 0 || d.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

```js
s.cookieDomainPeriods = "2"; 
if(window.location.indexOf(".co.jp") > 0 || window.location.indexOf(".com.au") > 0) 
    {s.cookieDomainPeriods = "3";}
```

**Problemas, preguntas y consejos** {#section_F3BE3F039E5C4359B694DBB61369822C}

* If you notice that visitor click map data is absent, or that the [!UICONTROL Traffic] &gt; [!UICONTROL Technology] &gt; [!UICONTROL Cookies] report shows a large percentage of visitors who reject cookies, check that the value of *`cookieDomainPeriods`* is correct.

* If *`cookieDomainPeriods`* is higher than the number of sections in the domain, cookies will be set with the full domain. Esto puede provocar la pérdida de datos cuando los visitantes cambien de un subdominio a otro.
* La variable *`cookieDomainPeriods`* se utilizaba en implementaciones obsoletas antes de *`trackingServer`* establecer la cookie de ID de visitante. Though only present in outdated code, failure to correctly define *`cookieDomainPeriods`* in this circumstance puts your implementation at risk of data loss.

## s.fpCookieDomainPeriods {#concept_0A25BD152B0744989E7C662A95448274}

<!-- 
fpCookieDomainPeriods.xml
-->

La variable está destinada a cookies configuradas por JavaScript (s_sq, s_cc, complementos), que son cookies inherentemente de origen, aunque su implementación utilice los dominios de terceros 2o7.net u omtrdc.net.

The *`fpCookieDomainPeriods`* variable should never be dynamically set . If you use *`cookieDomainPeriods`*, it is good practice to specify a value for *`fpCookieDomainPeriods`* as well. *`fpCookieDomainPeriods`* hereda el *`cookieDomainPeriods`* valor. Note that *`fpCookieDomainPeriods`* does not affect the domain on which the visitor ID cookie is set, even if your implementation treats this as a first-party cookie.

The name " *`fpCookieDomainPeriods`*" refers to the number of periods (".") que contiene el dominio cuando comienza por "www". For example, `www.mysite.com` contains two periods, while `www.mysite.co.jp` contains three periods. Another way to describe the variable is the number of sections in the main domain of the site (two for `mysite.com` and three for `mysite.co.jp`).

The [!DNL AppMeasurement] for JavaScript file uses the *`fpCookieDomainPeriods`* variable to determine the domain with which to set first-party cookies other than the [!UICONTROL visitor ID] (s_vi) cookie. Hay por lo menos dos cookies que se ven afectadas por esta variable, incluyendo s_sq y s_cc (utilizadas respectivamente para mapa de clics de visitantes y para la verificación de cookies, respectivamente). Las cookies usadas por complementos como [!UICONTROL getValOnce] también se ven afectadas.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | cookieDomainPeriods |

**Código de ejemplo para configurar variables de dominio de cookies** {#section_5200A92D40384C82998606E800B69E13}

```js
s.fpCookieDomainPeriods="2" 
var d=window.location.hostname 
if(d.indexOf('.co.uk')>-1||d.indexOf('.com.au')>-1) 
  s.fpCookieDomainPeriods="3" 
```

**Sintaxis y valores posibles** {#section_87923F4C12E74AF99CC9AFC0FFD77D49}

The *`cookieDomainPeriods`* variable is expected to be a string, as shown below.

```js
s.fpCookieDomainPeriods="3"
```

**Ejemplos** {#section_EF7355718AD849BF963EE9F6F9F79891}

```js
s.fpCookieDomainPeriods="3"
```

```js
s.fpCookieDomainPeriods="2"
```

**Parámetros de configuración** {#section_DB65D9BC4F3048C8AD08F9A7CD8FCFC0}

Ninguna

## s.cookieLifetime {#concept_8347C6648B0E4D4996E2F223C34B9A3D}

<!-- 
cookielifetime.xml
-->

La variable la usan tanto JavaScript como los servidores de recopilación de datos para determinar la vida de una cookie.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | cl | Tráfico &gt; Tecnología &gt; Cookies &gt; Todos los informes relacionados con el visitante | "" |

Si *`cookieLifetime`* se configura, anula todas las demás caducidades de las cookies tanto para JavaScript como para los servidores de recopilación de datos, con una excepción que se describe a continuación. The *`cookieLifetime`* variable can have one of three values:

* [!DNL Analytics] Cookies
* Cookies
* Opciones de configuración y complementos de JavaScript

**Sintaxis y valores posibles** {#section_09D4D122451B45FAB2C9398600EC66F1}

```js
s.cookieLifetime="value"
```

A continuación se enumeran los posibles valores:

* ""
* "NONE"
* "SESSION"
* Un entero que represente la cantidad de segundos hasta la caducidad

**Ejemplos** {#section_91499F70C8B14D3292FCF1B60F04E30A}

```js
s.cookieLifetime="SESSION"
```

```js
s.cookieLifetime="86400" // one day in seconds
```

**Parámetros de configuración** {#section_7BDAD4CFE8414C9BA5717A8C8B1BDD34}

Ninguna

**Problemas, preguntas y consejos** {#section_23E24877F6554E0D9F8C8B7A9C2994B2}

*`cookieLifetime`* afecta [!DNL Analytics] al seguimiento. If, for example, *`cookieLifetime`* is two days, then monthly, quarterly, and yearly unique visitor reports will be incorrect. Tenga cuidado al configurar *`cookieLifetime`*.

## s.doPlugins {#concept_676EAE4FAFCF4B018876390FC874EFDA}

<!-- 
doPlugins.xml
-->

La variable es una referencia a la función y permite llamar a la función en el lugar apropiado dentro del archivo JavaScript.

The *`s_doPlugins`* function is called each time any of the following occurs:

* The *`t()`* function is called
* The *`tl()`* function is called
* Se hace clic en un vínculo de salida o de descarga
* Se hace clic en un elemento de página seguido por el mapa de clics de visitantes

La función *`doPlugins`* se usa para ejecutar rutinas personalizadas para recopilar o modificar datos. If you are using an object name other than "s," make sure that the *`s_doPlugins`* is renamed appropriately. For example, if your object name is s_mc, the *`s_doPlugins`* function should be called s_mc_doPlugins.

**Sintaxis y valores posibles** {#section_5CFB94598521455E80947964A306EA89}

The *`s_doPlugins`* function should not be in quotes, and *`doPlugins`* should always be assigned to the exact name of the *`s_doPlugins`* function (if that function is renamed).

```js
s.doPlugins=s_doPlugins;
```

**Ejemplos** {#section_A5CF0054C56745268A1313CCC7730022}

```js
s.doPlugins=s_doPlugins;
```

```js
s_mc.doPlugins=s_mc_doPlugins;
```

**Parámetros de configuración** {#section_641F0EC55E3349E5A3F8671446797074}

Ninguna

**Problemas, preguntas y consejos** {#section_0C7FB61CF0C946EF8A7D1B686D36E6ED}

* El único motivo para cambiar el nombre de objeto (por ejemplo, de s a s_mc) es si comparte contenido con otros clientes o extrae información de ellos. Cambiar el nombre de la función *`s_doPlugins`* a [!UICONTROL s_ mc_ doplugins] garantiza que el archivo JavaScript de otro cliente no sobrescriba su *`doPlugins`* función.

* If you unexpectedly start pulling in content from another Adobe customer, and your *`s_doPlugins`* function is being overwritten, it is possible to simply rename the *`s_doPlugins`* function without changing the object name. Aunque la mejor solución es usar un nombre de objeto diferente de otros archivos JavaScript en la misma página, no es obligatorio.

## s. registerpretrackcallback y s. registerposttrackcallback

Estas funciones toman como parámetros la rellamada (una función) y los parámetros que llevan a esa función. Por ejemplo:

```
s.registerPreTrackCallback(function(requestUrl,a,b,c) { 
    console.log("pre track callback"); 
    console.dir(requestUrl); // Request URL 
    console.dir(a); // param1 
    console.dir(b); // param2 
    console.dir(c); // param3 
}, "param1", "param2", "param3");
```

La rellamada se invoca con `requestUrl` y cualquier parámetro que haya pasado cuando se registró la rellamada. Esto ocurre antes o después de la llamada de seguimiento, según el método que se utilice para registrar la rellamada.

No se puede garantizar el orden en el que se realizan estas rellamadas. Las rellamadas que se registran en la función previa se invocan después de crearse la URL de seguimiento final. Las rellamadas posteriores se realizan cuando se ha llevado a cabo una llamada de seguimiento con éxito (si la llamada de seguimiento falla, no se llaman a estas funciones). Las rellamadas que se registren con `registerPreTrackCallback` no afectan a la llamada de seguimiento. Además, no se recomienda llamar a ninguno de los métodos de seguimiento en una rellamada registrada, ya que podría causar un bucle infinito.

## s.trackDownLoadLinks {#concept_0A7AEAB3172A4BEA8B2E8B1A3A8F596C}

<!-- 
trackDownloadLinks.xml
-->

Configure como 'true' si desea realizar el seguimiento de los vínculos a archivos descargables del sitio.

If *`trackDownloadLinks`* is 'true,' *`linkDownloadFileTypes`* is used to determine which links are downloadable files.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | True |

La variable *`trackDownloadLinks`* solo debe configurarse como 'false' si no hay vínculos a archivos descargables en el sitio o si no le importa realizar el seguimiento del número de clics en archivos descargables. If *`trackDownloadLinks`* is 'true,' when a file download link is clicked, data is immediately sent to [!DNL Analytics]. Los datos que se envían con un vínculo de descarga incluyen la dirección URL de descarga del vínculo y los datos del mapa de clics de visitantes para dicho vínculo. Si *`trackDownloadLinks`* es'false ', es probable que los datos del mapa de clics de visitantes para los vínculos a archivos descargables del sitio estén debajo de los informes.

**Sintaxis y valores posibles** {#section_828492CC2A144BC68D18C30CF397EEFC}

Se espera que la variable *`trackDownloadLinks`sea 'true' o 'false'.*

**Ejemplos** {#section_BE2FA1873EBD4C5CA95E98B922B10280}

```js
s.trackDownloadLinks=true 
```

```js
s.trackDownloadLinks=false
```

**Parámetros de configuración** {#section_9A5F69966BAF433A8DA2BCF655A652D1}

Ninguna

**Problemas, preguntas y consejos** {#section_B3764520D81143968F96CB69AADD457F}

* When *`trackDownloadLinks`* is 'false,' links that people use to download files on your site are likely to be under reported in visitor click map.
* When *`trackDownloadLinks`* is 'true,' data is sent each time a visitor clicks a file download link.

## s.trackExternalLinks {#concept_E1321318696841648A54CF77F6C4A7AF}

<!-- 
trackExternalLinks.xml
-->

Si es'true'y se utiliza para determinar si un vínculo pulsado es un vínculo de salida.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | True |

La variable *`trackExternalLinks`* solo debe configurarse como 'false' si no hay vínculos de salida en el sitio o si no le importa realizar el seguimiento del número de clics en esos vínculos de salida. Un vínculo de salida es cualquier vínculo que conduce al visitante fuera del sitio. Si *`trackExternalLinks`* es'true ', cuando hace clic en un vínculo de salida, los datos de seguimiento se envían inmediatamente. Los datos que se envían con un vínculo de salida incluyen la dirección URL, el nombre y los datos del mapa de clics de visitantes para dicho vínculo. Si *`trackExternalLinks`* es'false ', es probable que los datos del mapa de clics de visitantes para los vínculos de salida del sitio estén debajo de los informes.

**Sintaxis y valores posibles** {#section_267748949A7544658E1D838AAEF964B2}

Se espera que la variable *`trackExternalLinks`sea 'true' o 'false'.*

```js
s.trackExternalLinks=true|false
```

**Ejemplos** {#section_EF18DB05884240F5B5062631E68E10A7}

```js
s.trackExternalLinks=true 
```

```js
s.trackExternalLinks=false
```

**Parámetros de configuración** {#section_C8748CFE36324FAFB14C23E3E1FB5082}

Ninguna

**Problemas, preguntas y consejos** {#section_FE2C3AF17DA24EA8A944BF1D394FB5BC}

* When *`trackExternalLinks`* is 'false,' links that take people away from your site are likely to be under reported in visitor click map.
* When *`trackExternalLinks`* is 'true,' data is sent each time a visitor clicks on an exit link (before link target loads).

## s.trackInlineStats {#concept_E3A811D9761E4917935F6CD9059C7FCC}

<!-- 
trackInlineStats.xml
-->

La variable determina si los datos de ClickMap se recopilan.

If *`trackInlineStats`* is 'true,' data about the page and link clicked are stored in a cookie called s_sq. If 'false,' s_sq will have a value of "[[B]]," which is considered null.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | ClickMap | False |

**Sintaxis y valores posibles** {#section_46B2C1DD0D104A01A9C239929420CD90}

```js
s.trackInlineStats=true|false
```

Se espera que la variable *`trackInlineStats`sea 'true' o 'false'.*

**Ejemplos** {#section_F146770917A3493AB8007626913CD6AB}

```js
s.trackInlineStats=true
```

```js
s.trackInlineStats=false
```

**Parámetros de configuración** {#section_FB2CDB07CDCE454786D96A66E4D8EDCD}

Ninguna

## s.linkDownloadFileTypes {#concept_06CC14C69DFD4887A5E6967A157A9E05}

<!-- 
linkDownloadFileTypes.xml
-->

La variable es una lista de extensiones de archivo separados por coma.

Si su sitio contiene vínculos a archivos con cualquiera de estas extensiones, las direcciones URL de estos vínculos se verán en el informe [!UICONTROL Descargas de archivos].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N.D. | N.D. | Tráfico &gt; Tráfico del sitio &gt; Descargas de archivos | "exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls" |

La variable *`linkDownloadFileTypes`* solo es relevante cuando *`trackDownloadLinks`* se establece en'true '.

En el informe [!UICONTROL Descargas de archivos] solo se contabilizan los clics con el botón principal del ratón. En el informe [!UICONTROL Descargas de archivos] no se contabilizan todas las descargas de archivos que se inician automáticamente cuando se carga una página o las que solo se descargan después de una redirección. Cuando se hace clic con el botón secundario en un archivo y se selecciona la opción "Guardar destino como...", no se contabiliza en el informe [!UICONTROL Descargas de archivos].

La variable *`linkDownloadFileTypes`* puede utilizarse para realizar el seguimiento de los clics a fuentes RSS. If you have links to RSS feeds with a .xml or other extension, appending ",xml" to the *`linkDownloadFileTypes`* list allows you to see how often each RSS link is clicked.

**Sintaxis y valores posibles** {#section_E0B3F3817BBF4B11AFAABEF8BB951E5A}

Incluya solamente extensiones de archivos (sin espacios).

```js
s.linkDownloadFileTypes="type1[,type2[,type3[...]]]"
```

En la lista se puede incluir cualquier extensión de archivo. Asegúrese de no incluir una extensión de archivo común, como htm o aspx, en  *`linkDownloadFileTypes`*. De hacerlo, enviará una solicitud de imagen adicional por cada clic, lo que se cobrará como una llamada al servidor primario.

**Ejemplos** {#section_C53F1AF768434CEBA65F3D255BC470AD}

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls"
```

```js
s.linkDownloadFileTypes="exe,zip,wav,mp3,mov,mpg,avi,wmv,doc,pdf,xls,xml"
```

**Parámetros de configuración** {#section_CE24D5852E4D441A958A4EDDB82382A7}

Ninguna

**Problemas, preguntas y consejos** {#section_786CF22D5553429EB6524B13774793BC}

* Solamente los clics en archivos de descarga que se hagan con el botón principal del ratón harán que la dirección URL aparezca en el informe de [!UICONTROL descargas de archivos].
* La inclusión de una extensión de archivo común en *`linkDownloadFileTypes`* puede incrementar de manera significativa el total de llamadas al servidor enviadas a los servidores de Adobe. 
* Los vínculos a redirecciones del lado del servidor o a páginas HTML que comienzan automáticamente a descargar un archivo no se cuentan, a menos que la extensión del archivo esté en *`linkDownloadFileTypes`*.
* Los vínculos que utilizan JavaScript (como javascript:openLink( )) no se contabilizan en las descargas de archivos.

## s.linkInternalFilters {#concept_D53C1186762E4AAE82451712B0801CAD}

<!-- 
linkInternalFilters.xml
-->

La variable se usa para determinar qué vínculos del sitio son vínculos de salida.

Es una lista de filtros separados por coma que representan los vínculos que son parte del sitio.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Rutas &gt; Entradas y salidas &gt; Vínculos de salida |  |

>[!NOTE]
>
>Antes habíamos sugerido configurar linkinternalfilters en javascript:. Sin embargo, el resultado era que todos los dominios se consideraban externos, incluido el dominio actual en el que reside la etiqueta. Si desea que algunos dominios se consideren internos, puede agregarlos como se muestra en los ejemplos siguientes.

The *`linkInternalFilters`* variable is used to determine whether a link is an exit link, which is defined as any link that takes a visitor away from your site. El vínculo puede aparecer en el informe de vínculos de salida independientemente de si la ventana objetivo de un vínculo de salida es una ventana emergente o la ventana actual. Solo se realiza el seguimiento de los vínculos de salida si es *`trackExternalLinks`* está configurada como `"true"`. (Consulte [Seguimiento de vínculos](https://marketing.adobe.com/resources/help/en_US/dtm/link_tracking.html) en la documentación de Dynamic Tag Management para obtener información sobre cómo administra DTM los vínculos de salida). The filters in *`linkInternalFilters`* are not case-sensitive.

The list of filters in *`linkInternalFilters`* applies to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to `"true"`, then the filters apply to the entire URL (domain, path, and query string). Los filtros siempre se aplican a la ruta absoluta de la dirección URL, incluso si se utiliza una ruta relativa como el valor href.

Asegúrese de que todos los dominios del sitio (y de los socios que usen su archivo JavaScript) estén incluidos en  *`linkInternalFilters`*. Si no todos los dominios están incluidos en la lista, todos los vínculos de esos dominios y hacia esos dominios se considerarán vínculos de salida, lo que aumenta las llamadas al servidor enviadas. If you would like multiple domains or companies to use a single [!DNL AppMeasurement] for JavaScript file, you may consider populating *`linkInternalFilters`* on the page, overriding the value specified in the JavaScript file. Si tiene dominios personales que se redireccionan inmediatamente al dominio principal, no es necesario incluir dichos dominios personales en la lista.

El siguiente ejemplo ilustra cómo se utiliza esta variable. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="mysite.com" 
s.linkExternalFilters="" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Exit Link</a> 
<a href="https://www2.site1.com/partners/">Exit Link</a> 
```

**Sintaxis y valores posibles** {#section_810966F09912415B96EA9C2EDAE0CEA0}

The *`linkInternalFilters`* variable is a comma-separated list of ASCII characters. No se permiten espacios.

```js
s.linkInternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

**Ejemplos** {#section_491F48556DC247889D54C66FC431B4EC}

```js
s.linkInternalFilters="mysite.com"
```

```js
s.linkInternalFilters="mysite.com,mysite.net,vanity1.com"
```

**Parámetros de configuración** {#section_546AC1FACB664ABFBCF312990097C987}

Ninguna

**Problemas, preguntas y consejos** {#section_E83A6F8B6EE44D51A2800D83F8BB264F}

* Include all domains that the [!DNL AppMeasurement] for JavaScript file may be served under in the filter list.
* Compruebe periódicamente el informe [!UICONTROL Rutas] &gt; [!UICONTROL Entradas y salidas] &gt; [!UICONTROL Vínculos de salida] para asegurarse de que ninguna de las entradas del informe son incorrectas.

* Revise periódicamente los contratos con los socios para determinar si contienen restricciones sobre el seguimiento de vínculos. Por ejemplo, quizás tenga prohibido realizar el seguimiento de vínculos que aparecen en los anuncios en pantalla de los socios. Filtre los vínculos de los socios agregando su dominio a  *`linkInternalFilters`*:

```js
s.linkInternalFilters="mysite.com,mysite.net,mypartner.net/adclick"
```

## s.linkLeaveQueryString {#concept_118C280E29394DB5A16DBBF41EB4D742}

<!-- 
linkLeaveQueryString.xml
-->

De manera predeterminada, las cadenas de consulta están excluidas de todos los informes.

Para algunos vínculos de salida y vínculos de descarga, la parte importante de la dirección URL puede estar en la cadena de consulta, como se muestra en la siguiente URL de ejemplo.

```js
https://www.mycompany.com/download.asp?filename=myfile.exe
```

El nombre del archivo de descarga puede estar definido en la cadena de consulta y, por lo tanto, esta es necesaria para que el informe [!UICONTROL Descargas de archivos] sea más preciso.

La variable *`linkLeaveQueryString`* determina si la cadena de consulta debe incluirse en los informes [!UICONTROL Vínculos de salida] y [!UICONTROL Descargas de archivos].

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| N.D. | N.D. | Descargas de archivos de vínculos de salida | false |

>[!NOTE]
>
>Setting `linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.

**Sintaxis** {#section_C40CF036B71A496D92574C6E46DE8302}

```js
s.linkLeaveQueryString=[false/true]
```

**Ejemplos** {#section_E42CEC8DDE624A4B979F4F6C8094A7F9}

```js
s.linkLeaveQueryString=false
```

**Valores posibles** {#section_E13211451B664B909B1BFDD050472F18}

```js
s.linkLeaveQueryString=false
```

```js
s.linkLeaveQueryString=true
```

**Parámetros de configuración** {#section_835FD74D3CA9425A9D091CACF88A6F1F}

No es necesaria ninguna configuración para esta variable.

**Problemas, preguntas y consejos** {#section_085E79D1A7F74F5D95F82D34FB82AEC4}

* Setting `s.linkLeaveQueryString=true` includes all query string parameters for all exit links and download links.
* The `linkLeaveQueryString` variable does not affect recorded page URLs, visitor click map, or [!UICONTROL Path] reports.

## s.linkTrackVars {#concept_A6B117826C15402EBD0781A94C8065B9}

<!-- 
linkTrackVars.xml
-->

La variable es una lista de variables separadas por coma que se envían con vínculos personalizados, de salida y de descarga.

If *`linkTrackVars`* is set to "", all variables that have values are sent with link data. To avoid inflation of instances or page views associated with other variables, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

All variables that should be sent with link data (custom, exit, and download links) should be listed in *`linkTrackVars`*. If *`linkTrackEvents`* is used, *`linkTrackVars`* should contain "events."

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Cualquiera | "None" |

Al rellenar *`linkTrackVars`*, no use el prefijo's.' para las variables. For example, instead of populating *`linkTrackVars`* with "s.prop1," you should populate it with "prop1." The following example illustrates how *`linkTrackVars`* should be used.

```js
s.linkTrackVars="eVar1,events" 
s.linkTrackEvents="event1" 
s.events="event1" 
s.eVar1="value A" 
s.eVar2="value B" 
s.t() // eVar1, event1 and event2 are recorded 
<a href="https://google.com">event1 and eVar1 are recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.eVar1='value C';s.events='';s.tl(this,'o')">eVar1 is recorded</a> 
```

Puesto que el vínculo a google.com es un vínculo de salida (a menos que usted sea Google), event1 y eVar1 se envían con los datos del vínculo de salida, lo que aumenta las instancias asociadas a eVar1 y el número de veces que se activa event1. In the link to [!DNL test.php], [!UICONTROL eVar1] is sent with a value of 'value C' because that is the current value of [!UICONTROL eVar1] at the time that *`tl()`* is called.

**Sintaxis y valores posibles** {#section_DCC239F5CFE74959856764DAB1862BA7}

The *`linkTrackVars`* variable is a case-sensitive, comma-separated list of variable names, without the object name prefix. Use 'eVar1' en lugar de 's.eVar1'.

```js
s.linkTrackVars="variable_name[,variable_name[...]]"
```

La variable *`linkTrackVars`* puede contener únicamente variables a las [!DNL Analytics]que se envían, concretamente: *`events`**`campaign`**`purchaseID`*, *`products`*[!UICONTROL Evar 1-75], [!UICONTROL prop 1-75], [!UICONTROL hier 1-5]*`channel`**`server`**`state`**`zip`*, y *`pageType`*.

**Ejemplos** {#section_546BAAC7373A41BF8583B280EAAB607C}

```js
s.linkTrackVars="events,prop1,eVar49"
```

```js
s.linkTrackVars="products"
```

**Parámetros de configuración** {#section_E387604B8A434A7F89A82A886649A89D}

Ninguna

**Problemas, preguntas y consejos** {#section_99E0783A608C4462945F35D21AB4AC2B}

* If *`linkTrackVars`* is blank, all variables that have values are tracked with all server calls.
* Any variable listed in *`linkTrackVars`* that has a value at the time of any download, exit, or custom link, are tracked.
* If *`linkTrackEvents`* is used, *`linkTrackVars`* must contain "events."

* No use el prefijo "s." ni "s_objectname." para las variables.

## s.linkTrackEvents {#concept_34D029097A674D0A97690C9569590EF5}

<!-- 
linkTrackEvents.xml
-->

The  variable is a comma-separated list of events that are sent with a [!UICONTROL custom], [!UICONTROL exit], or [!UICONTROL download] link.

If an event is not in *`linkTrackEvents`*, it is not sent to [!DNL Analytics], even if it is populated in the [!UICONTROL onClick] event of a link, as shown in the following example:

```js
s.linkTrackVars="events" 
s.events="event1,event2" 
s.t() // both event1 and event2 are recorded 
<a href="help.php" onClick="s=s_gi('rs1');s.tl(this,'o')">event1 is recorded</a> 
<a href="test.php" onClick="s=s_gi('rs1');s.events='event2';s.tl(this,'o')">No events are recorded</a> 
```

En el primer vínculo a [!DNL help.php], observe que la variable events retiene el valor que se configuró antes de hacer clic en el vínculo. Esto permite enviar event1 con el vínculo personalizado. In the second example, the link to [!DNL test.php], event2 is not recorded because it is not listed in *`linkTrackEvents`*.

To avoid confusion and potential problems, Adobe recommends populating *`linkTrackVars`* and *`linkTrackEvents`* in the [!UICONTROL onClick] event of a link that is used for link tracking.

The *`linkTrackEvents`* variable contains the events that should be sent with [!UICONTROL custom], [!UICONTROL download], and [!UICONTROL exit] links. This variable is only considered if *`linkTrackVars`* contains "events."

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Conversión | "None" |

**Sintaxis y valores posibles** {#section_89BA2425FBDC400A8C8B7FCDE7D67D63}

*`linkTrackEvents`* La variable es una lista de eventos separados por coma (sin espacios).

```js
s.linkTrackEvents="event1[,event2[,event3[...]]]"
```

Solo se permiten nombres de evento en *`linkTrackEvents`*. These events are listed in [Events](../../../implement/js-implementation/c-variables/page-variables.md#concept_FFD115543D54401B98FE683BD7D5B3FE). Si aparece un espacio antes o después del nombre de evento, el evento no se puede enviar con ninguna solicitud de imagen de vínculo.

**Ejemplos** {#section_AB7F952E522A4DCC92944EBF74C26BDD}

```js
s.linkTrackEvents="purchase,event1"
```

```js
s.linkTrackEvents="scAdd,scCheckout,purchase,event14"
```

**Parámetros de configuración** {#section_D938A47346D94A0C9E98FB327F2EF349}

Ninguna

**Problemas, preguntas y consejos** {#section_DBB68BECC9D44380816113DB2566C38C}

* The JavaScript file only uses *`linkTrackEvents`* if *`linkTrackVars`* contains the "events" variable. "events" should be included in *`linkTrackVars`* only when *`linkTrackEvents`* is defined.

* Beware if an event is fired on a page, and is listed in *`linkTrackEvents`*. That event is recorded again with any [!UICONTROL exit], [!UICONTROL download], or [!UICONTROL custom] links unless the events variable is reset prior to that event (in the [!UICONTROL onClick] of a link or after the call to the *`t()`* function).

* If *`linkTrackEvents`* contains spaces between event names, the events are not recorded.

## s.linkExternalFilters {#concept_92A59169DCE443EBAE81A373B27BB6DD}

<!-- 
linkExternalFilters.xml
-->

Si el sitio contiene muchos vínculos a sitios externos y no se desea realizar el seguimiento de todos los vínculos de salida, use para crear un informe de un subconjunto específico de vínculos de salida.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | Rutas &gt; Entradas y salidas &gt; Vínculos de salida | "" |

La variable *`linkExternalFilters`* es una variable opcional utilizada junto con *`linkInternalFilters`* para determinar si un vínculo es un vínculo de salida. Un vínculo de salida se define como un vínculo que conduce a un visitante fuera del sitio. El vínculo puede aparecer en el informe de vínculos de salida independientemente de si la ventana objetivo de un vínculo de salida es una ventana emergente o la ventana actual. Los vínculos de salida solo se rastrean si *`trackExternalLinks`* se establece en'true '. The filters in *`linkExternalFilters`* and *`linkInternalFilters`* are case insensitive.

>[!NOTE]
>
>If you don't want to use *`linkExternalFilters`*, delete it or set it to "".

The filters list in *`linkExternalFilters`* and *`linkInternalFilters`* apply to the domain and path of any link by default. If *`linkLeaveQueryString`* is set to 'true,' the filters apply to the entire URL (domain, path, and query string). Estos filtros siempre se aplican a la ruta absoluta de la dirección URL, incluso si se utiliza una ruta relativa como el valor href.

Para la mayoría de las empresas, *`linkInternalFilters`* proporciona suficiente control sobre los vínculos de salida que no necesitan *`linkExternalFilters`*. Using *`linkExternalFilters`* simply decreases the likelihood that an exit link is considered external. If *`linkExternalFilters`* has a value, then a link is considered only external if it does not match *`linkInternalFilters`* and does match *`linkExternalFilters`*.

El siguiente ejemplo ilustra cómo se utiliza esta variable. In this example, the URL of the page is `https://www.mysite.com/index.html`.

```js
s.trackExternalLinks=true 
s.linkInternalFilters="javascript:,mysite.com" 
s.linkExternalFilters="site1.com,site2.com,site3.com/partners" 
s.linkLeaveQueryString=false 
... 
<a href="https://www.mysite.com">Not an Exit Link</a> 
<a href="/careers/job_list.html">Not an Exit Link</a> 
<a href="https://www2.site3.com">Not an Exit Link</a> 
<a href="https://www.site1.com">Exit Link</a> 
<a href="https://www2.site3.com/partners/offer.asp">Exit Link</a> 
```

**Sintaxis y valores posibles** {#section_E35DAAAE8BDE44CEB8F6763EF1344693}

The *`linkExternalFilters`* variable is a comma-separated list of ASCII characters. No se permiten espacios.

```js
s.linkExternalFilters="site1.com[,site2.com[,site3.net[...]]]"
```

Se puede incluir cualquier parte de una dirección URL en *`linkExternalFilters`*, separada con comas.

**Ejemplos** {#section_1D2F13EEC28942868C2F4207ADF2DDE0}

```js
s.linkExternalFilters="partnersite.com,partnertwo.net/path/"
```

```js
s.linkExternalFilters=""
```

**Parámetros de configuración** {#section_2D0CA911855B4B3698145FC18D5021C3}

Ninguna

**Problemas, preguntas y consejos** {#section_8B40E6F539E3473B934A8DB7C5086D73}

* Using *`linkExternalFilters`* can result in fewer links on your site being exit links. Do not use this variable in place of *`linkInternalFilters`* to force internal links to become exit links.

* If *`linkExternalFilters`* should be applied to the query string of a link, make sure *`linkLeaveQueryString`* is set to 'true.' See [linkLeaveQueryString](../../../implement/js-implementation/c-variables/configuration-variables.md#concept_118C280E29394DB5A16DBBF41EB4D742) before setting to `"true"`.

* To disable exit link tracking, set *`trackExternalLinks`* to `"false"`.

## s.usePlugins {#concept_81836470A25C41228CE04084565F667D}

<!-- 
s_usePlugins.xml
-->

If the  function is available and contains useful code, [!UICONTROL s_usePlugins] should be set to 'true.'

When [!UICONTROL usePlugins] is 'true,' the *`s_doPlugins`* function is called prior to each image request.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | True |

**Sintaxis y valores posibles** {#section_BAD0F150047A4B7FB1214491B939A1FC}

```js
s.usePlugins=true|false
```

Se espera que la variable [!UICONTROL usePlugins] sea 'true' o 'false'.

**Ejemplos** {#section_1423CC3026384B1A9F78B272166B1DF5}

```js
s.usePlugins=true
```

```js
s.usePlugins=false
```

The [!UICONTROL usePlugins] variable should only be false (or not declared) if the *`s_doPlugins`* function is not declared in your JavaScript file.

**Parámetros de configuración** {#section_DFD41717134147E988B6AFC7DE5BB9E3}

Ninguna