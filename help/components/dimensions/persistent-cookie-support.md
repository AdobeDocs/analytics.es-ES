---
title: Compatibilidad con cookies persistentes
description: Determina si el visitante puede admitir cookies persistentes.
feature: Dimensions
exl-id: ced69e41-d992-4c5a-8541-920aeb7186ae
TQID: https://experienceleague.adobe.com/QmbTee9NoWeTmiRdFI3p24idNhzEzK66xb5RY-KKnQ4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 4516f6de27be12a2ae2fafe4e06d724f4a89fb83
workflow-type: tm+mt
source-wordcount: '243'
ht-degree: 67%
---
# Compatibilidad con cookies persistentes

La &quot;Compatibilidad con cookies persistentes&quot; [dimension](overview.md) muestra si la visita utilizó un identificador de visitante originado en una fuente persistente. La fuente persistente más común es de una cookie, pero también puede utilizar encabezados móviles y otras fuentes.

## Rellene esta dimensión con datos

Adobe determina esta dimensión del lado del servidor, en función de si el identificador de visitante de la visita se originó a partir de una fuente que normalmente persiste (como una cookie). No hay ninguna variable que establecer y funciona de forma predeterminada para todas las implementaciones.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado del lado del servidor) |
| **Campo Web SDK / XDM** | Ninguno (derivado del lado del servidor) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | N/A |

## Elementos de dimensión

* **`Enabled`**: el identificador de visitante del hit proviene de un origen que normalmente persiste. Los ejemplos más comunes incluyen parámetros de cadena de consulta `aid`, `fid` o `mid`, ya que derivan sus valores de una cookie.
* **`Disabled`**: el identificador de visitante del hit proviene de una fuente que Adobe no reconoce como persistente, como IP + cadena del agente de usuario. Este elemento de dimensión también incluye los ID de visitante personalizados que utilizan la variable [`visitorID`](/help/implement/vars/config-vars/visitorid.md).

## Diferencia entre “Compatibilidad con cookies” y “Compatibilidad con cookies persistentes”

* **Compatibilidad con cookies**: AppMeasurement intenta establecer una cookie genérica. El elemento de dimensión se basa en si la cookie se configuró correctamente.
* **Compatibilidad con cookies persistentes**: el elemento de dimensión se basa en si el identificador del hit se originó a partir de una fuente persistente, como una cookie.
