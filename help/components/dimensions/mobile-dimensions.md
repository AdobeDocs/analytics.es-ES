---
title: Dimensiones móviles
description: Dimension basados en la dirección IP del dispositivo.
translation-type: tm+mt
source-git-commit: 76605232c180fb6a3d4c181614f43b75e1d06cd5
workflow-type: tm+mt
source-wordcount: '891'
ht-degree: 93%

---


# Dimensiones móviles

*Esta página hace referencia a las propiedades de los dispositivos móviles que tienen acceso al sitio web. Si desea realizar un seguimiento de los dispositivos en una aplicación móvil, consulte [Implementación de Analytics para dispositivos móviles](/help/implement/mobile-device-sdk.md) en la Guía del usuario de implementación.*

Las dimensiones móviles proporcionan una visión detallada de las propiedades de los dispositivos móviles que visitan el sitio. Puede utilizar estas dimensiones para comprender las funciones que admite un dispositivo móvil.

## Rellene estas dimensiones con datos

Estas dimensiones hacen referencia a reglas de búsqueda internas del Adobe. [!UICONTROL Las ] búsquedas de operadores de telefonía móvil están determinadas por la dirección IP, utilizando los datos que obtenemos de NetAcuity (un producto de elementos digitales).
Si utiliza una biblioteca de AppMeasurement (por ejemplo, mediante Adobe Experience Platform Launch), todas las dimensiones móviles funcionarán de forma predeterminada.

## Descripciones de dimensiones móviles

>[!NOTE]
>
>Los elementos de dimensión etiquetados como `"None"` son dispositivos no móviles. Si desea un informe que solo incluya dispositivos móviles, arrastre la dimensión “Dispositivo móvil” al área de segmentos del lienzo del espacio de trabajo.

* **Compatibilidad con audio móvil**: Determina los formatos de archivo que puede reproducir el dispositivo. Los valores de ejemplo incluyen `"MP3"`, `"AAC"` y `"MIDI Monophonic"`. Los valores de esta dimensión no se excluyen mutuamente; una sola visita puede atribuirse a varios elementos de dimensión.
* **Operador de telefonía** móvil: Los valores de esta dimensión se rellenan buscando datos de terceros (elementos digitales) basados en las direcciones IP capturadas por Analytics. Los valores de ejemplo incluyen `"Reliance Jio"`, `"Airtel"`, `"Vodafone"` y `"Verizon"`.
* **Profundidad de color del dispositivo móvil**: Profundidad de color del dispositivo en bits.
* **Compatibilidad con cookies móviles**: Determina si el dispositivo móvil admite cookies. Este informe no indica si el explorador acepta cookies. Los elementos de dimensión incluyen `"Supported"`, `"Not supported"` y `"Unknown"`.
* **Dispositivo móvil**: El dispositivo móvil que utiliza el visitante.
* **Número de dispositivo móvil**: Determina si el dispositivo móvil transmite su número. Los elementos de dimensión incluyen `"Supported"`, `"Not supported"` y `"Unknown"`.
* **Tipo de dispositivo móvil**: Tipo de dispositivo móvil. Los valores de ejemplo incluyen `"Mobile phone"`, `"Tablet"`, `"Media player"` y `"Gaming console"`.
* **DRM móvil**: Tipo de DRM que admite el dispositivo móvil. Los valores de ejemplo incluyen `"DRM OMA forward"`, `"DRM OMA combined delivery"` y `"DRM OMA separate delivery"`.
* **Compatibilidad con la imagen del dispositivo móvil**: Tipos de imágenes que admite un dispositivo móvil. Los valores de ejemplo incluyen `"PNG"`, `"JPEG"` y `"GIF 87"`. Los valores de esta dimensión no se excluyen mutuamente; una sola visita puede atribuirse a varios elementos de dimensión.
* **Servicios de información móvil**: Tipos de servicios de noticias compatibles con el dispositivo. Los dispositivos recientes no suelen notificar esta información.
* **VM de Java móvil**: Versiones de Java que admite el dispositivo.
* **Decoración del correo móvil**: Determina si el dispositivo es compatible con Decomail, una funcionalidad que, hace tiempo, era popular en dispositivos japoneses.
* **Fabricante del dispositivo móvil**: Agrupa los dispositivos móviles por fabricante. Los valores de ejemplo incluyen `"Apple"`, `"Samsung"`, `"Huawei"` y `"Motorola"`.
* **Longitud máxima del marcador móvil**: El número máximo de bytes que admite el dispositivo móvil en las direcciones URL con marcador. Los dispositivos recientes no suelen tener un límite.
* **Longitud máxima de la URL del explorador móvil**: El número máximo de bytes que admite el dispositivo móvil en las direcciones URL. Los dispositivos recientes no suelen tener un límite.
* **Longitud máxima del correo electrónico móvil**: Número máximo de bytes que admite el dispositivo móvil en un mensaje de correo electrónico. Los dispositivos recientes no suelen tener un límite.
* **Protocolos de red móvil**: Los tipos de protocolo que admite el dispositivo al acceder a Internet. Los valores de ejemplo incluyen `"EDGE"`, `"GPRS"`, `"UMTS"` y `"LTE"`.
* **Sistema operativo móvil (obsoleto)**: En su lugar, utilice la dimensión [Sistema operativo](operating-systems.md).
* **Pulsar móvil para hablar**: Determina si el dispositivo admite PTT (pulsar para hablar), lo que permite que el dispositivo móvil se comporte de forma similar a una radio bidireccional. Los dispositivos recientes no suelen notificar esta función.
* **Altura de la pantalla del dispositivo móvil**: Altura de la pantalla, en píxeles. Tenga en cuenta que los iPhones siempre informan `"480"` debido a la incapacidad para determinar la versión del dispositivo iPhone. Consulte la sección siguiente sobre cómo determinar la versión del dispositivo iPhone.
* **Tamaño de la pantalla del dispositivo móvil**: Dimensiones completas del dispositivo móvil en píxeles. El tamaño de pantalla del informe no indica la orientación del dispositivo. Independientemente de la orientación de pantalla, cada dispositivo tiene una resolución de pantalla fija en el informe. Este tamaño se basa en la búsqueda que determina la orientación más probable. Pueden aparecer tamaños como `"768x1024"` y `"1024x768"` en el mismo informe. Cada uno de los tamaños representa uno o varios dispositivos diferentes.
* **Anchura de la pantalla del dispositivo móvil**: Ancho de la pantalla, en píxeles.
* **Compatibilidad con vídeo móvil**: Los formatos y códecs de archivo de vídeo compatibles con el dispositivo móvil. Existen varios elementos de dimensión para diferentes códecs de archivos MP4 y 3GPP. Los valores de esta dimensión no se excluyen mutuamente; una sola visita puede atribuirse a varios elementos de dimensión.

## Separación de iPhone por modelo o versión

Los dispositivos móviles informan de su versión de firmware en la cadena del agente de usuario, pero no de la versión del dispositivo. Por ejemplo, un iPhone de generación actual contiene un agente de usuario idéntico al de la generación anterior, si se encuentran en la misma versión de firmware. Dado que no hay forma de determinar la versión del dispositivo de un iPhone mediante JavaScript, todos los iPhone pertenecen al mismo grupo. Las dimensiones móviles se basan estrictamente en búsquedas que hacen referencia al agente de usuario, por lo que todos los iPhone informan de un tamaño de pantalla móvil de `320 x 480`.

Si desea recopilar la versión del dispositivo iPhone, hay dos formas de evitar esta limitación.

* **Utilice el SDK de iOS**: El SDK móvil contiene dimensiones que exponen la versión del dispositivo para usarla en sistemas de informes. Este método es más ideal para las aplicaciones móviles que para los sitios web.
* **Utilice otras variables disponibles mediante JavaScript**: Algunas variables, como `screen.height` y `screen.width`, pueden utilizarse para deducir la versión del dispositivo. Por ejemplo, puede utilizar el siguiente fragmento de código en el sitio:

   ```js
   if (navigator.userAgent.indexOf('iPhone') > -1) {
     s.eVarXX = screen.width + "x" + screen.height;
     }
   ```

   Este bloque de código detecta primero si el dispositivo es un iPhone. Si es así, el código utiliza JavaScript para extraer la resolución de pantalla en una eVar. Este método permite detectar aproximadamente la versión del dispositivo si las resoluciones de pantalla son únicas.
