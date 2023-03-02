---
title: Flujo de trabajo del seguimiento de campañas
description: Utilice Adobe Analytics para realizar un seguimiento de sus esfuerzos de marketing.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
source-git-commit: c118d42667c4a1af55929834b87d148a5973bed9
workflow-type: tm+mt
source-wordcount: '581'
ht-degree: 0%

---

# Flujo de trabajo del seguimiento de campañas

Si su organización desea rastrear el rendimiento y la tasa de pulsaciones de los esfuerzos de marketing, puede utilizar el siguiente proceso. Cada uno de estos pasos tiene secciones dedicadas a continuación que contienen más detalles.

1. [Establecimiento de un proceso de generación de código de seguimiento](#establish-a-tracking-code-generation-process)
1. [Agregue el código de seguimiento deseado al correo electrónico](#add-the-desired-tracking-code-to-the-email)
1. [Configure o ajuste su implementación de Adobe Analytics para incluir datos del código de seguimiento](#include-campaign-variables-in-your-implementation)
1. [Ver los informes en Analysis Workspace](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) puede ayudarle a simplificar cada uno de estos pasos para sacar el máximo partido a sus esfuerzos de marketing. Póngase en contacto con el representante de ventas de Adobe para obtener más información.

## Establecimiento de un proceso de generación de código de seguimiento

Cada organización tiene diferentes necesidades de códigos de seguimiento. Algunas organizaciones pueden tener necesidades mínimas en las que los códigos de seguimiento creados manualmente sean más que suficientes. Es posible que otras organizaciones deseen tener más control sobre el seguimiento y disponer de varios sistemas para crear los códigos de seguimiento deseados. Si su organización utiliza Google Analytics además de Adobe Analytics, es posible que su organización ya tenga un `utm` modelo de código de seguimiento establecido.

Independientemente de cómo elija crear o generar códigos de seguimiento, tener un sistema coherente le permite a su organización un momento mucho más fácil cuando desea agrupar los códigos de seguimiento para realizar informes. Los códigos de seguimiento estructurados de forma coherente le permiten crear [Reglas de clasificación](/help/components/classifications/crb/classification-rule-builder.md) para que pueda obtener información sobre el rendimiento categórico.

## Agregue el código de seguimiento deseado a una URL

Una vez que tenga el valor de código de seguimiento deseado, puede agregarlo a cualquier vínculo que anuncie en línea, como publicidad, medios sociales o correo electrónico. La adición de estos códigos de seguimiento suele realizarse en la cadena de consulta de un vínculo. El parámetro de cadena de consulta que utilice depende de los requisitos de seguimiento de su organización; un parámetro de cadena de consulta común es `cid` (abreviatura de ID de campaña). Algunas organizaciones que también utilizan Google Analytics pueden tener ya varios parámetros de cadena de consulta de campaña como `utm_source`, `utm_medium`, y otros.

Añadir cadenas de consulta a un vínculo en un correo electrónico tendría un aspecto similar al siguiente:

```text
https://example.com?cid=EM989027
```

## Incluir variables de campaña en la implementación

Adobe Analytics tiene una [Código de seguimiento](/help/components/dimensions/tracking-code.md) dimensión que puede utilizar para medir diferentes esfuerzos de marketing en su organización. Sin embargo, las distintas organizaciones pueden tener diferentes requisitos de seguimiento. Es importante hacer referencia a las [Documento de diseño de la solución](../prepare/solution-design.md) para realizar un seguimiento coherente de los valores correctos en las variables correctas.

Si su organización aún no ha configurado el seguimiento de campañas, puede ajustar la implementación para establecer la variable [`campaign`](/help/implement/vars/page-vars/campaign.md) variable. Consulte la [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) para aprender a recopilar valores de parámetros de cadena de consulta específicos de la implementación de su organización.

Si su organización recopila `utm` cadenas de consulta, puede elegir:

* Enviar todo `utm` consulta cadenas en la dimensión Código de seguimiento como valores concatenados. A continuación, puede usar [Reglas de clasificación](/help/components/classifications/crb/classification-rule-builder.md) para crear dimensiones adicionales que se centren en cada `utm` parámetro. Este método tiene una curva de aprendizaje más compleja, pero no utiliza eVars adicionales.
* Envíe cada `utm` cadena de consulta en una [eVar](/help/components/dimensions/evar.md). Este método es más sencillo de implementar en general, pero requiere el uso de eVars adicionales.

## Ver los informes en Analysis Workspace

Una vez configurada correctamente la implementación para recopilar datos del código de seguimiento, puede ver los informes en Analysis Workspace.

1. Inicie sesión en la [Adobe Experience Cloud](https://experience.adobe.com) y seleccione [!UICONTROL Adobe Analytics].
1. Cree un [Proyecto de Workspace](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. En la lista de componentes de la izquierda, arrastre el [Código de seguimiento](/help/components/dimensions/tracking-code.md) al lienzo del espacio de trabajo.
1. Arrastre la métrica que desee, como [Visitas](/help/components/metrics/visits.md) o [Pedidos](/help/components/metrics/orders.md) a la derecha del lienzo del espacio de trabajo.

![Informe de seguimiento de campaña](../assets/campaign-tracking-report.png)