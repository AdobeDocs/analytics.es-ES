---
description: A la hora de especificar los valores de una variable, hay que seguir algunas prácticas recomendadas.
keywords: Implementación de Analytics
seo-description: A la hora de especificar los valores de una variable, hay que seguir algunas prácticas recomendadas.
seo-title: Uso de comillas
solution: Analytics
subtopic: Resolución de problemas
title: Uso de comillas
topic: Desarrollador e implementación
uuid: 9 f 09 c 48 b -7 ae 5-441 e -8635-fd 6 bdc 2 e 94 c 7
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Uso de comillas

A la hora de especificar los valores de una variable, hay que seguir algunas prácticas recomendadas.

Puede usar comillas simples o dobles; asegúrese de ser coherente. Si usa comillas simples, use siempre comillas simples. Si usa comillas dobles, use siempre comillas dobles. Los dos ejemplos siguientes son correctos.

```js
s.prop2='test' (single quotes)
```

```js
s.prop2="test" (double quotes)
```

Asegúrese de tener desactivadas las comillas tipográficas. Si está usando comillas simples y tiene un apóstrofo en el valor de la variable, JavaScript lo interpreta como una comilla simple. Esto significa que es el final de la cadena. Consideremos el siguiente ejemplo:

```js
s.pageName='John's Home Page'
```

En este caso, JavaScript interpretaría el apóstrofo (que también es una comilla simple) de "John's" como el final de la cadena. Como "'s Home Page" no tiene significado en JavaScript, provoca un error que impide que se realice la solicitud de imagen. Cualquiera de los siguientes ejemplos funcionaría:

```js
s.pageName='John\'s Home Page'
```

```js
s.pageName="John's Home Page"
```

En el primer ejemplo, puede insertar el carácter de escape de barra invertida (\) inmediatamente antes. Esto indica a JavaScript que el apóstrofo no es el final de la cadena sino parte de ella. La cadena termina como está previsto, en la comilla simple de cierre. El segundo ejemplo usa comillas dobles encerrando toda la cadena. En este caso, una comilla simple no indica el final de la cadena. Lo mismo sucede si una comilla doble forma parte de la cadena. Un valor de s.pageName="Team Says "We Win!"" sería incorrecto debido a que se usan comillas dobles dentro de la cadena y también para encerrarla. Sería correcto si se escribiera como s.pageName="Team Says \"We Win!\"".
