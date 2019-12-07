---
description: El complemento getTimeParting rellena variables personalizadas con los valores de hora del día, día de la semana y fin de semana y día laborable. Analysis Workspace incluye dimensiones de división del tiempo. Debe utilizarse el complemento si se necesitan las dimensiones de división del tiempo en otras soluciones de Analytics fuera de Analysis Workspace.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getTimeParting

El complemento getTimeParting rellena variables personalizadas con los valores de hora del día, día de la semana y fin de semana y día laborable. [!UICONTROL Analysis Workspace] incluye dimensiones de división del tiempo. Debe utilizarse el complemento si se necesitan las dimensiones de división del tiempo en otras soluciones de Analytics fuera de [!UICONTROL Analysis Workspace].

Este complemento captura la información sobre la fecha y hora disponible en el explorador del usuario. A partir de esta información obtiene la hora del día y el día de la semana. A continuación convierte estos datos a la zona horaria que usted elija. Asimismo, tiene en cuenta el horario de verano.

> [!NOTE] Las instrucciones siguientes exigen modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Código de complemento {#section_1390D6FA53BE4C40B748B0C0AE09C4FA}

**Sección config**

Inserte el código siguiente en el área del archivo [!DNL s_code.js] etiquetado [!UICONTROL SECCIÓN CONFIG], y realice las actualizaciones necesarias tal como se describe a continuación.

`s._tpDST`: matriz de valores de horario de verano. La matriz tiene el siguiente formato: `YYYY:'MM/DD,MM/DD'`

```js
//time parting configuration 
//Australia 
s._tpDST = { 
2012:'4/1,10/7', 
2013:'4/7,10/6', 
2014:'4/6,10/5', 
2015:'4/5,10/4', 
2016:'4/3,10/2', 
2017:'4/2,10/1', 
2018:'4/1,10/7', 
2019:'4/7,10/6',
2020:'4/5,10/4',
2021:'4/4,10/3'} 
  
//US 
s._tpDST = { 
2012:'3/11,11/4', 
2013:'3/10,11/3', 
2014:'3/9,11/2', 
2015:'3/8,11/1', 
2016:'3/13,11/6', 
2017:'3/12,11/5', 
2018:'3/11,11/4', 
2019:'3/10,11/3',
2020:'3/8,11/1',
2021:'3/14,11/7'} 
  
//Europe 
s._tpDST = { 
2012:'3/25,10/28', 
2013:'3/31,10/27', 
2014:'3/30,10/26', 
2015:'3/29,10/25', 
2016:'3/27,10/30', 
2017:'3/26,10/29', 
2018:'3/25,10/28', 
2019:'3/31,10/27',
2020:'3/29,10/25',
2021:'3/28,10/31'}
```

Nota para clientes del hemisferio norte: en la matriz, los valores de horario de verano son valores de inicio y finalización del horario de verano.

Nota para clientes del hemisferio sur: en la matriz, los valores de horario de verano son valores de finalización e inicio del horario de verano.

**Parámetros**

```js
var tp = s.getTimeParting(h,z);
```

* h = (requerido) Hemisferio: especifique el hemisferio al que va a convertir la hora. Debe ser un valor 'n' o 's'. Se usa para determinar cómo se usa la matriz de horario de verano pasada. Si se pasa 'n', el complemento usa las fechas cuando el horario de verano está activado. Si se pasa 's', el complemento usa las fechas cuando el horario de verano está desactivado.
* z = (opcional) Zona horaria: si desea que los datos se basen en un período de tiempo específico, se tendrá que especificar aquí como diferencia horaria respecto a GMT. Tenga en cuenta que debe ser GMT durante los horarios que no sean de verano. Si no se especifica ningún valor, el valor predeterminado es GMT (por ejemplo, "-5" para la hora del este de EE. UU.).

**Devuelve**

Devuelve un valor concatenado de hora, a nivel de minuto y día de la semana, por ejemplo:

```
8:03 AM|Monday
```

Puede usar [Clasificaciones](https://marketing.adobe.com/resources/help/en_US/reference/classifications.html) para agrupar las visitas en períodos de tiempo. Por ejemplo, podría configurar una regla del Generador de reglas de clasificación para crear un bloque con las visitas realizadas entre las 9:00 AM y las 9:59 AM en "9:00 AM - 10:00 AM". Como alternativa a las clasificaciones, podría proporcionar lógica adicional de lado del cliente para crear bloques con las visitas en JavaScript.

**Llamada de ejemplo**

```js
var tp = s.getTimeParting('n','-7'); 
s.prop1 = tp;
```

**SECCIÓN DE COMPLEMENTOS**

Agregue el código siguiente a la [!UICONTROL SECCIÓN DE COMPLEMENTOS] en el archivo [!DNL s_code.js].

```js
/* 
 * Plugin: getTimeParting 3.4 
 */ 
s.getTimeParting=new Function("h","z","" 
+"var s=this,od;od=new Date('1/1/2000');if(od.getDay()!=6||od.getMont" 
+"h()!=0){return'Data Not Available';}else{var H,M,D,U,ds,de,tm,da=['" 
+"Sunday','Monday','Tuesday','Wednesday','Thursday','Friday','Saturda" 
+"y'],d=new Date();z=z?z:0;z=parseFloat(z);if(s._tpDST){var dso=s._tp" 
+"DST[d.getFullYear()].split(/,/);ds=new Date(dso[0]+'/'+d.getFullYea" 
+"r());de=new Date(dso[1]+'/'+d.getFullYear());if(h=='n'&&d>ds&&d<de)" 
+"{z=z+1;}else if(h=='s'&&(d>de||d<ds)){z=z+1;}}d=d.getTime()+(d.getT" 
+"imezoneOffset()*60000);d=new Date(d+(3600000*z));H=d.getHours();M=d" 
+".getMinutes();M=(M<10)?'0'+M:M;D=d.getDay();U=' AM';if(H>=12){U=' P" 
+"M';H=H-12;}if(H==0){H=12;}D=da[D];tm=H+':'+M+U;return(tm+'|'+D);}");
```

**Notas**

* Antes de su implementación en la producción, realice pruebas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
* Para que funcionen correctamente, las variables de configuración deben configurarse para el complemento.

