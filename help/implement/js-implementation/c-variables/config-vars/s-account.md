---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.account

La variables determina el grupo de informes donde se almacenan los datos y se crean los informes sobre ellos.

If sending to multiple report suites (multi-suite tagging), `s.account` may be a comma-separated list of values. La ID del grupo de informes viene determinada por Adobe.

## Parámetros

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| 40 bytes | En la ruta de URL | N.D. | N.D. |

Cada ID de grupo de informes debe coincidir con el valor creado en [!DNL Admin Console]. Cada ID de grupo de informes debe tener 40 bytes o menos, pero la suma de todos los grupos (es decir, la lista separada por comas completa) no tiene límite. 

El grupo de informes es el nivel más fundamental de segmentación en los informes. Puede configurar todos los grupos de informes que permita el contrato. Cada grupo de informes hace referencia a un conjunto de tablas dedicadas que se rellenan en los servidores de recopilación de Adobe. Un grupo de informes se identifica mediante la variable `s_account` en el código JavaScript.

En [!DNL Analytics], el cuadro desplegable del sitio en la esquina superior izquierda de los informes muestra el grupo de informes actual. Cada grupo de informes tiene un identificador único denominado ID de grupo de informes. La variable `s_account` contiene una o más ID del grupo de informes al que se envían los datos. Adobe debe proporcionar o aprobar el valor de la ID del grupo de informes, que es invisible para los usuarios de [!DNL Analytics], antes de que pueda utilizarla. Cada ID de grupo de informes tiene asociado un "nombre descriptivo" que se puede cambiar en la sección de grupos de informes de [!DNL Admin Console].

The `s_account` variable is normally declared inside the JavaScript file (s_code.js). You can declare the `s_account` variable on the HTML page, which is a common practice when the value of `s_account` may change from page to page. Because the `s_account` variable has a global scope, it should be declared immediately before including Adobe's JavaScript file. If `s_account` does not have a value when the JavaScript file is loaded, no data is sent to [!DNL Analytics].

Adobe's [!DNL DigitalPulse Debugger] displays the value of `s_account` in the path of the URL that appears just below the word "Image," just after /b/ss/. In some cases, the value of `s_account` also appears in the domain, before 112.2o7.net. El valor en la ruta es el único valor que determina el grupo de informes de destino. El texto en negritas que sigue muestra el grupo de informes al que se envían los datos, según aparecerá en el depurador. Consulte [DigitalPulse Debugger](https://docs.adobe.com/content/help/en/analytics/implementation/testing-and-validation/debugger.html).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## Sintaxis y valores posibles

La ID del grupo de informes es una cadena alfanumérica de caracteres ASCII, de no más de 40 bytes de longitud. El único carácter no alfanumérico permitido es un guión. No se permite ningún espacio, punto, coma u otro signo de puntuación. La variable `s_account` puede contener varios grupos de informes, y todos ellos recibirán datos de esa página.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

Adobe debe proporcionar o aprobar todos los valores de `s_account` .

## Ejemplos

```js
var s_account="mycompanycom"
```

```js
var s_account="mycompanycom,mycompanysection"
```

## Configuración de la variable en Analytics

Adobe [!DNL Customer Care] puede cambiar el nombre descriptivo asociado a cada ID de grupo de informes. Este nombre descriptivo se puede ver en [!DNL Analytics], en el cuadro desplegable del sitio situado en la parte superior izquierda de la pantalla.

## Problemas, preguntas y consejos

* If `s_account` is empty, not declared, or contains an unexpected value, no data is collected.
* When the `s_account` variable is a comma-separated list (multi-suite tagging), do not put spaces between report suite IDs.
* If [!UICONTROL s.dynamicAccountSelection] is set to *True* the URL is used to determine the destination report suite. Utilice [!DNL DigitalPulse Debugger] para determinar los grupos de informes de destino.

* En algunos casos, se puede utilizar [!DNL VISTA] para modificar el grupo de informes de destino. Se recomienda utilizar [!DNL VISTA] para volver a enrutar o copiar los datos en otro grupo de informes cuando se utilizan cookies de origen o si el sitio tiene más de 20 grupos de informes activos.

* Always declare `s_account` inside the JS file or just before it is included.
