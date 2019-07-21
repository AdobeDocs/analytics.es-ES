---
description: En HTML, hay varios caracteres que crean un espacio en blanco.
keywords: Implementación de Analytics
seo-description: En HTML, hay varios caracteres que crean un espacio en blanco.
seo-title: Uso de espacio en blanco en valores de variable
solution: Analytics
subtopic: Resolución de problemas
title: Uso de espacio en blanco en valores de variable
topic: Desarrollador e implementación
uuid: 1 edd 7934-9 b 3 e -43 e 2-9 f 24-65 f 42 cb 306 e 2
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Uso de espacio en blanco en valores de variable

En HTML, hay varios caracteres que crean un espacio en blanco.

Estos son un espacio, una tabulación y un retorno de carro (o inserción de línea). Consideremos el siguiente ejemplo:

```js
<head> 
 <title> 
   Home Page 
 </title> 
</head> 
<body> 
<script language="javascript"> 
 s.pageName=document.title 
</script> 
```

En este caso, document.title rellena [!UICONTROL s.pageName], que debería recibir el valor "Home Page". Observe el espacio antes de "Home Page". No todos los exploradores interpretan este espacio en blanco de la misma manera. El resultado puede ser cualquiera de los dos ejemplos siguientes:

```js
s.pageName="Home Page"
```

```js
s.pageName="        Home Page"
```

El primer valor se muestra correctamente, pero el segundo muestra un espacio en blanco antes del texto. [!DNL Analytics] trata estos valores como si fueran distintos para la variable [!UICONTROL s.pageName]. La interfaz de [!DNL Analytics] elimina el espacio en blanco inicial del segundo valor. El resultado es un informe que se muestra como se indica a continuación.

![](assets/white_space.jpg)

Esta error de implementación hace que los valores de la variable se fragmenten en varios elementos de línea. [!DNL SAINT] no permite espacios en blanco iniciales en un valor clave. Esto significa que no se puede usar para agrupar varios elementos de línea como solución en caso de que este problema esté afectando a su sitio. La única manera de solucionar el problema es procesar previamente el valor de variable deseado (en este caso, la propiedad document.title) para eliminar los espacios en blanco iniciales (o finales).

El ejemplo anterior usa la variable [!UICONTROL s.pageName] con la propiedad document.title. Adobe no recomienda usar document.title como nombre de página y este problema no afecta solo a la variable [!UICONTROL s.pageName]. Cualquier variable con un espacio en blanco inicial o final puede verse afectada.
