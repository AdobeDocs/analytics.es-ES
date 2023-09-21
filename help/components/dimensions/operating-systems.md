---
title: Sistema operativo
description: El sistema operativo del visitante.
feature: Dimensions
exl-id: e3911ae0-d242-4da2-a4bc-b2f4877f9dd2
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '412'
ht-degree: 22%

---

# Sistema operativo

El &#39;sistema operativo&#39; [dimensión](overview.md) muestra el sistema operativo y la versión que el visitante utilizó. Si tiene funciones en la propiedad web específicas del sistema operativo, esta dimensión le ayuda a comprender qué sistemas operativos son los más comunes.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a una tabla de búsqueda interna de Adobe. El valor de búsqueda se basa en el encabezado HTTP `User-Agent` de las solicitudes de imagen. Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante etiquetas en Adobe Experience Platform), esta dimensión funciona de forma predeterminada.

## Elementos de dimensión

Los elementos de dimensión incluyen sistemas operativos que utilizan los visitantes. Los ejemplos incluyen `"Windows 10"`, `"OS X 10.15"` y `"Android 9"`.

## Cambios en etiquetado y definición

A continuación se muestra una lista de problemas específicos con la forma en que se ha representado el sistema operativo en el agente de usuario y en los informes de Adobe Analytics.

### Cambio en la granularidad del sistema operativo

El 2 de marzo de 2023, actualizamos nuestros informes para incluir más detalles en el sistema operativo. Después de esta fecha incluimos la versión de parche del sistema operativo. Por ejemplo, un usuario con OS X 10.15.7 habría aparecido como &quot;OS X 10.15&quot; antes del 2 de marzo. Después del 2 de marzo aparecerán como &quot;OS X 10.15.7&quot;.

### Cambio en la convención de nombres del sistema operativo Apple:

A partir de la versión 11 utilizaremos MacOS en lugar de OS X para hacer referencia al sistema operativo Apple.

Ejemplos:

* &quot;OS X 10.15&quot; (consulte la nota a continuación acerca de la versión 10.15.7 sobre la representación en cadenas de UA).
* &quot;MacOS 11.0.0

### La versión del sistema operativo Mac es incorrecta en el agente de usuario después de la versión 10.15.7 

El agente de usuario de los equipos Apple muestra la versión del sistema operativo como 10.15.7, incluso en las versiones más recientes. Esto se hizo porque la inclusión de la versión 11 en la UA aparentemente causó problemas con algunos sitios web. Esto se aplica a *todos los exploradores* y no está relacionado con la &quot;congelación&quot; por parte de Google del agente de usuario en exploradores Chromium.

Tenga en cuenta que las sugerencias del cliente incluyen la versión correcta en la sugerencia de versión de plataforma (&quot;Sec-CH-UA-Platform-Version&quot;). Se trata de una sugerencia de alta entropía, por lo que el Adobe no la recopila automáticamente. Consulte la [Preguntas frecuentes sobre Adobe Analytics Hints](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) para obtener más información sobre cómo recopilar sugerencias de alta entropía.

### La versión de Windows es incorrecta en el agente de usuario a partir de Windows 11

A partir de enero de 2023, el agente de usuario en todos los exploradores muestra Windows 11 como Windows 10.

Tenga en cuenta que las sugerencias del cliente incluyen la versión correcta en la sugerencia de versión de plataforma (&quot;Sec-CH-UA-Platform-Version&quot;). Se trata de una sugerencia de alta entropía, por lo que el Adobe no la recopila automáticamente. Consulte la [Preguntas frecuentes sobre Adobe Analytics Hints](https://experienceleague.adobe.com/docs/analytics/technotes/client-hints.html?lang=en) para obtener más información sobre cómo recopilar sugerencias de alta entropía.
