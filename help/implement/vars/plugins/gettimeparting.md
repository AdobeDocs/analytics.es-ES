---
title: getTimeParting
description: Mida el tiempo en que se produce una acción específica.
translation-type: tm+mt
source-git-commit: 468f97ee61f5d573d07475836df8d2c313b29fb3

---


# Complemento de Adobe: getTimeParting

> [!IMPORTANT] Este complemento lo proporciona Adobe Consulting por cortesía para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

El `getTimeParting` complemento le permite capturar los detalles del momento en que se produce cualquier actividad medible en el sitio. Este complemento es valioso cuando desea desglosar métricas por cualquier división de tiempo repetible en un intervalo de fechas determinado. Por ejemplo: puede comparar las tasas de conversión entre dos días diferentes de la semana, como todos los domingos vs. todos los jueves. También puede comparar períodos del día, como todas las mañanas vs. todas las noches.

Analysis Workspace proporciona dimensiones similares listas para usar con un formato ligeramente diferente al de este complemento. Consulte las dimensiones [de partición de](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) tiempo en la guía del usuario de Análisis para obtener más información. Algunas organizaciones consideran que las dimensiones integradas de Analysis Workspace son suficientes.

> [La versión 4.0 o posterior IMPORTANTE] de este complemento es considerablemente diferente a la versión anterior. Adobe recomienda encarecidamente implementar este complemento &quot;desde cero&quot;. El código que hace referencia al complemento antes de la versión 4.0 no es compatible con la versión actual de este complemento.

## Instalación del complemento con la extensión Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad que desee.
1. Vaya a la ficha [!UICONTROL Extensions] y haga clic en el [!UICONTROL Catalog]
1. Instalación y publicación de la [!UICONTROL Common Analytics Plugins] extensión
1. Si aún no lo ha hecho, cree una regla con la etiqueta &quot;Inicializar complementos&quot; con la siguiente configuración:
   * Condición: Ninguno
   * Evento: Core - Biblioteca cargada (Principio de página)
1. Agregue una acción a la regla anterior con la siguiente configuración:
   * Extensión: Complementos comunes de Analytics
   * Tipo de acción: Inicializar getTimeParting
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado Iniciar

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
1. Haga clic en la propiedad deseada.
1. Vaya a la [!UICONTROL Extensions] ficha y, a continuación, haga clic en el [!UICONTROL Configure] botón situado debajo de la extensión de Adobe Analytics.
1. Expanda el [!UICONTROL Configure tracking using custom code] acordeón, que muestra el [!UICONTROL Open Editor] botón.
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento mediante AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (mediante [`s_gi`](../functions/s-gi.md)). La conservación de los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier problema potencial.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.2 */
var getTimeParting=function(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Utilizar el complemento

El `getTimeParting` método utiliza el siguiente argumento:

**`t`** (Opcional pero recomendada, cadena): Nombre del huso horario al que convertir la hora local del visitante.  El valor predeterminado es UTC/GMT. Consulte [Lista de husos horarios](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) de la base de datos TZ en Wikipedia para obtener una lista completa de los valores válidos.

Los valores válidos comunes incluyen:

* `"America/New_York"` para hora del este
* `"America/Chicago"` para hora central
* `"America/Denver"` para el tiempo de montaña
* `"America/Los_Angeles"` por hora del Pacífico

Al llamar a este método se devuelve una cadena que contiene lo siguiente delimitado por una barra vertical (`|`):

* El año actual
* El mes actual
* El día del mes
* El día de la semana
* Hora actual (AM/PM)

## Llamadas de ejemplo

### Ejemplos de zonas horarias específicas

Utilice el siguiente código de muestra si el cliente está en París, Francia:

```js
s.eVarX = getTimeParting("Europe/Paris");
```

Si el cliente está en San José, California:

```js
s.eVarX = getTimeParting("America/Los_Angeles");
```

Si el cliente está en Ghana:

```js
s.eVarX = getTimeParting();
```

Ghana está dentro del huso horario UTC/GMT.  Este ejemplo muestra que en tales circunstancias no será necesario ningún argumento de complemento.

### Contabilidad de exploradores de Internet Explorer

Utilice el siguiente ejemplo si desea excluir los datos de partición de tiempo de los visitantes de Internet Explorer (ya que el valor devuelto por los exploradores IE solo puede estar en la hora local del visitante)

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Resultados de las llamadas

Si un visitante de Denver, Colorado visita un sitio el 31 de agosto de 2020 a las 9:15 AM,

Ejecutando el siguiente código...

```js
s.eVar10 = getTimeParting("Europe/Athens");
```

...configuraría s.eVar10 igual a &quot;year=2020| month=August| date=31| day=Friday| time=6:15 PM&quot;

Mientras que el siguiente código...

```js
s.eVar10 = getTimeParting("America/Nome");
```

...configuraría s.eVar10 igual a &quot;year=2020| month=August| date=31| day=Friday| time=6:15 AM&quot;

El siguiente código...

```js
s.eVar10 = getTimeParting("Asia/Calcutta");
```

...configuraría s.eVar10 igual a &quot;year=2020| month=August| date=31| day=Friday| time=8:45 PM&quot;

Y el siguiente código...

```js
s.eVar10 = getTimeParting("Australia/Sydney");
```

...configuraría s.eVar10 igual a &quot;year=2020| month=September| date=1| day=Saturday| time=1:15 AM&quot;

## Historial de versiones

### 6.2 (5 de noviembre de 2019)

* Corrección de errores pequeños
* Reducción del tamaño general del código

### 6.1 (26 de noviembre de 2018)

* Corrección para exploradores de Internet Explorer. Pueden devolver la hora, pero solo en la hora local del visitante.

### 6.0 (14 de agosto de 2018)

* Reescritura completa para adaptarse a los estándares internacionales. Ahora convierte adecuadamente el ahorro de luz del día y todos los husos horarios.

### 5.0 (17 de abril de 2018)

* Versión puntual (recompilada, tamaño de código más pequeño)
* Se ha eliminado la necesidad del `tpDST` parámetro, ya que las fechas de inicio y finalización del horario de verano ahora se detectan automáticamente

### 4.0 (22 de agosto de 2016)

* Proporciona una solución completamente nueva y ahora incluye información de año, mes y fecha.
