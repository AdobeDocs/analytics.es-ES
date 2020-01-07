---
description: El complemento getTimeParting rellena variables personalizadas con los valores de hora del día, día de la semana y fin de semana y día laborable. Analysis Workspace incluye dimensiones de división del tiempo. Debe utilizarse el complemento si se necesitan las dimensiones de división del tiempo en otras soluciones de Analytics fuera de Analysis Workspace.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getTimeParting
topic: Developer and implementation
uuid: 74f696a3-7169-4560-89b2-478b3d8385e1
translation-type: tm+mt
source-git-commit: 73d20b23e38bc619c156c418c95096a94d2fdfce

---


# getTimeParting

El complemento getTimeParting proporciona una solución de análisis completa que le permite capturar los detalles del tiempo en que se produce cualquier actividad medible en el sitio.

Debe utilizar el complemento getTimeParting si desea desglosar las métricas por cualquier división de tiempo repetible en un intervalo de fechas determinado.  Por ejemplo: el complemento getTimeParting le permitirá comparar tasas de conversión entre dos días diferentes de la semana (por ejemplo: todos los domingos vs. todos los jueves), dos períodos diferentes del día (por ejemplo: todas las mañanas vs. todas las noches) o incluso dos minutos subsiguientes (por ejemplo: todas las instancias de 10:00 AM vs. todas las instancias de intervalo de 10:01 AM) para la fecha especifique en el informe.

[!DNL Analysis Workspace] proporciona dimensiones similares listas para usar con formato que tienen un formato ligeramente diferente al que proporciona este complemento (consulte [aquí](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/dimensions/time-parting-dimensions.html)).  Adobe Consulting recomienda leer el resto de esta sección de ayuda para determinar si este complemento proporciona datos de una manera que se adapte mejor a sus necesidades.

Si no necesita desglosar las métricas por una división de tiempo repetible en un intervalo de fechas específico, no necesitará utilizar el complemento getTimeParting.  Además, si encuentra que las dimensiones de partición de tiempo [!DNL Analysis Workspace] son suficientes, no necesitará implementar este complemento.

>[!CAUTION] La solución que ofrece la versión 4.0 o posterior del complemento getTimeParting es muy diferente a la que ofrecían las versiones anteriores del complemento.  Si decide actualizar desde una versión anterior a la 4.0, debe implementar la solución &quot;desde cero&quot;.  En otras palabras, debe configurar una eVar completamente nueva - una eVar - para guardar los datos proporcionados por el complemento y leer esta documentación cuidadosamente antes de implementar la solución.

>[!CAUTION] También: Esta versión del complemento no es *totalmente* compatible con los exploradores de Microsoft Internet Explorer, aunque el complemento es totalmente compatible con los exploradores de Microsoft Edge.   Los visitantes que utilicen Internet Explorer podrán proporcionar la hora pero solo en su zona horaria *local* en lugar de convertirse al huso horario que especifique.  Consulte los ejemplos siguientes para obtener una solución que no incluya datos de los exploradores de Internet Explorer pero que tenga en cuenta su presencia.

> [!NOTE] Las instrucciones siguientes exigen modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

> [!WARNING] Pruebe siempre todas las implementaciones de complementos antes de implementarlas en producción para asegurarse de que la recopilación de datos funciona correctamente.

## Requisitos previos

Ninguna

## Cómo implementar

* Copie y pegue el siguiente código en cualquier lugar de la sección Complementos del código de AppMeasurement:

```function getTimeParting(a){a=document.documentMode?void 0:a||"Etc/GMT";a=(new Date).toLocaleDateString("en-US",{timeZone:a, minute:"numeric",hour:"numeric",weekday:"long",day:"numeric",year:"numeric",month:"long"});a=/([a-zA-Z]+).*?([a-zA-Z]+).*?([0-9]+).*?([0-9]+)(.*?)([0-9])(.*)/.exec(a);return"year="+a[4]+" | month="+a[2]+" | date="+a[3]+" | day="+a[1]+" | time="+(a[6]+a[7])}```

> [!NOTE] También puede utilizar un administrador de etiquetas como Adobe Launch para implementar el código del complemento sin necesidad de adjuntarlo a AppMeasurement o a cualquier otra solución de análisis

* Ejecute la función getTimeParting como se describe a continuación dentro de la función doPlugins o en cualquier otra ubicación donde necesite capturar los datos de partición de tiempo

**Argumentos para pasar**

* t: (Cadena **OPCIONAL pero recomendada**) El nombre del huso horario al que se va a convertir la hora local del visitante.  El valor predeterminado es &quot;Etc/GMT&quot; o UTC/GMT cuando no está establecido.  Visite [https://en.wikipedia.org/wiki/List_of_tz_database_time_zones] para obtener la lista completa de valores que desea introducir.

Los valores comunes incluyen:

* &quot;América/Nueva York&quot; para la Hora del Este
* &quot;América/Chicago&quot; para el tiempo central
* &quot;América/Denver&quot; para los tiempos de montaña
* &quot;América/Los Ángeles&quot; para la hora del Pacífico

## Devuelve

El complemento getTimeParting devuelve una cadena que contiene lo siguiente:

* El año actual
* El mes actual
* Fecha actual (es decir, día del mes)
* Día actual (es decir, día de la semana)
* La hora actual (tiempo no militar)

Cada uno de los elementos anteriores está delimitado por un carácter de barra vertical (&quot;|&quot;).

## Llamadas de ejemplo

Utilice el siguiente código si se encuentra en París, Francia y desea utilizar eVar10 (en Adobe Analytics) para capturar los datos de partición de tiempo:

```s.eVar10 = getTimeParting("Europe/Paris")```

Utilice el siguiente código si se encuentra en San José, California:

```s.eVar10 = getTimeParting("America/Los_Angeles")```

Utilice el siguiente código si se encuentra en el país africano de Ghana:

```s.eVar10 = getTimeParting();```

Ghana está dentro del huso horario UTC/GMT.  Por lo tanto, este ejemplo muestra que en tales circunstancias no será necesario ningún argumento de complemento.

Utilice el siguiente código si se encuentra en Nueva York y no desea incluir datos de los visitantes de Internet Explorer (ya que los valores devueltos por los exploradores IE solo se pueden proporcionar en la hora local del visitante)

```if(!document.documentMode) s.eVar10 = getTimeParting("America/New_York");```
```else s.eVar10 = "Internet Explorer Visitors";```

**Resultados de llamadas**

Si un visitante de Denver, Colorado visita un sitio el 31 de agosto de 2020 a las 9:15 AM, el siguiente código...

```s.eVar10 = getTimeParting("Europe/Athens");```

...establecería s.eVar10 igual a **year=2020| month=August| date=31| day=Monday| time=6:15 PM**

El siguiente código...

```s.eVar10 = getTimeParting("America/Nome");```

... en su lugar, establecería s.eVar10 igual a **year=2020| month=August| date=31| day=Monday| time=6:15 AM**

El siguiente código...

```s.eVar10 = getTimeParting("Asia/Calcutta");```

... en su lugar, establecería s.eVar10 igual a **year=2020| month=August| date=31| day=Monday| time=8:45 PM**

El siguiente código...

```s.eVar10 = getTimeParting("Australia/Sydney");```

... en su lugar, establecería s.eVar10 igual a **year=2020| month=September| date=1| day=Martes| time=1:15 AM**

## Configuración de Adobe Analytics

Si desea capturar los datos de partición de tiempo en Adobe Analytics, configure una nueva eVar con las siguientes características:

* Nombre: Partición de tiempo
* Asignación: Más reciente (última)
* Caduca después de: Visita
* Todos los demás atributos utilizan los valores predeterminados proporcionados
