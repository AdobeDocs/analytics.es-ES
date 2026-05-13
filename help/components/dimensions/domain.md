---
title: Dominio
description: La organización o el ISP que el visitante utiliza para acceder a Internet.
feature: Dimensions
exl-id: 292dc256-e9e7-47be-8586-774f1c047011
TQID: https://experienceleague.adobe.com/D-qRVSeU1Gx9YMDXvcDYLbSo9tCcR-0mUiD-2KsN3g4
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c8add8f2-4250-4fd9-9cde-9707036c567d
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 141
ht-degree: 54%

---

# Dominio

La dimensión [Dominio](overview.md) indica los puntos de acceso que los visitantes utilizan para acceder a Internet.

## Rellene esta dimensión con datos

Adobe está asociado con [Digital Element](https://www.digitalelement.com/es/) para determinar el dominio del punto de acceso. Para determinar el dominio del punto de acceso se utilizan varios métodos, incluida la búsqueda inversa de DNS. No requiere ninguna configuración y no tiene una variable que rellenar.

* Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada.
* Para implementaciones de Web SDK, habilita [!UICONTROL Búsqueda de red] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

## Elementos de dimensión

Los elementos de dimensión de ejemplo incluyen `comcast.net`, `rr.com`, `sbcglobal.net` y `amazonaws.com`. Estos dominios son puntos de acceso y no necesariamente el dominio que representa a un ISP u organización.

Los valores de dimensión de `None` significan que el propietario de la dirección IP del punto de acceso no proporcionó un dominio.
