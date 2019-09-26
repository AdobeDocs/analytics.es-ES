---
description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
keywords: Implementación de análisis
seo-description: Las variables dinámicas permiten copiar valores entre distintas variables sin necesidad de escribir varias veces los valores completos en las solicitudes de imagen del sitio.
solution: null
title: Variables dinámicas
translation-type: tm+mt
source-git-commit: b38ba4222951d957c607cd764224028527835c7e

---


# s.dynamicAccountList

[!DNL AppMeasurement] para JavaScript puede seleccionar dinámicamente el grupo de informes al que envía los datos. La variable contiene las reglas que se utilizarán para determinar el grupo de informes de destino.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | N.D. | N.D. | "" |

Esta variable se usa junto con las variables *`dynamicAccountSelection`* and *`dynamicAccountMatch`* variables. Las reglas de *`dynamicAccountList`* se aplican si *`dynamicAccountSelection`* se establece en 'true' y se aplican a la sección de la URL especificada en *`dynamicAccountMatch`*.

If none of the rules in  matches the URL of the page, the report suite identified in  is used. *`dynamicAccountList`*`s_account` Las reglas enumeradas en esta variable se aplican con un orden de izquierda a derecha. Si la dirección URL de la página coincide con más de una regla, se usa la regla situada más a la izquierda para determinar el grupo de informes. Como resultado, las reglas más genéricas deben situarse a la derecha de la lista.

In the following examples, the page URL is  and  is set to true and  is set to `www.mycompany.com/path1/?prod_id=12345``dynamicAccountSelection`**`s_account``mysuitecom.`

| Valor de DynamicAccountList | Valor de DynamicAccountMatch | Grupo de informes que recibirá los datos |
|---|---|---|
| `mysuite2=www2.mycompany.com;mysuite1=mycompany.com` | window.location.host | mysuite1 |
| "mysuite1=path4,path1;mysuite2=path2" | window.location.pathname | mysuite1, mysuite2 |
| "mysuite1=path5" | window.location.pathname | mysuitecom, mysuite1 |
| "myprodsuite=prod_id" | window.location.search?window.location.search:"?") | myprodsuite |

## Sintaxis y valores posibles

La sintaxis de la variable `dynamicAccountList`es una lista de pares nombre=valor (reglas) separadas por punto y coma. Cada parte de la lista debe contener los siguientes elementos:

* una o varias ID de grupo de informes (separadas por coma)
* un signo igual
* uno o varios filtros de URL (separados por coma)

```js
s.dynamicAccountList=rs1[,rs2]=domain1.com[,domain2.com/path][;...]
```

En la cadena solo deben usarse caracteres ASCII estándar (sin espacios).

## Ejemplos

```js
s.dynamicAccountList="mysuite2=www2.mycompany.com;mysuite1=mycompany.com"
```

```js
s.dynamicAccountList="ms1,ms2=site1.com;ms1,ms3=site3.com"
```

## Parámetros de configuración

Ninguno.

## Problemas, preguntas y consejos

* La selección de cuentas dinámicas no se admite en [AppMeasurement para JavaScript](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/appmeasurement-js/appmeasure-mjs.html).

* Si la dirección URL de la página coincide con varias reglas, se usa la regla situada más a la izquierda.
* Si no coincide ninguna regla, se usa el grupo de informes predeterminado.
* Si su página se guarda en el disco duro de otra persona o se traduce mediante un motor de traducción web (como las páginas traducidas de Google), la selección de cuentas dinámicas probablemente no funcionará. Para un seguimiento más preciso, rellene el lado del servidor de la variable `s_account`.
* The `dynamicAccountSelection` rules apply only to the section of the URL specified in `dynamicAccountMatch`.

* Cuando utilice la selección de cuentas dinámicas, asegúrese de actualizar *`dynamicAccountList`* cada vez que obtenga un nuevo dominio.
* Use [!DNL DigitalPulse Debugger] cuando trate de identificar el grupo de informes de destino. The `dynamicAccountSelection` variable always overrides the value of `s_account`.
