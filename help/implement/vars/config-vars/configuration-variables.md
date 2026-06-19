---
title: Variables de configuración
description: Utilice variables de configuración para determinar cómo se recopilan los datos.
feature: Appmeasurement Implementation
exl-id: 3f017a94-b71d-47da-8ab4-daf32475ed34
role: Admin, Developer
TQID: https://experienceleague.adobe.com/amtLWIgyADqWBOv38xdJ6AF4IjhJ0aGVrvYqXLckfkI
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
  - id: d3cdead0-685a-4489-9250-4bb709942f66
source-git-commit: ccf6c5e3f25f562a3bfffe89b9ff057c28aab409
workflow-type: tm+mt
source-wordcount: 385
ht-degree: 18%

---

# Información general de variables de configuración

Las variables de configuración controlan la manera en que se capturan y procesan los datos en los informes. No suelen contener valores de dimensión o valores de métrica.

## Establecer variables de configuración

En implementaciones que utilizan la extensión Web SDK o la extensión Analytics, las variables de configuración generalmente se encuentran en la configuración de la extensión:

1. Inicie sesión en [Adobe Experience Platform Data Collection](https://experience.adobe.com/data-collection) con sus credenciales de Adobe ID.
1. Haga clic en la propiedad de etiquetas deseada.
1. Haga clic en la ficha [!UICONTROL Extensiones] y, a continuación, haga clic en [!UICONTROL Configurar] en la extensión.

En implementaciones de JavaScript que utilizan `AppMeasurement.js`, las variables de configuración generalmente se establecen en la parte superior del archivo JS.

>[!IMPORTANT]
>
>Asegúrese de que todas las variables de configuración estén establecidas antes de llamar a un método de seguimiento ([`t()`](../functions/t-method.md) o [`tl()`](../functions/tl-method.md)). Evite establecer variables de configuración en la función [`doPlugins()`](../functions/doplugins.md).

## Variables de configuración retiradas

Se retiran las siguientes variables de configuración. Están documentados aquí como referencia si los encuentra en una implementación heredada.

* **`account`**: determinó el grupo de informes al que se enviaron los datos. El grupo de informes ahora se administra mediante la creación de instancias de objeto de seguimiento (el método [`s_gi()`](../functions/s-gi.md)). Utilice el método [`s.sa()`](../functions/sa-method.md) si necesita cambiar el grupo de informes después de crear una instancia del objeto de seguimiento.
* **`cookieDomain`**: se determinó el dominio donde AppMeasurement estableció las cookies. Las versiones actuales de AppMeasurement detectan automáticamente el dominio de cookie correcto, lo que hace que esta variable quede obsoleta.
* **`cookieDomainPeriods`**: ayudó a AppMeasurement a determinar dónde almacenar las cookies cuando un dominio contenía varios puntos. Las versiones actuales de AppMeasurement detectan automáticamente el dominio correcto, lo que hace que esta variable quede obsoleta.
* **`fpCookieDomainPeriods`**: el equivalente de origen de `cookieDomainPeriods`, que se usa para establecer cookies en la ubicación correcta cuando el sufijo de un dominio de origen contenía un punto adicional (como `example.co.uk`). Las versiones actuales de AppMeasurement detectan automáticamente el dominio correcto, lo que hace que esta variable quede obsoleta.
* **`trackingServer`**: se especificó el dominio usado para enviar datos a Adobe a través de HTTP. Está en desuso a favor de la recopilación de datos seguros sobre HTTPS. Utilice [`trackingServerSecure`](trackingserversecure.md) en su lugar.
* **`trackInlineStats`**: se habilitaron o deshabilitaron las versiones anteriores de [Activity Map](/help/analyze/activity-map/overview.md).
* **`visitorMigrationKey`**: llevaba una clave utilizada para migrar visitantes de cookies de terceros a cookies de origen. Se ha retirado porque las bibliotecas modernas establecen una cookie de reserva propia (`fid`) y dependen del servicio de Experience Cloud ID para su identidad.
* **`visitorMigrationServer`**: se especificó el servidor utilizado durante la migración de cookies de terceros a cookies de origen.
* **`visitorMigrationServerSecure`**: el equivalente HTTPS de `visitorMigrationServer`.
* **`visitorNameSpace`**: ayudó a determinar el dominio de cookies de terceros. Se sustituye por el uso de la variable [`trackingServerSecure`](trackingserversecure.md) en implementaciones que no utilizan el servicio de Experience Cloud ID.
