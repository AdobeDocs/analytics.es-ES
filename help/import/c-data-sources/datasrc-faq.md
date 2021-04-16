---
description: En esta sección encontrará respuestas a preguntas comunes.
subtopic: Data sources
title: Preguntas frecuentes sobre las fuentes de datos
topic-fix: Developer and implementation
uuid: 394a627f-093c-400a-bfb3-c2aa24568deb
exl-id: 2a5d38fe-5c5b-4275-bc44-e9cb02ec2f5d
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '1496'
ht-degree: 95%

---

# Preguntas frecuentes sobre las fuentes de datos

En esta sección encontrará respuestas a preguntas comunes.

## ¿Cómo se pueden conectar datos sin conexión con eventos en línea? {#section_F48A9474A70D4CB8B449DE305F199AD6}

Para que las fuentes de datos de ID de transacción vinculen datos sin conexión a eventos en línea, es necesario activar el registro de ID de transacción. Consulte el [registro de ID de transacción](/help/import/c-data-sources/datasrc-integrating-offline-data.md#section_30D6D47AEC0F4A36B87EBFE4C858F20C) para obtener más información.

## ¿Cuánto cuesta utilizar la opción de fuente de datos?  {#section_0B84E3E8891B45E8970EA9D8AAD1ADEC}

Las fuentes de datos no conllevan tasas adicionales, más allá de la llamada a servidor estándar. Los cargos por la llamada a servidor estándar solo se aplican a los tipos de fuentes de datos de procesamiento completo, en que los accesos (hits) individuales se envían como filas de datos. Las fuentes de datos agregadas y de tráfico no conllevan costes adicionales.

## ¿Cómo se pueden incluir comentarios en los archivos de fuente de datos? {#section_AA42152C7B30425EA541A7BA274E78ED}

Cada fila del archivo de fuente de datos que comience con un signo de almohadilla (#) se considera un comentario.

## ¿Es necesario incluir una columna de fecha en los datos de la hoja de cálculo?  {#section_EA37F5FFB13446C497B3C64943F7084E}

Sí. Puesto que muchos informes de marketing usan la columna de fecha como clave, las fuentes de datos deben incluir una columna de fecha.

## ¿Se pueden almacenar datos en variables que ya se están utilizando? {#section_AB557C2997D04EAFBDC61398B13D13C6}

Para la importación de datos mediante fuentes de datos, Adobe recomienda seleccionar variables nuevas que no estén en uso. Si no está seguro de la configuración del archivo de datos o desea comprender mejor por qué la reutilización de variables comporta riesgos, póngase en contacto con el Servicio de atención al cliente.

## ¿Se pueden eliminar los datos importados mediante fuentes de datos?  {#section_DB73BC06BD774738BF019B347D9DED96}

No. Una vez importados, los datos cargados a informes mediante fuentes de datos no se pueden eliminar (ni siquiera con ayuda de técnicos de Adobe). Estos datos se incorporan en forma permanente a los otros datos y no pueden distinguirse de datos que se hayan obtenido por medios de recopilación tradicionales (p. ej., JavaScript, ActionSource, API de inserción de datos, etc.). Por eso, Adobe recomienda enfáticamente cargar las fuentes de datos a grupos de informes de prueba antes de importarlas a grupos de informes de producción.

## ¿Cuántos datos se pueden importar a la vez?  {#section_7A76D59E2C5B434D9BDBD2ABD2873168}

Si el tamaño de datos supera los 50 MB, el procesamiento se detendrá y no se reanudará hasta que el total sea menor que 50 MB. Para evitar demoras en la generación de informes, no cargue datos de más de 90 días por día.

## Cuando se importan datos a través de fuentes de datos, ¿se sobrescriben los datos ya presentes?  {#section_BDBD16D0AFD54D55AFDB8AC77D35FE77}

Cuando se cargan datos mediante fuentes de datos, estos no sobrescriben otros datos ya presentes en los informes, sino que se añaden a los datos previos.

## Cuando se cargan datos por medio de fuentes de datos, ¿por qué no aparecen también las métricas?  {#section_33176B39744F4F5A861E69AD87B99B78}

Cuando se cargan datos al sistema de fuentes de datos, se están cargando métricas que estarán disponibles en la interfaz de informes.

Por ejemplo, al cargar los ingresos del centro de llamadas correspondientes a los productos que se venden en el sitio web, puede colocarlos en el mismo informe que los ingresos obtenidos a través de Internet. Pero no se pueden usar junto con las visitas, porque la información correspondiente a las visitas no se ha cargado junto con la de ingresos. Adobe únicamente puede generar informes sobre las métricas y los elementos cargados mediante las fuentes de datos (además de las métricas habituales de informes de marketing).

## ¿Qué sucede si se transmiten valores negativos a informes a través de fuentes de datos? {#section_77E5F37F3CFB4407BA32A91E6F3132B2}

El valor disminuye según corresponda.

## ¿Qué diferencia hay entre una fuente de datos (genérica) de conversión y una de tráfico?  {#section_A34C952490814D4FB802F22D9FB3E9F8}

La fuente de datos de tráfico se carga mucho más rápido, porque solamente hay que actualizar los valores de resumen en las tablas que correspondan. La fuente de datos genérica con datos de conversión (eventos, etc.) crea una visita para cada valor en la columna que se procesará.

Archivo de muestra:

<table id="table_D5408E0BDB984229B4C60A66BB53CEBB"> 
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Date </code> </p> </td> 
   <td colname="col2"> <p> <code> Event15 </code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> 01/01/2013 </code> </p> </td> 
   <td colname="col2"> <p> <code> 553 </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

En el ejemplo anterior, se crean 553 visitas para procesar en el sistema de caché.

## ¿El sistema de fuentes de datos tiene en cuenta las subrelaciones, las correlaciones y la información sobre rutas?  {#section_7ABAE2F3C4DD48E18FB8CB20AE8AFD14}

Como durante el procesamiento de fuentes de datos (genéricas, no de tráfico) se crean accesos (hits) individuales que se procesan mediante caché, se pueden procesar subrelaciones, pero no correlaciones. Si hubiera información de rutas se podría procesar, pero como cada acceso será una visita separada, no se generará ninguna información de ruta. En la importación de registros web sí se generan datos de ruta.

## En las cargas de fuentes de datos o en los archivos de clasificación, ¿la extensión de archivo distingue entre mayúsculas y minúsculas?  {#section_710787BA4D8C403D8326D666807832B8}

Si la extensión de un archivo de clasificación o de carga de fuente de datos contiene mayúsculas, no se procesará. Es decir, las extensiones de los archivos de carga de fuentes de datos tienen que estar en minúsculas. Por ejemplo, no se procesan ni [!DNL file.TXT] ni [!DNL file.FIN]. Tampoco se procesarán las extensiones [!DNL .TAB] ni [!DNL .FIN]. Sin embargo, [!DNL .txt] y [!DNL .fin] sí se procesan.

## ¿Se pueden agregar otros eventos a la plantilla generada o no se puede pasar de tres? {#section_F184913926DD43B1872956CED308ADB5}

Se pueden agregar todos los eventos que quiera. Sin embargo, el asistente solo permite agregar hasta tres. Una vez creada la plantilla, se pueden agregar otros eventos según sea necesario.

## ¿Qué ocurre si en un archivo de fuente de datos hay registros que no tienen la misma cantidad de columnas que el registro de encabezado?  {#section_2666949CB11B49768774C904C93A16D4}

Si en un archivo de fuente de datos hay registros que no tienen la misma cantidad de columnas que el registro de encabezado, ocurrirá lo siguiente:

* Se enviará por correo electrónico un mensaje al creador de la fuente de datos para avisarle del error.
* El archivo no se procesará debido a la cantidad errónea de columnas.

## ¿La información de las fuentes de datos se resume?  {#section_E0E44C55A84245918E7CF5A4232F5C88}

La información de las fuentes de datos se puede resumir, pero el Servicio de atención al cliente de Adobe debe reprocesar el resumen desde la fecha histórica para incluir los datos históricos. Por ejemplo, si la fecha actual es 31 de octubre de 2015 y mediante fuentes de datos se cargan datos para el período que va del 1 al 15 de agosto de 2015, se tendrá que configurar el proceso de resumen de modo que comience el reprocesamiento el 1 de agosto de 2015 a fin de que se puedan incluir los datos recién importados.

Tenga en cuenta también que nunca se deben importar datos directamente a un grupo de informes de resumen con fuentes de datos. Si necesita incluir estos datos en un resumen, impórtelos en un grupo de informes estándar (también llamado *`child suite`* en el resumen). Para obtener más información, póngase en contacto con el Servicio de atención al cliente de Adobe.

## ¿Por qué en el informe de vistas de página no se muestran datos de la fuente de datos para un día particular, pero sí se muestran los datos correctos para una semana?  {#section_E361A93AFDE1487989B4B0C4438EEDF7}

El sistema de fuentes de datos no presenta datos desglosados por hora. Cuando se intenta ejecutar un informe para un día en particular, los datos solamente pueden estar desglosados por hora; por eso, no aparece nada en el informe. Solamente se pueden ver datos que estén desglosados con un nivel de granularidad diario o superior, para lo cual se puede ejecutar un informe semanal o mensual.

## ¿Cómo se calculan los visitantes únicos en las cargas de fuente de datos de registros de servidor web?  {#section_477FEDFD1DBE45278E7D09AFBD59CDAC}

La cantidad de visitantes únicos en los registros de servidor web se calcula según la cantidad de combinaciones distintas de *`IP Address`* y *`User Agent`* que aparezcan en el registro. Cada combinación única de estos dos elementos se calcula como un visitante único. Si la columna del [!UICONTROL Agente de usuario] está vacía (o no se incluye en el registro del servidor web), no será posible identificar cantidades de visitantes únicos, y toda la carga de datos se contará como un mismo visitante único (incluso si hay más de una dirección IP).

## En el sistema de fuentes de datos, ¿cómo se puede saber qué usuario corresponde a cada grupo de informes?  {#section_8EF9D22D5BE14C218724B06E78EF7DF4}

En el sistema de fuentes de datos, el ID del grupo de informes es la primera parte del nombre de usuario, al que se le agrega un número aleatorio que identifica la fuente de datos específica que se configuró. Por ejemplo: `RSID-drmossdev5 Login-drmossdev5_0001343430`.

## ¿Cuál es el efecto que tienen la versión 15 y la segmentación en las fuentes de datos? {#section_7E9E541DB73C49CDAADC031B678F8678}

En la versión 15, la manera de funcionar de las fuentes de datos varía según el tipo de fuente:

* Las fuentes de datos de procesamiento completo, registro web y el ID de transacción aparecen como es habitual. Cuando se aplican segmentos, los datos se filtran de acuerdo con las reglas de los segmentos.
* Las fuentes de datos estándar o de conversión (campañas de publicidad, CRM, satisfacción de clientes, rendimiento del sitio, datos de resumen genéricos, compras en línea, posibles clientes y presupuestos y datos de canales sin conexión) aparecen en la versión 15. Sin embargo, dado que esas fuentes de datos no están vinculadas a las visitas ni los visitantes, quedan excluidas al aplicar segmentos.

## ¿Las métricas que se importan con un ID de transacción están disponibles en fuentes de datos del flujo de navegación y en Data Warehouse?  {#section_01CD14CA3E11490CB2CBA433C649029E}

La fuente de datos contiene todas las métricas del ID de transacción que se han recibido. Sin embargo, si se cargan datos del ID de transacción correspondientes a una fecha ya pasada, la única forma de obtener esos datos es volver a descargar la fuente de datos de ese día.

## ¿Las eVars que continúan en este momento en el perfil del visitante se asignan a métricas cargadas mediante fuentes de datos?  {#section_1748BD5C6A12467F8082E07D6A9CD595}

En el caso del procesamiento completo, no. En el caso del ID de transacción, sí. Las fuentes de datos de procesamiento completo se procesan mediante perfiles de visitante independientes. Por eso, aunque los ID de visitante coincidan, no se vinculan entre ellos desde el punto de vista de una asignación de eVar. Como las fuentes de datos del ID de transacción están vinculadas al perfil del visitante principal, las eVars persistentes se asignan a eventos cargados con el ID de transacción.

## ¿Las eVars cargadas mediante fuentes de datos continúan en el comportamiento en Internet posterior?  {#section_0B490CEAAB604826AFD3E8B2531C8F2D}

No. Las eVars cargadas a través de fuentes de datos del ID de transacción solo consultarán la información de perfil almacenada, no actualizarán el perfil.
No. eVars son las únicas variables que se guardan en la instantánea del perfil del visitante.

## ¿Cómo funcionan los eventos numéricos y monetarios con las fuentes de datos?

El procesamiento completo solo admite formatos de lista de eventos heredados, excluido el valor de evento numérico/monetario/contador (más de 1) directamente en la lista de eventos, es decir, `"eventNN,eventKK"` no `"eventNN=#.##"`. Significa que solo admite un evento de contador si se pasa en la columna de eventos en el archivo de fuente de datos y se incrementa en 1.

Si se requieren eventos numéricos, monetarios o de contador (más de 1), utilice la lista de productos:

```js
s.products="Footwear;Running Shoes;1;99.99;event1=4.50";
s.products="Footwear;Running Shoes;1;99.99;event1=4.50|event4=1.99";
```
