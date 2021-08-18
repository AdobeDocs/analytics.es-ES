---
description: 'Consideraciones especiales al usar grupos de informes virtuales de A4T y Adobe Analytics '
title: Grupos de informes virtuales y Analytics para Target (A4T)
source-git-commit: 6a47ebc58cb36079940cfc4e5cdc80cf99c18a50
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 0%

---


# Grupos de informes virtuales y Analytics para Target (A4T)

Tenga en cuenta estas advertencias al utilizar grupos de informes virtuales en el contexto de Adobe Target:

* No puede enviar datos directamente desde Target a un grupo de informes virtuales, solo a un grupo de informes real.
* Puede crear informes sobre las actividades de A4T dentro de un grupo de informes virtuales. Sin embargo, los datos de A4T se limitan a las filas que coinciden con el segmento del grupo de informes virtuales (y con cualquier otro segmento aplicado). Por ejemplo, si ha creado un grupo de informes virtuales para sus clientes de EMEA, los datos de A4T de ese grupo de informes virtuales reflejarán únicamente los datos de Target para sus clientes de EMEA.
* No puede volver a publicar segmentos de un grupo de informes virtuales en Target para su activación.