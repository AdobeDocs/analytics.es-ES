---
title: Eliminación de bots en Adobe Analytics
seo-title: Eliminación de bots en Adobe Analytics
description: 3 formas de eliminar bots en Adobe Analytics
seo-description: 3 formas de eliminar bots en Adobe Analytics
translation-type: tm+mt
source-git-commit: ef17712b4a8a4a5c13dde9be9fdf2281eeb40091

---


# Eliminación de bots en Adobe Analytics

En Adobe Analytics, tiene varias opciones para eliminar el tráfico de bots de los informes:

## Usar reglas de bots

Los métodos de filtrado de bots estándar y personalizados se admiten en **[!UICONTROL Analytics]** &gt; **[!UICONTROL Administración]** &gt; Grupos **[!UICONTROL de]** informes &gt; **[!UICONTROL Editar configuración]** &gt; **[!UICONTROL General]** ****&gt; Reglas de bots:

| Tipo de regla | Descripción |
|--- |--- |
| Reglas de bots estándar IAB | Al seleccionar **[!UICONTROL Activar las reglas]** de filtrado de bots de la IAB, se utiliza la lista internacional de arañas y bots de la [IAB](https://www.iab.com/) (International Advertising Bureau's) para eliminar el tráfico de bots. La mayoría de los clientes selecciona esta opción como mínimo. |
| Reglas de bots personalizadas | Puede definir y agregar reglas de bots personalizadas basadas en agentes de usuario, direcciones IP o intervalos de IP. |

Para obtener más información, consulte Descripción general [de las reglas de](/help/admin/admin/bot-removal/bot-rules.md)bots.

## Utilizar el complemento de implementación `hitGovernor`

Utilice el complemento [de implementación](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/plugins/hitgovernor.html)s.hitGobernador, que elimina a los visitantes que se comportan como bots, lo que significa que estos visitantes envían docenas o cientos de visitas por minuto.

## Uso de una combinación de herramientas de Adobe

Además, como los bots están cambiando rápidamente, Adobe ofrece otras funciones potentes que, combinadas correctamente y de forma regular, pueden ayudar a eliminar estos enemigos de la calidad de los datos. Estas características son: Servicio Experience Cloud ID, Segmentación, Almacén de datos, Atributos del cliente y Grupos de informes virtuales. A continuación se muestra una descripción general de cómo puede aprovechar estas herramientas.

### Paso 1: Pasar el ID de Experience Cloud de los visitantes a un ID declarado nuevo

Para empezar, debe crear un nuevo ID declarado en el servicio [principal](https://docs.adobe.com/content/help/en/core-services/interface/audiences/audience-library.html)Personas. Deberá pasar el ID de Experience Cloud de su visitante a este nuevo ID declarado, que se puede realizar rápida y fácilmente con [Adobe Experience Platform Launch](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html). Usemos el nombre "ECID" para el ID declarado.

![](assets/bot-cust-attr-setup.png)

Esta es la manera en que se puede capturar este ID mediante el elemento de datos. Asegúrese de completar correctamente el identificador de organización de Experience Cloud en el elemento de datos.

```return Visitor.getInstance("REPLACE_WITH_YOUR_ECORG_ID@AdobeOrg").getExperienceCloudVisitorID();```

Una vez configurado este elemento de datos, siga [estas instrucciones](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) para pasar los ID declarados a la herramienta ECID en Launch.

### Paso 2: Usar la segmentación para identificar bots

Ahora que el ECID de su visitante se ha pasado a un ID declarado, puede utilizar la [segmentación en Analysis Workspace](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/components/t-freeform-project-segment.html) para identificar a los visitantes que actúan como bots. Los bots suelen definirse por su comportamiento: visitas de acceso único, agentes de usuario inusuales, información desconocida sobre dispositivos y exploradores, sin referentes, visitantes nuevos, páginas de aterrizaje inusuales, etc. Utilice los poderes de los desgloses y la segmentación del espacio de trabajo para identificar los bots que han evadido el filtrado de IAB y las reglas de bots del grupo de informes. Por ejemplo, a continuación se muestra una captura de pantalla de un segmento que puede utilizar:

![](assets/bot-filter-seg1.png)

### Paso 3: Exportar todo [!DNL Experience Cloud IDs] desde el segmento a través del almacén de datos

Ahora que ha identificado los bots mediante segmentos, el paso siguiente es aprovechar el almacén de datos para extraer todos los ID de Experience Cloud asociados a este segmento. Así debe configurar la solicitud [del almacén](https://docs.adobe.com/content/help/en/analytics/export/data-warehouse/data-warehouse.html) de datos:

![](assets/bot-dwh-3.png)

Recuerde usar el ID de visitante de Experience Cloud como dimensión y aplicar el segmento Bots.

### Paso 4: Volver a pasar esta lista a Adobe como atributo de cliente

Una vez que llegue el informe Almacén de datos, tendrá una lista de los ECID que deben filtrarse a partir de los datos históricos. Copie y pegue estos ECID en un archivo .CSV en blanco con solo dos columnas, ECID y marca de bots.

* **ECID**: Asegúrese de que el encabezado de esta columna coincide con el nombre que dio al nuevo ID declarado anterior.
* **Indicador** de bots: Agregue esto como dimensión de esquema de atributo de cliente.

Utilice este archivo .CSV como archivo de importación de atributos del cliente y, a continuación, suscriba los grupos de informes al atributo del cliente como se describe en esta publicación [de](https://theblog.adobe.com/link-digital-behavior-customers)blog.

![](assets/bot-csv-4.png)

### Paso 5: Cree un segmento que aproveche el nuevo atributo de cliente

Una vez que el conjunto de datos se haya procesado e integrado en Analysis Workspace, cree otro segmento que aproveche la nueva dimensión de atributos del cliente "Marca de bots" y un contenedor de [!UICONTROL exclusión] :

![](assets/bot-filter-seg2.png)

### Paso 6: Utilice este segmento como filtro de grupo de informes virtuales

Finalmente, debe crear un grupo [de informes](/help/components/vrs/vrs-about.md) virtuales que aproveche este segmento para filtrar los bots identificados:

![](assets/bot-vrs.png)

Este grupo de informes virtuales recién segmentado ahora resultará en un conjunto de datos mucho más limpio, con los bots identificados completamente eliminados.

### Paso 7: Repita los pasos 2, 3 y 4 con regularidad

Configure por lo menos un recordatorio mensual para identificar y filtrar nuevos bots, tal vez antes del análisis programado regularmente.
