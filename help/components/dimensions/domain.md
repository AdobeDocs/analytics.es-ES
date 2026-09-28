---
title: Dominio
description: La organización o el ISP que el visitante utiliza para acceder a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
TQID: 'https://experienceleague.adobe.com/D-qRVSeU1Gx9YMDXvcDYLbSo9tCcR-0mUiD-2KsN3g4'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
    internal-label: Methods
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
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
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 31%
---
# Dominio

La dimensión [Dominio](overview.md) indica los puntos de acceso que los visitantes utilizan para acceder a Internet.

>[!NOTE]
>
>Data Warehouse incluye una dimensión &#39;[!UICONTROL Domains]&#39; (plural) retirada que informa de información similar. Adobe recomienda usar esta dimensión, &#39;[!UICONTROL Domain]&#39; (singular), para mantener la coherencia.

## Rellene esta dimensión con datos

Adobe deriva esta dimensión del lado del servidor de la dirección IP del visitante, mediante varios métodos, incluida la búsqueda inversa de DNS, para determinar el dominio del punto de acceso. Adobe se asocia con [Digital Element](https://www.digitalelement.com/es/) para mantener esta búsqueda. No hay ninguna variable que establecer.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | Ninguno (derivado de la dirección IP del visitante) |
| **Campo Web SDK / XDM** | Ninguno (derivado de la dirección IP del visitante) |
| **Parámetro de consulta** | n/a |
| **etiqueta XML** | n/a |
| **Límite de bytes** | n/a |
| **Persistencia** | n/a |

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de Web SDK, habilita [!UICONTROL Búsqueda de red] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de dimensión de ejemplo incluyen `comcast.net`, `rr.com`, `sbcglobal.net` y `amazonaws.com`. Estos dominios son puntos de acceso y no necesariamente el dominio que representa a un ISP u organización.

Los valores de dimensión de `None` significan que el propietario de la dirección IP del punto de acceso no proporcionó un dominio.
