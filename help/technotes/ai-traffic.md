---
description: Obtenga información sobre cómo informar sobre el tráfico desde bots de chat de IA
title: Analizar el tráfico de los bots de chat de IA
feature: Metrics, Data Configuration and Collection
exl-id: 0b013b7d-02a2-405d-bdd6-c991f0baac8e
TQID: https://experienceleague.adobe.com/lyzSP-7iZ8Y5XiTG1t7Axsg1f5AJf6BbcZbu7MmkwWU
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: b7156124-d291-4de4-ac0c-ed17d8078449
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2:
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 643
ht-degree: 2%

---

# Analizar el tráfico desde las herramientas de IA conversacional

Adobe Analytics proporciona herramientas para analizar el tráfico de IA en el sitio web.

Al analizar el tráfico de IA, primero debe comprender los tipos de tráfico de IA que se pueden producir y los tipos que generan visitas. A continuación, puede analizar el tráfico en Analysis Workspace.

## Explicación del tráfico de IA

### Comprender los tipos de tráfico de IA

El tráfico de IA en su sitio web puede ocurrir en cualquiera de las siguientes circunstancias:

* **Durante el aprendizaje previo**: Ocurre con poca frecuencia cuando el contenido del sitio web se copia y se copia en los datos de aprendizaje de IA.

* **Al responder a peticiones bajo demanda**: Se produce en el momento en que el usuario pregunta a AI y el bot de chat de AI responde. El bot de chat de IA realiza una búsqueda web y el contenido del sitio web se incluye en la respuesta. (Este tipo de interacciones a veces se denomina Generación aumentada de recuperación (RAG).)

  Algunas respuestas del bot de chat de IA incluyen vínculos al material de origen del sitio y otras no.

* **Al ejecutar flujos de trabajo auténticos**: Se produce cada vez que un agente de IA visita su sitio web al hacer clic en una serie de páginas web en un explorador para responder a una solicitud del usuario. En este caso, la IA actúa como agente para el usuario que realizó la solicitud.

### Comprenda cuándo se generan las visitas para el tráfico de IA

Se genera una visita en una página web cuando se ejecuta JavaScript en la página. Según el tipo de tráfico de IA que se produzca en el sitio, JavaScript puede ejecutarse o no.

| Tipo de tráfico de IA | Genera visitas | Consideraciones |
|---------|----------|---------|
| **Formación preliminar** | Sí | Las visitas se generan durante el aprendizaje previo cuando el contenido del sitio web se ingiere en la API. Sin embargo, el preentrenamiento ocurre con poca frecuencia, y el contenido que se incluye en el preentrenamiento de una IA se puede reutilizar una y otra vez en respuestas futuras sin generar más visitas en su sitio web. <p>En otras palabras, una sola visita que se produce durante el preaprendizaje de una IA se puede reutilizar una y otra vez para varias respuestas bajo demanda sin generar visitas adicionales en el sitio web.</p><p>Para obtener información sobre cómo analizar este tipo de tráfico de IA en Analysis Workspace, consulte [Análisis del tráfico de IA mediante la detección de bots](#analyze-ai-traffic-using-bot-detection).</p> |
| **Mensajes a petición** | No | La respuesta de IA no genera ninguna visita porque la respuesta utiliza una combinación de:<ul><li>Los datos con formación previa <br/> ya contienen información sobre los conocimientos con formación previa de la IA, por lo que esta no ejecuta JavaScript en las páginas.</li><li>Búsqueda web bajo demanda <br/>Obtiene solamente la HTML sin procesar de la página web durante la búsqueda web, por lo que la API no ejecuta JavaScript en las páginas.</li></ul> |
| **Vínculos de material de Source en respuestas de IA** | Sí | Las visitas se generan cuando un usuario hace clic en el vínculo al material de origen que se incluye en la respuesta de IA. No se genera una visita si se incluye un vínculo en la respuesta y el usuario no hace clic en el vínculo. <p>Algunas respuestas del bot de chat de IA incluyen vínculos al material de origen y otras no. </p><p>Para obtener información sobre cómo analizar este tipo de tráfico de IA en Analysis Workspace, consulte [Analizar el tráfico de IA por tipo de referente](#analyze-ai-traffic-by-referrer-type).</p> |
| **Flujos de trabajo activos** | Sí | Las visitas se generan en cada página a medida que el agente de IA hace clic en el flujo de trabajo en nombre del usuario. <p>Para obtener información sobre cómo analizar este tipo de tráfico de IA en Analysis Workspace, consulte [Analizar el tráfico de IA por tipo de referente](#analyze-ai-traffic-by-referrer-type).</p> |

## Analizar el tráfico de IA en Analysis Workspace

### Analizar el tráfico de IA por tipo de referente

Puede usar la dimensión Tipo de remitente del reenvío en Analysis Workspace para analizar los siguientes tipos de tráfico de IA:

* Vínculos de material de Source en respuestas de IA

* Flujos de trabajo agénticos

La dimensión Tipo de remitente del reenvío incluye el [elemento de dimensión Herramientas de inteligencia artificial aplicada a la conversación](/help/components/dimensions/referrer-type.md#conversational-ai-tools). Este elemento de dimensión incluye una lista predefinida de bots de chat de IA.

Para obtener más información, consulte [Tipo de referente](/help/components/dimensions/referrer-type.md).

### Análisis del tráfico de IA mediante la detección de bots

Puede utilizar la detección de bots en Analysis Workspace para analizar el tráfico de IA proveniente de la formación previa.
