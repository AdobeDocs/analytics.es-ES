---
description: Obtenga información sobre cómo informar sobre el tráfico desde bots de chat de IA
title: Analizar el tráfico de los bots de chat de IA
feature: Metrics, Data Configuration and Collection
source-git-commit: d16214865a037efe41b9f95682758daa577a12ed
workflow-type: tm+mt
source-wordcount: '638'
ht-degree: 0%

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

