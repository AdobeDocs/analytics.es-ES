---
description: Consideraciones especiales al usar grupos de informes virtuales de A4T y Adobe Analytics
title: Grupos de informes virtuales y Analytics for Target (A4T)
feature: VRS
exl-id: b81e5100-f512-4219-a8ab-5d7f6219d206
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '137'
ht-degree: 100%

---

# Grupos de informes virtuales y Analytics for Target (A4T)

Tenga en cuenta estas advertencias al utilizar grupos de informes virtuales en el contexto de Adobe Target:

* No puede enviar datos directamente desde Target a un grupo de informes virtuales, solo a un grupo de informes reales.
* Puede crear informes sobre las actividades de A4T dentro de un grupo de informes virtuales. Sin embargo, los datos de A4T se limitan a las filas que coinciden con el segmento del grupo de informes virtuales (y con cualquier otro segmento aplicado). Por ejemplo, si ha creado un grupo de informes virtuales para sus clientes de EMEA, los datos de A4T de ese grupo de informes virtuales reflejarán únicamente los datos de Target para sus clientes de EMEA.
* No pueden volver a publicar segmentos de un grupo de informes virtuales en Target para su activación.
