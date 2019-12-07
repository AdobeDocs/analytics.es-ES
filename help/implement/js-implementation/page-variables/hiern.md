---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---



# hierN

La variable ]hierarchy[!UICONTROL  determina la ubicación de una página en la jerarquía del sitio.


<!-- 

hierN.xml

 -->

Esta variable resulta muy útil para los sitios que tienen más de tres niveles en la estructura del sitio. Por ejemplo, un sitio de noticias puede tener cuatro niveles en la sección de deportes: deportes, deportes locales, béisbol y Red Sox. Si alguien visita la página de béisbol, tanto deportes como deportes locales y béisbol reflejarán esa visita.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 255 bytes | H1-H5 | Jerarquía | "" |

Hay cinco variables [!UICONTROL hierarchy] disponibles, que deben ser habilitadas por el Servicio de atención al cliente de Adobe. En el momento de habilitar hierarchy, debe decidir un delimitador para la variable y el número de niveles de la jerarquía. Por ejemplo: si el delimitador es una coma, la jerarquía de deportes puede mostrarse de la siguiente manera.

```js
s.hier1="Sports,Local Sports,Baseball"
```

Asegúrese de que ninguno de los nombres de sección contenga un delimitador. Por ejemplo, si una de las secciones se llama "Coach Griffin, Jim", debe elegir un delimitador que no sea una coma. Cada sección de la jerarquía se limita a 255 bytes, mientras que el límite total de la variable es de 255 bytes. Después de elegir un delimitador (en el momento de crear la jerarquía), no se puede cambiar fácilmente.

Póngase en contacto con el Servicio de atención al cliente de Adobe para obtener información sobre cómo cambiar el delimitador para una jerarquía existente. Los delimitadores también pueden consistir en múltiples caracteres, como || o /|\, que es menos probable que aparezcan en una sección de jerarquía.

**Sintaxis y valores posibles** {#section_0739948A68A2420DAB1CBEA3115A5A66}

No inserte un espacio entre los delimitadores. En el siguiente ejemplo de sintaxis, N es un número entre uno y cinco.

```js
s.hierN="Level 1[<delimiter>Level 2[<delimiter>Level 3[...]]]"
```

No use el delimitador excepto para delimitar los niveles de la jerarquía. El delimitador puede ser cualquier carácter o caracteres que elija.

**Ejemplos** {#section_38E0929F88DD45B6ACDF473DF155971D}

```js
s.hier1="Toys|Boys 6+|Legos|Super Block Tub"
```

```js
s.hier4="Sports/Local Sports/Baseball"
```

**Parámetros de configuración** {#section_E823FB3CAD744D2480EBCE2DF9B134CC}

Ninguna

**Problemas, preguntas y consejos** {#section_104E5BD320764BDEA5FA8D13A70C78E3}

* El delimitador no se puede cambiar una vez configurada la jerarquía. Si debe cambiar el delimitador para su jerarquía, comuníquese con el Servicio de Atención al cliente de Adobe.
* El número de niveles no puede cambiarse una vez configurada la jerarquía.

> [!NOTE] Los cambios en las jerarquías pueden conllevar cargos por servicio.

