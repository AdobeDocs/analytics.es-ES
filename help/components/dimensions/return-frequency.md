---
title: Frecuencia de retorno
description: Cantidad de tiempo acumulada entre la visita actual y la anterior.
feature: Dimensions
exl-id: 8ec31e17-a57d-416f-b471-c2c37a98d134
TQID: 'https://experienceleague.adobe.com/k0H7kOCgrBRY3cZckPXaJ9UgLBPTYWHxKT8gzeMQjcI'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 76%
---
# Frecuencia de retorno

La &quot;Frecuencia de retorno&quot; [dimensión](overview.md) muestra el tiempo que transcurre entre las visitas de un visitante que retorna. Cuando un visitante regresa a su sitio, Adobe consulta hace cuánto tiempo se produjo la visita anterior y agrupa el hit en el elemento de dimensión correspondiente. Esta dimensión es valiosa para ayudar a medir el atractivo y la importancia que su sitio web tiene para los visitantes a lo largo del tiempo. También puede ayudar a identificar el impacto del contenido y las promociones del sitio en sus visitantes.

>[!TIP]
>
>Esta dimensión no incluye visitantes nuevos.

## Rellene esta dimensión con datos

Adobe calcula esta dimensión del lado del servidor comparando la visita actual con la visita anterior del visitante. No hay ninguna variable que establecer; funciona de forma predeterminada para todas las implementaciones.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (calculado por Adobe) |
| **Campo Web SDK / XDM** | Ninguno (calculado por Adobe) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | Visita |

## Elementos de dimensión

Los elementos de dimensión incluyen bloques basados en tiempo, según el tiempo transcurrido desde la visita anterior.

* Menos de 1 día
* 1 a 3 días
* 3 a 7 días
* 7 a 14 días
* 14 días a 1 mes
* Más de 1 mes

## Los elementos de dimensión aparecen bajo bloques fuera del intervalo de fechas del proyecto

Cuando se establece el intervalo de fechas de un proyecto, es común ver los elementos de dimensión atribuidos a las visitas fuera del intervalo de fechas. Por ejemplo, un visitante llega al sitio en julio y vuelve dos veces en el mismo día en septiembre. La dimensión Frecuencia de retorno del mes de septiembre incluirá una visita en “Más de 1 mes” y una visita en “Menos de un día”.
