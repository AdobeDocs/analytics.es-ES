---
description: Las variables de datos de contexto permiten definir las variables personalizadas de cada página que pueden leer las reglas de procesamiento.
keywords: Implementación de Analytics; contextdata; s. contextdata
seo-description: Las variables de datos de contexto permiten definir las variables personalizadas de cada página que pueden leer las reglas de procesamiento.
seo-title: Variables de datos de contexto
solution: Analytics
subtopic: Variables
title: Variables de datos de contexto
topic: Desarrollador e implementación
uuid: 4 b 215803-99 d 4-46 f 2-b 3 c 1-e 78558987764
translation-type: tm+mt
source-git-commit: 01a6fc7e44dc71b868bd38a4f6a5a4089eae6349

---


# Variables de datos de contexto

Las variables de datos de contexto permiten definir las variables personalizadas de cada página que pueden leer las reglas de procesamiento.

En lugar de asignar explícitamente valores a props y eVars en el código, puede enviar datos en las variables de datos de contexto que se asignan mediante reglas de procesamiento. Las reglas de procesamiento proporcionan una poderosa interfaz gráfica para realizar cambios en los datos a medida que se reciben. En función de los valores enviados en los datos de contexto, puede configurar eventos, copiar valores a eVars y props y ejecutar enunciados condicionales adicionales.

>[!NOTE]
>
>Las variables de datos de contexto no distinguen entre mayúsculas y minúsculas. Por ejemplo, las dos instancias siguientes son iguales a todos los efectos: &gt;
>```>
>s.contextData['article_title'] = 'Weekend Concert Controversy'; 
>
>
```>
>and 
>
>
```>
>s.contextData['ARTICLE_TITLE'] = 'Weekend Concert Controversy';
>```>



El uso de datos de contexto le ayuda a evitar tener que hacer actualizaciones del código para admitir configuraciones de grupos de informes distintas.

Por ejemplo, puede definir la siguiente variable *`s.contextData`* :

```
s.contextData['myco.rsid'] = 'value'
```

Con las reglas de procesamiento, puede agregar una condición que compruebe la variable `myco.rsid` de datos de contexto. Puede agregar una acción para que, al encontrarse esta variable, se copie en una prop o eVar.

Las variables de datos de contexto también se pueden definir directamente en la interfaz Reglas de procesamiento para almacenar temporalmente un valor, o para recopilar valores de una variable de datos de contexto que sepa que se va a usar en el grupo de informes. Por ejemplo, si necesita intercambiar dos valores, puede crear una variable de datos de contexto para almacenar un valor durante el intercambio.

Debido a que las reglas de procesamiento se aplican únicamente cuando los datos se recopilan, es importante configurar las reglas de procesamiento antes de comenzar a enviar datos de contexto. Los valores de datos de contexto que las reglas de procesamiento no lean cuando se procese una visita, se descartarán.

## Reglas {#section_2229739F6B1A4C1CAD7140BDF4687523}

<table id="table_4433A32A952340699B189CAEAF158B06"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Regla </p> </th> 
   <th colname="col2" class="entry"> <p>Descripción </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Nombres y caracteres admitidos </p> </td> 
   <td colname="col2"> <p>Los nombres de variables de datos de contexto solo pueden contener caracteres alfanuméricos, guión bajo y punto. Todos los demás caracteres se eliminan. Las variables de datos de contexto no tienen una designación numérica, sino que se les asigna un nombre. </p> <p>Por ejemplo, la variable de datos de contexto <code>login_page-home</code> se transforma automáticamente en <code>login_pagehome </code>. Todos los datos que se envíen a la variable <code>login_page-home</code> se asignan a <code>login_pagehome </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Espacio de nombres </p> </td> 
   <td colname="col2"> <p>Se recomienda prefijar las variables con el nombre de su empresa, el nombre de su sitio o un valor similar para así asegurarse de que el nombre es único en el grupo de informes. </p> <p>Se puede poner nombre a las variables de datos de contexto de forma similar a como se hace con otras variables de JavaScript. Tenga en cuenta que el espacio de nombres <code>a.*</code> está reservado para el uso de los productos de Adobe en los nombres de las variables de contexto. Por ejemplo, la biblioteca de AppMeasurement para iOS usa <code>a.InstallEvent</code> para medir las instalaciones de aplicaciones. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Límites de URL para Internet Explorer </p> </td> 
   <td colname="col2"> <p>Puede encontrarse con una limitación de URL antiguas para Internet Explorer 6 y 7, donde las URL se truncan a los 2000 bytes. Puede utilizar <span class="keyword">DigitalPulse Debugger</span> para averiguar el tamaño de una cadena de URL. </p> <p>Con las actualizaciones recientes de AppMeasurement (septiembre de 2014), se utiliza HTTP POST con Internet Explorer 8+, lo cual elimina los problemas de truncado. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Versión de AppMeasurement admitida </p> </td> 
   <td colname="col2"> <p>Las variables de datos de contexto requieren al menos un código H23 o posterior. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Envío de datos de contexto en una llamada de seguimiento de vínculos {#section_35EBE5D1CF29427598BD4B2165CE64FC}

Incluya `ContextData` + el nombre de la variable que desea insertar en `s.linkTrackVars`:

```
s.contextData['myco.value'] = "some value"; 
s.linkTrackVars = "contextData.myco.value"; 
s.tl(true,"o","Link Name"); 
```

## Ejemplos {#section_A16AD9E6E0E84F6A85CA4F08512480B3}

Possible ways to replace implementation of the *`s.pageName`* variable, assuming that processing rules are set up correctly for each:

```
s.contextData['page'] = "Home Page" 
s.contextData['pagename'] = document.title // Takes the web page's title and passes it into the pageName context data variable 
s.contextData['pagevar'] = s.pageName // This example would be considered redundant, as both the pageName and contextData variable are available in Processing rules
```

Otros ejemplos de implementación de variables de datos de contexto:

```
s.contextData['owner'] = "Jesse" 
s.contextData['campaign'] = "Campaign A" 
s.contextData['author'] = "Sheridan Andrius"
```

Por ejemplo, consulte [Copia de una variable de datos de contexto en una eVar](https://marketing.adobe.com/resources/help/en_US/reference/?f=processing_rules_copy_context_data) en la referencia de Analytics.
