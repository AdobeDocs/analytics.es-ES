---
description: Las reglas de procesamiento permiten realizar cambios en los datos según ciertas condiciones definidas. Cuando los atributos o los valores coinciden con las condiciones definidas, se pueden definir y eliminar valores, y definir eventos.
subtopic: Processing rules
title: Funcionamiento de las reglas de procesamiento
topic: Admin tools
uuid: 19c31f94-c8d8-47b1-97fa-29ed98c94e87
translation-type: ht
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02
workflow-type: ht
source-wordcount: '690'
ht-degree: 100%

---


# Funcionamiento de las reglas de procesamiento

Las reglas de procesamiento permiten realizar cambios en los datos según ciertas condiciones definidas. Cuando los atributos o los valores coinciden con las condiciones definidas, se pueden definir y eliminar valores, y definir eventos.

Las reglas de procesamiento se aplican a los datos según se van recopilando y a todos los datos que pasan a través de las bibliotecas AppMeasurement y a través de la API de inserción de datos. Las reglas de procesamiento también se aplican a las fuentes de datos de registro y completas. Estas fuentes contienen datos que representan una *`hit`* o una acción que realiza un usuario. Las reglas de procesamiento no se aplican a otras fuentes de datos.

## Conceptos básicos {#section_EB138775E7C64C74B0D1D3213F7A823C}

La siguiente tabla contiene los principales conceptos que debe comprender al utilizar reglas de procesamiento:

<table id="table_287C606AE26E47AA8F737411990ACEB2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Concepto </p> </th> 
   <th colname="col2" class="entry"> <p>Detalles </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Las reglas se aplican a un solo grupo de informes. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/t-processing-rules-copy-to-rs.md"> Copiar reglas de procesamiento en otro grupo de informes </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Las reglas de procesamiento se aplican por orden de lista. </p> </td> 
   <td colname="col2"> <p>Si una acción cambia un valor, las siguientes condiciones utilizarán el nuevo valor. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Las reglas de procesamiento se aplican inmediatamente al grupo de informes después de guardarse. </p> </td> 
   <td colname="col2"> <p>Los cambios de las reglas de procesamiento deberían estar visibles en el grupo de informes tras unos minutos después de guardarse. A la hora de probar reglas de procesamiento, es recomendable configurar <a href="/help/admin/admin/realtime/t-realtime-admin.md"> Informes en tiempo real</a> en su grupo de informes de prueba para poder ver rápidamente los resultados de una regla de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Las reglas de procesamiento son la única forma de acceder a las variables de datos de contexto. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/processing-rules-copy-context-data.md"> Copiar una variable de datos de contexto en una eVar </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Las reglas de procesamiento se aplican antes que las reglas de VISTA y las reglas de canal de marketing. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/c-processing-rules-configuration/processing-rule-order.md"> Orden de procesamiento </a> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Las visitas no se pueden excluir. </p> </td> 
   <td colname="col2"> <p>Puede utilizar reglas de VISTA para excluir visitas. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>La cadena de producto, el referente y el agente de usuario no se pueden cambiar. </p> </td> 
   <td colname="col2"> <p>El referente y el agente de usuario son de solo lectura. La cadena de producto no está disponible. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Los atributos y las clasificaciones de los dispositivos móviles no están disponibles. </p> </td> 
   <td colname="col2"> <p>La búsqueda de dispositivos móviles es anterior a las reglas de procesamiento, pero los atributos no están disponibles en las reglas de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Si se ejecuta JavaScript AppMeasurement H.25.2 o anterior, no pueden leerse los parámetros de cadena a partir de los primeros 255 caracteres de la dirección URL. JavaScript AppMeasurement H.25.3 y posteriores ofrecen la dirección URL completa de todos los parámetros de cadena de búsqueda para las reglas de procesamiento. </p> </td> 
   <td colname="col2"> <p>Existe la posibilidad de actualizar a H.25.3 o posterior, o de leer los parámetros de cadena de consulta de las direcciones URL largas del lado del cliente y almacenar los valores en variables de datos de contexto. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Los valores de las cadenas de consulta deben estar codificados en Unicode o UTF-8 para que puedan leerlos las reglas de procesamiento. </p> </td> 
   <td colname="col2"> <p>Esto puede afectar a los caracteres multibyte que se transfieren mediante cadenas de consulta. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Cada grupo de informes tiene un límite total de 150 reglas con 30 condiciones cada una. </p> </td> 
   <td colname="col2"> <p>Los límites de las reglas de procesamiento se aplican por grupo de informes, no por empresa. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Se deben configurar reglas de procesamiento para recuperar las variables de datos de contexto antes de que se envíen los datos. </p> </td> 
   <td colname="col2"> <p>Las reglas de procesamiento se aplican según se envían las llamadas al servidor. Los valores almacenados en variables de datos de contexto se descargan si no se copian mediante reglas de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Las comparaciones de valores en la IU distinguen entre mayúsculas y minúsculas. </p> </td> 
   <td colname="col2"> <p> <a href="/help/admin/admin/c-processing-rules/processing-rules-examples/clean-up-values-in-a-report.md"> Limpiar los valores de un informe </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Los nombres de las variables de datos de contexto solo pueden contener caracteres alfanuméricos, guiones bajos y puntos. Quedan descartados todos los caracteres restantes. </p> </td> 
   <td colname="col2"> <p>Por ejemplo, la variable de data de contexto <code> login_page-home</code> se transforma automáticamente en <code> login_pagehome</code>. Todos los datos enviados a la variable <code> login_page-home</code> se asignan en <code> login_pagehome</code>. </p> <p>Las variables de datos de contexto que contienen caracteres no admitidos no pueden agregarse en la interfaz de reglas de procesamiento. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>El acento circunflejo (^) es un carácter especial en el sistema de reglas de procesamiento. </p> </td> 
   <td colname="col2"> <p>Para hacer coincidir con un solo carácter de acento circunflejo, use dos caracteres de acento circunflejo (^^). </p> </td> 
  </tr> 
 </tbody> 
</table>

## Condiciones de las reglas de procesamiento {#section_387390EEE9BA4DA98698522A84326DB4}

Las condiciones buscan en las variables de la página un valor que coincida, o averiguan si está presente un valor. Se pueden agregar varias condiciones, y puede seleccionar si desea que se cumplan todas ellas.

Puede crear una regla sin condiciones para ejecutar siempre las acciones definidas.

No se buscan valores automáticamente en las variables antes de que ocurran las acciones. Por ejemplo, Prop1 contiene el valor &quot;algo&quot;, y eVar1 está vacía. Si define Prop1 de modo que sea igual a eVar1, ambos valores estarán vacíos. Si es necesario evitar que esto ocurra, agregue una condición para comprobar si existe un valor.

## Acciones de las reglas de procesamiento {#section_E2285C9D008442C7BF136E52A9A4CC06}

Las acciones definen y eliminan variables de página, o activan eventos. Las acciones también pueden concatenar valores para que aparezcan en un informe.

Por ejemplo, si se desea mostrar `category:product` concatenando dos variables.
