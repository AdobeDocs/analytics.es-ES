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


# canal

La variable se utiliza generalmente para identificar una sección del sitio.


<!-- 

channel.xml

 -->

Por ejemplo: un comerciante puede tener secciones como Electrónica, Juguetes o Ropa. Un sitio de medios puede tener secciones como Noticias, Deportes o Negocios.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | CH | Contenido del sitio &gt; Secciones del sitio | "" |

Adobe recomienda rellenar la variable channel en cada página. También puede activar una correlación entre las variables *`channel`* y [!UICONTROL pageName].

Cuando las secciones tienen uno o más niveles de subsecciones, es posible mostrar dichas secciones en la variable *`channel`* o utilizar variables separadas para identificar niveles.

**Sintaxis y valores posibles**

```js
s.channel="value"
```

La variable *`channel`* no tiene limitaciones adicionales en sus valores.

**Ejemplos** {#section_2527B2BB1CFD46CB952178ABF7A9028A}

```js
s.channel="Electronics"
```

```js
s.channel="Media"
```

**Problemas, preguntas y consejos** {#section_61941D5E4E644B59A267A4F44FD5DE8C}

Si el sitio contiene varios niveles, utilice *`hierarchy`* u otra variable para designarlos. El valor *`channel`* no persiste, pero los eventos de éxito activados en la misma página se atribuyen al valor de *`channel`*.
