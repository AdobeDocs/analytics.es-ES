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


# purchaseID

se usa para evitar que un pedido se cuente varias veces en los informes.


<!-- 

purchaseID.xml

 -->

Siempre que se use el evento [!UICONTROL purchase] en el sitio, se debe usar la variable *`purchaseID`*.

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 20 bytes | purchaseID | Conversión &gt; Compras &gt; Conversión de ingresos | "" |

Cuando un visitante compra un artículo en su sitio, *`purchaseID`* se rellena en la página "Gracias" en el mismo lugar donde se activa el evento [!UICONTROL purchase]. Si *`purchaseID`* se rellena, los productos de la página “Gracias” se contabilizan solo una vez por *`purchaseID`*. Esto resulta crítico porque muchos visitantes del sitio guardarán las páginas "Gracias" o "Página de confirmación" para sus propios fines. La variable *`purchaseID`* evita que las compras se contabilicen cada vez que se visita la página.

Además de evitar que los datos de la compra se cuenten dos veces, el *`purchaseID`*, cuando se utiliza, evita que los datos de conversión se cuenten dos veces en los informes.

**Sintaxis y valores posibles** {#section_E352CE2370D54BA69A368E1F63A9C32D}

```js
s.purchaseID="unique_id"
```

El *`purchaseID`* debe tener un máximo de 20 caracteres, que deben ser ASCII estándar.

**Ejemplos** {#section_60A5C1EAF42F4611898CD6A4F4CF5A28}

```js
s.purchaseID="11223344" 
s.purchaseID="a8g784hjq1mnp3"
```

**Parámetros de configuración** {#section_1808631C96674380BF9C4A6D9A2C568E}

Ninguna

**Problemas, preguntas y consejos** {#section_F5D010F234ED43F19AD1FCD2CD64E060}

La variable *`purchaseID`* permite contabilizar todas las variables de conversión de la página solo una vez en los informes.
