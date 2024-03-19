---
title: Flujo de trabajo de seguimiento de campaña
description: Utilice Adobe Analytics para realizar un seguimiento de sus esfuerzos de marketing.
feature: Implementation Basics
exl-id: 9f7920e0-471c-46bc-9314-7b0a7c93fdce
role: Admin, Developer, Leader
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: ht
source-wordcount: '576'
ht-degree: 100%

---

# Flujo de trabajo de seguimiento de campaña

Si su organización desea rastrear el rendimiento y la tasa de clics de los esfuerzos de marketing, puede utilizar el siguiente proceso. Cada uno de estos pasos tiene secciones dedicadas a continuación que contienen más detalles.

1. [Establezca un proceso de generación de código de seguimiento](#establish-a-tracking-code-generation-process)
1. [Añada el código de seguimiento deseado al correo electrónico](#add-the-desired-tracking-code-to-the-email)
1. [Configure o ajuste la implementación de Adobe Analytics para incluir los datos del código de seguimiento](#include-campaign-variables-in-your-implementation)
1. [Ver los informes en Analysis Workspace](#view-the-reports-in-analysis-workspace)

[Adobe Campaign](https://business.adobe.com/products/campaign/adobe-campaign.html) puede ayudar a simplificar cada uno de estos pasos para obtener el máximo valor de sus esfuerzos de marketing. Para obtener más información, póngase en contacto con el representante de ventas de Adobe.

## Establezca un proceso de generación de código de seguimiento

Cada organización tiene diferentes necesidades de códigos de seguimiento. Algunas organizaciones pueden tener necesidades mínimas en las que los códigos de seguimiento creados manualmente sean más que suficientes. Es posible que otras organizaciones deseen tener más control sobre el seguimiento y disponer de varios sistemas para crear los códigos de seguimiento deseados. Si su organización utiliza Google Analytics además de Adobe Analytics, es posible que su organización ya tenga un modelo de código de seguimiento establecido de `utm`.

Independientemente de cómo elija crear o generar códigos de seguimiento, tener un sistema coherente en su lugar permite a su organización pasar un tiempo mucho más fácil cuando desea agrupar los códigos de seguimiento para la creación de informes. Los códigos de seguimiento estructurados de forma coherente le permiten crear [Reglas de clasificación](/help/components/classifications/crb/classification-rule-builder.md) para obtener información sobre el rendimiento categórico.

## Añada el código de seguimiento deseado a una dirección URL

Una vez que tenga el valor de código de seguimiento deseado, puede añadirlo a cualquier vínculo que publique en línea, como anuncios, medios sociales o correo electrónico. La adición de estos códigos de seguimiento suele realizarse en la cadena de consulta de un vínculo. El parámetro de cadena de consulta que utilice dependerá de los requisitos de seguimiento de su organización; un parámetro de cadena de consulta común es `cid` (abreviatura de ID de campaña). Es posible que algunas organizaciones que también utilizan Google Analytics ya tengan varios parámetros de cadena de consulta de campaña, como `utm_source`, `utm_medium`, y otros.

Añadir cadenas de consulta a un vínculo en un correo electrónico tendría un aspecto similar al siguiente:

```text
https://example.com?cid=EM989027
```

## Incluir variables de campaña en la implementación

Adobe Analytics tiene una dimensión de [Código de seguimiento](/help/components/dimensions/tracking-code.md) específica que puede utilizar para medir varios esfuerzos de marketing en su organización. Sin embargo, es posible que diferentes organizaciones tengan diferentes requisitos de seguimiento. Es importante hacer referencia al [Documento de diseño de solución](../prepare/solution-design.md) de su organización para realizar un seguimiento coherente de los valores correctos en las variables correctas.

Si su organización aún no ha configurado el seguimiento de campañas, puede ajustar la implementación para establecer la variable [`campaign`](/help/implement/vars/page-vars/campaign.md). Consulte el método [`getQueryParam`](/help/implement/vars/plugins/getqueryparam.md) para aprender a recopilar valores de parámetros de cadena de consulta específicos de la implementación de su organización.

Si su organización recopila cadenas de consulta de `utm`, puede elegir entre:

* Enviar todas las cadenas de consulta de `utm` en la dimensión Código de seguimiento como valores concatenados. A continuación, puede utilizar [Reglas de clasificación](/help/components/classifications/crb/classification-rule-builder.md) para crear dimensiones adicionales que se centren en cada parámetro `utm`. Este método tiene una curva de aprendizaje más compleja, pero no utiliza eVars adicionales.
* Enviar cada `utm` cadena de consulta a una [eVar](/help/components/dimensions/evar.md) separada. Este método es más fácil de implementar en general, pero requiere el uso de eVars adicionales.

## Ver los informes en Analysis Workspace

Una vez que haya configurado correctamente la implementación para recopilar datos de código de seguimiento, puede ver los informes en Analysis Workspace.

1. Inicie sesión en [Adobe Experience Cloud](https://experience.adobe.com) y seleccione [!UICONTROL Adobe Analytics].
1. Cree un [proyecto del espacio de trabajo](/help/analyze/analysis-workspace/build-workspace-project/freeform-overview.md).
1. En la lista de componentes de la izquierda, arrastre la dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md) al lienzo del espacio de trabajo.
1. Arrastre la métrica deseada, como [Visitas](/help/components/metrics/visits.md) o [Pedidos](/help/components/metrics/orders.md) a la parte derecha del lienzo del espacio de trabajo.

![Informe de seguimiento de la campaña](../assets/campaign-tracking-report.png)
