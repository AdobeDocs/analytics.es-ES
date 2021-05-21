---
title: Nuevos compromisos
description: Número de veces que se establece un canal de primer contacto.
exl-id: a419d048-9715-4d7b-9c24-d34129755371
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '148'
ht-degree: 100%

---

# Nuevos compromisos

La métrica “Nuevas participaciones” muestra el número de veces que un visitante coincide con un canal de marketing por primera vez en el periodo de participación de ese visitante. Esta métrica es útil cuando desea comparar cualquier dimensión con un visitante que coincida con una regla de procesamiento de canal de marketing por primera vez.

## Cálculo de esta métrica

Durante el procesamiento de datos, cada visita se ejecuta a través de las [reglas de procesamiento del canal de marketing](../c-marketing-channels/c-rules.md). Si una visita individual coincide con cualquier regla de procesamiento de canales de marketing y el visitante no tiene ya un canal de primer contacto, la visita es una nueva participación. Si una visita no coincide con ninguna regla de procesamiento de canal de marketing o si el visitante ya tiene un canal de primer contacto, la visita no es una nueva participación.

Los visitantes pueden tener más de una nueva participación si dejan que caduque el periodo de participación del visitante.
