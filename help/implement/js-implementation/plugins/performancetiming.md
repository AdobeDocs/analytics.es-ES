---
description: Este complemento funciona por medio de la API JavaScript de Temporización de navegación para medir el rendimiento en la Web de forma precisa. Esto proporciona un método nativo para obtener estadísticas de temporización precisas y detalladas para eventos de carga de páginas y tiempos de carga de recursos. Anteriormente, las mediciones de este tipo utilizaban el objeto Date de JavaScript para métricas de temporización, o una extrapolación rudimentaria de las métricas de Temporización de navegación. Ambas metodologías, si bien proporcionan datos de tendencias para tiempos de carga de página, no son fiables.
keywords: Implementación de Analytics
seo-description: Este complemento funciona por medio de la API JavaScript de Temporización de navegación para medir el rendimiento en la Web de forma precisa. Esto proporciona un método nativo para obtener estadísticas de temporización precisas y detalladas para eventos de carga de páginas y tiempos de carga de recursos. Anteriormente, las mediciones de este tipo utilizaban el objeto Date de JavaScript para métricas de temporización, o una extrapolación rudimentaria de las métricas de Temporización de navegación. Ambas metodologías, si bien proporcionan datos de tendencias para tiempos de carga de página, no son fiables.
seo-title: performanceTiming
solution: Analytics
title: performanceTiming
topic: Desarrollador e implementación
uuid: ab 2 a 6 c 51-8791-41 e 7-9 bea-c 1 ce 8 d 312 de 8
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# performanceTiming

Este complemento funciona por medio de la API JavaScript de Temporización de navegación para medir el rendimiento en la Web de forma precisa. Esto proporciona un método nativo para obtener estadísticas de temporización precisas y detalladas para eventos de carga de páginas y tiempos de carga de recursos. Anteriormente, las mediciones de este tipo utilizaban el objeto Date de JavaScript para métricas de temporización, o una extrapolación rudimentaria de las métricas de Temporización de navegación. Ambas metodologías, si bien proporcionan datos de tendencias para tiempos de carga de página, no son fiables.

## Qué hace este complemento {#section_4E0771B959FD4F86B4B91BD18CA01DF1}

>[!IMPORTANT]
>
>Es una versión beta del complemento y podrían llegar actualizaciones adicionales.

Este complemento utiliza los siguientes eventos detallados para el seguimiento de los componentes de temporización individuales de una carga de página:

| Evento | Nombre | Calculado a partir de |
|---|---|---|
| 1 | Temporización de redirección | fetchStart - navigationStart |
| 2 | Temporización de caché de aplicación | domainLookupStart - fetchStart |
| 3 | Temporización de DNS | domainLookupEnd - domainLookupStart |
| 4 | Temporización de TCP | connectEnd - connectStart |
| 5 | Temporización de solicitud | responseStart - connectEnd |
| 6 | Temporización de respuesta | responseEnd - responseStart |
| 7 | Temporización de procesamiento | loadEventStart - domLoading |
| 8 | Temporización de onLoad | loadEventEnd - loadEventStart |
| 9 | Tiempo total de carga de la página | loadEventEnd - navigationStart |
| 10 | Instancias de rendimiento | Contador |

El siguiente gráfico ilustra los atributos de temporización definidos por la interfaz de PerformanceTiming y la interfaz de PerformanceNavigation con o sin redirección, respectivamente.

![](assets/timing-attributes.png)

Aquí podrá encontrar los detalles completos sobre el objeto Temporización de navegación:

[https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface](https://www.w3.org/TR/navigation-timing/#sec-navigation-timing-interface)

Además, el complemento puede usar de forma opcional el objeto performanceEntries para registrar los detalles sobre nombre del recurso, inicio de tiempo de carga del recurso y duración de tiempo de carga del recurso para cada recurso individual que se carga en una página dada. Se registra una gran cantidad de información con este complemento, y como tal requiere que el objeto de almacenamiento DOM esté habilitado para almacenar la información de carga de página entre vistas de páginas. Asegúrese de que la política de privacidad de la empresa permita el uso del objeto de almacenamiento DOM antes de habilitar esta funcionalidad. También requiere el uso de una listVar para el seguimiento de todos los recursos.

## Complementos de soporte requeridos {#section_B6447EB6548942EFBC219AEFDC245639}

* appendList
* getPreviousValue

## Implementación y código de complemento {#section_564D77E1CF0E445586D95AD9769CE57D}

>[!NOTE]
>
>Las instrucciones siguientes requieren modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de Adobe Analytics. This plugin is compatible only with [!DNL AppMeasurement] tracking libraries.

**Sección Config (antes de doPlugins):**

`s.pte`: Lista de eventos separada por comas que contiene los 10 eventos que desea usar: los componentes de evento de temporización individuales (eventos 1 a 8), el tiempo total de carga de la página (evento 9) y las instancias de rendimiento totales (evento 10) en ese orden específico.

`s.ptc`: Establezca para determinar si se ejecutará o no el complemento dentro de doPlugins. Siempre se establece como falso.

*Llamadas de muestra*

```
s.pte = 'event10,event11,event12,event13,event14,event15,event16,event17,event18,event19' 
//[--------------------------- 1 to 8 ---------------------------][-- 9 --][- 10 -] 
s.ptc = false; 
```

**Sección doPlugins:**

Para inicializar el complemento, se requiere una línea de código en la sección `doPlugins` del s_code, preferiblemente tras haber designado la variable `s.pageName`. Si desea utilizar la funcionalidad de tiempo de carga de recursos dentro del complemento, debe pasar el nombre de la variable de lista que se usará. De lo contrario, solo se realizará el seguimiento de las entradas de temporización de rendimiento en los eventos especificados previamente en la variable `s.pte`.

>[!NOTE]
>
>In order to correlate performance timing entries with pages on your site, you must also initialize the `getPreviousValue` plug-in. Se recomienda comparar estas entradas de rendimiento con el nombre de página anterior o el valor de dirección URL de página anterior.

*Llamadas de muestra*

```
/* Performance Timing */ 
s.eVar9 = s.getPreviousValue(s.pageName,'gpv_v9','');  //Record the previous page name in the designated eVar of your choice 
s.performanceTiming('list2')  
```

**Sección de complementos:**

Finalmente, agregue el complemento a su implementación JavaScript.

```
/* Plugin: Performance Timing Tracking - 0.11 BETA */ 
s.performanceTiming=new Function("v","" 
+"var s=this;if(v)s.ptv=v;if(typeof performance!='undefined'){if(perf" 
+"ormance.timing.loadEventEnd==0){s.pi=setInterval(function(){s.perfo" 
+"rmanceWrite()},250);}if(!s.ptc||s.linkType=='e'){s.performanceRead(" 
+");}else{s.rfe();s[s.ptv]='';}}"); 
s.performanceWrite=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";try{if(s.c_r('s_ptc')==''&&performance.timing.loadEventEnd>0){try{" 
+"var pt=performance.timing;var pta='';pta=s.performanceCheck(pt.fetc" 
+"hStart,pt.navigationStart);pta+='^^'+s.performanceCheck(pt.domainLo" 
+"okupStart,pt.fetchStart);pta+='^^'+s.performanceCheck(pt.domainLook" 
+"upEnd,pt.domainLookupStart);pta+='^^'+s.performanceCheck(pt.connect" 
+"End,pt.connectStart);pta+='^^'+s.performanceCheck(pt.responseStart," 
+"pt.connectEnd);pta+='^^'+s.performanceCheck(pt.responseEnd,pt.respo" 
+"nseStart);pta+='^^'+s.performanceCheck(pt.loadEventStart,pt.domLoad" 
+"ing);pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.loadEventStart" 
+");pta+='^^'+s.performanceCheck(pt.loadEventEnd,pt.navigationStart);" 
+"s.c_w('s_ptc',pta);if(sessionStorage&&navigator.cookieEnabled&&s.pt" 
+"v!='undefined'){var pe=performance.getEntries();var tempPe='';for(v" 
+"ar i=0;i<pe.length;i++){tempPe+='!';tempPe+=pe[i].name.indexOf('?')" 
+">-1?pe[i].name.split('?')[0]:pe[i].name;tempPe+='|'+(Math.round(pe[" 
+"i].startTime)/1000).toFixed(1)+'|'+(Math.round(pe[i].duration)/1000" 
+").toFixed(1)+'|'+pe[i].initiatorType;}sessionStorage.setItem('s_pec" 
+"',tempPe);}}catch(err){return;}}}catch(err){return;}"); 
s.performanceCheck=new Function("a","b","" 
+"if(a>=0&&b>=0){if((a-b)<60000&&((a-b)>=0)){return((a-b)/1000).toFix" 
+"ed(2);}else{return 600;}}"); 
s.performanceRead=new Function("","" 
+"var s=this;if(performance.timing.loadEventEnd>0)clearInterval(s.pi)" 
+";var cv=s.c_r('s_ptc');if(s.pte){var ela=s.pte.split(',');}if(cv!='" 
+"'){var cva=s.split(cv,'^^');if(cva[1]!=''){for(var x=0;x<(ela.lengt" 
+"h-1);x++){s.events=s.apl(s.events,ela[x]+'='+cva[x],',',2);}}s.even" 
+"ts=s.apl(s.events,ela[ela.length-1],',',2);}s.linkTrackEvents=s.apl" 
+"(s.linkTrackEvents,s.pte,',',2);s.c_w('s_ptc','',0);if(sessionStora" 
+"ge&&navigator.cookieEnabled&&s.ptv!='undefined'){s[s.ptv]=sessionSt" 
+"orage.getItem('s_pec');sessionStorage.setItem('s_pec','',0);}else{s" 
+"[s.ptv]='sessionStorage Unavailable';}s.ptc=true;"); 
/* Remove from Events 0.1 - Performance Specific,  
removes all performance events from s.events once being tracked. */ 
s.rfe=new Function("","" 
+"var s=this;var ea=s.split(s.events,',');var pta=s.split(s.pte,',');" 
+"try{for(x in pta){s.events=s.rfl(s.events,pta[x]);s.contextData['ev" 
+"ents']=s.events;}}catch(e){return;}"); 
/* Plugin Utility - RFL (remove from list) 1.0*/ 
s.rfl=new Function("l","v","d1","d2","ku","" 
+"var s=this,R=new Array(),C='',d1=!d1?',':d1,d2=!d2?',':d2,ku=!ku?0:" 
+"1;if(!l)return'';L=l.split(d1);for(i=0;i<L.length;i++){if(L[i].inde" 
+"xOf(':')>-1){C=L[i].split(':');C[1]=C[0]+':'+C[1];L[i]=C[0];}if(L[i" 
+"].indexOf('=')>-1){C=L[i].split('=');C[1]=C[0]+'='+C[1];L[i]=C[0];}" 
+"if(L[i]!=v&&C)R.push(C[1]);else if(L[i]!=v)R.push(L[i]);else if(L[i" 
+"]==v&&ku){ku=0;if(C)R.push(C[1]);else R.push(L[i]);}C='';}return s." 
+"join(R,{delim:d2})"); 
```

## Notas {#section_131C5D97A0094880AFC3A2BBE0BC9DE4}

* Antes de su implementación en un entorno de desarrollo, realice pruebas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
* Debido a que el complemento pasa datos de rendimiento asociados a la página anterior, no se recopilan datos de la visualización de la página final de la visita.
* Si está realizando el seguimiento de la temporización de recursos, este complemento depende de la capacidad de establecer valores de almacenamiento DOM en el explorador web del usuario. Si el usuario no acepta cookies y tiene deshabilitado el almacenamiento DOM, el complemento no pasará datos a Analytics.
* Un porcentaje muy pequeño de usuarios no pasará datos de temporización de navegación debido a las limitaciones del explorador y la lógica se encuentra dentro del complemento para garantizar que los datos no se desvíen como resultado, particularmente con una pequeña porción de exploradores móviles. No obstante, este complemento se ha probado con éxito en Internet Explorer, Firefox, Chrome, y Safari.
* [!UICONTROL Las métricas calculadas] deben crearse para ayudar a resumir y comprender el comportamiento de los visitantes asociado con estas métricas:

   * Temporización de redirección promedio (Temporización de redirección/Instancias de temporización de rendimiento)
   * Temporización de caché de aplicación promedio (Temporización de caché de aplicación/Instancias de temporización de rendimiento)
   * Temporización de DNS promedio (Temporización de DNS/Instancias de temporización de rendimiento)
   * Temporización de TCP promedio (Temporización de TCP/Instancias de temporización de rendimiento)
   * Temporización de solicitud promedio (Temporización de solicitud/Instancias de temporización de rendimiento)
   * Temporización de respuesta promedio (Temporización de respuesta/Instancias de temporización de rendimiento)
   * Temporización de procesamiento promedio (Temporización de procesamiento/Instancias de temporización de rendimiento)
   * Temporización de onLoad promedio (Temporización de onLoad/Instancias de temporización de rendimiento)
   * Tiempo de carga de la página promedio (Tiempo total de carga de la página/Instancias de temporización de rendimiento)

