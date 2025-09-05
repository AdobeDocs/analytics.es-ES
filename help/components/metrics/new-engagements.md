---
title: Nuevos compromisos
description: Número de veces que se establece un canal de primer contacto.
feature: Metrics
exl-id: a419d048-9715-4d7b-9c24-d34129755371
source-git-commit: a6967c7d4e1dca5491f13beccaa797167b503d6e
workflow-type: tm+mt
source-wordcount: '148'
ht-degree: 83%

---

# Nuevos compromisos

La [métrica](overview.md) &quot;Nuevas participaciones&quot; muestra el número de veces que un visitante coincide con un canal de marketing por primera vez en el periodo de participación de ese visitante. Esta métrica es útil cuando desea comparar cualquier dimensión con un visitante que coincida con una regla de procesamiento de canal de marketing por primera vez.

## Cálculo de esta métrica

Durante el procesamiento de datos, cada visita se ejecuta a través de las [reglas de procesamiento del canal de marketing](/help/admin/tools/manage-rs/edit-settings/marketing-channels/c-rules.md). Si una visita individual coincide con cualquier regla de procesamiento de canales de marketing y el visitante no tiene ya un canal de primer contacto, la visita es una nueva participación. Si una visita no coincide con ninguna regla de procesamiento de canal de marketing o si el visitante ya tiene un canal de primer contacto, la visita no es una nueva participación.

Los visitantes pueden tener más de una nueva participación si dejan que caduque el periodo de participación del visitante.
