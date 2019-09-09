---
title: Eliminación de bots en Adobe Analytics
seo-title: Eliminación de bots en Adobe Analytics
description: 3 formas de eliminar bots en Adobe Analytics
seo-description: 3 formas de eliminar bots en Adobe Analytics
translation-type: tm+mt
source-git-commit: 53b1559c7596fae7bc36bb7337967a71d9fc22e2

---


# Eliminación de bots en Adobe Analytics

En Adobe Analytics, tiene varias opciones para eliminar el tráfico de bots de los informes:

## Utilizar reglas Bot

Los métodos de filtrado de bots estándar y personalizados son compatibles en !![UICONTROL Analytics > Admin > Report Suites > Edit Settings > General > Bot Rules]:

| Tipo de regla | Descripción |
|--- |--- |
| Reglas de bots estándar de IAB | Al seleccionar «Activar reglas de filtrado para bots de IAB», se utiliza la [lista internacional de bots y arañas de Web de IAB](https://www.iab.com/) (International Advertising Bureau's International Advertising Bureau) para eliminar el tráfico de bots. La mayoría de los clientes selecciona esta opción como mínimo. |
| Reglas de bots personalizadas | Puede definir y agregar reglas de bots personalizadas basadas en agentes de usuario, direcciones IP o intervalos IP. |

Para obtener más información, consulte [Descripción general de reglas Bot](/help/admin/admin/bot-removal/bot-rules.md).

## Uso del `hitGovernor` complemento de implementación

Utilice el complemento de implementación [s. hitcabinet](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html), que elimina a los visitantes que se comportan como bots enviando docenas o cientos de visitas por minuto.

## Uso de una combinación de herramientas de Adobe

Además, como los bots avanzan rápidamente, Adobe ofrece varias otras funciones poderosas que, cuando se combinan de forma correcta y periódica, pueden ayudar a eliminar estos enemigos de la calidad de los datos. Estas funciones son: Servicio Experience Cloud ID, Segmentación, Almacén de datos, Atributos del cliente y Grupos de informes virtuales. Esta es una descripción general de cómo aprovechar estas herramientas.

### Paso 1: Pasar el ID de Experience Cloud de visitantes a un nuevo ID declarado

Para comenzar, debe crear un nuevo ID declarado en [el servicio principal Personas](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html). Tendrá que pasar el ID de Experience Cloud de su visitante a este nuevo ID declarado, que se puede realizar rápida y fácilmente con [Launch Platform Launch. ](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) Vamos a utilizar el nombre "ECID" para el ID declarado.

![](assets/bot-cust-attr-setup.png)

Esta es la forma de capturar este ID mediante el elemento de datos. Asegúrese de rellenar correctamente su orgid de Experience Cloud en el elemento de datos.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Una vez configurado este elemento de datos, siga [estas instrucciones](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) para pasar el ID declarado a la herramienta ECID en Launch.

### Paso 2: Uso de la segmentación para identificar bots

Ahora que tiene el ECID de su visitante pasado a un ID declarado, puede utilizar [la segmentación en Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) para identificar a los visitantes que actúan como bots. Los bots suelen definirse por su comportamiento: visitas de acceso único, agentes de usuario inusuales, información desconocida sobre dispositivos o exploradores, ningún referente, visitantes nuevos, páginas de aterrizaje inusuales, etc. Utilice las capacidades de exploración y segmentación de espacio de trabajo para identificar los bots que han evitado el filtrado de IAB y las reglas de bots de grupos de informes. Por ejemplo, a continuación se muestra una captura de pantalla de un segmento que puede utilizar:

![](assets/bot-filter-seg1.png)

### Paso 3: Exportar todos los ecids desde el segmento a través del Almacén de datos

Ahora que ha identificado los bots con segmentos, el próximo paso es aprovechar el almacén de datos para extraer todos los ID de Experience Cloud asociados con este segmento. Así es como debe configurar la [solicitud de Data Warehouse](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) :

![](assets/bot-dwh-3.png)

Recuerde utilizar el ID de visitante de Experience Cloud como dimensión y aplicar el segmento Bots.

### Paso 4: Devolver esta lista a Adobe como Atributo del cliente

Una vez que llegue el informe Almacén de datos, tendrá una lista de ECID que deben filtrarse de los datos históricos. Copie y pegue estos ecids en un archivo. CSV en blanco con solo dos columnas, ECID y Bandera de bots.

* **ECID**: Asegúrese de que este encabezado de columna coincide con el nombre que ha entregado al nuevo ID declarado.
* **Marca de Bot**: Agregue esto como una dimensión de esquema de Atributo de cliente.

Utilice este archivo. CSV como archivo de importación de Atributos del cliente y, a continuación, suscriba los grupos de informes al atributo del cliente como se describe en esta publicación [de blog](https://theblog.adobe.com/link-digital-behavior-customers).

![](assets/bot-csv-4.png)

### Paso 5: Crear un segmento que aproveche el nuevo Atributo del cliente

Una vez que el conjunto de datos se haya procesado y integrado en Analysis Workspace, cree un segmento más que aproveche la nueva dimensión de atributo de cliente «Bandera Bot» y un !![UICONTROL Exclude] contenedor:

![](assets/bot-filter-seg2.png)

### Paso 6: Utilizar este segmento como filtro de grupo de informes virtuales

Por último, debe crear un [grupo de informes virtuales](/help/components/vrs/vrs-about.md) que aproveche este segmento para filtrar los bots identificados:

![](assets/bot-vrs.png)

Este grupo de informes virtuales recientemente segmentado dará como resultado un conjunto de datos mucho más limpios, con los bots identificados totalmente eliminados.

### Paso 7: Repita los pasos 2, 3 y 4 regularmente

Establezca al menos un recordatorio mensual para identificar y filtrar nuevos bots, tal vez antes de un análisis programado regular.
