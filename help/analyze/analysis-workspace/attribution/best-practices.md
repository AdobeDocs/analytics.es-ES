---
title: Prácticas recomendadas de atribución
description: Comprenda las prácticas recomendadas para decidir qué modelo de atribución utilizar.
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
TQID: 'https://experienceleague.adobe.com/3h12v3wRMC0SY63jsXBbG6kkTM8ArVOz6ctJVikdKb4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b3a8b8a0-1cc2-48a8-ac82-ffd9c66ccab4
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 444
ht-degree: 64%

---

# Prácticas recomendadas de atribución

Elegir el modelo de atribución correcto para su organización depende de una serie de consideraciones. Este artículo explora una metodología y algunas prácticas recomendadas generales:

* [Análisis exploratorio](#exploratory-analysis)
* [Atribuciones basadas en reglas](#rule-base-attribution)
* [Uso de atribución algorítmica](#use-algorithmic-attribution)

## Análisis de exploración

>[!NOTE]
>Este análisis debe realizarse antes de elegir un modelo de atribución.

Esta fase consiste inicialmente en comprender el comportamiento del cliente y definir las métricas de conversión. En función de las métricas de conversión, herramientas como [Fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) (para datos sin procesar) o Analysis Workspace le facilitan la comprensión de

* El número de clientes que están tocando diferentes canales de marketing antes de convertir
* La proporción/distribución de estos comportamientos

Por ejemplo, si el 50 % de los clientes tocan tres canales antes de la conversión, ¿existe interacción entre esos tres canales?
A continuación puede realizar análisis de canal superior e inferior para ampliar su comprensión.

### Análisis del canal superior

Los canales de análisis del canal superior se utilizan para concienciar sobre la marca o el producto. Por ejemplo, el objetivo de la mayoría de los anuncios de TV es la imagen de marca. Puede usar el [modelo de atribución Time Decay](/help/analyze/analysis-workspace/attribution/models.md), ya que las personas se olvidarán de su anuncio de TV con el tiempo.

### Análisis de canal inferior

En el análisis de canal inferior, la suposición es que las personas ya conocen su marca y usted quiere que se conviertan. Utilice correos electrónicos, notificaciones push o anuncios de Facebook.

## Atribución basada en reglas

El propósito de este paso es validar las hipótesis.

**Ejemplo 1**

Supongamos que su hipótesis es: &quot;*Mi canal de primer contacto tiene más impacto en la conversión que mi canal de último contacto.*&quot;

En este caso, debe usar el [modelo de atribución en forma de J invertida](/help/analyze/analysis-workspace/attribution/models.md) para probar esta hipótesis. Este modelo proporciona el 60 % del crédito al primer punto de contacto.

**Ejemplo 2**

Supongamos que su hipótesis es: *&quot;En un sector específico (como el de los viajes), la ventana de atribución es de 60 o 90 días, no de 30, porque los clientes investigan mucho antes de comprar un producto.*&quot;

En este caso, cambiaría su [ventana retrospectiva](/help/analyze/analysis-workspace/attribution/models.md) a 90 días.

## Uso de atribución algorítmica

Si todavía no tiene un modelo de atribución que proporcione respuestas satisfactorias a todas las preguntas, puede emplear [atribución algorítmica](/help/analyze/analysis-workspace/attribution/algorithmic.md). Como es muy difícil validar un gran número de hipótesis y combinaciones posibles, la atribución algorítmica recurre a algoritmos integrados para asignar crédito entre elementos de dimensión.

## Otras consideraciones

* Es posible que necesite utilizar los servicios de un científico de datos en lugar de depender solo de Analysis Workspace.
* Puede confiar en los datos sin procesar, como en las fuentes de datos de Adobe.
* Considere utilizar [Customer Journey Analytics](https://experienceleague.adobe.com/en/docs/analytics-platform/using/cja-overview/cja-b2c-overview/cja-overview), por ejemplo, si quiere tener en cuenta los datos de sus impresiones.
