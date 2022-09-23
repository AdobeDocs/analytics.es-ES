---
title: Sugerencias del cliente
description: Obtenga información sobre cómo las sugerencias del cliente reemplazarán gradualmente al agente de usuario como fuente de información del dispositivo.
source-git-commit: 72ef2d5e34220f1703714fac40a9dae4e76c1ab1
workflow-type: tm+mt
source-wordcount: '833'
ht-degree: 5%

---


# Información general y preguntas frecuentes sobre sugerencias del cliente

Las sugerencias del cliente son información individual sobre el dispositivo de un usuario. Los proporcionan exploradores Chromium como Google Chrome y Microsoft Edge. Para estos exploradores, las sugerencias del cliente reemplazarán gradualmente al agente de usuario como fuente de información del dispositivo. Adobe Analytics actualizará su proceso de búsqueda de dispositivos para que utilice sugerencias del cliente además de User-Agent para determinar la información del dispositivo.

Google divide las sugerencias del cliente User-Agent en dos categorías: sugerencias de baja entropía y alta entropía.

* **Sugerencias de baja entropía** contienen información más genérica sobre dispositivos. Estos consejos los proporcionan automáticamente los exploradores Chromium.

* **Alta entropía** las sugerencias contienen información más detallada. Estas sugerencias solo están disponibles si se solicita. AppMeasurement y SDK web [se puede configurar](/help/implement/vars/config-vars/collecthighentropyuseragenthints.md) para solicitar sugerencias de alta entropía. De forma predeterminada, ambas bibliotecas sí lo hacen **not** solicite sugerencias de alta entropía.

>[!NOTE]
>
>A partir de octubre de 2022, las nuevas versiones de los exploradores Chromium empezarán a &quot;congelar&quot; la versión del sistema operativo representada en la cadena User-Agent. A medida que los usuarios actualizan sus dispositivos, el sistema operativo del agente de usuario no cambiará. Por lo tanto, con el tiempo, la información de la versión operativa tal como se representa en el User-Agent será menos precisa. La versión del sistema operativo es una sugerencia de alta entropía, por lo que para mantener la precisión de la versión del sistema operativo en los informes es necesario configurar la biblioteca de recopilación para recopilar estas sugerencias de alta entropía. Con el tiempo, se bloqueará otra información del dispositivo del User-Agent, lo que requiere sugerencias del cliente para mantener la precisión de los informes de dispositivos.

## Preguntas frecuentes

+++**¿Dónde puedo obtener más información sobre las sugerencias del cliente?**

Esta [Publicación de blog de Google](https://web.dev/user-agent-client-hints/) es una buena referencia y punto de partida.

+++

+++**¿Cómo habilito la recopilación de sugerencias del cliente?**

El explorador proporciona automáticamente sugerencias de baja entropía que se incluyen en el proceso de Adobe para obtener información del dispositivo y el explorador. Se pueden configurar versiones más recientes de AppMeasurement (a partir de 2.23.0) y del SDK web (a partir de 2.12.0) para recopilar sugerencias de alta entropía. Para ambas bibliotecas, la recopilación de sugerencias de alta entropía es **desactivado de forma predeterminada**.

+++

+++**¿Cómo capturo las sugerencias de alta entropía?**

Las sugerencias de alta entropía se pueden configurar con las bibliotecas SDK web y AppMeasurement a través de sus respectivas extensiones Tags o directamente con el indicador collectHighEntropyUserAgentHints .

+++

+++**¿Puedo elegir qué sugerencias de alta entropía recopilo?**

En este momento no. Puede elegir recopilar todas las sugerencias de alta entropía o ninguna.

+++

+++**¿Se producirán cambios en los informes de dispositivos en Analytics?**

Los campos de dispositivo disponibles para informes no cambiarán. Los datos capturados para esos campos pueden cambiar en función del campo y de cómo haya configurado la recopilación para las sugerencias del cliente.

+++

+++**¿Qué campos de informes de Analytics se derivan del agente de usuario?**

* [Explorador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=en)
* [Tipo de explorador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=en)
* [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=en)
* [Tipos de sistemas operativos](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=en)
* [Tipo de dispositivo móvil y dispositivo móvil](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=en)
* [Archivos de fuentes de datos](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-contents/datafeeds-reference.html?lang=es)

+++

+++**¿Qué campos de informes de Analytics se derivan de valores almacenados en sugerencias de alta entropía?**

A partir de septiembre de 2022, la cronología publicada por Google para &quot;congelar&quot; las sugerencias de usuario-agente indica que la versión del sistema operativo dejará de actualizarse a partir de octubre de 2022. Cuando los usuarios actualizan su sistema operativo, la versión del sistema operativo del agente de usuario no se actualiza. Si no hay una entropía alta, la precisión de la versión del sistema operativo, que se incluye en la dimensión &quot;Sistema operativo&quot; de Analytics, se degradará gradualmente.

Consulte la [cronología publicada por Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) para ver el tiempo de congelación de otras partes del User-Agent.

+++

+++**¿Cómo usará Adobe las sugerencias del cliente para derivar información del dispositivo?**

Adobe utiliza un tercero, Device Atlas, que usará tanto las sugerencias del cliente como el agente de usuario para obtener información del dispositivo.

+++

+++**¿Qué exploradores se ven afectados por las sugerencias del cliente?**

Las sugerencias del cliente solo se aplican a exploradores Chromium como Google Chrome y Microsoft Edge. No se han realizado cambios en los datos de otros navegadores o aplicaciones móviles.

+++

+++**¿Estarán disponibles las sugerencias del cliente en los datos enviados a AEP y CJA a través del conector de origen de Adobe?**

Planeamos incluir sugerencias del cliente en los datos a través del conector de origen de Adobe en el primer semestre de 2023.

+++

+++**¿Cómo se representan las sugerencias del cliente en XDM?**

Consulte la [documentación del esquema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) en Adobe Experience Platform.

+++

+++**¿Cuáles son los distintos campos de sugerencias? ¿Cuáles afectan a los informes de dispositivos?**

En la tabla siguiente se describen las sugerencias del cliente a partir de septiembre de 2022.

| Sugerencia | Descripción | Entropía alta o baja | Ejemplo |
| --- | --- | --- | --- | 
| Sec-CH-UA | Navegador y versión significativa | Bajo | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | Dispositivo móvil (verdadero o falso) | Bajo | TRUE |
| Sec-CH-UA-Platform | Sistema operativo/Plataforma | Bajo | &quot;Android&quot; |
| Sec-CH-UA-Arch | Arquitectura del sitio | Alto | &quot;arm&quot; |
| Sec-CH-UA-Bitness | Perfiles de arquitectura | Alto | &quot;64&quot; |
| Sec-CH-UA-Full-Version | Versión completa del explorador | Alto | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | Lista de marcas con su versión | Alto | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | Modelo de dispositivo | Alto | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | Versión del sistema operativo/plataforma | Alto | &quot;10&quot; |

+++



+++**¿Qué partes del Agente-Usuario se están &quot;congelando&quot; y cuándo?**

Consulte la [cronología publicada por Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Esto puede estar sujeto a cambios.

+++
