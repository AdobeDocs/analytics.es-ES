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


# visitorNamespace

La variable se usa para identificar el dominio con el que se configuran las cookies.


<!-- 

visitorNamespace.xml

 -->

Si *`visitorNamespace`* se usa en el archivo JavaScript, no la elimine ni la modifique. Si *`visitorNamespace`* cambia, es probable que todos los visitantes notificados a Analytics se conviertan en nuevos visitantes. El historial de visitantes se desconecta del tráfico actual y futuro. No modifique esta variable sin la autorización de un representante de Adobe.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| N.D. | ns | N.D. | "" |

Analytics utiliza una cookie para identificar de manera única a los visitantes del sitio. Si *`visitorNamespace`* no se utiliza, la cookie se asocia con 2o7.net. Si se utiliza *`visitorNamespace`*, la cookie se asocia con un subdominio de 2o7.net. Todos los visitantes del sitio deberán tener las cookies asociadas con el mismo dominio o subdominio.

El motivo para usar la variable *`visitorNamespace`* es evitar la posibilidad de sobrecargar el límite de cookies de un explorador. Internet Explorer impone un límite de 20 cookies por dominio. Usando la variable *`visitorNamespace`*, las cookies de Analytics de otras empresas no entrarán en conflicto con las cookies del visitante.

**Sintaxis y valores posibles** {#section_EE247FE371784CA4B6058182181F3EA1}

El valor de *`visitorNamespace`* debe proporcionarlo Adobe y es una cadena de caracteres ASCII que no contienen comas, puntos, espacios o caracteres especiales.

```js
s.visitorNamespace="company_specific_value"
```

**Identificación de visitante en grupos de informes** {#section_7AC5A97FC8C045DD8850245A62BB09F4}

Si no especifica un `visitorNamespace`, cada grupo de informes en su empresa recibe su propia cookie de ID de visitante como `s_vi_[random string]`. Si especifica `visitorNamespace`, se utilizará la misma cookie `s_vi` para todos los grupos de informes que envían datos al `trackingServer` especificado. Si ha implementado etiquetado de grupos múltiples, asegúrese de especificar el espacio de nombres del visitante de modo que cada grupo de informes utilice la misma cookie.

**Ejemplos** {#section_89A95852AB9446E794AD3283B8800B09}

```js
s.visitorNamespace="company_name"
```

```js
s.visitorNamespace="Adobe"
```

**Parámetros de configuración** {#section_1128A2531ECC43DFA6749ECC21F050A2}

Ninguna
