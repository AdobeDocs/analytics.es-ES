---
title: Prácticas recomendadas de atribución
description: Comprenda las prácticas recomendadas para decidir qué modelo de atribución utilizar.
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
TQID: 'https://experienceleague.adobe.com/3h12v3wRMC0SY63jsXBbG6kkTM8ArVOz6ctJVikdKb4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
    internal-label: Analysis Workspace
subfeature_v2:
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
    internal-label: Attribution
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
source-git-commit: 12464bdfe5e8bf2b7b0d253a27b5ad248716731f
workflow-type: tm+mt
source-wordcount: '445'
ht-degree: 58%
---
# Prácticas recomendadas de atribución

Elegir el modelo de atribución correcto para su organización depende de una serie de consideraciones. Este artículo explora una metodología y algunas prácticas recomendadas generales:

* [Análisis exploratorio](#exploratory-analysis)
* [Atribución basada en reglas](#rule-based-attribution)
* [Uso de atribución algorítmica](#use-algorithmic-attribution)

## Análisis de exploración

>[!NOTE]
>Este análisis debe realizarse antes de elegir un modelo de atribución.

Esta fase consiste inicialmente en comprender el comportamiento del cliente y definir las métricas de conversión. En función de las métricas de conversión, herramientas como [Fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) (para datos sin procesar) o Analysis Workspace le facilitan la comprensión de

* El número de clientes que están tocando diferentes canales de marketing antes de convertir
* La proporción/distribución de estos comportamientos

Por ejemplo, si el 50 % de los clientes tocan tres canales antes de la conversión, ¿existe interacción entre esos tres canales?
Para ampliar su comprensión, realice análisis de funnel superiores e inferiores.

### Análisis del embudo superior

Los embudos de análisis del embudo superior se utilizan para concienciar sobre la marca o el producto. Por ejemplo, el objetivo de la mayoría de los anuncios de TV es la imagen de marca. Use el [modelo de atribución Time Decay](/help/analyze/analysis-workspace/attribution/models.md), ya que las personas se olvidarán de su anuncio de TV con el tiempo.

### Análisis de embudo inferior

En el análisis de embudo inferior, la suposición es que las personas ya conocen su marca y usted quiere que se conviertan. Utilice correos electrónicos, notificaciones push o anuncios de Facebook.

## Atribución basada en reglas

El propósito de este paso es validar las hipótesis.

**Ejemplo 1**

Supongamos que su hipótesis es: &quot;*Mi canal de primer contacto tiene más impacto en la conversión que mi canal de último contacto.*&quot;

En este caso, use el [modelo de atribución en forma de J inverso](/help/analyze/analysis-workspace/attribution/models.md) para probar esta hipótesis. Este modelo proporciona el 60 % del crédito al primer punto de contacto.

**Ejemplo 2**

Supongamos que su hipótesis es: *&quot;En la industria de viajes, la ventana de atribución es de 60 o 90 días, no de 30, porque los clientes investigan mucho antes de comprar.&quot;*

En este caso, cambie su [ventana retrospectiva](/help/analyze/analysis-workspace/attribution/models.md) a 90 días.

## Uso de atribución algorítmica

>[!NOTE]
>
>Debe tener el paquete **Ultimate** para usar la atribución algorítmica. Póngase en contacto con su administrador si no está seguro de qué paquete de Adobe Analytics tiene.

Si todavía no tiene un modelo de atribución que proporcione respuestas satisfactorias a todas las preguntas, puede emplear [atribución algorítmica](/help/analyze/analysis-workspace/attribution/algorithmic.md). Como es muy difícil validar un gran número de hipótesis y combinaciones posibles, la atribución algorítmica recurre a algoritmos integrados para asignar crédito entre elementos de dimensión.

## Otras consideraciones

* Es posible que necesite utilizar los servicios de un científico de datos en lugar de depender solo de Analysis Workspace.
* Puede confiar en los datos sin procesar, como en las fuentes de datos de Adobe.
* Considere utilizar [Customer Journey Analytics](https://experienceleague.adobe.com/es/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview), por ejemplo, si quiere tener en cuenta los datos de sus impresiones.
