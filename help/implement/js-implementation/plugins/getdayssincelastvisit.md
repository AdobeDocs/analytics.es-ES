---
description: Determina el número de días transcurridos desde la última vez que un usuario visitó el sitio y captura esta información en una variable de Analytics.
keywords: Implementación de Analytics
seo-description: Determina el número de días transcurridos desde la última vez que un usuario visitó el sitio y captura esta información en una variable de Analytics.
seo-title: getDaysSinceLastVisit
solution: Analytics
subtopic: Complementos
title: getDaysSinceLastVisit
topic: Desarrollador e implementación
uuid: cad 95882-3 bd 0-4 f 94-a 0 c 3-4 e 7 b 6058 d 246
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getDaysSinceLastVisit

Determina el número de días transcurridos desde la última vez que un usuario visitó el sitio y captura esta información en una variable de Analytics.

>[!IMPORTANT]
>
>[Analysis Workspace](https://marketing.adobe.com/resources/help/en_US/analytics/analysis-workspace/) incluye ahora un **[!UICONTROL día desde la dimensión de la última visita]** fuera del cuadro, por lo que se nula la necesidad de este complemento.

Los datos de frecuencia de retorno se pueden emplear para responder a las preguntas siguientes:

* ¿Con qué frecuencia regresan a mi sitio los usuarios?
* ¿Cómo se correlaciona la frecuencia de retorno con la conversión? ¿Los compradores habituales realizan visitas frecuentemente o con poca frecuencia?
* ¿Los usuarios que hacen clic en mis campañas regresan frecuentemente?

El complemento también puede generar valores para segmentación. Por ejemplo, puede crear un segmento para ver únicamente todos los datos de aquellas visitas que estuvieron precedidas por 30 días o más en los que el usuario no realizó ninguna visita.

>[!NOTE]
>
>Las instrucciones siguientes requieren modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Implementación y código de complemento {#section_5600DBB819F143D59527A73BD94418DE}

**SECCIÓN CONFIG**

No es necesario realizar ningún cambio.

**Configurar complemento**

Place the following code within the `s_doPlugins()` function, which is located in the area of the [!DNL s_code.js] file labeled *Plugin Config*. Seleccione una variable de tráfico personalizado (término de búsqueda interna s.prop) y/o una variable de conversión personalizada (s.eVar) que se utilizarán en la captura de datos de frecuencia de retorno. Debe seleccionarse una variable que se haya activado mediante Admin Console pero que en la actualidad no se esté utilizando para ningún otro fin. El siguiente es solo un ejemplo y debe actualizarse según sus necesidades.

```js
s.prop1=s.getDaysSinceLastVisit(Cookie_Name);
```

**SECCIÓN DE COMPLEMENTOS**
Agregue el código siguiente al área del archivo [!DNL s_code.js] etiquetado *SECCIÓN DE COMPLEMENTOS*. No realice ningún cambio en esta parte del código de complemento.

```js
/* 
 * Plugin: Days since last Visit 1.1 - capture time from last visit 
 */ 
s.getDaysSinceLastVisit=new Function("c","" 
+"var s=this,e=new Date(),es=new Date(),cval,cval_s,cval_ss,ct=e.getT" 
+"ime(),day=24*60*60*1000,f1,f2,f3,f4,f5;e.setTime(ct+3*365*day);es.s" 
+"etTime(ct+30*60*1000);f0='Cookies Not Supported';f1='First Visit';f" 
+"2='More than 30 days';f3='More than 7 days';f4='Less than 7 days';f" 
+"5='Less than 1 day';cval=s.c_r(c);if(cval.length==0){s.c_w(c,ct,e);" 
+"s.c_w(c+'_s',f1,es);}else{var d=ct-cval;if(d>30*60*1000){if(d>30*da" 
+"y){s.c_w(c,ct,e);s.c_w(c+'_s',f2,es);}else if(d<30*day+1 && d>7*day" 
+"){s.c_w(c,ct,e);s.c_w(c+'_s',f3,es);}else if(d<7*day+1 && d>day){s." 
+"c_w(c,ct,e);s.c_w(c+'_s',f4,es);}else if(d<day+1){s.c_w(c,ct,e);s.c" 
+"_w(c+'_s',f5,es);}}else{s.c_w(c,ct,e);cval_ss=s.c_r(c+'_s');s.c_w(c" 
+"+'_s',cval_ss,es);}}cval_s=s.c_r(c+'_s');if(cval_s.length==0) retur" 
+"n f0;else if(cval_s!=f1&&cval_s!=f2&&cval_s!=f3&&cval_s!=f4&&cval_s" 
+"!=f5) return '';else return cval_s;");
```

**Notas**

* Antes de su implementación en un entorno de desarrollo, realice pruebas exhaustivas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
* El complemento establece las siguientes categorías de usuarios en función de la frecuencia de retorno:

   * Primera visita
   * Menos de 1 día
   * Menos de 7 días
   * Más de 7 días
   * Más de 30 días

* Este complemento depende de las cookies para indicar que un usuario ha realizado visitas previas. Si el explorador no acepta cookies, el complemento devuelve el valor *Cookies no admitidas*.

