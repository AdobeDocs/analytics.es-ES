---
title: Eliminación de bots en Adobe Analytics
description: Eliminación de bots en Adobe Analytics
feature: Bot Removal
role: Admin
exl-id: 6d4b1925-4496-4017-85f8-82bda9e92ff3
source-git-commit: 429aaa43fdae669350bdb5a5a54a7d4b9b1c65f2
workflow-type: tm+mt
source-wordcount: '763'
ht-degree: 81%

---

# Eliminación de bots en Adobe Analytics

Adobe Analytics ofrece varias opciones para eliminar el tráfico de bots de los informes:

## Usar reglas de bots

Los métodos de filtrado de bots estándar y personalizados se admiten en **[!UICONTROL Analytics]** > **[!UICONTROL Administración]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Reglas de bots]**:

| Tipo de regla | Descripción |
|--- |--- |
| Reglas de bots estándar IAB | Al seleccionar **[!UICONTROL Activar las reglas de filtrado de bots de la IAB]**, se utiliza la Lista internacional de arañas web y bots de la [IAB](https://www.iab.com/) (International Advertising Bureau&#39;s) para eliminar el tráfico de bots. La mayoría de los clientes selecciona esta opción como mínimo. |
| Reglas de bots personalizadas | Puede definir y agregar reglas de bots personalizadas basadas en agentes de usuario, direcciones IP o intervalos de IP. |

Para obtener más información, consulte [Comprender y configurar las reglas de bots](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/bot-rules.md).

## Utilice el plug-in [!UICONTROL websiteBot] para identificar bots

El plug-in [!UICONTROL websiteBot] permite identificar de forma dinámica si los visitantes de escritorio son bots. Puede utilizar estos datos para aumentar la precisión en todos los tipos de creación de informes, lo que le permite medir mejor el tráfico legítimo del sitio.

Este plug-in realiza dos comprobaciones:

* En primer lugar, determina si el dispositivo es de escritorio o de dispositivo móvil mediante la variable navigator.UserAgent. Los dispositivos móviles se ignoran.
* Si es un dispositivo de escritorio, agrega un detector de evento para el movimiento del ratón.

Para obtener más información, consulte la [Guía de implementación de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/implementation/vars/plugins/websitebot.html?lang=es).

## Uso de una combinación de Herramientas de Adobe

Además, como los bots cambian rápidamente, Adobe ofrece otras funciones útiles que, combinadas correctamente y de forma regular, pueden ayudar a eliminar estos enemigos de la calidad de los datos. Estas funciones son: servicio de ID de Experience Cloud, segmentación, Data Warehouse, atributos del cliente y grupos de informes virtuales. A continuación, se muestra una descripción general de cómo puede aprovechar estas herramientas.

### Paso 1: Pase el Experience Cloud ID de sus visitantes a un ID declarado nuevo

Para empezar, le recomendamos que cree un nuevo ID declarado en el [Servicio principal de Personas](https://experienceleague.adobe.com/docs/core-services/interface/audiences/audience-library.html?lang=es). Deberá pasar el Experience Cloud ID de su visitante a este nuevo ID declarado, lo cual se puede realizar rápida y fácilmente con [etiquetas en Adobe Experience Platform](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=es). Usemos el nombre “ECID” para el ID declarado.

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-cust-attr-setup.png)

A continuación, se muestra cómo que se puede capturar este ID mediante el elemento de datos. Asegúrese de completar correctamente el ID de organización de Experience Cloud en el elemento de datos.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Una vez configurado este elemento de datos, siga [estas instrucciones](https://experienceleague.adobe.com/docs/experience-platform/tags/extensions/adobe/id-service/overview.html?lang=es) para pasar los ID declarados a la herramienta ECID con etiquetas en Adobe Experience Platform.

### Paso 2: Use la segmentación para identificar bots

Ahora que el ECID de su visitante se ha pasado a un ID declarado, puede utilizar la [segmentación en Analysis Workspace](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/components/segments/t-freeform-project-segment.html?lang=es) para identificar a los visitantes que actúan como bots. Los bots suelen definirse por su comportamiento: visitas de acceso único, agentes de usuario inusuales, información desconocida sobre dispositivos y exploradores, sin referentes, visitantes nuevos, páginas de aterrizaje inusuales, etc. Utilice los capacidades de los desgloses y la segmentación de Workspace para identificar los bots que han evadido el filtrado de IAB y las reglas de bots del grupo de informes. Por ejemplo: a continuación se muestra una captura de pantalla de un segmento que puede usar:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg1.png)

### Paso 3: Exporte todos los [!DNL Experience Cloud IDs] desde el segmento a través de Data Warehouse

Ahora que ha identificado los bots mediante segmentos, el paso siguiente es aprovechar Data Warehouse para extraer todos los Experience Cloud ID asociados a este segmento. Esta captura de pantalla muestra cómo debe configurar la solicitud de [Data Warehouse](/help/export/data-warehouse/data-warehouse.md):

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-dwh-3.png)

Recuerde usar el ID de visitante de Experience Cloud como dimensión y aplicar el segmento Bots.

### Paso 4: Devuelva esta lista al Adobe como atributo de cliente

Una vez que llegue el informe de Data Warehouse, tendrá una lista de los ECID que deben filtrarse a partir de los datos históricos. Copie y pegue estos ECID en un archivo .CSV en blanco con solo dos columnas, ECID e Indicador de bots.

* **ECID**: Asegúrese de que el encabezado de esta columna coincide con el nombre que dio al nuevo ID declarado antes.
* **Indicador de bots**: Agregue &quot;Indicador de bots&quot; como dimensión de esquema de atributo de cliente.

Use este archivo .CSV como archivo de importación de atributos del cliente y, a continuación, suscriba los grupos de informes al atributo del cliente como se describe en esta [publicación de blog](https://blog.adobe.com/en/publish/2016/10/20/link-digital-behavior-customers).

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-csv-4.png)

### Paso 5: Cree un segmento que aproveche el nuevo atributo de cliente

Una vez que el conjunto de datos se haya procesado e integrado en Analysis Workspace, cree otro segmento que aproveche la nueva dimensión de atributos del cliente “Indicador de bots” y un contenedor de [!UICONTROL Exclusión]:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-filter-seg2.png)

### Paso 6: Utilice este segmento como filtro de grupo de informes virtuales

Finalmente, cree un [grupo de informes virtuales](/help/components/vrs/vrs-about.md) que use este segmento para filtrar los bots identificados:

![](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/general/bot-removal/assets/bot-vrs.png)

Este grupo de informes virtuales recién segmentado ahora generará un conjunto de datos más limpio, con los bots identificados eliminados.

### Paso 7: Repita los pasos 2, 3 y 4 con regularidad

Configure, por lo menos, un recordatorio mensual para identificar y filtrar nuevos bots, tal vez antes del análisis programado de forma regular.
