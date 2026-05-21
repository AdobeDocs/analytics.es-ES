---
title: Política de retención de datos
description: Una política de retención de datos determina el tiempo que Adobe almacena los datos.
exl-id: f3bb02d2-380d-4eb7-8449-e0318fc8c0a6
feature: Data Governance
TQID: https://experienceleague.adobe.com/ymM-0bethfijutq5sprEuEfOFgw3Xn4gTsLNNgKTEio
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: ff9b434a-2221-4df7-81d1-5bcbf5f80bce
subfeature_v2:
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c7d04a2c-412a-4c9d-9d7a-4456eaa5adeb
  - id: f4e6943a-c91a-4134-a2c7-f4f20cfff2f0
source-git-commit: f570a4d2e66c2af8ad85ab097078dd95c574fc83
workflow-type: tm+mt
source-wordcount: 617
ht-degree: 92%

---

# Política de retención de datos

Los datos recopilados por Adobe Analytics se conservan durante un período de tiempo específico. El tiempo que Adobe mantiene estos datos varía según el contrato y se describe en la política de retención de datos de una organización. Esta política se aplica a los propios datos, por lo que afecta a todas las capacidades de informes de Analytics (Analysis Workspace, la API de informes, etc.).

**La directiva de retención de datos predeterminada para Adobe Analytics es de 25 meses.** La política de retención de su organización puede ser diferente en función del contrato.

Los datos retenidos se basan en la fecha actual y en la fecha y hora de los datos históricos. La fecha y la hora registradas en las visitas pueden no coincidir con la fecha y la hora en que Adobe recibió la visita o visitas.

## Ajuste del período de retención de datos predeterminado

Si desea reducir o ampliar el período de retención de datos predeterminado, póngase en contacto con el equipo de cuentas de Adobe.

* Reducir el período de retención de datos predeterminado no entraña coste alguno.
* Para prolongar la retención de datos más allá del período de retención predeterminado de 25 meses se deben comprar extensiones (cada una de ellas aumenta el período en un año). Se pueden adquirir hasta ocho extensiones, lo que equivale a un total de 10 años y 1 mes (2 años y 1 mes de la retención por defecto, más los 8 años adquiridos).

## Retención de datos y privacidad de datos

Adobe, en calidad de procesador de datos, debe tomar las medidas adecuadas para ayudar a sus clientes a cumplir con solicitudes de diversa índole (acceso, eliminación y otras) que puedan recibir por parte de particulares. La aplicación de directivas de eliminación adecuadas, seguras y regulares es una parte importante para cumplir con esta obligación. El RGPD se aplica a todos los clientes que comercialicen o procesen información de ciudadanos de la UE. La CCPA se aplica a todos los clientes que comercialicen o procesen información de ciudadanos del estado de California. Esto significa que la privacidad de datos es un cambio regulatorio de alcance mundial.

## Eliminación de datos

Una vez que los datos hayan superado el límite temporal de la política de retención de datos, Adobe se reserva el derecho de eliminarlos sin opción de recuperación. Debe asegurarse de que todos los datos que desea conservar no hayan superado dicho límite de la política de retención de datos de su organización.

## Ver/administrar la directiva de retención de datos actual

El cuadro de diálogo Gobernanza de datos en las herramientas del [!UICONTROL Administrador] proporciona información general sobre los grupos de informes que se han configurado para la gobernanza de datos. También indica si se han asignado a una organización de CX Enterprise y si se ha implementado una política de retención de datos para este grupo de informes.

## Preguntas frecuentes

+++ ¿Cómo puedo decidir el período de retención de datos de mi organización?

Su empresa, como controlador de datos, puede identificar las partes interesadas (por ejemplo, los equipos de marketing, análisis y privacidad) de la organización que sean responsables de tomar decisiones relativas a la retención de datos. Su organización es la más indicada para determinar durante cuánto tiempo retendrá los datos Adobe Analytics.

+++

+++ ¿Cómo se puede calcular el período de retención de datos?

La directiva de retención de datos define un período de retención de datos gradual en el que se pueden consultar los datos e informar al respecto. La fecha de inicio de la retención de datos está determinada por la fecha actual menos el período de retención de datos. La fecha de finalización de la retención de datos está determinada por la fecha actual. Los datos se incluyen en el período de retención de datos si la marca de tiempo de estos se encuentra entre la fecha de inicio y la de finalización.

+++

+++ ¿Puedo solicitar una copia de mis datos antes de que se eliminen?

Sí. Adobe puede proporcionarle el conjunto de datos históricos, compuesto por datos sin procesar y de nivel de visita. Consulte [Fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) en la guía de usuario sobre exportación para obtener más información. Si la interfaz de usuario no puede adecuarse a sus necesidades especiales de exportación de datos, póngase en contacto con el equipo de cuentas de Adobe. Se pueden hacer adaptaciones especiales con costes variables.

+++

+++ ¿Cuándo elimina Adobe los datos?

Póngase en contacto con el equipo de cuentas de Adobe para conocer el período de tiempo específico en el que está programado que se eliminen sus datos. Los datos suelen eliminarse mensualmente.

+++

