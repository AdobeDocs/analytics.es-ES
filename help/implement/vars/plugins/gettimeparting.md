---
title: getTimeParting
description: Mida el tiempo en que sucede una acción específica.
feature: Appmeasurement Implementation
exl-id: 3fab36c8-a006-405a-9ef1-2547c2b36b0d
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '801'
ht-degree: 77%

---

# Complemento de Adobe: getTimeParting

{{plug-in}}

El complemento `getTimeParting` le permite registrar en qué momento se produce cualquier actividad que se pueda medir en su sitio web. Este complemento es útil si quiere desglosar métricas para cualquier franja de tiempo que se repita en un intervalo de fechas determinado. Por ejemplo: puede comparar las tasas de conversión entre dos días diferentes de la semana, como los domingos frente a los jueves. También puede comparar periodos del día, como las mañanas frente a las noches.

Analysis Workspace ofrece dimensiones innovadoras similares con un formato ligeramente diferente al de este complemento. Consulte [las dimensiones de partición de tiempo](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) en la guía del usuario de Analyze si desea más información. Algunas organizaciones consideran que las innovadoras dimensiones de Analysis Workspace son suficientes.

>[!IMPORTANT]
>
>La versión 4.0 o posterior de este plug-in es considerablemente diferente a las versiones anteriores. Adobe recomienda encarecidamente implementar este complemento “desde cero”. El código que hace referencia al complemento en las versiones anteriores a la 4.0 no es compatible con la versión actual de este complemento.

## Instalación del complemento con la extensión Web SDK

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con Web SDK.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en **[!UICONTROL Etiquetas]** a la izquierda y luego haga clic en la propiedad de etiquetas deseada.
1. Haga clic en **[!UICONTROL Extensiones]** a la izquierda y, a continuación, haga clic en la ficha **[!UICONTROL Catálogo]**
1. Busque e instale la extensión **[!UICONTROL Common Web SDK Plugins]**.
1. Haga clic en **[!UICONTROL Elementos de datos]** a la izquierda y, a continuación, haga clic en el elemento de datos deseado.
1. Establezca el nombre del elemento de datos deseado con la siguiente configuración:
   * Extensión: Common Web SDK Plugins
   * Elemento de datos: `getTimeParting`
1. Establezca el parámetro `Time Zone` a la derecha.
1. Guarde y publique los cambios en el elemento de datos.

## Instalación manual del complemento que implementa Web SDK

Este complemento aún no es compatible con una implementación manual de Web SDK.

## Instalación del complemento con la extensión de Adobe Analytics

Adobe ofrece una extensión que le permite utilizar los complementos más utilizados con Adobe Analytics.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo].
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins].
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar getTimeParting
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de 

Si no desea utilizar la extensión de complemento Common Analytics Plugins, puede utilizar el editor de código personalizado.

1. Inicie sesión en la [Recopilación de datos de Adobe Experience Platform](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón **[!UICONTROL Configurar]** en la extensión de Adobe Analytics.
1. Expanda [!UICONTROL Configurar seguimiento con el código personalizado], que muestra el botón [!UICONTROL Abrir editor].
1. Abra el editor de código personalizado y pegue el código del complemento que se proporciona a continuación en la ventana de edición.
1. Guarde y publique los cambios en la extensión de Analytics.

## Instalación del complemento con AppMeasurement

Copie y pegue el siguiente código en cualquier parte del archivo AppMeasurement después de crear una instancia del objeto de seguimiento de Analytics (con [`s_gi`](../functions/s-gi.md)). Conservar los comentarios y los números de versión del código en la implementación ayuda a Adobe a solucionar cualquier posible problema.

```js
/******************************************* BEGIN CODE TO DEPLOY *******************************************/
/* Adobe Consulting Plugin: getTimeParting v6.3 (No Prerequisites Needed) */
function getTimeParting(t){var c=t;if("-v"===t)return{plugin:"getTimeParting",version:"6.3"};a:{if("undefined"!==typeof window.s_c_il){var a=0;for(var b;a<window.s_c_il.length;a++)if(b=window.s_c_il[a],b._c&&"s_c"===b._c){a=b;break a}}a=void 0}"undefined"!==typeof a&&(a.contextData.getTimeParting="6.3");c=document.documentMode?void 0:c||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:c,minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])};
/******************************************** END CODE TO DEPLOY ********************************************/
```

## Uso del complemento

La función `getTimeParting` utiliza el argumento siguiente:

**`t`** (opcional pero recomendado, cadena): Nombre del huso horario al que convertir la hora local del visitante.  El valor predeterminado es UTC/GMT. Consulte la [lista de husos horarios de la base de datos TZ](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) en Wikipedia para obtener una lista completa de los valores válidos.

Los valores válidos comunes incluyen:

* `"America/New_York"` para la hora del este
* `"America/Chicago"` para la hora central
* `"America/Denver"` para la hora de montaña
* `"America/Los_Angeles"` para la hora del Pacífico

La llamada a esta función hace que devuelva una cadena que contiene lo siguiente delimitado por una barra vertical (`|`):

* El año en curso
* El mes en curso
* El día del mes
* El día de la semana
* La hora (AM/PM)

## Ejemplos

```js
// Use the following code if the visitor resides in Paris, France
s.eVar8 = getTimeParting("Europe/Paris");

// Use the following code if the visitor resides in San Jose, California
s.eVar17 = getTimeParting("America/Los_Angeles");

// Use the following code if the visitor resides in Ghana.
// Note that Ghana is in GMT time, the default time zone that the plug-in uses with no argument
s.eVar22 = getTimeParting();

// Internet Explorer only returns the visitor's local time. Use this conditional statement to accommodate IE visitors
if(!document.documentMode) s.eVar39 = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";

// Given a visitor from Denver Colorado visits a site on August 31, 2020 at 9:15 AM
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"
s.eVar10 = getTimeParting("Europe/Athens");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"
s.eVar11 = getTimeParting("America/Nome");

// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"
s.eVar12 = getTimeParting("Asia/Calcutta");

// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
s.eVar13 = getTimeParting("Australia/Sydney");
```

## Historial de versiones

### 6.3 (19 de marzo de 2021)

* Se ha añadido el número de versión como datos de contexto.

### 6.2 (5 de noviembre de 2019)

* Se han corregido errores menores
* Se ha reducido el tamaño general del código

### 6.1 (26 de noviembre de 2018)

* Se ha corregido para exploradores de Internet Explorer. Pueden devolver la hora, pero solo en la hora local del visitante.

### 6.0 (14 de agosto de 2018)

* Se ha reescrito por completo para que se adapte a los estándares internacionales. Ahora convierte adecuadamente el horario de verano y todos los husos horarios.

### 5.0 (17 de abril de 2018)

* Versión puntual (compilada de nuevo, con un tamaño de código más pequeño)
* Se ha eliminado la necesidad del parámetro `tpDST`, ya que las fechas de inicio y finalización del horario de verano ahora se detectan automáticamente

>[!CAUTION]
>
>Las versiones anteriores de este plug-in no se adaptaron a todos los años en el futuro. Si utiliza una versión anterior de este plug-in, Adobe recomienda encarecidamente actualizar a la versión más reciente para evitar errores de JavaScript y pérdida de datos. Si no es posible actualizar este plug-in, asegúrese de que la variable `s._tpdst` del código del plug-in contenga los años correspondientes en el futuro.

### 4.0 (22 de agosto de 2016)

* Ofrece una solución completamente nueva y ahora incluye información de año, mes y fecha.
