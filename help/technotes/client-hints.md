---
title: Sugerencias del cliente
description: Obtenga información acerca de cómo las sugerencias del cliente reemplazarán gradualmente al agente de usuario como fuente de información del dispositivo.
source-git-commit: 9dfeb0f5cc3bb488fa28fb0d21c6969dfdfc9ef6
workflow-type: tm+mt
source-wordcount: '1073'
ht-degree: 60%

---


# Información general y preguntas frecuentes sobre sugerencias del cliente

Las sugerencias del cliente son información individual acerca del dispositivo de un usuario. Las proporcionan exploradores Chromium como Google Chrome y Microsoft Edge. Para estos, las sugerencias del cliente reemplazarán gradualmente al agente de usuario como fuente de información del dispositivo. Adobe Analytics actualizará su proceso de búsqueda de dispositivos para que utilice sugerencias del cliente además de las del agente de usuario para determinar la información del dispositivo.

Google divide las sugerencias del cliente agente de usuario en dos categorías: sugerencias de baja entropía y de alta entropía.

* Las **sugerencias de baja entropía** contienen información más genérica acerca de los dispositivos. Estas las proporcionan automáticamente los exploradores Chromium.

* Las sugerencias de **alta entropía** contienen información más detallada. Estas solo están disponibles si se solicitan. AppMeasurement y SDK web se puede configurar para solicitar sugerencias de alta entropía. De forma predeterminada, **ninguna** de las dos bibliotecas solicita sugerencias de alta entropía.

>[!NOTE]
>
>Las sugerencias del cliente se incorporarán al proceso de búsqueda de dispositivos de Analytics a partir de mediados de enero de 2023. AppMeasurement y el SDK web admiten actualmente la recopilación de datos de sugerencias, pero no se utilizarán en la búsqueda de dispositivos hasta mediados de enero. Esto tiene por objeto evitar posibles interrupciones en los informes durante el período crítico de fin de año. Como se indica a continuación, la versión del sistema operativo se bloqueará a partir de octubre, pero debido a un despliegue gradual y al hecho de que la mayoría de los agentes de usuario se congelarán en la versión del sistema operativo correcta, estimamos que esto afectará a &lt;3% de los visitantes de Chrome.

>[!NOTE]
>
>A partir de octubre de 2022, las nuevas versiones de los exploradores Chromium empezarán a “congelar” la versión del sistema operativo representada en la cadena del agente de usuario. La versión del sistema operativo es una sugerencia de alta entropía, por lo que para mantener su precisión en la creación de informes es necesario configurar la biblioteca de colección para recopilar estas sugerencias de alta entropía. Con el tiempo, se bloqueará otra información del dispositivo del agente de usuario, lo que requiere sugerencias del cliente para mantener la precisión de la creación de informes de dispositivos.

>[!NOTE]
>
>AAM requiere que se recopilen sugerencias de alta entropía para conservar la funcionalidad completa. Si está utilizando [reenvío del lado del servidor a AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=es) a continuación, es posible que desee habilitar la recopilación de sugerencias de alta entropía.

## Preguntas frecuentes

+++**¿Dónde puedo obtener más información acerca de las sugerencias del cliente?**

Esta [publicación de blog de Google](https://web.dev/user-agent-client-hints/) es una buena referencia y punto de partida.

+++

+++**¿Cómo habilito la colección de sugerencias del cliente?**

El explorador proporciona automáticamente sugerencias de baja entropía que se incorporan para obtener información del dispositivo y el explorador. Se pueden configurar versiones más recientes del SDK web (a partir de 2.12.0) y AppMeasurement (a partir de 2.23.0) para recopilar sugerencias de alta entropía mediante sus respectivas extensiones de etiquetas o directamente mediante una opción de configuración. Consulte las instrucciones para [SDK web](https://experienceleague.adobe.com/docs/experience-platform/edge/fundamentals/user-agent-client-hints.html?lang=en#enabling-high-entropy-client-hints) y [AppMeasurement](https://experienceleague.adobe.com/docs/analytics/implementation/vars/config-vars/collecthighentropyuseragenthints.html?lang=en).

Para ambas bibliotecas, la colección de sugerencias de alta entropía está **desactivada de forma predeterminada**.

+++

+++**¿Puedo elegir qué sugerencias de alta entropía recopilo?**

En este momento no. Puede elegir recopilar todas las sugerencias de alta entropía o ninguna.

+++

+++**¿Cuáles son los distintos valores de sugerencias del cliente?**

En la tabla siguiente se describen las sugerencias del cliente a partir de octubre de 2022.

| Sugerencia | Descripción | Entropía alta o baja | Ejemplo |
| --- | --- | --- | --- | 
| Sec-CH-UA | Explorador y versión significativa | Bajo | &quot;Google Chrome 84&quot; |
| Sec-CH-UA-Mobile | Dispositivo móvil (verdadero o falso) | Bajo | TRUE |
| Sec-CH-UA-Platform | Sistema operativo/Plataforma | Bajo | &quot;Android&quot; |
| Sec-CH-UA-Arch | Arquitectura del sitio | Alto | &quot;arm&quot; |
| Sec-CH-UA-Bitness | Perfiles de arquitectura | Alto | &quot;64&quot; |
| Sec-CH-UA-Full-Version | Versión completa del explorador | Alto | &quot;84.0.4143.2&quot; |
| Sec-CH-UA-Full-Version-List | Lista de marcas con su versión | Alto | &quot;Not A;Brand&quot;;v=&quot;99&quot;, &quot;Chromium&quot;;v=&quot;98&quot;, &quot;Google Chrome&quot;;v=&quot;98&quot; |
| Sec-CH-UA-Model | Modelo de dispositivo | Alto | &quot;Pixel 3&quot; |
| Sec-CH-UA-Platform-Version | Versión del sistema operativo/plataforma | Alto | &quot;10&quot; |

+++

+++**¿Se producirán cambios en la creación de informes de dispositivos en Analytics?**

Los campos de dispositivo disponibles para la creación de informes no cambiarán. Los datos capturados para esos campos pueden cambiar en función del campo y de cómo haya configurado la colección para las sugerencias del cliente.

+++

+++**¿Qué campos de creación de informes de Analytics se derivan del agente de usuario?**

Estos campos se derivan directamente del User-Agent, pero el User-Agent se puede utilizar para ayudar a derivar valores para otros campos relacionados con el dispositivo, según los detalles del dispositivo.

* [Explorador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser.html?lang=es)
* [Tipo de explorador](https://experienceleague.adobe.com/docs/analytics/components/dimensions/browser-type.html?lang=es)
* [Sistema operativo](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-systems.html?lang=es)
* [Tipos de sistemas operativos](https://experienceleague.adobe.com/docs/analytics/components/dimensions/operating-system-types.html?lang=es)
* [Tipo de dispositivo móvil y dispositivo móvil](https://experienceleague.adobe.com/docs/analytics/components/dimensions/mobile-dimensions.html?lang=es)

+++

+++**¿Qué partes del Agente-Usuario se están &quot;congelando&quot; y cuándo?**

Consulte la [cronología publicada por Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html). Esto puede estar sujeto a cambios.

+++

+++**¿Qué campos de creación informes de Analytics se derivan de valores almacenados en sugerencias de alta entropía?**

Esto cambiará con el tiempo a medida que Google &quot;congela&quot; más partes del agente de usuario. El primer campo que se verá directamente afectado es &quot;Sistema operativo&quot; que incluye la versión del sistema operativo Según la cronología publicada por Google para &quot;congelar&quot; sugerencias de usuario-agente, la versión del sistema operativo se bloqueará a partir de finales de octubre de 2022 con la versión 107 de Chromium. En ese punto, la versión del sistema operativo en el agente de usuario será inexacta en algunos casos.

Consulte la [cronología publicada por Google](https://blog.chromium.org/2021/09/user-agent-reduction-origin-trial-and-dates.html) para ver la temporalización de congelación de otras partes del agente de usuario.

+++

+++**¿Cómo usará Adobe las sugerencias del cliente para derivar información del dispositivo?**

Adobe utiliza un tercero, Device Atlas, que usará tanto las sugerencias del cliente como el agente de usuario para obtener información del dispositivo.

+++

+++**¿Qué exploradores se ven afectados por las sugerencias del cliente?**

Las sugerencias del cliente solo se aplican a exploradores Chromium como Google Chrome y Microsoft Edge. No se han realizado cambios en los datos de otros navegadores o aplicaciones móviles.

+++

+++**¿Se admiten sugerencias del cliente en conexiones inseguras?**

No. Las sugerencias del cliente solo se pueden recopilar mediante una conexión HTTP segura, como HTTPS.

+++

+++**¿Cómo puedo incluir datos de sugerencias del cliente al utilizar el envío de API?**

Consulte la documentación para incluirlas en [API de inserción de datos en lotes](https://developer.adobe.com/analytics-apis/docs/2.0/guides/endpoints/bulk-data-insertion/file-format/).

+++

+++**¿Estarán disponibles las sugerencias del cliente en los datos enviados a AEP y CJA a través del conector de origen de Adobe?**

Adobe tiene previsto incluir sugerencias del cliente en los datos a través del conector de origen de Adobe en el primer semestre de 2023.

+++

+++**¿Cómo se representan las sugerencias del cliente en XDM?**

Consulte la [documentación del esquema](https://github.com/adobe/xdm/blob/master/components/datatypes/browserdetails.schema.json#L121) en Adobe Experience Platform.

+++

+++**¿Admitirá AAM reenvío del lado del servidor las sugerencias del cliente?**

Sí. Las sugerencias del cliente se incluirán en los datos reenviados a AAM. Tenga en cuenta que AAM requiere que se recopilen sugerencias de alta entropía para conservar la funcionalidad completa. Si está utilizando [reenvío del lado del servidor a AAM](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) a continuación, es posible que desee habilitar la recopilación de sugerencias de alta entropía.

+++

