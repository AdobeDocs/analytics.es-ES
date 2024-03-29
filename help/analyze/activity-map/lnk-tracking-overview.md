---
description: Activity Map realiza un seguimiento de los vínculos con un algoritmo más seguro que
title: Potente seguimiento de vínculos
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
feature: Activity Map
role: User, Admin
exl-id: 1f077234-ff88-46ce-a931-2d21d68042b0
source-git-commit: 7226b4c77371b486006671d72efa9e0f0d9eb1ea
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%

---

# Potente seguimiento de vínculos

Activity Map realiza un seguimiento de los vínculos con un algoritmo más seguro que:

* Incluye el seguimiento de las regiones de página para evitar que un mismo vínculo se pueda confundir en distintos dispositivos si aparece en posiciones distintas de la página.
* Garantiza la exclusividad de los vínculos, lo que implica que los vínculos que sean distintos no se puedan confundir por problemas con los ID o entre distintos tipos de explorador.

Para obtener más información sobre el seguimiento de vínculos en Activity Map, entre [aquí](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## Recopilar datos PII con el seguimiento de vínculos de Activity Map {#section_AEE57510D17B4C21A7D49D32D21D67B9}

>[!CAUTION]
>
>Si activa el seguimiento de Activity Map, es posible que recopile información de identificación personal (PII). Dicha información se puede utilizar, tanto por sí sola como con otros datos, para identificar o localizar a una persona única, para ponerse en contacto con ella o para identificar a una persona en contexto.

A continuación se indican algunos casos conocidos en los que pueden recopilarse datos PII con el seguimiento de Activity Map:

* Vínculos `Mailto`. Un vínculo mailto es un tipo de vínculo HTML que activa el cliente de correo predeterminado en el equipo para enviar un mensaje de correo electrónico.
* Los vínculos de `User ID` pueden aparecer en el encabezado o pie de página de un sitio web una vez que el usuario ha iniciado sesión.
* Para las instituciones financieras, es posible que se muestre como vínculo el número de cuenta. Al hacer clic en dicho vínculo, se recopilará el texto que contenga.
* Los sitios web de entidades sanitarias también pueden mostrar datos PII como vínculos. Al hacer clic en dichos vínculos, se recopilará el texto que contengan, por lo que se recopilarán datos PII.
