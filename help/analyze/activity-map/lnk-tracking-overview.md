---
description: 'Activity Map realiza un seguimiento de los vínculos con un algoritmo más seguro que '
title: Potente seguimiento de vínculos
topic: Activity map
uuid: a72b1652-2e69-41c7-8cf2-d39e9c705302
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Potente seguimiento de vínculos

Activity Map realiza un seguimiento de los vínculos con un algoritmo más seguro que:

* Incluye el seguimiento de las regiones de la página para evitar que se confundan los casos en los que el mismo vínculo se muestra en diferentes posiciones de la página;
* Garantiza la exclusividad de los vínculos, lo que significa que los vínculos distintos no se pueden confundir con uno debido a problemas con LinkID o con diferentes tipos de explorador.

Para obtener más información sobre el seguimiento de vínculos en el mapa de Actividad, vaya [aquí](/help/analyze/activity-map/activitymap-link-tracking/activitymap-link-tracking-methodology.md).

## Recopilar datos PII con el seguimiento de vínculos de Activity Map {#section_AEE57510D17B4C21A7D49D32D21D67B9}

>[!CAUTION] Si activa el seguimiento de Activity Map, es posible que recopile información de identificación personal (PII). Dicha información se puede utilizar, tanto por sí sola como con otros datos, para identificar o localizar a una persona única, para ponerse en contacto con ella o para identificar a una persona en contexto.

A continuación se indican algunos casos conocidos en los que pueden recopilarse datos PII con el seguimiento de Activity Map:

* Vínculos `Mailto`. Un vínculo mailto es un tipo de vínculo HTML que activa el cliente de correo predeterminado en el equipo para enviar un mensaje de correo electrónico.
* Los vínculos de `User ID` pueden aparecer en el encabezado o pie de página de un sitio web una vez que el usuario ha iniciado sesión.
* En el caso de las instituciones financieras, el número de cuenta puede mostrarse en forma de vínculo. Al hacer clic en él, se recopilará el texto del vínculo.
* En los sitios web de asistencia sanitaria también es posible que los datos PII se muestren como vínculos. Al hacer clic en ellos, se recopilará el texto del vínculo y, en consecuencia, los datos PII.
