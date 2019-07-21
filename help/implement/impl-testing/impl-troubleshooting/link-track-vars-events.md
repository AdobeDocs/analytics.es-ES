---
description: La clave para una implementación correcta del seguimiento de vínculos es comprender las variables s.linkTrackVars y s.linkTrackEvents. Esto permite pasar valores de variable personalizados en acciones del usuario.
keywords: Implementación de Analytics
seo-description: La clave para una implementación correcta del seguimiento de vínculos es comprender las variables s.linkTrackVars y s.linkTrackEvents. Esto permite pasar valores de variable personalizados en acciones del usuario.
seo-title: Uso de s.linkTrackVars y s.linkTrackEvents
solution: Analytics
title: Uso de s.linkTrackVars y s.linkTrackEvents
topic: Desarrollador e implementación
uuid: f 6 b 7019 b -987 b -4 b 7 d-a 446-80205 f 7 cc 36 c
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Uso de s.linkTrackVars y s.linkTrackEvents

La clave para una implementación correcta del seguimiento de vínculos es comprender las variables s.linkTrackVars y s.linkTrackEvents. Esto permite pasar valores de variable personalizados en acciones del usuario.

Si va a implementar el seguimiento de vínculos personalizados y configura variables [!UICONTROL personalizadas] y *`events`*, asegúrese de que la variable [!UICONTROL s. linktrackvars] contiene una lista separada por comas de todas las variables que está pasando, incluida *`events`* la variable. Asegúrese de que [!UICONTROL s.linkTrackEvents] incluye una lista separada por comas de todos los eventos que vaya a pasar.

Configurar [!UICONTROL s.linkTrackVars] y [!UICONTROL s.linkTrackEvents] no configura realmente estas variables y eventos, solo prepara el código de [!DNL Analytics] para hacerlo. Aún necesita configurar las variables manualmente, como se muestra en el siguiente ejemplo:

```js
<script language="javascript"> 
function customLinks () { 
 var s=s_gi('myreportsuite'); 
 s.linkTrackVars="prop1,eVar7,products,events"; 
 s.linkTrackEvents="event5,event9"; 
 s.prop1="Link Click"; 
 s.eVar7="my_page.html"; 
 s.events="event5"; 
 s.tl(true,'o','Custom Link Click'); 
} 
</script> 
<a href="my_page.html" onclick="customLinks();">My Page</a> 
```

Observe que events está incluida en la variable [!UICONTROL s.linkTrackVars]. Los eventos individuales que se puedan pasar se incluyen en la variable [!UICONTROL s.linkTrackEvents] y también se incluirán en [!UICONTROL s.events] más adelante en la función. Todas las variables que se pasan están incluidas en [!UICONTROL s.linkTrackVars] antes de que se rellenen más adelante en la función. Asimismo, se ha incluido "event9″ en [!UICONTROL s.linkTrackEvents] pero no en [!UICONTROL s.events]. No se registra, pero podría registrarse si el usuario hubiera elegido configurar s.events="event5,event9".

El seguimiento automático de descargas de archivos y de vínculos de [!UICONTROL salida] funcionan de forma diferente. [!UICONTROL s.linkTrackVars] y [!UICONTROL s.linkTrackEvents] están incluidas en el archivo [!DNL s_code.js] estándar, y ambas están configuradas como "none". Por lo general, estas variables se dejan configuradas como "none" en el archivo [!DNL s_code.js] para que el seguimiento de vínculos automático, a diferencia del [!UICONTROL seguimiento de vínculos personalizado], use los valores de [!UICONTROL s.linkTrackVars] y [!UICONTROL s.linkTrackEvents] que configure en el archivo JavaScript global. También pasan los valores existentes de esas variables siempre que se registra una descarga de archivo o un vínculo de [!UICONTROL salida].

Tomemos un ejemplo donde s.channel="Home" cuando la página se carga y donde s.linkTrackVars="channel" en el archivo [!DNL s_code.js]. Si un usuario hace clic para descargar un archivo, el seguimiento automático de descargas de archivos pasa datos a [!DNL Analytics], incluido el valor de [!UICONTROL s.channel] configurado al cargar la página. "Home" se pasa una segunda vez, lo que provoca el aumento de los datos de vistas de página para este valor en el informe [!UICONTROL Secciones del sitio].

Adobe recomienda dejar [!UICONTROL s.linkTrackVars] y [!UICONTROL s.linkTrackEvents] como "none" en el archivo JavaScript global y configurarlas explícitamente según sea necesario con su implementación del [!UICONTROL seguimiento de vínculos personalizados].
