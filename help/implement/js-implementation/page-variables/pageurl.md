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


# pageURL

La variable anula la dirección URL real de la página.


<!-- 

pageURL.xml

 -->

En casos excepcionales, la dirección URL de la página no es la dirección URL que se desearía registrar en Analytics.

<table id="table_D4DC6B476FFD4BEEB36A5C6B2D026255"> 
 <thead> 
  <tr> 
   <th class="entry"> Tamaño máximo </th> 
   <th class="entry"> Parámetro depurador </th> 
   <th class="entry"> Informes rellenados </th> 
   <th class="entry"> Valor predeterminado </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Sin límite* </td> 
   <td> <p>G </p> </td> 
   <td> Tráfico &gt; Segmentación &gt; Páginas más populares </td> 
   <td> URL de la página </td> 
  </tr> 
 </tbody> 
</table>

> [!NOTE] Aunque Adobe admite valores para *`pageURL`* de hasta 64 K, algunos exploradores imponen un límite de tamaño en la dirección URL de las solicitudes de imagen. Para evitar el truncamiento de otros datos, las direcciones URL de la página superiores a 255 bytes se dividen: los primeros 255 bytes aparecen en el parámetro `g=` y los bytes restantes se muestran más adelante en la cadena de consulta, en el parámetro de consulta `-g=`.

**Sintaxis y valores posibles** {#section_22AF3BF7C2F743549967B0C760A095C0}

La variable *`pageURL`* debe ser una dirección URL válida, con un protocolo válido. El dominio será obligado a mostrarse en letra minúscula antes de rellenarse en los informes, y la cadena de consulta puede ser depurada, en función de la configuración de Analytics.

```js
s.pageURL="proto://domain/path?query_string"
```

Solo se permiten caracteres compatibles con URL en la dirección URL de la página.

> [!NOTE] Se recomienda encarecidamente que se ponga en contacto con su asesor de Adobe o con el servicio de Atención al cliente antes de utilizar la variable *`pageURL`* con fines personalizados.

**Ejemplos** {#section_45158FDA3F8F4574BDEB5CBC9F7E6C97}

```js
s.pageURL="https://mysite.com/home.jsp?id=1224" 
```

```js
s.pageURL="https://www.mysite.com/"
```

**Parámetros de configuración** {#section_A8F77DAD88164528ACC5C16C066B47DF}

Ninguna

