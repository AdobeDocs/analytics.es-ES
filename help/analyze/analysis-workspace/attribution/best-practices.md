---
title: Prácticas recomendadas de atribución
description: ¿Cuáles son las mejores prácticas para decidir un modelo de atribución?
feature: Attribution
exl-id: 92c6039c-f950-4746-8b34-ba18be258c08
source-git-commit: 10ae8213b8745439ab5968853f655a1176b8c38a
workflow-type: ht
source-wordcount: '430'
ht-degree: 100%

---

# Prácticas recomendadas de atribución

Elegir el modelo de atribución correcto para su organización depende de una serie de consideraciones. Este artículo explora una metodología y algunas prácticas recomendadas generales.

## Paso 1: análisis exploratorio

>[!NOTE]
>Este análisis debe realizarse antes de elegir un modelo de atribución.

Esta fase consiste inicialmente en comprender el comportamiento del cliente y definir las métricas de conversión. En función de las métricas de conversión, herramientas como [Fuentes de datos](https://experienceleague.adobe.com/docs/analytics/export/analytics-data-feed/data-feed-overview.html?lang=es) (para datos sin procesar) o Analysis Workspace le facilitan la comprensión de

* ¿Cuántos clientes están tocando diferentes canales de marketing antes de la conversión?
* La proporción/distribución de estos comportamientos.

Por ejemplo, si el 50 % de los clientes tocan tres canales antes de la conversión, ¿existe interacción entre esos tres canales?
A continuación puede realizar análisis de canal superior e inferior para ampliar su comprensión.

### Análisis del canal superior

El análisis del canal superior analiza los canales utilizados para crear la imagen de marca o del producto. Por ejemplo, el objetivo de la mayoría de los anuncios de TV es la imagen de marca. Puede utilizar el modelo de atribución [&quot;Time decay&quot;](/help/analyze/analysis-workspace/attribution/models.md), ya que las personas se olvidarán de su anuncio de TV a lo largo del tiempo.

### Análisis de canal inferior

En este análisis, la suposición es que las personas ya conocen su marca y usted quiere que se conviertan. Utilice notificaciones push o por correo electrónico o anuncios de Facebook.

## Paso 2: atribución basada en reglas

El propósito de este paso es validar las hipótesis.

**Ejemplo 1**

Digamos que su hipótesis es &quot;Mi canal de primer contacto tiene más impacto en la conversión que mi canal del último contacto. A continuación, utilice el modelo de atribución [&quot;Inverse J-shape&quot;](/help/analyze/analysis-workspace/attribution/models.md) para probar esta hipótesis. Este modelo proporciona el 60 % del crédito al primer punto de contacto.

**Ejemplo 2**

Su hipótesis puede ser: &quot;En nuestra industria (como la industria de viajes), la ventana de atribución es de 60 o 90 días, no de 30 días, porque los clientes hacen mucha investigación antes de comprar un producto. Luego cambiaría su [ventana retrospectiva](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/attribution/models.html?lang=es#lookback-windows) a 90 días.

## Paso 3: utilizar atribución algorítmica

Como es muy difícil validar un gran número de hipótesis y combinaciones posibles, puede utilizar la [atribución algorítmica](/help/analyze/analysis-workspace/attribution/algorithmic.md) para dejar este trabajo en algoritmos integrados. Si ya ha encontrado el modelo de atribución perfecto que responde a todas sus preguntas, entonces no necesita realizar este paso.

## Otras consideraciones

* Es posible que necesite utilizar los servicios de un científico de datos en lugar de depender solo de Analysis Workspace.
* Puede confiar en los datos sin procesar, como en las fuentes de datos de Adobe.
* Considere utilizar [Customer Journey Analytics](https://experienceleague.adobe.com/docs/analytics-platform/using/cja-overview/cja-overview.html?lang=es), por ejemplo, si desea tener en cuenta los datos de Impresiones.
