---
title: Canal de último contacto
description: El canal de marketing más reciente dentro de la caducidad de la participación del visitante.
exl-id: 62a47de5-ee1a-4394-aa63-75cdda92ba6a
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '250'
ht-degree: 100%

---

# Canal de último contacto

La dimensión “Canal de último contacto” informa del canal de marketing más reciente con el que coincide un visitante durante el periodo de participación de ese visitante (de forma predeterminada, 30 días). Esta dimensión es valiosa para comprender qué canales de marketing conducen el tráfico al sitio y cuáles resultan en conversiones, lo que permite enfocar los esfuerzos de marketing en las áreas más efectivas.

## Rellene esta dimensión con datos

Esta dimensión hace referencia directamente a los nombres de canales que ha definido en el [administrador de canales de marketing](/help/admin/admin/marketing-channels-admin.md).

Cada visita enviada a los servidores de recopilación de datos de Adobe se ejecuta a través de las reglas de procesamiento del canal de marketing del grupo de informes. Se repite por cada regla en orden numérico hasta que encuentra una coincidencia, en la que ese canal de marketing se vincula con la visita. El canal de último contacto persiste con el visitante hasta que no visita el sitio durante más tiempo que el período de participación de visitante (de forma predeterminada, 30 días).

Si desea establecer esta dimensión en un valor específico, se requieren los siguientes pasos:

* Establezca el elemento de dimensión deseado como un canal en el administrador de canales de marketing en la configuración del grupo de informes.
* Establezca una regla de procesamiento de canal de marketing que contenga los criterios deseados para la visita.
* La visita del visitante al sitio debe coincidir con los criterios descritos en la regla de procesamiento del canal de marketing.

## Elementos de dimensión

Los elementos de dimensión incluyen cualquier nombre de canal en el administrador de canales de marketing. De forma predeterminada, los valores incluyen `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` y `"Referring domains"`. Puede añadir o eliminar canales en el administrador de canales de marketing, que afectan a los valores de esta dimensión.
