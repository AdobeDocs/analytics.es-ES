---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
solution: Analytics
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 47291fb3d55ab3eb5ef181770bf2078c7ea55bc4

---


# referrer

La variable puede utilizarse para restablecer la información perdida del referente.


<!-- 

referrer.xml

 -->

Las redirecciones de JavaScript y del lado del servidor generalmente se utilizan para enrutar a los visitantes hacia las ubicaciones correctas. Sin embargo, cuando se redirecciona un explorador, la dirección URL de referencia original se pierde.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 255 bytes | R | Tráfico &gt; Conversión &gt; Métodos de búsqueda | document.referrer |

Muchas empresas usan redirecciones en numerosos lugares de sus sitios web. Por ejemplo, se puede enviar a un visitante a través de una redirección desde un resultado de búsqueda de pago del motor de búsqueda. Cuando se redirecciona un explorador, generalmente el referente se pierde. La variable La variable *`referrer`* se puede utilizar para restaurar el valor original de *`referrer`* en la primera página después de una redirección. La variable *`referrer`* puede rellenarse desde el servidor o por medio de JavaScript desde la cadena de consulta.

Para que Analytics registre un referente, debe estar "bien formado", lo que significa que debe seguir el formato URL estándar, con un protocolo y una ubicación apropiados.

**Sintaxis y valores posibles** {#section_A0365D76789C4F4A959E81FE5A9D491D}

```js
s.referrer="URL"
```

Solamente debe haber valores compatibles con URL en *`referrer`*. Asegúrese de que la cadena tenga codificación URL (sin espacios).

**Ejemplos** {#section_86FB1577670C4AA18BF3718F0832FCD4}

```js
s.referrer="https://www.google.com/search?q=search+string" 
s.referrer=<%=referrerVar%> // populated server-side  
if(s.getQueryParam('ref') 
s.referrer=s.getQueryParam('ref') 
```

**Parámetros de configuración** {#section_7AAEF28A7CBC446984F32C0659EFBF8D}

Ninguna

**Problemas, preguntas y consejos** {#section_B42BF7FBA1094FF9805707FEA810CFE1}

La variable *`referrer`* debe parecer una dirección URL estándar e incluir un protocolo.
