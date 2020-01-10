---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Analytics Implementation
solution: null
title: Variables dinámicas
translation-type: ht
source-git-commit: f1ebe5e89f62957c8bcc829be4b1a97463210f93

---


# s.useForcedLinkTracking


La variables determina el grupo de informes donde se almacenan los datos y se crean los informes sobre ellos.

Si envía datos a grupos de informes múltiples (etiquetado de grupos múltiples), `s.account` puede ser una lista de valores separados por coma. La ID del grupo de informes viene determinada por Adobe.

## Parámetros

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|--- |--- |--- |--- |
| 40 bytes | En la ruta de URL | N/A | N/A |

Cada ID de grupo de informes debe coincidir con el valor creado en [!DNL Admin Console]. Cada ID de grupo de informes debe tener 40 bytes o menos, pero la suma de todos los grupos (es decir, la lista separada por comas completa) no tiene límite.

El grupo de informes es el nivel más fundamental de segmentación en los informes. Puede configurar todos los grupos de informes que permita el contrato. Cada grupo de informes hace referencia a un conjunto de tablas dedicadas que se rellenan en los servidores de recopilación de Adobe. Un grupo de informes se identifica mediante la variable `s_account` en el código JavaScript.

En [!DNL Analytics], el cuadro desplegable del sitio en la esquina superior izquierda de los informes muestra el grupo de informes actual. Cada grupo de informes tiene un identificador único denominado ID de grupo de informes. La variable `s_account` contiene una o más ID del grupo de informes al que se envían los datos. Adobe debe proporcionar o aprobar el valor de la ID del grupo de informes, que es invisible para los usuarios de [!DNL Analytics], antes de que pueda utilizarla. Cada ID de grupo de informes tiene asociado un "nombre descriptivo" que se puede cambiar en la sección de grupos de informes de [!DNL Admin Console].

La variable `s_account` se declara normalmente dentro del archivo JavaScript (s_code.js). Puede declarar la variable `s_account` en la página HTML, lo cual es una práctica común cuando el valor de `s_account` varía de página en página. Puesto que esta variable `s_account` tiene un alcance global, debe declararse inmediatamente antes de incluir el archivo JavaScript de Adobe. Si `s_account` no tiene un valor cuando se carga el archivo JavaScript, no se envían datos a [!DNL Analytics].

[!DNL DigitalPulse Debugger]de Adobe muestra el valor de `s_account` en la ruta de la dirección URL que aparece justo debajo de la palabra “Image”, después de /b/ss/. En algunos casos, el valor de `s_account` también aparece en el dominio, antes de 112.2o7.net. El valor en la ruta es el único valor que determina el grupo de informes de destino. El texto en negritas que sigue muestra el grupo de informes al que se envían los datos, según aparecerá en el depurador. Consulte [DigitalPulse Debugger](https://docs.adobe.com/content/help/es-ES/analytics/implementation/testing-and-validation/debugger.translate.html).

```js
https://mycompany.112.207.net/b/ss/ 
<b>mycompanycom,mycompanysection</b>/1/H.1-pdv-2/s21553246810948?[AQB]
```

## Sintaxis y valores posibles

La ID del grupo de informes es una cadena alfanumérica de caracteres ASCII, de no más de 40 bytes de longitud. El único carácter no alfanumérico permitido es un guión. No se permite ningún espacio, punto, coma u otro signo de puntuación. La variable `s_account` puede contener varios grupos de informes, y todos ellos recibirán datos de esa página.

```js
var s_account="reportsuitecom[,reportsuite2[,reportsuite3]]"
```

Adobe debe proporcionar o aprobar todos los valores de `s_account`.

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

* Si `s_account` está vacía, sin declarar o contiene un valor inesperado, no se recopilará ningún dato.
* Si la variable `s_account` es una lista separada por comas (etiquetado de grupos múltiples), no coloque espacios entre los ID de grupos de informes.
* Si [!UICONTROL s.dynamicAccountSelection] está configurada como *True*, se utiliza la dirección URL para determinar el grupo de informes de destino. Utilice [!DNL DigitalPulse Debugger] para determinar los grupos de informes de destino.

* En algunos casos, se puede utilizar [!DNL VISTA] para modificar el grupo de informes de destino. Se recomienda utilizar [!DNL VISTA] para volver a enrutar o copiar los datos en otro grupo de informes cuando se utilizan cookies de origen o si el sitio tiene más de 20 grupos de informes activos.

* Establezca el valor de `s_account` dentro del archivo JS o justo antes de que se incluya.
