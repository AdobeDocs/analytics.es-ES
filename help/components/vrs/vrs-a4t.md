---
description: Consideraciones especiales al usar grupos de informes virtuales de A4T y Adobe Analytics
title: Grupos de informes virtuales y Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
TQID: https://experienceleague.adobe.com/SIJbZiyHFtGFUrlno5-Kov3kDP4QOXREW00jyDsIGFI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 137
ht-degree: 100%

---

# Grupos de informes virtuales y Analytics for Target (A4T)

Tenga en cuenta estas advertencias al utilizar grupos de informes virtuales en el contexto de Adobe Target:

* No puede enviar datos directamente desde Target a un grupo de informes virtuales, solo a un grupo de informes reales.
* Puede crear informes sobre las actividades de A4T dentro de un grupo de informes virtuales. Sin embargo, los datos de A4T se limitan a las filas que coinciden con el segmento del grupo de informes virtuales (y con cualquier otro segmento aplicado). Por ejemplo, si ha creado un grupo de informes virtuales para sus clientes de EMEA, los datos de A4T de ese grupo de informes virtuales reflejarán únicamente los datos de Target para sus clientes de EMEA.
* No pueden volver a publicar segmentos de un grupo de informes virtuales en Target para su activación.
