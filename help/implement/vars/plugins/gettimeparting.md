---
title: getTimeParting
description: Mida el tiempo en que sucede una acción específica.
translation-type: tm+mt
source-git-commit: 97778ee83cd44eaf2d14dd3e6891612eb99744a9
workflow-type: tm+mt
source-wordcount: '821'
ht-degree: 83%

---


# Complemento de Adobe: getTimeParting

>[!IMPORTANT]
>
>Adobe Consulting proporciona este complemento por cortesía para ayudarle a sacar el máximo partido a Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica con este complemento, incluida la instalación o solución de problemas. Si necesita ayuda con este complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

El complemento `getTimeParting` le permite registrar en qué momento se produce cualquier actividad que se pueda medir en su sitio web. Este complemento es útil si quiere desglosar métricas para cualquier franja de tiempo que se repita en un intervalo de fechas determinado. Por ejemplo: puede comparar las tasas de conversión entre dos días diferentes de la semana, como los domingos frente a los jueves. También puede comparar periodos del día, como las mañanas frente a las noches.

Analysis Workspace ofrece dimensiones innovadoras similares con un formato ligeramente diferente al de este complemento. Consulte [las dimensiones de partición de tiempo](/help/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.md) en la guía del usuario de Analyze si desea más información. Algunas organizaciones consideran que las innovadoras dimensiones de Analysis Workspace son suficientes.

>[!IMPORTANT]
>
>La versión 4.0 o posterior de este complemento es considerablemente diferente a las versiones anteriores. Adobe recomienda encarecidamente implementar este complemento “desde cero”. El código que hace referencia al complemento en las versiones anteriores a la 4.0 no es compatible con la versión actual de este complemento.

## Instalación del complemento con la extensión de Adobe Experience Platform Launch

Adobe ofrece una extensión que le permite disfrutar de los complementos más utilizados.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Catálogo].
1. Instalación y publicación de la extensión [!UICONTROL Common Analytics Plugins].
1. Si aún no lo ha hecho, cree una regla con la etiqueta “Inicializar complementos” con la siguiente configuración:
   * Condición: Ninguna
   * Evento: Core – Biblioteca cargada (Principio de página)
1. Añada una acción a la regla anterior con la siguiente configuración:
   * Extensión: Common Analytics Plugins
   * Tipo de acción: Inicializar getTimeParting
1. Guarde y publique los cambios en la regla.

## Instalación del complemento con el editor de código personalizado de Launch

Si no desea utilizar la extensión del complemento, puede utilizar el editor de código personalizado.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad deseada.
1. Vaya a la pestaña [!UICONTROL Extensiones] y, a continuación, haga clic en el botón [!UICONTROL Configurar] en la extensión de Adobe Analytics.
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

El método `getTimeParting` utiliza el siguiente argumento:

**`t`** (opcional pero recomendado, cadena): Nombre del huso horario al que convertir la hora local del visitante.  El valor predeterminado es UTC/GMT. Consulte la [lista de husos horarios de la base de datos TZ](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) en Wikipedia para obtener una lista completa de los valores válidos.

Los valores válidos comunes incluyen:

* `"America/New_York"` para la hora del este
* `"America/Chicago"` para la hora central
* `"America/Denver"` para la hora de montaña
* `"America/Los_Angeles"` para la hora del Pacífico

Llamar a este método devuelve una cadena que contiene lo siguiente, delimitado por una barra vertical (`|`):

* El año en curso
* El mes en curso
* El día del mes
* El día de la semana
* La hora (AM/PM)

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

Si el cliente está en el país africano Ghana:

```js
s.eVarX = getTimeParting();
```

Ghana está dentro del huso horario UTC/GMT. Este ejemplo muestra que no es necesario ningún argumento de complemento para UTC/GMT.

### Contabilidad para exploradores de Internet Explorer

Utilice el siguiente ejemplo si desea excluir los datos de partición de tiempo de los visitantes de Internet Explorer. El valor devuelto por los exploradores IE solo se encuentra en la hora local del visitante.

```js
if(!document.documentMode) s.eVarX = getTimeParting("America/New_York");
else s.eVarX = "Internet Explorer Visitors";
```

### Resultados de las llamadas

Considere un escenario en el que un visitante de Denver Colorado visite un sitio el 31 de agosto de 2020 a las 9:15 AM.

```js
s.eVar10 = getTimeParting("Europe/Athens");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 PM"

s.eVar11 = getTimeParting("America/Nome");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=6:15 AM"

s.eVar12 = getTimeParting("Asia/Calcutta");
// Returns the string value "year=2020 | month=August | date=31 | day=Friday | time=8:45 PM"

s.eVar13 = getTimeParting("Australia/Sydney");
// Returns the string value "year=2020 | month=September | date=1 | day=Saturday | time=1:15 AM"
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
>Las versiones anteriores de este complemento no se adaptaron a todos los años en el futuro. Si utiliza una versión anterior de este complemento, Adobe recomienda encarecidamente actualizar a la versión más reciente para evitar errores de JavaScript y pérdida de datos. Si no es posible actualizar este complemento, asegúrese de que la variable `s._tpdst` del código del complemento contenga los años correspondientes en el futuro.

### 4.0 (22 de agosto de 2016)

* Ofrece una solución completamente nueva y ahora incluye información de año, mes y fecha.
