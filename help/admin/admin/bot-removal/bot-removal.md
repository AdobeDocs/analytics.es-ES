---
title: Eliminación de bots en Adobe Analytics
seo-title: Eliminación de bots en Adobe Analytics
description: 3 formas de eliminar bots en Adobe Analytics
seo-description: 3 formas de eliminar bots en Adobe Analytics
translation-type: tm+mt
source-git-commit: 3b363c6d457dbeaef443aa059d2f7de3cdccbbb2

---


# Eliminación de bots en Adobe Analytics

En Adobe Analytics, tiene 3 opciones principales para eliminar el tráfico de bots de los informes:

1. El método predeterminado de filtrado de bots en Adobe Analytics es [crear reglas](/help/admin/admin/bot-removal/bot-rules.md) de bots basadas en la lista de bots de la IAB. Esta lista se actualiza mensualmente y obtiene su lista desde muchas fuentes, incluidas las CDN y las principales propiedades de Internet. Incluye miles de bots conocidos, incluidos todos los favoritos: Google, Bing, Mozilla, etc. Esta lista cubre la abrumadora mayoría de casos de uso y necesidades en torno a la filtración de bots.

1. Utilice el complemento de implementación [s. hitcabinet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html), que elimina a los visitantes que se comportan como bots enviando docenas o cientos de visitas por minuto.

1. Además, como los bots avanzan rápidamente, Adobe ofrece varias otras funciones poderosas que, cuando se combinan de forma correcta y periódica, pueden ayudar a eliminar estos enemigos de la calidad de los datos. Estas funciones son: Servicio Experience Cloud ID, Segmentación, Almacén de datos, Atributos del cliente y Grupos de informes virtuales. Esta es una descripción general de cómo aprovechar estas herramientas:

## Paso 1: Pasar el ID de Experience Cloud de visitantes a un nuevo ID declarado

Para comenzar, debe crear un nuevo ID declarado en el servicio principal [de Audiencias](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html). Tendrá que pasar el ID de Experience Cloud de su visitante a este nuevo ID declarado, que se puede realizar rápida y fácilmente con [Launch Platform Launch. ](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) Vamos a utilizar el nombre "ECID" para el ID declarado.

screenshot here

Esta es una captura de pantalla de cómo se puede capturar este ID mediante el elemento de datos. Asegúrese de rellenar correctamente el ID de mcorg de Adobe en el elemento de datos.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Una vez configurado este elemento de datos, siga [estas instrucciones](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) para pasar el ID declarado a la herramienta ECID en Launch.

## Paso 2: Uso de la segmentación para identificar bots

Ahora que tiene el ECID de su visitante pasado a un ID declarado, es hora de utilizar la segmentación en Analysis Workspace para identificar a los visitantes que actúan como bots. Los bots suelen definirse por su comportamiento: visitas de acceso único, agente de usuario inusual, información desconocida sobre dispositivos o exploradores, sin referentes, visitantes nuevos, páginas de aterrizaje inusuales, etc. Utilice las capacidades de exploración y segmentación de espacio de trabajo para identificar los bots que han evitado el filtrado de IAB y las reglas de bots de grupos de informes. Por ejemplo, a continuación se muestra una captura de pantalla de un segmento que puede utilizar:

![](assets/bot-filter-seg1.png)

## Paso 3: Exportar todos los ecids desde el segmento a través del Almacén de datos

Ahora que ha identificado los bots con segmentos, el próximo paso es aprovechar el almacén de datos para extraer todos los ID de Experience Cloud asociados con este segmento. Así es como debe configurar el [informe Almacén](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) de datos:

![](assets/bot-dwh-3.png)

Recuerde utilizar el ID de visitante de Experience Cloud como dimensión y aplicar el segmento Bots.

## Paso 4: Devolver esta lista a Adobe como Atributo del cliente

Una vez que llegue el informe Almacén de datos, tendrá una lista de ECID que deben filtrarse de los datos históricos. Copie y pegue estos ecids en un archivo. CSV en blanco con solo dos columnas, ECID y Bandera de bots:

![](assets/bot-csv-4.png)

Asegúrese de que el encabezado de la primera columna coincida con el nombre que ha entregado al nuevo ID declarado. Utilice este archivo. CSV como archivo de importación de Atributos del cliente y, a continuación, suscriba los grupos de informes al atributo del cliente como se describe en esta publicación [de blog](https://theblog.adobe.com/link-digital-behavior-customers).

## Paso 5: Crear un segmento que aproveche el nuevo Atributo del cliente

Una vez que el conjunto de datos se haya procesado y integrado en Analysis Workspace, cree un segmento más que aproveche la nueva dimensión de atributo del cliente «Bandera Bot»:

