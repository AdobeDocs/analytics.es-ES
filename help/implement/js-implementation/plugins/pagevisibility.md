---
description: Registra el número de segundos que la página ha sido la ficha activa del explorador y pasa ese valor a una métrica en la siguiente visualización de página.
keywords: Implementación de Analytics
seo-description: Registra el número de segundos que la página ha sido la ficha activa del explorador y pasa ese valor a una métrica en la siguiente visualización de página.
seo-title: getPageVisibility
solution: Analytics
title: getPageVisibility
topic: Desarrollador e implementación
uuid: 3891 e 2 aa-d 5 c 1-4 a 2 b -8522-eb 2 bae 39 ea 2 e
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getPageVisibility

Registra el número de segundos que la página ha sido la ficha activa del explorador y pasa ese valor a una métrica en la siguiente visualización de página.

>[!NOTE]
>
>Es una versión beta del complemento y podrían llegar actualizaciones adicionales.

This plug-in requires [getVisitStart](../../../implement/js-implementation/plugins/getvisitstart.md#concept_1C3CD25A87094A498A1D8A455963FBD8).

Este complemento también registra el número total de segundos que la página estaba en el explorador (tanto en forma de visualización activa como pasiva). Se requiere el uso del complemento getPreviousValue para poder realizar un seguimiento del nombre de página anterior asociado con los eventos de visibilidad de página. Realizar un seguimiento de estos valores le permite obtener un mejor entendimiento del compromiso de los visitantes y seguir de forma más precisa el comportamiento de dichos visitantes en las páginas.

Se requiere el uso del complemento getPreviousValue para poder realizar un seguimiento del nombre de página anterior asociado con los eventos de visibilidad de página. Realizar un seguimiento de estos valores le permite obtener un mejor entendimiento del compromiso de los visitantes y seguir de forma más precisa el comportamiento de dichos visitantes en las páginas.

>[!NOTE]
>
>Las instrucciones siguientes requieren modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de Analytics. This plug-in is compatible only with [!DNL AppMeasurement] tracking libraries.

## Complementos de soporte requeridos {#section_0CA7624F4A7B4B5F851A4300937887AD}

* appendList
* getPreviousValue
* getVisitStart

## Implementación y código de complemento {#section_543ABD8B3E6A48A5AFD86CFEDE144696}

**Sección config**

La variable `s.pvel` debería contener los tres eventos que desee utilizar.

| Evento | Definición |
|---|---|
| Total de segundos de visibilidad de la página (numérico) | La cantidad total de tiempo que la página ha estado activa en el explorador |
| Total de segundos de la página (numérico) | La cantidad de tiempo que la página ha estado cargada en el explorador, sin importar su estado de visibilidad |
| Total de instancias de visibilidad de la página (contador) | El número total de veces que se ha registrado un valor para los dos eventos anteriores |

**Llamadas de muestra**

```
//Page Visibility Event List (total page visibility seconds, total page seconds, total page visibility instances) 
s.pvel='event7,event8,event9' 
```

**Sección doPlugins**

Para inicializar el complemento, se requieren dos líneas de código en la sección `doPlugins` del s_code, preferiblemente tras haber designado la variable `s.pageName`.

**Llamadas de muestra**

```
/* Page Visibility */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.getPageVisibility(); 
```

**Sección complementos**

```
/* Page Visibility Plugin 0.1 (BETA) */ 
s.getPageVisibility=new Function("","" 
+"var s=this;if(s.getVisitStart()){s.Util.cookieWrite('s_pvs','');s.U" 
+"til.cookieWrite('s_tps','');}if(s.Util.cookieRead('s_pvs')&&s.pvt<1" 
+"){if(parseInt(s.Util.cookieRead('s_pvs'))<=parseInt(s.Util.cookieRe" 
+"ad('s_tps'))){s.pve=s.pvel.split(',');s.events=s.apl(s.events,s.pve" 
+"[0]+'='+(parseInt(s.Util.cookieRead('s_pvs'))),',',2);s.Util.cookie" 
+"Write('s_pvs','');s.events=s.apl(s.events,s.pve[1]+'='+(parseInt(s." 
+"Util.cookieRead('s_tps'))),',',2);s.Util.cookieWrite('s_tps','');s." 
+"events=s.apl(s.events,s.pve[2],',',2);}}s.pvi=setInterval(s.pvx,100" 
+"0);s.wpvi=setInterval(s.wpvc,5000);"); 
s.gbp=new Function("","" 
+"if('hidden'in document){return null;}var bp=['moz','ms','o','webkit" 
+"'];for(var i=0;i<bp.length;i++){var p=bp[i]+'Hidden';if(p in docume" 
+"nt){return bp[i];}}return null;"); 
s.hp=new Function("p","" 
+"if(p){return p+'Hidden';}else{return'hidden';}"); 
s.vs=new Function("p","" 
+"if(p){return p+'VisibilityState';}else{return'visibilityState';}"); 
s.ve=new Function("p","" 
+"if(p){return p+'visibilitychange';}else{return'visibilitychange';}"); 
s.pvx=new Function("","" 
+"s.pvt+=1;"); 
s.wpvc = function(){var tempDate = Date.now();s.Util.cookieWrite('s_tps', 
Math.ceil((tempDate - s.totalTime)/1000));s.Util.cookieWrite('s_pvs', s.pvt)} 
document.addEventListener('visibilitychange',function(event){if(document.hidden){s.visibility = false;clearTimeout(s.pvi);}else{s.visibility=true;s.pvi=setInterval(s.pvx,1000);}});s.totalTime=new Date();s.pvt=0;s.prefix=s.gbp;s.hidden=s.hp(s.prefix);s.visibility=true;s.visibilityState=s.vs(s.prefix);s.visibilityEvent=s.ve(s.prefix); 
```

## Notas {#section_47964BB9D0A24BFEB4B2498A41D8B017}

* Antes de su implementación en un entorno de desarrollo, realice pruebas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
* Debido a que el complemento pasa los segundos de visibilidad de la página y el total de segundos asociados a la página anterior, no se recopilan datos de la visualización de la página final de la visita.
* Este complemento depende de la capacidad de establecer cookies en el explorador web del usuario. Si el usuario no acepta cookies de origen, el complemento no pasará datos a Analytics.
* The plug-in creates its own first-party cookies named `s_tps` and `s_pvs`.

* Un porcentaje muy pequeño de usuarios no pasará un porcentaje de datos de página visualizada debido a las limitaciones del explorador y el complemento contiene lógica para asegurarse de que, como resultado, los datos no se desvíen. No obstante, este complemento se ha probado con éxito en Internet Explorer, Firefox, Chrome, y Safari.
* Debido al modo que tiene el complemento de medir el total de segundos y asociar dicho valor con el nombre de página anterior, habrá diferencias entre el tiempo predeterminado transcurrido en las métricas de página y las métricas de segundos totales.
* [!UICONTROL Se pueden crear métricas] calculadas para ayudar a resumir y comprender el comportamiento de los visitantes asociado con estas métricas:

   * ** Tasa de visibilidad de página** (Total de segundos de visibilidad de la página/Total de segundos de la página)
   * ** Total de segundos ocultos** (Total de segundos de la página - Total de segundos de visibilidad de la página)
   * ** Promedio de segundos de visibilidad de la página** (Total de segundos de visibilidad de la página/Total de instancias de visibilidad de la página)
   * **Media de segundos de página oculta** ((Total de segundos de la página - Total de segundos de visibilidad de la página)/Total de instancias de visibilidad de la página)

* Debido al modo que tiene el complemento de redondear los segundos, podría haber una diferencia de entre 1 y 2 segundos entre el total de segundos de visibilidad de la página y los segundos totales, siendo estos últimos un valor mayor. (Se resolverá en una actualización futura)
* El uso del complemento getVisitStart debería tener en cuenta los visitantes que inician una nueva visita tras un periodo superior a 30 minutos de inactividad. Este aspecto no funciona como fue diseñado; no obstante, es probable que haya una solución cuando incorporemos el "total de segundos en activo" en una futura iteración del complemento.

## Preguntas más frecuentes {#section_1ED9391D3BAA4208817F0DF69ABBB25E}

**¿Realizará este complemento llamadas al servidor adicionales? **

El complemento solo registrará valores de visibilidad de la página en las llamadas al servidor de las visualizaciones de páginas siguientes. No se utilizarán llamadas adicionales al servidor en conjunción.

** Si no deseo capturar el total de segundos de la página o de instancias de visibilidad de página totales,¿puedo excluirlos de la lista de eventos? **

Sí, el total de segundos de página y el total de instancias de visibilidad son eventos opcionales y pueden excluirse de la lista si así lo desea.

**¿Tendrán sentido los eventos capturados si los utilizo en informes que no sean el Nombre de página anterior? **

Teniendo en cuenta que el complemento registra valores en las solicitudes de imagen siguiente, solo se podrán aplicar otras eVars que se hayan capturado en el contexto de "página anterior", por ejemplo "URL de página anterior".

**¿Enviará el complemento el tiempo de visibilidad en una llamada s.tl() o solo en una llamada s.t()?**

El tiempo de visibilidad solo se registra con las llamadas s.t().
