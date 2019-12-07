---
description: A la hora de especificar los valores de una variable, hay que seguir algunas prácticas recomendadas.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Uso de comillas
topic: Developer and implementation
uuid: 9f09c48b-7ae5-441e-8635-fd6bdc2e94c7
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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
