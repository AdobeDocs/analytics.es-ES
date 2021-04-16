---
description: Descripción de los tipos de grupos de informes y comparación de los grupos de informes globales y los grupos de informes resumidos.
title: Enfoques de los grupos de informes
feature: Herramientas de administración
uuid: c90b8e38-2c95-4318-8165-a362106b6142
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '975'
ht-degree: 27%

---

# Enfoques de los grupos de informes

<!-- change filename since page name changed? -->

Puede configurar los grupos de informes como *grupos de informes globales* o *grupos de informes resumidos*.

## Grupos de informes globales

Un grupo de informes globales recopila datos de todos los dominios y aplicaciones que posee su organización. Requiere implementación para enviar todas las solicitudes de imagen a un único grupo de informes.

Adobe recomienda implementar un grupo de informes globales en la mayoría de los casos. Consulte &quot;[Consideraciones del grupo de informes globales](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html)&quot; para conocer las ventajas de implementar un grupo de informes globales.

Puede proporcionar subconjuntos de los datos del grupo de informes globales de su empresa a distintos usuarios finales mediante los enfoques *etiquetado de grupos múltiples* y *grupo de informes virtuales*:

* **Etiquetado de grupos múltiples**: El etiquetado de grupos múltiples le permite enviar solicitudes de imagen no solo a un grupo de informes globales, sino también a grupos de informes secundarios individuales. La duplicación de los datos del informe global se anula en todos los grupos de informes.

   Por ejemplo, podría recopilar todos los datos de un grupo de informes globales y también configurar grupos de informes secundarios según la marca, la región u otro diferenciador. Los diferentes equipos de su empresa podrían entonces centrarse en los datos de los grupos de informes que les interesen.

   Para utilizar el etiquetado de grupos múltiples, implemente grupos de informes secundarios y un grupo de informes globales que incluya todos los datos de los grupos secundarios. El código de seguimiento de sus páginas web y aplicaciones incluirá el ID del grupo de informes (RSID) para el grupo de informes globales y también los RSID para los grupos de informes secundarios aplicables.<!-- Wording/be more specific? And include any links? -->

   Se realiza una llamada al servidor independiente a cada grupo de informes en la solicitud de imagen. Las llamadas a los grupos de informes secundarios son llamadas secundarias.

* **Grupo de informes virtuales**: Un grupo de informes  [virtuales ](/help/components/vrs/vrs-about.md) es una consulta sobre segmentos específicos recopilados en un grupo de informes globales y disponibles para grupos específicos de usuarios. Los grupos de informes virtuales le permiten depurar elementos de informes para distintos usuarios finales sin utilizar el etiquetado de grupos múltiples, evitando así llamadas secundarias al servidor.

   Para utilizar grupos de informes virtuales, implemente un grupo de informes globales y luego analice los datos para crear grupos de informes virtuales con segmentos específicos aplicados y con permisos de grupo específicos. Puede crear grupos de informes virtuales en el Administrador de grupos de informes virtuales ([!UICONTROL Componentes] > [!UICONTROL Grupos de informes virtuales]). Consulte &quot;[Flujo de trabajo del grupo de informes virtuales](/help/components/vrs/c-workflow-vrs/vrs-workflow.md)&quot; para obtener más información.

El uso de grupos de informes virtuales en lugar del etiquetado de grupos múltiples suele ser una práctica recomendada, pero los grupos de informes virtuales tienen algunas limitaciones. Consulte &quot;[Grupos de informes virtuales y consideraciones sobre el etiquetado de grupos múltiples](/help/components/vrs/vrs-considerations.md)&quot; para determinar qué enfoque de grupo de informes es la mejor opción para sus necesidades comerciales. Para obtener una comparación detallada de los grupos de informes virtuales y la funcionalidad de etiquetado de grupos múltiples, consulte &quot;[Grupos de informes virtuales vs. Etiquetado multigrupo](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78)&quot;.

## Informes de resumen

>[!NOTE]
>
>[!DNL Reports & Analytics] es la única herramienta que admite informes de resumen y Adobe ya no recomienda el uso de resúmenes. Considere la posibilidad de utilizar un grupo de informes globales con etiquetado de grupos múltiples o grupos de informes virtuales.

Un informe de resumen es una simple agregación de datos de varios grupos de informes, sin deduplicación ni desglose de datos o segmentos. Los resúmenes no requieren la implementación de código. Para utilizar informes resumidos, [implemente grupos de informes secundarios](/help/admin/c-manage-report-suites/c-new-report-suite/t-create-a-report-suite.md) y luego [combínelos en un informe resumido](/help/admin/c-manage-report-suites/t-rollups.md) mediante [!UICONTROL Herramientas de administración].

Los informes resumidos son gratuitos: los grupos de informes secundarios realizan sus propias llamadas al servidor, pero el resumen no realiza llamadas adicionales. Los resúmenes son una característica heredada y tienen muchas limitaciones.

### Limitaciones de los informes resumidos {#limitations-rollups}

* Los resúmenes proporcionan datos totales, pero no registran valores individuales en los informes. Por ejemplo, los valores de eVar1 no se incluyen, pero sí se puede incluir su total agregado.
* La duplicación de datos no se anula cuando el resumen combina datos de varios grupos de informes.
* Los resúmenes se ejecutan todas las noches a medianoche.
* Cuando se agrega un grupo de informes a un resumen existente, los datos históricos no se incluyen en el resumen.
* Todos los grupos de informes secundarios deben contener datos para que un resumen funcione. Si se incluyen nuevos grupos de informes en un resumen, asegúrese de enviar al menos una vista de página a cada uno de esos grupos de informes.
* Los grupos de informes resumidos pueden incluir un máximo de 40 grupos de informes secundarios.
* Los grupos de informes resumidos pueden incluir un máximo de 100 eventos.
* Los datos contenidos en grupos de informes resumidos no admiten desgloses ni segmentos.
* El informe de páginas se reemplaza por el informe de sitios más populares, que trata sobre las métricas en el nivel de grupo secundario.

## Comparación de las funciones del grupo de informes globales y del informe resumido

**Llamadas secundarias al servidor**: los resúmenes no realizan llamadas adicionales al servidor más allá de lo que recopila un solo grupo de informes. Si su organización utiliza el etiquetado de grupos múltiples, se realizan llamadas secundarias al servidor para cada grupo de informes adicional incluido en una solicitud de imagen.

>[!TIP]
>
>Si solo utiliza un grupo de informes globales con [grupos de informes virtuales](/help/components/vrs/vrs-considerations.md), no se necesitan llamadas secundarias al servidor.

**Cambios de implementación**: los resúmenes no requieren ningún cambio de implementación, mientras que los grupos de informes globales requieren que incluya el ID del grupo de informes global en la implementación.

**Duplicación**: a diferencia de los grupos de informes resumidos, los globales anulan la duplicación de visitantes únicos. Por ejemplo, si un usuario visita tres dominios de un mismo propietario el mismo día, los grupos de informes resumidos contabilizarían tres visitantes únicos diarios. Los grupos de informes globales registrarían un único visitante.

**Lapso de tiempo**: los grupos de informes resumidos solo se procesan cada medianoche, mientras que los globales registran datos con latencia estándar.

**Espectro**: los grupos de informes resumidos no permiten la comunicación entre grupos de informes. Los grupos de informes globales pueden atribuir crédito a variables de conversión entre grupos de informes y proporcionar rutas entre los distintos grupos de informes.

**Datos históricos**: los grupos de informes resumidos pueden acumular datos históricos, mientras que los globales solo registran datos a partir del momento en que se implementan.

**Informes**: los grupos de informes globales ofrecen datos de todas las dimensiones, mientras que los resumidos ofrecen datos acumulados sobre los informes principales.

**Productos compatibles**: los grupos de informes resumidos solo se pueden usar en Reports &amp; Analytics. No son compatibles con Analysis Workspace ni con la Data Warehouse. Los grupos de informes globales se pueden utilizar en todos los productos.

**Número de grupos de informes agregados**: los grupos de informes resumidos solo admiten un máximo de 40 grupos de informes secundarios. Los grupos de informes globales se pueden implementar en cualquier dominio o aplicación de su propiedad.
