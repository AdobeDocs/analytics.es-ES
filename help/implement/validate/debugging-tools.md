---
title: Herramientas de depuración para implementaciones de Analytics
description: Inspeccione los datos que su implementación envía a Adobe mediante depuradores de Analytics, herramientas para desarrolladores de exploradores y servidores proxy de depuración HTTP.
keywords: analizador de paquetes, monitor de paquetes, detector de paquetes, depurador, charles, NS_BINDING_ABORTED, sendBeacon
feature: Implementation Basics
exl-id: db077293-f72c-4933-8a30-f1e1963f332e
role: Admin, Developer, Leader
TQID: 'https://experienceleague.adobe.com/debgxI3FK1fp1Q02GY1-0H40z-L4G2HSmq11Tog97-Y'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: a421fb65-2c82-457a-921c-28c46b697a39
    internal-label: Analytics basics
subfeature_v2:
  - id: e992d880-33bc-4949-a648-aa7d410276cd
    internal-label: Validation
  - id: c24fe15a-643a-47bd-8278-5e027df49785
    internal-label: Implementation basics
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
  - id: f8a45b24-4be7-4f1b-909b-60d06b483a20
    internal-label: Leader
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
    internal-label: Developer
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
  - id: d3cdead0-685a-4489-9250-4bb709942f66
    internal-label: Data collection
source-git-commit: 319f78bb5f8c2449a7263e3f1c378c49656889a7
workflow-type: tm+mt
source-wordcount: '991'
ht-degree: 3%
---
# Herramientas de depuración para implementaciones de Analytics

Las herramientas de depuración, a veces denominadas analizadores de paquetes o detectores de paquetes, permiten inspeccionar los datos que la implementación envía a Adobe. Pueden ayudarle a confirmar que las solicitudes se activan correctamente, inspeccionar las variables y las cargas útiles incluidas en esas solicitudes y solucionar problemas de comportamiento de implementación inesperado.

>[!NOTE]
>
>Las herramientas enumeradas en esta página no son completas. Representan herramientas que los clientes de Adobe Analytics han encontrado útiles. Excepto para las herramientas proporcionadas por Adobe, Adobe no admite estos productos ni soluciona sus problemas. Consulte con el editor de la herramienta para obtener información de instalación, uso y asistencia.

## Elegir una herramienta de depuración

Las siguientes categorías pueden ayudarle a seleccionar una herramienta según lo que desee inspeccionar.

| Tipo de herramienta | Útil cuando |
| --- | --- |
| **Depuradores de etiquetas y análisis** | Desea que las variables, etiquetas, capas de datos o solicitudes de recopilación de Analytics se interpreten y presenten en un formato legible en lenguaje natural. |
| **Herramientas para desarrolladores de navegadores** | Está depurando una implementación web y desea inspeccionar las solicitudes de red directamente sin instalar una aplicación de depuración independiente. |
| **HTTP(S) que depuran proxies** | Desea inspeccionar el tráfico HTTP desde navegadores, aplicaciones móviles, vistas web, API u otros clientes, o necesita funcionalidades que vayan más allá de las herramientas para desarrolladores de navegadores. |

## Analytics y depuradores de etiquetas

Los depuradores de etiquetas de Analytics reconocen las tecnologías de Analytics e interpretan sus solicitudes. Estas herramientas pueden facilitar la identificación de variables de Adobe Analytics, cargas útiles de Experience Platform Web SDK, etiquetas e información de implementación relacionada sin descodificar manualmente las solicitudes de red.

| Herramienta | Disponibilidad | Útil para | Consideraciones |
| --- | --- | --- | --- |
| **[Adobe Experience Platform Debugger](https://experienceleague.adobe.com/es/docs/experience-platform/debugger/home)** | Extensión de explorador | Depuración de implementaciones de Adobe Experience Platform y CX Enterprise, incluidas Adobe Analytics, etiquetas, capas de datos y Experience Platform Web SDK | Herramienta proporcionada por Adobe centrada en las tecnologías de Adobe |
| **[Omnibug](https://omnibug.io)** | Navegadores basados en Chromium y Firefox | Descodificación de Adobe Analytics, Experience Platform Web SDK, etiquetas de Adobe y solicitudes de muchos otros proveedores de análisis y marketing | Útil para implementaciones que contienen tecnologías de varios proveedores |
| **[ObservePoint Debugger](https://www.observepoint.com/solutions/observepoint-debugger/)** | CHROME y EDGE | Inspección y descodificación de etiquetas de análisis, marketing y medición, incluidas las solicitudes de Adobe Analytics | Debugger basado en explorador; ObservePoint también ofrece productos de validación de implementación automatizados independientes |
| **[Adobe Experience Platform Assurance](https://experienceleague.adobe.com/es/docs/experience-platform/assurance/home)** | Aplicación web en CX Enterprise | Inspección y validación de eventos de implementaciones de Mobile SDK, y visualización de cómo Edge Network procesa eventos | Herramienta proporcionada por Adobe; conecte la aplicación a una sesión de Assurance para ver sus eventos |

## Herramientas para desarrolladores de navegadores

Todos los exploradores modernos incluyen herramientas para desarrolladores que pueden inspeccionar solicitudes de red, por lo que a menudo no necesita una herramienta independiente para depurar una implementación web. Presione **F12** o **Ctrl+Mayús+I** (Windows y Linux) o **Cmd+Opción+I** (macOS) y, a continuación, seleccione la ficha **Red**. En Safari, primero habilita las características de desarrollador en la configuración **Avanzada** de Safari.

## Depuración de proxies HTTP(S)

Los proxies de depuración HTTP interceptan el tráfico HTTP y HTTPS entre un cliente y un servidor. Resultan útiles cuando las herramientas para desarrolladores de exploradores no proporcionan suficiente visibilidad o cuando la implementación se ejecuta fuera de un explorador web tradicional.

La inspección HTTPS generalmente requiere configurar el cliente para que confíe en un certificado proporcionado por el proxy de depuración. Siga las políticas de seguridad de su organización al instalar certificados o interceptar tráfico cifrado.

| Herramienta | Útil para |
| --- | --- |
| **[Charles](https://www.charlesproxy.com/)** | Inspección del tráfico HTTP(S), de dispositivos móviles, aplicaciones y exploradores |
| **[Fiddler en todas partes](https://www.telerik.com/fiddler/fiddler-everywhere)** | Captura e inspección del tráfico HTTP(S) entre aplicaciones y dispositivos. Distinto del antiguo producto Fiddler Classic. |
| **[Proxy](https://proxyman.com/)** | Inspección y modificación del tráfico HTTP(S) desde navegadores, aplicaciones y dispositivos móviles |
| **[Kit de herramientas HTTP](https://httptoolkit.com/)** | Inspección del tráfico desde aplicaciones, API, entornos de desarrollo y dispositivos móviles, con flujos de trabajo orientados a la depuración de aplicaciones y API |
| **[mitmproxy](https://www.mitmproxy.org/)** | Interceptación, inspección y modificación de HTTP(S) con scripts a través de interfaces web y de línea de comandos. Ideal para usuarios que se sientan cómodos con flujos de trabajo de línea de comandos. |

## Localizar solicitudes de Adobe Analytics

En el caso de implementaciones que envían datos directamente a Adobe Analytics, como AppMeasurement, filtre solicitudes de red para:

```text
/ss/
```

Las solicitudes de recopilación de Adobe Analytics contienen variables de Analytics en la dirección URL o la carga útil de la solicitud. Las solicitudes sin procesar utilizan nombres de parámetros de consulta en lugar de nombres de variables; por ejemplo, eVar1 aparece como `v1` y prop1 aparece como `c1`. Los depuradores de Analytics descodifican estos nombres automáticamente. Para descodificarlos, consulte la [referencia de variable](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference) en la documentación de la API de inserción de datos.

Para ver los códigos de estado HTTP que devuelven los servidores de recopilación de datos de Analytics, consulte [Códigos de respuesta HTTP](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/troubleshooting#http-response-codes) en la documentación de la API de inserción de datos.

En implementaciones que utilizan Adobe Experience Platform Web SDK, filtre las solicitudes de red de:

```text
/ee/
```

Seleccione la solicitud e inspeccione su carga útil para ver los datos enviados a Adobe Experience Platform Edge Network. Web SDK envía datos a Edge Network, que puede reenviar datos a Adobe Analytics y a otros servicios configurados. Al inspeccionar la solicitud del cliente, se verifica lo que el explorador envió a Edge Network; no se confirma por sí solo que los datos hayan sido procesados correctamente por todos los servicios descendentes. Para ver cómo Edge Network procesó un evento, usa [Adobe Experience Platform Assurance](https://experienceleague.adobe.com/es/docs/experience-platform/assurance/home).

## Solicitudes anuladas

Cuando una página sale, el explorador puede cancelar las solicitudes que aún están en curso. Firefox etiqueta estas solicitudes `NS_BINDING_ABORTED`; Chrome y Edge las etiquetan como `(canceled)`. Para mantener las solicitudes visibles después de la navegación, habilita **Conservar el registro** (Chrome y Edge) o **Conservar registros** (Firefox).

Una solicitud cancelada no significa necesariamente que se hayan perdido datos. Es posible que el explorador haya enviado la solicitud completa y haya dejado de esperar solo la respuesta. Las herramientas para desarrolladores de navegadores no suelen mostrar la diferencia, pero un proxy de depuración HTTP sí.

Las solicitudes enviadas con `navigator.sendBeacon()` no se cancelaron durante la navegación. AppMeasurement usa `sendBeacon` para los vínculos de salida y siempre que [`useBeacon`](/help/implement/vars/config-vars/usebeacon.md) esté habilitado. Web SDK lo utiliza para los eventos enviados con [`documentUnloading`](https://experienceleague.adobe.com/en/docs/experience-platform/collection/js/commands/sendevent/documentunloading). Si las solicitudes de seguimiento de vínculos se cancelan con frecuencia, utilice estas opciones.
