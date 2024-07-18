---
title: Canal de primer contacto
description: El primer canal de marketing en el período de caducidad de la participación del visitante.
feature: Dimensions
exl-id: cca9794c-1305-4e54-aa13-809b9ebc6230
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 91%

---

# Canal de primer contacto

El &quot;Canal de primer contacto&quot; [dimension](overview.md) informa del primer canal de marketing con el que coincide un visitante durante el periodo de participación de ese visitante (de forma predeterminada, 30 días). Esta dimensión es valiosa para comprender qué canales de marketing dirigen el tráfico inicial al sitio, lo que permite enfocar los esfuerzos de marketing a las áreas más efectivas.

## Rellene esta dimensión con datos

Esta dimensión hace referencia directamente a los nombres de canales que ha definido en el [administrador de canales de marketing](/help/admin/admin/c-manage-report-suites/c-edit-report-suites/marketing-channels/c-channels.md).

Cada visita enviada a los servidores de recopilación de datos de Adobe se ejecuta a través de las reglas de procesamiento del canal de marketing del grupo de informes. Se repite por cada regla en orden numérico hasta que encuentra una coincidencia, en la que ese canal de marketing se vincula con la visita. El canal de primer contacto persiste con el visitante hasta que no visita el sitio durante más tiempo que el periodo de participación de visitante (de forma predeterminada, 30 días).

Si desea establecer esta dimensión en un valor específico, se requieren los siguientes pasos:

* Establezca el elemento de dimensión deseado como un canal en el administrador de canales de marketing en la configuración del grupo de informes.
* Establezca una regla de procesamiento de canal de marketing que contenga los criterios deseados para la visita.
* La visita del visitante a su sitio debe coincidir con los criterios descritos en la regla de procesamiento del canal de marketing _y_ debe ser el primer valor de canal de marketing que lo haga en el periodo de participación del visitante.

Si una visita posterior coincide con criterios de un canal de marketing diferente, esta dimensión no se sobrescribe con el nuevo canal de marketing.

## Elementos de dimensión

Los elementos de dimensión incluyen cualquier nombre de canal en el administrador de canales de marketing. De forma predeterminada, los valores incluyen `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"` y `"Referring domains"`. Puede añadir o eliminar canales en el administrador de canales de marketing, que afectan a los valores de esta dimensión.
