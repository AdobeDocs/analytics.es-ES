---
title: canal de primer toque
description: El primer canal de mercadotecnia dentro de la caducidad del compromiso del visitante.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 0%

---


# canal de primer toque

La dimensión &#39;canal de primer toque&#39; informa del primer canal de marketing con el que coincide un visitante durante el período de compromiso del visitante (de forma predeterminada, 30 días). Esta dimensión es valiosa para comprender qué canales de mercadotecnia conducen el tráfico inicial a su sitio, permitiéndole enfocar los esfuerzos de mercadotecnia en las áreas más efectivas.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia directamente a los nombres de canales que ha definido en el administrador [de canales](/help/admin/admin/marketing-channels-admin.md)de marketing.

Cada visita enviada a los servidores de recopilación de datos de Adobe se ejecuta a través de las reglas de procesamiento de Marketing canal del grupo de informes. Se repite por cada regla en orden numérico hasta que encuentra una coincidencia, en la que ese canal de mercadotecnia se vincula con la visita. El canal de primer toque persiste con el visitante hasta que no visita el sitio durante más tiempo que el período de compromiso de visitante (de forma predeterminada, 30 días).

Si desea establecer esta dimensión en un valor específico, se requieren los siguientes pasos:

* Defina el elemento de dimensión deseado como un canal en el Administrador de canales de marketing en Configuración del grupo de informes.
* Establezca una regla de procesamiento de Marketing canal que contenga los criterios deseados para la visita.
* La visita del visitante a su sitio debe coincidir con los criterios descritos en la regla de procesamiento de canal de mercadotecnia __ y debe ser el primer valor de canal de mercadotecnia que lo haga en el período de compromiso del visitante.

Si una visita posterior coincide con criterios de un canal de marketing diferente, esta dimensión no se sobrescribe con el nuevo canal de marketing.

## Elementos de dimensión

Los elementos de dimensión incluyen cualquier nombre de canal en el administrador de Marketing canal. De forma predeterminada, los valores incluyen `"Paid search"`, `"Natural search"`, `"Display"`, `"Email"`, `"Affiliate"`, `"Direct"`, `"Internal"`, `"Social networks"`y `"Referring domains"`. Puede agregar o eliminar canales en el administrador de canales de marketing, que afectan a los valores de esta dimensión.
