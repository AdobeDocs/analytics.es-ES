---
description: En HTML, hay varios caracteres que crean un espacio en blanco.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Uso de espacios en blanco en valores de variable
topic: Developer and implementation
uuid: 1edd7934-9b3e-43e2-9f24-65f42cb306e2
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Uso de espacios en blanco en valores de variable

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
