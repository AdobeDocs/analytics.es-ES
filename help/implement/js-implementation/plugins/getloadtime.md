---
description: Obtiene el tiempo de carga de la página en décimas de segundo y permite almacenar el valor en un evento numérico, una eVar o una prop.
keywords: Analytics Implementation
title: getLoadTime
topic: Developer and implementation
uuid: 5d26a69b-cbde-4be1-bac1-5ee8a4e55ca3
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getLoadTime

Obtiene el tiempo de carga de la página en décimas de segundo y permite almacenar el valor en un evento numérico, una eVar o una prop.

Para usar este complemento, inserte el código de la función y llame a la función dos veces desde el archivo [!DNL s_code.js]: una al principio del archivo y otra en la sección `doPlugins`. Este complemento no se ha definido como un método del objeto s de forma deliberada. De hacerlo, aumentaría el tiempo de carga calculado de la página.

> [!NOTE] Las instrucciones siguientes exigen modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Implementación y código de complemento {#section_968AC379C3004C359A85AFED5A48D5AE}

**Adición de la función**

Agregue la siguiente definición de la función `s_getLoadTime` a [!DNL s_code.js], en cualquier ubicación anterior a la sección "DO NOT ALTER ANYTHING BELOW THIS LINE":

```js
function s_getLoadTime(){if(!window.s_loadT){var b=new Date().getTime(),o=window.performance?performance.timing:0,a=o?o.requestStart:window.inHeadTS||0;s_loadT=a?Math.round((b-a)/100):''}return s_loadT}
```

**Realización de la llamada a la función inicial**

Agregue una llamada a `s_getLoadTime()` próxima al principio de [!DNL s_code.js], fuera de cualquier función.

**Realización de la llamada a la función final**

Agregue otra llamada a `s_getLoadTime()` en la función `s_doPlugins()` y guarde el valor devuelto en una prop, una eVar o un evento numérico.

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

