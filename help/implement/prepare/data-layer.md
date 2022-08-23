---
title: Creación de una capa de datos
description: Descubra qué es una capa de datos en su implementación de Analytics y cómo se puede utilizar para asignar variables en Adobe Analytics.
feature: Implementation Basics
exl-id: 271dd8fa-3ba1-4a7f-b16a-c48a736a5bb5
source-git-commit: 6a43a24cfe6a2a7f92a9613898660df41daf2c89
workflow-type: tm+mt
source-wordcount: '468'
ht-degree: 60%

---

# Creación de una capa de datos

Una capa de datos es un marco de objetos JavaScript del sitio que contienen los valores de variables que se utilizan en la implementación de Analytics. Permite un bueno control y un mantenimiento más sencillo al asignar valores a variables de Analytics.

## Requisitos previos

[Crear un documento de diseño de solución](solution-design.md): es importante que su organización se alinee en los requisitos de seguimiento. Asegúrese de estar listo con un documento de diseño de solución antes de ponerse en contacto con los equipos de desarrollo de su organización.

## Flujo de trabajo

La implementación de Adobe Analytics mediante una capa de datos suele seguir estos pasos:

1. **Trabaje con el equipo de desarrollo del sitio para implementar una capa de datos**: El equipo de desarrollo del sitio es el principal responsable de asegurarse de que el objeto de capa de datos se rellene con los valores correctos. Revise esta página con el equipo de desarrollo del sitio para asegurarse de que las expectativas estén alineadas entre los equipos.

   >[!NOTE]
   >
   >Seguir las especificaciones de capa de datos recomendadas por Adobe es opcional. Si ya dispone de una capa de datos o decide no seguir las especificaciones de Adobe, asegúrese de que su organización se ajuste a las siguientes especificaciones.
1. **Valide la capa de datos con una consola de explorador**: Una vez creada una capa de datos, puede validar que funcione con cualquier consola de desarrollador del explorador. Puede abrir la consola de desarrollador en la mayoría de los exploradores con la clave `F12`. Un valor de variable de ejemplo sería `adobeDataLayer.page.title`.
1. **Uso de la recopilación de datos de Adobe Experience Platform para asignar objetos de capa de datos a elementos de datos**: Este paso varía en función del método de implementación de su organización:
   * **Si se utiliza el SDK web**: Asigne los objetos de capa de datos deseados a los campos XDM deseados en Adobe Experience Platform Edge. Consulte [Asignación de variables de Analytics](../aep-edge/variable-mapping.md) para determinar la asignación de capa de datos que desee.
   * **Si se utiliza la extensión de Analytics**: Cree elementos de datos en Etiquetas en la recopilación de datos de Adobe Experience Platform y asígnelos a los objetos de capa de datos que desee. A continuación, dentro de la extensión de Analytics, asigne cada elemento de datos a la variable de Analytics correspondiente.

## Especificaciones

Adobe recomienda usar la variable [Capa de datos del cliente de Adobe](https://github.com/adobe/adobe-client-data-layer/wiki) para implementaciones nuevas o reestructuradas.

Su organización puede utilizar otras especificaciones de capa de datos, como el [Capa de datos digital de la experiencia del cliente](https://www.w3.org/2013/12/ceddl-201312.pdf), u otra especificación personalizada por completo. Lo más importante es alinear con una capa de datos coherente que satisfaga las necesidades de su organización.

Las capas de datos son extensibles; si tiene requisitos específicos de su organización, puede incluir objetos en su capa de datos para satisfacer esas necesidades.

## Configuración de los valores de la capa de datos

Las capas de datos se generan en el servidor, que hacen referencia a los mismos objetos utilizados para generar el contenido del sitio. Establezca la capa de datos del sitio en función de los requisitos de seguimiento establecidos en el [documento de diseño de la solución](solution-design.md) de su organización.

## Pasos siguientes

[Asignar objetos de capa de datos a elementos de datos](../launch/layer-to-elements.md): utilice la capa de datos del sitio en Adobe Experience Platform.
