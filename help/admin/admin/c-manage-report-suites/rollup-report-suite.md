---
description: Descripción de los tipos de grupos de informes y comparación de los grupos de informes globales y los grupos de informes resumidos.
title: Enfoques de los grupos de informes
feature: Report Suite Settings
exl-id: 97bdc9bd-2212-436b-b3b4-ec518624f9e6
source-git-commit: d173a6c6c9751a86f4218ec842da17da14f8485b
workflow-type: tm+mt
source-wordcount: '879'
ht-degree: 93%

---

# Enfoques de los grupos de informes

<!-- change filename since page name changed? -->

Puede configurar los grupos de informes como *grupos de informes globales* o *grupos de informes resumidos*.

## Grupos de informes globales

Un grupo de informes globales recopila datos de todos los dominios y las aplicaciones que posee su organización. Requiere implementación para enviar todas las solicitudes de imagen a un único grupo de informes.

Adobe recomienda implementar un grupo de informes globales en la mayoría de los casos. Consulte [Consideraciones sobre el grupo de informes globales](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/global-rs.html?lang=es) para conocer las ventajas de implementar un grupo de informes globales.

Puede proporcionar subconjuntos de los datos del grupo de informes globales de su compañía a distintos usuarios finales mediante los enfoques de *etiquetado de grupos múltiples* y *grupo de informes virtuales*:

* **Etiquetado de grupos múltiples**: el etiquetado de grupos múltiples le permite enviar solicitudes de imagen no solo a un grupo de informes globales, sino también a grupos de informes secundarios individuales. La duplicación de los datos del informe global se anula en todos los grupos de informes.

  Por ejemplo, podría recopilar todos los datos de un grupo de informes globales y también configurar grupos de informes secundarios según la marca, la región u otro diferenciador. Los diferentes equipos de su compañía podrían entonces centrarse en los datos de los grupos de informes que les interesen.

  Para utilizar el etiquetado de grupos múltiples, implemente grupos de informes secundarios y un grupo de informes globales que incluya todos los datos de los grupos secundarios. El código de seguimiento de sus páginas web y aplicaciones incluirá el ID del grupo de informes (RSID) para el grupo de informes globales y también los RSID para los grupos de informes secundarios aplicables.<!-- Wording/be more specific? And include any links? -->

  Se realiza una llamada al servidor independiente a cada grupo de informes en la solicitud de imagen. Las llamadas a los grupos de informes secundarios son llamadas secundarias.

* **Grupo de informes virtuales**: un [grupo de informes virtuales](/help/components/vrs/vrs-about.md) es una consulta en segmentos especificados recopilados en un grupo de informes globales y disponibles para grupos de usuarios especificados. Los grupos de informes virtuales le permiten depurar elementos de informes para distintos usuarios finales sin utilizar el etiquetado de grupos múltiples, lo cual evita llamadas secundarias al servidor.

  Para utilizar grupos de informes virtuales, implemente un grupo de informes globales y luego analice los datos para crear grupos de informes virtuales con segmentos específicos aplicados y con permisos de grupo específicos. Puede crear grupos de informes virtuales en el Administrador de grupos de informes virtuales ([!UICONTROL Componentes] > [!UICONTROL Grupos de informes virtuales]). Consulte [Flujo de trabajo de grupos de informes virtuales](/help/components/vrs/c-workflow-vrs/vrs-workflow.md) para obtener más información.

El uso de grupos de informes virtuales en lugar del etiquetado de grupos múltiples suele ser una práctica recomendada, pero los grupos de informes virtuales tienen algunas limitaciones. Consulte [Grupos de informes virtuales y consideraciones sobre el etiquetado de grupos múltiples](/help/components/vrs/vrs-considerations.md) para determinar qué enfoque de grupo de informes es la mejor opción para sus necesidades comerciales. Para obtener una comparación detallada de los grupos de informes virtuales y la funcionalidad de etiquetado de grupos múltiples, consulte &quot;[Grupos de informes virtuales frente al etiquetado de grupos múltiples](/help/components/vrs/vrs-about.md#section_317E4D21CCD74BC38166D2F57D214F78).&quot;

## Informes de resumen

>[!NOTE]
>
>[!DNL Reports & Analytics] es la única herramienta que admite informes de resumen. Reports &amp; Analytics finalizó su vida útil el 17 de enero de 2024.

### Limitaciones de los informes de resumen {#limitations-rollups}

* Los resúmenes proporcionan datos totales, pero no registran valores individuales en los informes. Por ejemplo, los valores de eVar1 no están incluidos, pero sí su total agregado.
* La duplicación de datos no se anula si el resumen combina datos de varios grupos de informes.
* Los resúmenes se ejecutan todos los días a medianoche.
* Al añadir un grupo de informes a un resumen existente, los datos históricos no se incluyen en el resumen.
* Todos los grupos de informes secundarios deben contener datos para que el resumen funcione. Si se incluyen nuevos grupos de informes en un resumen, asegúrese de enviar al menos una vista de página a cada uno de esos grupos de informes.
* Los grupos de informes de resumen pueden incluir un máximo de 40 grupos de informes secundarios.
* Los grupos de informes de resumen pueden incluir un máximo de 100 eventos.
* Los datos contenidos en los grupos de informes de resumen no admiten desgloses ni segmentos.
* El informe de páginas se reemplaza por el informe de sitios más populares, que trata sobre las métricas en el nivel de grupo secundario.

## Comparación de las funciones del grupo de informes globales y del informe de resumen

**Llamadas secundarias al servidor**: los resúmenes no realizan llamadas adicionales al servidor más allá de lo que recopila un solo grupo de informes. Si su organización utiliza el etiquetado de grupos múltiples, se realizan llamadas secundarias al servidor para cada grupo de informes adicional incluido en una solicitud de imagen.

>[!TIP]
>
>Si solo utiliza un grupo de informes globales con [grupos de informes virtuales](/help/components/vrs/vrs-considerations.md), no se necesitan llamadas secundarias al servidor.

**Cambios de implementación**: los resúmenes no requieren ningún cambio de implementación, mientras que los grupos de informes globales requieren que incluya el ID del grupo de informes global en la implementación.

**Duplicación**: a diferencia de los grupos de informes resumidos, los globales anulan la duplicación de visitantes únicos. Por ejemplo, si un usuario visita tres dominios de un mismo propietario el mismo día, los grupos de informes resumidos contabilizarían tres visitantes únicos diarios. Los grupos de informes globales registrarían un único visitante.

**Lapso de tiempo**: los grupos de informes resumidos solo se procesan cada medianoche, mientras que los globales registran datos con latencia estándar.

**Espectro**: los grupos de informes resumidos no permiten la comunicación entre grupos de informes. Los grupos de informes globales pueden atribuir crédito a variables de conversión entre grupos de informes y ofrecer rutas entre los distintos grupos de informes.

**Datos históricos**: los grupos de informes resumidos pueden acumular datos históricos, mientras que los globales solo registran datos a partir del momento en que se implementan.

**Informes**: los grupos de informes globales ofrecen datos de todas las dimensiones, mientras que los resumidos ofrecen datos acumulados sobre los informes principales.

**Productos compatibles**: los resúmenes solo se podían usar en Reports &amp; Analytics. No son compatibles con Analysis Workspace ni con Data Warehouse. Los grupos de informes globales se pueden utilizar en todos los productos.

**Número de grupos de informes agregados**: los grupos de informes resumidos solo admiten un máximo de 40 grupos de informes secundarios. Los grupos de informes globales se pueden implementar en cualquier dominio o aplicación de su propiedad.
