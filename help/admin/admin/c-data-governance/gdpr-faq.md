---
description: Preguntas frecuentes sobre la gobernanza de datos de Adobe Analytics
title: Preguntas frecuentes sobre la gobernanza de datos
feature: Data Governance
role: Admin
exl-id: 57399c1b-cf08-405b-8c1b-9d23e4c38716
source-git-commit: 43c39b99cbae3e714b7f017dec14dd02fa350790
workflow-type: ht
source-wordcount: '2042'
ht-degree: 100%

---

# Preguntas frecuentes

+++ **¿De qué modo admite Adobe Analytics las solicitudes de acceso y eliminación de usuarios finales (interesados) validadas por los clientes (responsables del tratamiento de datos)?**

Cuando entren en vigor varias normas de privacidad de datos (RGPD, CCPA), Adobe Analytics admitirá el procesamiento de solicitudes verificadas enviadas por los responsables del tratamiento de datos a la API de Privacidad de datos de Experience Cloud para permitir un proceso más automatizado. La API de privacidad de datos de Adobe se ha diseñado para tramitar las solicitudes de derechos individuales (como las solicitudes de acceso y eliminación) relacionadas con los datos de nuestros clientes almacenados en las soluciones de Adobe Experience Cloud. Resulta flexible y se escala según el número de solicitudes de acceso y eliminación de datos que recibe su compañía por parte de los interesados.

Además, la API de Privacy Service permite que los clientes comprueben el estado de cumplimiento de las solicitudes de acceso y eliminación. Para obtener más información, consulte la documentación de la [API de Privacy Service](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

+++

+++ **¿Quién es el responsable de la recepción, la aceptación y el cumplimiento de las solicitudes de privacidad de datos de los usuarios finales?**

El responsable del tratamiento de datos es el único responsable de recibir y aceptar solicitudes. El responsable del tratamiento de datos valida la identidad del interesado y luego cumple la solicitud. Parte de esta responsabilidad puede implicar contactar con Adobe con los ID de los interesados que pueden estar asociados con los datos almacenados en Adobe Analytics.

Como encargado del tratamiento de datos, Adobe debe proporcionar una asistencia razonable al responsable del tratamiento de datos para procesar las solicitudes verificadas en un plazo de tiempo aceptable.

+++

+++ **¿Cómo averiguan los clientes de Adobe (responsables del tratamiento de datos) qué solicitudes de privacidad de datos se corresponden con qué ID de Adobe Analytics para el procesamiento de la privacidad de datos?**

Los responsables del tratamiento de datos determinan cómo resolver la identidad en las solicitudes de los interesados. Considere la posibilidad de implementar una etiqueta de recuperación de ID de la privacidad de datos de Adobe. Sus equipos de desarrollo ahorran tiempo gracias al uso de la etiqueta de recuperación de ID de la privacidad de datos para capturar los ID de usuario (ID de cookies). A continuación, pueden utilizar nuestra API de privacidad de datos para enviar esos ID de usuario a las soluciones relevantes en Adobe Experience Cloud para el procesamiento de solicitudes de privacidad de datos. La API de privacidad de datos puede admitir una gran variedad de ID de cliente en múltiples soluciones de Adobe.

Si un interesado envía una solicitud junto con un identificador (variable personalizada: prop o eVar), Adobe Analytics analiza todo el historial conservado de los datos recopilados para el identificador proporcionado. Para obtener más información acerca de cómo configurar los ID personalizados almacenados en props o eVars de Analytics, consulte la [documentación de Analytics sobre áreas de nombres](/help/admin/admin/c-data-governance/data-labeling/gdpr-namespaces.md).

+++

+++ **¿Cómo puede ayudar la herramienta gobernanza de datos de Adobe Analytics con el procesamiento de solicitudes de privacidad de datos?**

Gobernanza de datos es una nueva herramienta dentro de Adobe Analytics que proporciona la capacidad de aplicar clasificaciones y controles de datos a los responsables del tratamiento de datos en sus datos de Analytics. Esta nueva herramienta permite que los clientes de Adobe personalicen el procesamiento de sus solicitudes de acceso y eliminación de datos de privacidad de datos. En la consola de Gobernanza de datos, los administradores pueden definir la configuración deseada que debe aplicarse a varias columnas de datos que residen en Adobe Analytics. Una vez que se han definido estas etiquetas, Adobe acepta y procesa cualquier solicitud de acceso de bajada o eliminación según la configuración de etiquetas que desee el cliente. El responsable del tratamiento de datos tiene la obligación de revisar esta configuración de etiquetas y buscar el asesoramiento de sus representantes legales con respecto a ella.

La herramienta gobernanza de datos contiene las siguientes etiquetas de datos:

* **Etiquetas de datos de identidad**: se utilizan para clasificar los datos que pueden identificar a un individuo tanto de forma directa como en combinación con otros datos. (Ninguna, I1, I2)

* **Etiquetas de datos confidenciales**: se utilizan para clasificar los datos como datos que pueden definirse como confidenciales según la legislación aplicable. (Ninguna, S1, S2) Tenga en cuenta que, en este momento, el uso de datos confidenciales en Adobe Analytics está generalmente prohibido, a excepción de datos concretos de geolocalización obtenidos de forma adecuada, según la legislación aplicable, los cuales pueden considerarse como datos confidenciales en algunas jurisdicciones.

* **Etiquetas de datos de privacidad de datos**: se utilizan para definir los campos que pueden contener identificadores personales para su uso en solicitudes de privacidad de datos o que deberán eliminarse como parte de una solicitud de eliminación de privacidad de datos. Estas etiquetas pueden superponerse a las etiquetas de Identidad y Datos confidenciales, en algunos casos.

Para obtener más información sobre las etiquetas de gobernanza de datos, consulte [Etiquetas de privacidad de datos para variables de Analytics](/help/admin/admin/c-data-governance/data-labeling/gdpr-labels.md).

+++

+++ **¿Cómo puedo validar que las solicitudes de Privacy Service funcionan correctamente para eliminar datos de Adobe Analytics?**

Normalmente, los clientes de Analytics configuran algunos grupos de informes de prueba para verificar la funcionalidad antes de que se publique al público general. Las aplicaciones o los sitios web de preproducción envían datos a estos grupos de informes de prueba, desarrollo o control de calidad para evaluar cómo funcionará todo cuando el código se publique antes de que el tráfico real se envíe a los grupos de informes de producción.

Sin embargo, con una configuración normal, el procesamiento de solicitudes de RGPD no se puede probar primero en estos grupos de informes de prueba antes de aplicar solicitudes a los grupos de informes de producción. Esto es porque una solicitud amparada en la privacidad de datos se aplica automáticamente a todos los grupos de informes de la organización de Experience Cloud, que a menudo son todos los grupos de informes de su empresa.

Con todo, hay varias maneras de probar el procesamiento de privacidad de datos antes de aplicarlo a todos los grupos de informes:

* Una opción consiste en configurar una organización de Experience Cloud independiente que solo contenga grupos de informes de prueba. A continuación, utilice esta organización de Experience Cloud para sus pruebas de privacidad de datos y su organización normal de Experience Cloud para el procesamiento real de la privacidad de datos.

* Otra opción consiste en asignar diferentes áreas de nombres a los ID en los grupos de informes de prueba, frente a los de los grupos de informes de producción. Por ejemplo, puede utilizar el prefijo “qa-” en cada área de nombres en los grupos de informes de prueba. Al enviar solicitudes de privacidad de datos con solo áreas de nombres con el prefijo qa, estas solicitudes se ejecutarán únicamente en los grupos de informes de prueba. Más adelante, cuando envíe solicitudes sin el prefijo qa, se aplicarán a los grupos de informes de producción. **Este es el método recomendado, a menos que utilice las áreas de nombres visitorId, AAID, ECID o customVisitorId. Estas áreas de nombres están codificadas y no se pueden especificar nombres alternativos en los grupos de informes de prueba.**

+++

+++ **¿Por dónde empiezo con la preparación para la privacidad de datos con Adobe Analytics?**

Para obtener un tutorial paso a paso con el fin de prepararse para el reglamento de privacidad de datos, consulte [Flujo de trabajo de privacidad de datos de Adobe Analytics](/help/admin/admin/c-data-governance/an-gdpr-workflow.md).

+++

+++ **¿Cómo deberían ver el consentimiento los responsables del tratamiento de datos cuando se habla de la participación del usuario?**

El RGPD y la CCPA son buenas oportunidades para reconsiderar su estrategia y prácticas de gestión del consentimiento. Esto incluye determinar cuándo se necesita consentimiento y pensar acerca de la propuesta de valor para el usuario. Considere la proposición de valor para la privacidad del consumidor, que puede ayudar a conseguir la conversión y la lealtad. El espacio de gestión del consentimiento (por ejemplo, herramientas, estándares, prácticas recomendadas) evoluciona rápidamente y es un área a tener en cuenta. Para minimizar el impacto en la participación del usuario, los responsables del tratamiento deben trabajar con los proveedores en este espacio, así como con sus asesores legales, para asegurarse de que están siguiendo las leyes y directrices emergentes sobre consentimiento y cookies. Una buena estrategia es considerar la “privacidad como una experiencia” mediante el uso de una experiencia relevante contextualmente para la marca que ofrezca una proposición de valor en sus actividades de recopilación de datos.

Usted, como responsable del tratamiento de datos, es el responsable de obtener un consentimiento explícito por parte de los interesados antes de recopilar datos acerca de ellos (que posiblemente incluyan datos de Adobe Analytics) y de implementar un [mecanismo de exclusión](https://www.adobe.com/es/privacy/opt-out.html#customeruse) en su sitio web. Esto permite que los interesados queden excluidos de la recopilación de datos futura de Adobe Experience Cloud.

+++

+++ **¿Cómo deberían plantearse los responsables del tratamiento la retención de datos en términos de la privacidad de datos?**

En general, los datos personales no se deben conservar más tiempo del que sea necesario para lograr el propósito para el que se han recopilado. Las condiciones generales de Adobe aplican un plan de retención de datos predeterminado de 25 meses, a menos que se acuerde contractualmente un plazo distinto. Es necesario que los clientes establezcan su política de retención de datos para que Adobe pueda procesar las solicitudes de privacidad de datos.

La política de retención de datos actual de cada grupo de informes se muestra en la nueva interfaz de usuario de la administración de la gobernanza de datos. Los clientes que necesiten modificar su política de retención de datos deberán ponerse en contacto con su representante de Adobe. Consulte el artículo [Preguntas frecuentes de retención de datos de Adobe Analytics](https://experienceleague.adobe.com/docs/analytics/technotes/data-retention.html?lang=es).

+++

+++ **¿Un cliente puede reducir o ampliar el período de retención de datos predeterminado?**

Los clientes pueden solicitar que sus datos se eliminen antes de que concluya el periodo de 25 meses llamando al Servicio de atención al cliente. Los clientes también pueden ampliar dicha retención de datos a más de 25 meses comprando una extensión. Las extensiones están disponibles en incrementos de 1 año adicional, hasta un máximo de 8 años adicionales, lo que hace un total de 10 años. Estas extensiones implicarán la actualización de las condiciones del contrato y la aplicación de tarifas adicionales.

+++

+++ **¿Qué consideraciones de privacidad debe tener en cuenta el responsable del tratamiento de datos cuando se exportan datos personales desde Adobe Analytics?**

Si un cliente utiliza las fuentes de datos de Adobe Analytics para exportar datos desde Analytics a su almacén de datos empresarial o a otros sistemas fuera de Adobe, es responsabilidad del cliente (del tratamiento de datos) garantizar que se apliquen las solicitudes de eliminación de los datos. Esto también es aplicable en las implementaciones locales de Adobe Data Workbench, donde una fuente de datos constante de Adobe Analytics introduce datos en Data Workbench. Adobe puede proporcionar herramientas para encontrar y eliminar los registros de ciertos tipos de fuentes de datos, incluidas aquellas utilizadas para Data Workbench, pero sigue siendo responsabilidad del cliente (del tratamiento de datos) garantizar que los datos se eliminan de forma coherente con sus propias políticas internas de retención y eliminación de datos.

También debe tener en cuenta los casos en los cuales los empleados hayan descargado informes de Adobe Analytics que contengan datos personales. Es posible que se deban actualizar o eliminar estos informes si se recibe una solicitud de eliminación de privacidad de datos relacionada con un ID presente en el informe. Los clientes deben colaborar con el asesor legal de su propia compañía para determinar los períodos de retención y los requisitos de privacidad y seguridad que deberán aplicarse a este tipo de documentos.

+++

+++ **Se han enviado por error a Adobe Analytics algunos datos que no debíamos recopilar. ¿Podemos usar la API de privacidad de datos para borrar dichos datos?**

La [API de Privacy Service de datos](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) se proporciona para ayudarle a completar las solicitudes de privacidad de datos, que suelen ser urgentes. Adobe no admite el uso de esta API para otros fines, y ello puede afectar a la capacidad de Adobe para proporcionar el retorno puntual de solicitudes de privacidad de datos iniciadas por los usuarios y de alta prioridad a otros clientes de Adobe.

Le rogamos que no use la API de privacidad de datos para otros fines, por ejemplo, para borrar datos que se hayan enviado por error a grupos de visitantes grandes. También debe tener en cuenta que cualquier información de estado de un visitante del cual se elimine una visita (actualizada o anonimizada) se restablecerá como resultado de una solicitud de eliminación de privacidad de datos. La próxima vez que el visitante vuelva a su sitio web, lo hará como visitante nuevo. Toda atribución de eVar partirá de cero, al igual que los detalles relativos al número de visitas, los referentes, la primera página visitada, etc. Este efecto colateral no es deseable en los casos en los que quiera borrar campos de datos, lo que a su vez representa uno de los motivos por los que la API de privacidad de datos no es apropiada para este uso.

Póngase en contacto con el equipo de cuentas de Adobe para que el equipo de consultoría de arquitectura de ingeniería realice una revisión más exhaustiva para eliminar cualquier problema con la información o los datos personales.

+++

+++ **Nuestro equipo legal ha determinado que algunos valores que llevamos años recopilando en una variable ya no cumplen nuestra política de privacidad actualizada. ¿Podemos usar la API de privacidad de datos para borrar todos los valores de esta variable?**

La [API de Privacy Service de datos](https://developer.adobe.com/experience-platform-apis/references/privacy-service/) se proporciona para ayudarle a completar las solicitudes de privacidad de datos, que suelen ser urgentes. Adobe no admite el uso de esta API para otros fines, y ello puede afectar a la capacidad de Adobe para proporcionar el retorno puntual de solicitudes de privacidad de datos iniciadas por los usuarios y de alta prioridad a otros clientes de Adobe. Le rogamos que no use la API de privacidad de datos para otros fines, por ejemplo, para borrar datos que se hayan enviado por error a grupos de visitantes grandes.

También debe tener en cuenta que cualquier información de estado de un visitante del cual se elimine una visita (actualizada o anonimizada) se restablecerá como resultado de una solicitud de eliminación de privacidad de datos. La próxima vez que el visitante vuelva a su sitio web, lo hará como visitante nuevo. Toda atribución de eVar partirá de cero, al igual que los detalles relativos al número de visitas, los referentes, la primera página visitada, etc. Este efecto colateral no es deseable en los casos en los que quiera borrar campos de datos, lo que a su vez representa uno de los motivos por los que la API de privacidad de datos no es apropiada para este uso.

Póngase en contacto con su equipo de cuentas de Adobe para que se coordine con nuestro equipo de consultoría encargado de la arquitectura de ingeniería para revisar más a fondo y proporcionar el nivel de esfuerzo necesario para eliminar cualquier problema relacionado con la información de identificación personal o los datos.

+++

Recursos adicionales de privacidad de datos:

* [Términos comunes del RGPD](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_commonterms.pdf)
* [Paquete de atención](https://landing.adobe.com/dam/uploads/2018/in/adobe_gdpr_carepackage.pdf) de privacidad de datos de Experience Cloud
* Privacidad de la experiencia [Publicación en el blog](https://theblog.adobe.com/experiential-privacy-an-investment-opportunity-for-the-experience-business/)
