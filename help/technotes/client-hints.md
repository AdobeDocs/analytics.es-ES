---
title: Sugerencias del cliente
description: Obtenga más información sobre
source-git-commit: b99852f4b8e0a3034ea8965e5646b1ab2f1a8c4c
workflow-type: tm+mt
source-wordcount: '889'
ht-degree: 4%

---


# Información general y preguntas frecuentes sobre sugerencias del cliente

Las sugerencias del cliente son información individual sobre el dispositivo de un usuario. Los proporcionan exploradores Chromium como Google Chrome y Microsoft Edge. Para estos exploradores, las sugerencias del cliente reemplazarán gradualmente al agente de usuario como fuente de información del dispositivo. Adobe Analytics actualizará su proceso de búsqueda de dispositivos para que utilice sugerencias del cliente además del agente de usuario a fin de determinar la información del dispositivo.

Google divide las sugerencias del cliente del agente de usuario en dos categorías: sugerencias de baja entropía y alta entropía.

* Las sugerencias de baja entropía tienen información más genérica sobre los dispositivos. Estos consejos los proporcionan automáticamente los exploradores Chromium.

* Las sugerencias de alta entropía tienen información más detallada. Estas sugerencias solo están disponibles si se solicita. AppMeasurement y el SDK web se pueden configurar para solicitar sugerencias de alta entropía. De forma predeterminada, ambas bibliotecas sí lo hacen **not** solicite sugerencias de alta entropía.

>[!NOTE]
>
>A partir de octubre de 2022, las nuevas versiones de los navegadores Chromium empezarán a &quot;congelar&quot; la versión del sistema operativo representada en la cadena del agente de usuario. Esto significa que, con el tiempo, la información de la versión operativa tal como se representa en el agente de usuario será menos precisa. La versión del sistema operativo es una sugerencia de alta entropía, por lo que para mantener la precisión de la versión del sistema operativo en los informes es necesario configurar la biblioteca de recopilación para recopilar estas sugerencias de alta entropía. Con el tiempo, se bloqueará otra información del dispositivo del agente de usuario, lo que requerirá sugerencias del cliente para mantener la precisión de los informes del dispositivo.

## Preguntas frecuentes

+++**¿Cómo habilito la recopilación de sugerencias del cliente?**

El explorador proporciona automáticamente sugerencias de baja entropía que se incluyen en el proceso de Adobe para obtener información del dispositivo. Se pueden configurar versiones más recientes de AppMeasurement (comenzando por TBD) y SDK web (comenzando por TBD) para recopilar sugerencias de alta entropía. Para ambas bibliotecas, la recopilación de sugerencias de alta entropía es **desactivado de forma predeterminada**. Consulte aquí los detalles sobre cómo implementar esto.

+++**¿Puedo elegir qué sugerencias de alta entropía recopilo?**

En este momento no. Puede elegir recopilar todas las sugerencias de alta entropía o ninguna.

+++**¿Se producirán cambios en los informes de dispositivos en Analytics?**

Los campos de dispositivo disponibles para informes no cambiarán. Los datos capturados para esos campos pueden cambiar según qué campo y cómo haya configurado la recopilación para sugerencias del cliente.

+++**¿Qué campos de informes de Analytics se derivan del agente de usuario?**

* [Explorador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Tipo de explorador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Tipos de sistemas operativos](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Tipo de dispositivo móvil y dispositivo móvil](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)??
* Fuentes de datos (tenga en cuenta que los usuarios deben actualizar para capturar estos campos. Además, existe una dependencia en la que no podemos exponer el ID móvil junto con la información del dispositivo).
* Conector de origen de Analytics (no está listo)

+++**¿Qué campos de informes de Analytics se derivan de valores almacenados en sugerencias de alta entropía?**

A partir de septiembre de 2022, la cronología publicada por Google para congelar las sugerencias de Usuario-Agente indica que la versión del sistema operativo dejará de actualizarse a partir de octubre de 2022. Si no hay una entropía alta, la precisión de la versión del sistema operativo, incluida en la dimensión &quot;Sistema operativo&quot; de Analytics, se degradará gradualmente.

Consulte la [cronología publicada por Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) para ver el tiempo de congelación del agente de usuario.

+++**¿Qué exploradores se ven afectados por las sugerencias del cliente?**

Las sugerencias del cliente solo se aplican a exploradores Chromium como Google Chrome y Microsoft Edge. No se han realizado cambios en los datos de otros navegadores o aplicaciones móviles.

+++**¿Cómo usará Adobe las sugerencias del cliente para derivar información del dispositivo?**

Adobe utiliza un tercero, Device Atlas, que usará tanto las sugerencias del cliente como el agente de usuario para obtener información del dispositivo.

+++**¿Las sugerencias del cliente estarán disponibles en las fuentes de datos?**

Sí. Consulte la documentación (a continuación).

+++**¿Estarán disponibles las sugerencias del cliente en los datos enviados a AEP y CJA a través del conector de origen de Adobe?**

Planeamos incluir sugerencias del cliente en los datos a través del conector de origen de Adobe en el primer semestre de 2023.

+++**¿Cómo se representan las sugerencias del cliente en XDM?**

Consulte la [documentación del esquema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) en Adobe Experience Platform.

+++**¿Dónde puedo obtener más información sobre las sugerencias del cliente?**

Esta [Publicación de blog de Google](https://web.dev/user-agent-client-hints/) es una buena referencia y punto de partida.

+++**¿Cuáles son los distintos campos de sugerencias? ¿Cuáles afectan a los informes de dispositivos?**

En la tabla siguiente se describen las sugerencias del cliente a partir de septiembre de 2022.

| Sugerencia (encabezado) | Sugerencia | Entropía alta o baja | Ejemplo | Campos de informes de Analytics |
| --- | --- | --- | --- | --- |
| Sec-CH-UA | Navegador y versión significativa | Bajo | Google Chrome 84 | [Navegador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en) y [Tipo de explorador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en) |
| Sec-CH-UA-Mobile | Dispositivo móvil (verdadero o falso) | Bajo | TRUE | [Tipo de dispositivo móvil y dispositivo móvil](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)?? |
| Sec-CH-UA-Platform | Sistema operativo/Plataforma | Bajo | Android | [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |
| Sec-CH-UA-Arch | Arquitectura del sitio | Alto | &quot;arm&quot; | Ninguna? |
| Sec-CH-UA-Bitness | Sec-CH-UA-Bitness | Alto |  | Ninguno? |
| Sec-CH-UA-Full-Version | Versión completa del explorador | Alto | &quot;84.0.4143.2&quot; | Ninguno? |
| Sec-CH-UA-Full-Version-List | ??? | Alto | ?? | Ninguno? |
| Sec-CH-UA-Model | Modelo de dispositivo | Alto | &quot;Pixel 3&quot; | Ninguno? |
| Sec-CH-UA-Platform-Version | Versión del sistema operativo/plataforma | Alto | &quot;10&quot; | [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en) |

+++**¿Cómo capturo las sugerencias de alta entropía?**

Se pueden configurar sugerencias de alta entropía

* Para AppMeasurement directamente [vínculo a la entrada del indicador en la Guía de implementación]
* En la extensión de análisis de etiquetas
* En el SDK web.

+++**¿Qué datos se eliminan del agente de usuario y cuándo?**

Consulte la [cronología publicada por Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Esto puede estar sujeto a cambios.

+++