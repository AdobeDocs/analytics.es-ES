---
description: Obtiene el tiempo de carga de la página en décimas de segundo y permite almacenar el valor en un evento numérico, una eVar o una prop.
keywords: Implementación de Analytics
seo-description: Obtiene el tiempo de carga de la página en décimas de segundo y permite almacenar el valor en un evento numérico, una eVar o una prop.
seo-title: getLoadTime
solution: Analytics
title: getLoadTime
topic: Desarrollador e implementación
uuid: 5 d 26 a 69 b-cbde -4 be 1-bac 1-5 ee 8 a 4 e 55 ca 3
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getLoadTime

Obtiene el tiempo de carga de la página en décimas de segundo y permite almacenar el valor en un evento numérico, una eVar o una prop.

Para usar este complemento, inserte el código de la función y llame a la función dos veces desde el archivo [!DNL s_code.js]: una al principio del archivo y otra en la sección `doPlugins`. Este complemento no se ha definido como un método del objeto s de forma deliberada. De hacerlo, aumentaría el tiempo de carga calculado de la página.

>[!NOTE]
>
>Las instrucciones siguientes requieren modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Implementación y código de complemento {#section_968AC379C3004C359A85AFED5A48D5AE}

**Adición de la función**

Agregue la siguiente definición de la función `s_getLoadTime` a [!DNL s_code.js], en cualquier ubicación anterior a la sección "DO NOT ALTER ANYTHING BELOW THIS LINE":

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**Realización de la llamada a la función inicial**

Add a call to `s_getLoadTime()` near the beginning of [!DNL s_code.js], outside of any function.

**Realización de la llamada a la función final**

Add another call to `s_getLoadTime()` in the `s_doPlugins()` function, saving the returned value in a prop, eVar, and/or a numeric event.

Ejemplo de uso 1 - Guardar el tiempo de carga de la página en prop10 y eVar20:

```js
s.eVar20=s.prop10=s_getLoadTime();
```

Ejemplo de uso 2 - Guardar el tiempo de carga de la página en el evento numérico event99:

```js
if(s_getLoadTime())s.events=s.apl(s.events,'event90='+s_getLoadTime(),',',1);
```

**(Opcional) Ampliación de la compatibilidad con exploradores más antiguos**

Para que se admitan los exploradores más antiguos que no disponen de la propiedad [window.performance.timing](https://www.html5rocks.com/en/tutorials/webperformance/basics/), incluya la línea siguiente en la sección HEAD del código HTML de la página, en una ubicación próxima al principio, antes de invocar al archivo .js, .css o a cualquier otro:

```
<script type="text/javascript">var inHeadTS=(new Date()).getTime();</script>
```

