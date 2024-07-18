---
title: Dimensiones de búsqueda móvil
description: Dimensiones basadas en la dirección IP y agente de usuario del dispositivo.
feature: Dimensions
exl-id: fa460888-513d-4d14-93b1-33d308e0758a
source-git-commit: e32821dd3f30404166554b8437c508172e4764e5
workflow-type: tm+mt
source-wordcount: '947'
ht-degree: 100%

---

# Dimensiones de búsqueda móvil

*Esta página hace referencia a las propiedades de los dispositivos móviles que tienen acceso al sitio web. Consulte [Dimensiones del ciclo de vida móvil](lifecycle-dimensions.md) o [Métricas del ciclo de vida móvil](../metrics/lifecycle-metrics.md) para realizar el seguimiento en una aplicación móvil.*

Las [dimensiones](overview.md) de búsqueda móvil proporcionan una visión detallada de las propiedades de los dispositivos móviles que visitan el sitio. Estas propiedades se basan en el agente de usuario y la dirección IP de la visita. Puede utilizar estas dimensiones para comprender las funciones que admite un dispositivo móvil.

## Rellene estas dimensiones con datos

Estas dimensiones hacen referencia a reglas de búsqueda internas de Adobe.

* Para la dimensión [!UICONTROL Operador de telefonía móvil], Adobe colabora con [Digital Element](https://www.digitalelement.com/es/) que utiliza NetAcuity para el mantenimiento de búsquedas entre direcciones IP y operadores de telefonía móvil.
* Para todas las demás dimensiones móviles, Adobe colabora con [DeviceAtlas](https://deviceatlas.com/) para mantener búsquedas entre el agente de usuario y cada dimensión móvil correspondiente.

La disponibilidad de estas dimensiones depende del tipo de implementación:

* Para implementaciones de AppMeasurement, estas dimensiones funcionan de forma predeterminada.
* Para implementaciones de SDK web, habilite [!UICONTROL Búsqueda geográfica] (para el operador de telefonía móvil) o [!UICONTROL Búsqueda de dispositivos] (para todas las demás dimensiones) al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Descripciones de dimensiones móviles

>[!NOTE]
>
>Los elementos de dimensión etiquetados como `"None"` son dispositivos no móviles. Si desea un informe que solo incluya dispositivos móviles, arrastre la dimensión Dispositivo móvil al área de segmentos del lienzo de Workspace.

* **[!UICONTROL Compatibilidad con audio móvil]**: Determina los formatos de archivo que puede reproducir el dispositivo. Los valores de ejemplo incluyen `"MP3"`, `"AAC"` y `"MIDI Monophonic"`. Los valores de esta dimensión no se excluyen mutuamente; una sola visita puede atribuirse a varios elementos de dimensión.
* **[!UICONTROL Operador de telefonía móvil]**: el proveedor de teléfono o datos del dispositivo. Los valores de ejemplo incluyen `"Reliance Jio"`, `"Airtel"`, `"Vodafone"` y `"Verizon"`.
* **[!UICONTROL Profundidad de color del dispositivo móvil]**: Profundidad de color del dispositivo en bits.
* **[!UICONTROL Compatibilidad con cookies móviles]**: Determina si el dispositivo móvil admite cookies. Esta dimensión no indica si el explorador acepta cookies. Los elementos de dimensión incluyen `"Supported"`, `"Not supported"` y `"Unknown"`.
* **[!UICONTROL Dispositivo móvil]**: El dispositivo móvil que utiliza el visitante.
* **[!UICONTROL Número de dispositivo móvil]**: Determina si el dispositivo móvil transmite su número. Esta dimensión no proporciona el número móvil en sí. Los elementos de dimensión incluyen `"Supported"`, `"Not supported"` y `"Unknown"`.
* **[!UICONTROL Tipo de dispositivo móvil]**: Tipo de dispositivo móvil. Los valores de ejemplo incluyen `"Mobile phone"`, `"Tablet"`, `"Media player"` y `"Gaming console"`.
* **[!UICONTROL DRM móvil]**: tipo de DRM que admite el dispositivo móvil. Los valores de ejemplo incluyen `"DRM OMA forward"`, `"DRM OMA combined delivery"` y `"DRM OMA separate delivery"`.
* **[!UICONTROL Compatibilidad con la imagen del dispositivo móvil]**: tipos de imágenes que admite un dispositivo móvil. Los valores de ejemplo incluyen `"PNG"`, `"JPEG"` y `"GIF 87"`. Los valores de esta dimensión no se excluyen mutuamente; una sola visita puede atribuirse a varios elementos de dimensión.
* **[!UICONTROL Servicios de información móvil]**: Tipos de servicios de noticias compatibles con el dispositivo. Los dispositivos actuales no suelen notificar esta información.
* **[!UICONTROL VM de Java móvil]**: versiones de Java que admite el dispositivo.
* **[!UICONTROL Decoración del correo móvil]**: determina si el dispositivo es compatible con [Decome](https://en.wikipedia.org/wiki/Decome), una funcionalidad que, hace tiempo, era popular en dispositivos japoneses.
* **[!UICONTROL Fabricante del dispositivo móvil]**: agrupa los dispositivos móviles por fabricante. Los valores de ejemplo incluyen `"Apple"`, `"Samsung"`, `"Huawei"` y `"Motorola"`.
* **[!UICONTROL Longitud máxima del marcador móvil]**: El número máximo de bytes que admite el dispositivo móvil en las direcciones URL con marcador. Los dispositivos actuales no suelen tener un límite.
* **[!UICONTROL Longitud máxima de la URL del explorador móvil]**: el número máximo de bytes que admite el dispositivo móvil en las direcciones URL. Los dispositivos actuales no suelen tener un límite.
* **[!UICONTROL Longitud máxima del correo electrónico móvil]**: número máximo de bytes que admite el dispositivo móvil en un mensaje de correo electrónico. Los dispositivos actuales no suelen tener un límite.
* **[!UICONTROL Protocolos de red móvil]**: Los tipos de protocolo que admite el dispositivo al acceder a Internet. Los valores de ejemplo incluyen `"EDGE"`, `"GPRS"`, `"UMTS"` y `"LTE"`.
* **[!UICONTROL Sistema operativo móvil (obsoleto)]**: En su lugar, utilice la dimensión [Sistema operativo](operating-systems.md).
* **[!UICONTROL Pulsar móvil para hablar]**: Determina si el dispositivo admite PTT (pulsar para hablar), lo que permite que el dispositivo móvil se comporte de forma similar a una radio bidireccional. Los dispositivos actuales no suelen notificar esta función.
* **[!UICONTROL Altura de la pantalla del dispositivo móvil]**: altura de la pantalla, en píxeles. Los iPhones siempre informan de `"480"` debido a la incapacidad para determinar la versión del dispositivo iPhone. Consulte la sección siguiente sobre cómo determinar la versión del dispositivo iPhone.
* **[!UICONTROL Tamaño de la pantalla del dispositivo móvil]**: Dimensiones completas del dispositivo móvil en píxeles. El tamaño de pantalla del informe no indica la orientación del dispositivo. Independientemente de la orientación de pantalla, cada dispositivo tiene una resolución de pantalla fija en el informe. Este tamaño se basa en la búsqueda que determina la orientación más probable. Pueden aparecer tamaños como `"768x1024"` y `"1024x768"` en el mismo informe. Cada uno de los tamaños representa uno o varios dispositivos diferentes.
* **[!UICONTROL Anchura de la pantalla del dispositivo móvil]**: Ancho de la pantalla, en píxeles.
* **[!UICONTROL Compatibilidad con vídeo móvil]**: Los formatos y códecs de archivo de vídeo compatibles con el dispositivo móvil. Existen varios elementos de dimensión para diferentes códecs de archivos MP4 y 3GPP. Los valores de esta dimensión no se excluyen mutuamente; una sola visita puede atribuirse a varios elementos de dimensión.

## Separación de iPhone por modelo o versión

Los dispositivos móviles informan de su versión de firmware en la cadena del agente de usuario, pero no de la versión del dispositivo. Por ejemplo, un iPhone de generación actual contiene un agente de usuario idéntico al de la generación anterior, si se encuentran en la misma versión de firmware. Dado que no hay forma de determinar la versión del dispositivo de un iPhone mediante JavaScript, todos los iPhone pertenecen al mismo grupo. Las dimensiones móviles se basan estrictamente en búsquedas que hacen referencia al agente de usuario, por lo que todos los iPhone presentan un tamaño de pantalla de `320 x 480`.

Si desea recopilar la versión del dispositivo iPhone, hay dos formas de evitar esta limitación.

* **Utilice el SDK móvil**: el SDK móvil contiene dimensiones que exponen la versión del dispositivo para usarla en sistemas de informes. Este método es más ideal para las aplicaciones móviles que para los sitios web.
* **Utilice otras variables disponibles mediante JavaScript**: Algunas variables, como `screen.height` y `screen.width`, pueden utilizarse para deducir la versión del dispositivo. Por ejemplo, puede utilizar el siguiente fragmento de código en el sitio:

  ```js
  if (navigator.userAgent.indexOf('iPhone') > -1) {
    s.eVarXX = screen.width + "x" + screen.height;
    }
  ```

  Este bloque de código detecta primero si el dispositivo es un iPhone. Si es así, el código utiliza JavaScript para extraer la resolución de pantalla en una eVar. Este método permite detectar aproximadamente la versión del dispositivo si las resoluciones de pantalla son únicas.
