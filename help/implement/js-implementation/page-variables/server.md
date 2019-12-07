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


# servidor

La variable se usa para mostrar el dominio de una página web (para mostrar a qué dominios vienen los usuarios) o el servidor que atiende la página (para una referencia rápida del balance de carga).


<!-- 

server.xml

 -->

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | servidor | Servidores | "" |

Si su sitio tiene más de un dominio que sirve el mismo contenido, la variable *`server`* se puede usar para realizar el seguimiento de cuál de esos dominios están usando los visitantes. El siguiente código JavaScript rellenará el dominio de la página en la variable server.

```js
s.server=window.location.hostname
```

Si utiliza la variable server como guía rápida del balance de carga, podría colocar un nombre o número de servidor en la variable server. Veamos el siguiente ejemplo:

```js
s.server="server 14"
```

Aunque el informe [!UICONTROL Servidores más populares] puede usarse como referencia rápida del balance de carga, no es una medida precisa de la carga del servidor. Por ejemplo, el tráfico del botón atrás no aumenta la carga del servidor, pero aparece en los informes. El informe no muestra qué servidores están sirviendo las imágenes o las grandes descargas.

**Sintaxis y valores posibles** {#section_48E4B9BFEBFF4409A246D86EC0C0FB13}

```js
s.server="server_name"
```

No existen limitaciones de la variable *`server`* además de las limitaciones estándar de las variables.

**Ejemplos** {#section_78B9EE3C27FB491384869E3D0BD503D6}

```js
s.server="server 18" 
s.server=window.location.hostname 
```

**Parámetros de configuración** {#section_969DB379D5BD469FBEE8D505D3000E49}

Ninguna

**Problemas, preguntas y consejos** {#section_42A28F9B01574F38891D9D54B411D8FE}

La variable *`server`* se puede usar para mostrar qué dominios son los más populares o qué servidores sirven la mayoría de las páginas.

