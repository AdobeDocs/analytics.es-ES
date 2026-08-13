---
title: Nuevos compromisos
description: Número de veces que se establece un canal de primer contacto.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
TQID: https://experienceleague.adobe.com/UsPu31wUqpoDYQy5aT9wnzSUgJ6i9mHVZ8pAtFQgzGo
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b3f03848-ae12-48b2-8aab-cad18567eb32
subfeature_v2: id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 148
ht-degree: 83%

---

# Nuevos compromisos

La [métrica](overview.md) &quot;Nuevas participaciones&quot; muestra el número de veces que un visitante coincide con un canal de marketing por primera vez en el periodo de participación de ese visitante. Esta métrica es útil cuando desea comparar cualquier dimensión con un visitante que coincida con una regla de procesamiento de canal de marketing por primera vez.

## Cálculo de esta métrica

Durante el procesamiento de datos, cada visita se ejecuta a través de las [reglas de procesamiento del canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/mc-proc-rules.md). Si una visita individual coincide con cualquier regla de procesamiento de canales de marketing y el visitante no tiene ya un canal de primer contacto, la visita es una nueva participación. Si una visita no coincide con ninguna regla de procesamiento de canal de marketing o si el visitante ya tiene un canal de primer contacto, la visita no es una nueva participación.

Los visitantes pueden tener más de una nueva participación si dejan que caduque el periodo de participación del visitante.
