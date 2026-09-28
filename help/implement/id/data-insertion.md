---
title: Identificación de visitante mediante la API de inserción de datos
description: Identifique a los visitantes para la recopilación de datos directa y del lado del servidor de Adobe Analytics con la API de inserción de datos.
feature: Implementation Basics
role: Admin, Developer, Leader
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
    internal-label: API
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
    internal-label: Functions
  - id: e7d92df1-c5ba-4e93-85df-f83171b889be
    internal-label: Variables
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '874'
ht-degree: 0%
---
# Identificación de visitante mediante la API de inserción de datos

La [API de inserción de datos](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) envía visitas a servidores de recopilación de Adobe Analytics sin una biblioteca del lado del cliente como AppMeasurement o Web SDK. Dado que no hay ninguna biblioteca para administrar la identidad, el identificador de visitante se establece por su cuenta, en el explorador para solicitudes de imagen directas o en el servidor para la recopilación del lado del servidor.

>[!NOTE]
>
>Esta página describe la identidad de los visitantes. Para generar y enviar las propias solicitudes, consulte la [documentación de la API de inserción de datos](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/) en Adobe Developer.

Adobe identifica a un visitante que usa el [orden de operaciones](overview.md) estándar: el `vid`, después el `aid`, `mid`, `fid` y, por último, la dirección IP y el agente de usuario. Con la API de inserción de datos, normalmente establece uno de los tres identificadores directamente: el ECID (`mid`), el ID de visitante de Analytics (`aid`) o un ID de visitante personalizado (`vid`).

## Uso del ECID (recomendado)

El ECID (enviado como `mid`) es el identificador de visitante moderno entre soluciones que se comparte en Adobe Analytics, Adobe Target y Adobe Audience Manager. Adobe recomienda utilizarlo siempre que sea posible.

Obtenga el ECID con el [servicio de ID de visitante](https://experienceleague.adobe.com/es/docs/id-service/using/home) (`VisitorAPI.js`). En un explorador, inicialice el servicio con su ID de organización de IMS usando [`getInstance`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getinstance) y, a continuación, lea el ECID con [`getMarketingCloudVisitorID`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getmcvid):

```js
var visitor = Visitor.getInstance("YOUR_ORG_ID@AdobeOrg");
var ecid = visitor.getMarketingCloudVisitorID();
```

Envíe ese valor en cada visita como el parámetro de consulta `mid`, junto con su ID de organización de IMS como el parámetro `mcorgid`, de modo que el ECID se resuelva correctamente. Si los datos se reenvían a Audience Manager, envíe también la región de [`getLocationHint`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/getlocationhint) como el parámetro `aamlh`. Para asociar sus propios identificadores de cliente con el visitante, use [`setCustomerIDs`](https://experienceleague.adobe.com/en/docs/id-service/using/id-service-api/methods/setcustomerids).

Para la recopilación del lado del servidor, obtenga el ECID en el cliente y reenvíelo a su servidor para que lo envíe en cada visita. Para generar un ECID completamente del lado del servidor, sin un cliente, use la [integración directa](https://experienceleague.adobe.com/en/docs/id-service/using/implementation/direct-integration) del servicio de ID.

## Uso del ID de visitante de Analytics

El identificador de visitante de Analytics (`aid`) se almacena en la cookie [`s_vi`](https://experienceleague.adobe.com/en/docs/core-services/interface/data-collection/cookies/analytics). Cuando llega una visita sin un identificador, el servidor de recopilación asigna un `aid` e intenta establecer una cookie que contenga ese identificador. Algunos [tipos de respuesta](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) también incluyen este identificador en el cuerpo de respuesta.

* **Lado del cliente (solicitudes de imagen directas).** El explorador almacena la cookie `s_vi` que devuelve el servidor y la envía en cada solicitud posterior al mismo dominio de recopilación. El visitante se reconoce automáticamente, sin que `aid` se establezca a sí mismo. Dado que este modelo depende de las cookies, lleva los mismos límites de durabilidad que cualquier identidad basada en cookies. Consulte la [Identificación de visitantes con AppMeasurement](appmeasurement.md) para ver el comportamiento de las cookies de origen frente a las de terceros, y el [orden de operaciones](overview.md) para ver cómo Adobe elige qué identificador utilizar. Adobe recomienda utilizar un ECID para la identidad duradera.

  >[!NOTE]
  >
  >Si lee el identificador de visitante directamente de la cookie `s_vi`, la cookie incluirá el identificador en datos adicionales (por ejemplo, `[CS]v1|<id>[CE]`), con lo que solo se extraerá la parte `<id>`. Leer el ID de una respuesta de visitante lo devuelve directamente, sin análisis.

* **Lado del servidor.** Un servidor no tiene un JAR de cookies, por lo que debe almacenar y reenviar `aid` usted mismo, con la clave para el usuario:

  1. Busque el(la) `aid` almacenado(a) para el usuario.
  1. Si tiene uno, envíelo como parámetro de consulta `aid`.
  1. Si no lo hace, envíe la visita sin identificador y solicite un tipo de respuesta que devuelva el(la) `aid` asignado(a) y, a continuación, guárdelo para la próxima vez.

  La primera visita sin identificador ya se atribuye al `aid` que devuelve el servidor, por lo que no pierde datos al enviarlo antes de tener un ID. Para los tipos de respuesta que devuelven el identificador (`3` para JavaScript, `11` para XML, `10` para JSON) y el formato de solicitud, consulte [Tipo de respuesta](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/response-types) en la documentación de la API de inserción de datos.

  Una solicitud del lado del servidor no lleva cookies de visitante, y su propia dirección IP y agente de usuario pertenecen al remitente. Para atribuir las visitas correctamente, reenvíe también la dirección IP real del visitante (el encabezado `X-Forwarded-For`) y el agente de usuario (el encabezado `User-Agent`).

## Uso de un ID de visitante personalizado

Si ya tiene un identificador duradero que controla completamente, puede enviarlo como [`visitorID`](/help/implement/vars/config-vars/visitorid.md) (`vid`) en cada visita individual y en cada identidad propia de extremo a extremo. Esto se adapta a las plataformas que no son de explorador y que proporcionan un identificador de dispositivo estable. Por ejemplo, una aplicación Unity puede enviar su identificador de dispositivo como `vid`.

>[!IMPORTANT]
>
>Use `vid` solo cuando pueda garantizar un valor estable en cada visita:
>
>* **Los exploradores no encajan bien.** Un explorador no tiene un identificador duradero que se pueda rellenar de forma fiable, por lo que un explorador `vid` tiende a fragmentarse o chocar. En su lugar, utilice el modelo del lado del cliente basado en cookies.
>* **Tenga cuidado con los identificadores de autenticación.** No tiene ningún identificador antes de que un usuario inicie sesión y, si lo hace, las visitas posteriores se atribuyen a un visitante diferente. Estas acciones dividen la actividad de una persona entre varios visitantes.

Consulte [`visitorID`](/help/implement/vars/config-vars/visitorid.md) para conocer el formato y las restricciones de un ID de visitante personalizado.
