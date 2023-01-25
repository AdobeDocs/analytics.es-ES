---
title: Sistema operativo
description: El sistema operativo del visitante.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: 17c441f8855b8ca0604076763817de8d4d3b8efb
workflow-type: tm+mt
source-wordcount: '357'
ht-degree: 29%

---

# Sistema operativo

La dimensión “Sistema operativo” muestra el sistema operativo y la versión que el visitante utilizó. Si tiene funciones en la propiedad web específicas del sistema operativo, esta dimensión le ayuda a comprender qué sistemas operativos son los más comunes.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `User-Agent` de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen sistemas operativos que utilizan los visitantes. Los ejemplos incluyen `"Windows 10"`, `"OS X 10.15"` y `"Android 9"`.

## Cambios en el etiquetado y la definición

A continuación se muestra una lista de problemas específicos con la representación del sistema operativo en el agente de usuario y en los informes de Adobe Analytics.

### Cambio en la convención de nombres para el sistema operativo Apple:

A partir de la versión 11, utilizaremos MacOS en lugar de OS X para hacer referencia al sistema operativo Apple.

Ejemplos:

* &quot;OS X 10.15&quot; (consulte la nota siguiente sobre la versión 10.15.7 sobre la representación en cadenas de UA).
* &quot;MacOS 11.0.0

### La versión del sistema operativo Mac es incorrecta en el agente de usuario después de la versión 10.15.7 

El agente de usuario de los equipos Apple muestra la versión del sistema operativo como 10.15.7 aunque sea una versión más reciente. Esto se hizo porque la inclusión de la versión 11 en la UA aparentemente causó problemas con algunos sitios web. Esto se aplica a *todos los navegadores* y no está relacionado con la &quot;congelación&quot; de Google del agente de usuario en los navegadores Chromium.

Tenga en cuenta que las sugerencias del cliente incluyen la versión correcta en la sugerencia de versión de la plataforma (&quot;Sec-CH-UA-Platform-Version&quot;). Se trata de una sugerencia de alta entropía, por lo que el Adobe no recopila automáticamente. Consulte la [Preguntas frecuentes sobre sugerencias de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) para obtener más información sobre cómo recopilar sugerencias de alta entropía.

### La versión de Windows es incorrecta en el Agente de usuario que comienza con Windows 11

A partir de enero de 2023, el agente de usuario en todos los navegadores muestra que Windows 11 es Windows 10.

Tenga en cuenta que las sugerencias del cliente incluyen la versión correcta en la sugerencia de versión de la plataforma (&quot;Sec-CH-UA-Platform-Version&quot;). Se trata de una sugerencia de alta entropía, por lo que el Adobe no recopila automáticamente. Consulte la [Preguntas frecuentes sobre sugerencias de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) para obtener más información sobre cómo recopilar sugerencias de alta entropía.
