---
description: Esta integración combina la potencia del sistema de comentarios integrado del software de marketing por correo electrónico y los informes de comportamiento de Adobe Analytics para crear potentes oportunidades de optimización y análisis para su organización.
seo-description: Esta integración combina la potencia del sistema de comentarios integrado del software de marketing por correo electrónico y los informes de comportamiento de Adobe Analytics para crear potentes oportunidades de optimización y análisis para su organización.
seo-title: conector de datos de Broadmail de Optivo® para Adobe Analytics
title: conector de datos de Broadmail de Optivo® para Adobe Analytics
uuid: bd713080-9d1a-49ee-aad0-86dd5c37c34a
translation-type: tm+mt
source-git-commit: 8c4c368a84ba5499d85f0b7512c99de47ddb14c2

---


# conector de datos de Broadmail de Optivo® para Adobe Analytics{#optivo-broadmail-data-connector-for-adobe-analytics}

Esta integración combina la potencia del sistema de comentarios integrado del software de marketing por correo electrónico y los informes de comportamiento de Adobe Analytics para crear potentes oportunidades de optimización y análisis para su organización.

[!DNL ~Partner~] es un software profesional de marketing por correo electrónico. Su función principal es crear, enviar y evaluar campañas de newsletter y correo electrónico. `[~Partner~]` está disponible como servicio en la nube (software como servicio).

La `[~Partner~]` integración ofrece remercadotecnia automatizada y sincronización de datos, lo que produce mayores conversiones e ingresos. La integración permite a los especialistas en mercadotecnia sincronizar automáticamente los segmentos de sus clientes, en función de su interacción por correo electrónico y del comportamiento del sitio. El intercambio automatizado de datos de segmentos personalizables le ayuda a crear campañas de correo electrónico con objetivos muy precisos que impulsan las ventas, como el abandono del carro de compras y la remercadotecnia posterior a la compra para productos que se venden, se incrementan y se revenden.

Esta integración también intercambia métricas de campañas de correo electrónico exitosas de `[~Partner~]` a Adobe Analytics. Los datos cruciales se muestran de forma centralizada en la descripción general de la campaña de correo electrónico.

## Programa de Laboratorio de Conectores de Datos {#section-51f9864851b64d96873127b9ac9c9a2b}

Este programa es un método rápido para que los socios de plataformas de terceros de Adobe creen integraciones y las entreguen a nuestro mercado conjunto. Las integraciones son completamente desarrolladas por nuestros socios y están disponibles en Adobe Experience Cloud según las metodologías de la comunidad. Están disponibles sin cargo adicional para los clientes de Adobe de Adobe Analytics y otras soluciones y se proporcionan tal cual sin garantías implícitas de Adobe debido a la naturaleza de terceros de las integraciones.

Si tiene alguna pregunta sobre el servicio actual, la garantía o la licencia, póngase en contacto con el administrador de cuentas de Adobe.

## Principales ventajas y características{#key-benefits-and-features}

Esta integración incluye las siguientes ventajas clave:

* Recuperar compradores que exploran y abandonan
* Aumentar las ventas con remercadotecnia de ventas cruzadas y de incremento de ventas dirigida
* Campañas automáticas basadas en segmentos
* Campañas optimizadas en curso
* Segmentos en [!DNL ~socio~] para remercadotecnia de objetivo
* Actualizaciones constantes de métricas de campaña
* Activadores de conversaciones automatizadas

## Segmentos de marketing dinámico{#dynamic-marketing-segments}

Esta integración incluye los siguientes segmentos dinámicos de marketing:

* **** Perfiles de compra: Aumentar los pedidos repetidos y el valor promedio de los pedidos a través de campañas dirigidas por patrones de compra de visitantes.
* **** Perfil de comportamiento de vista de contenido/producto: Llegar a los clientes potenciales a través de segmentos de marketing basados en vistas de productos y perfiles de acceso a contenido.
* **** Perfil de abandono del carro de compras: Ayudar a los visitantes a convertirse a clientes a través de campañas específicas diseñadas específicamente para aquellos que dudan en completar los carros.
* **** Remercadotecnia efectiva:Los clientes también pueden crear y programar segmentos de remercadotecnia personalizados específicos de las necesidades de sus usuarios.

## Antes de activar{#before-you-activate}

Antes de iniciar la integración de Conectores de datos para , complete los siguientes requisitos:

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **** Específico del grupo de informes: Tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración.
* **** Variables de Adobe Analytics disponibles y configuradas: Esta integración requiere eventos personalizados y eVars personalizadas.

* **** Representante autorizado: Tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara que es un representante autorizado de su empresa; y como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.
* **** ID del mensaje: La integración requiere que captemos y almacenemos un "ID de mensaje" dentro de una variable de Adobe Analytics (eVar). Estos ID son necesarios para identificar los envíos de correo. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el Asistente le solicite.
* **** Socio: La integración requiere que captemos y almacenemos un [!UICONTROL ~socio~] dentro de una variable de Adobe Analytics (eVar). Este ID es una representación numérica o codificada de una dirección de correo electrónico del sistema de [!UICONTROL ~socios~] . Este [!UICONTROL ~socio~] está asociado con el comportamiento de los visitantes intermedios en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora al sistema de [!UICONTROL ~socios~] y se puede aprovechar para fines de remercadotecnia. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el Asistente le solicite.
* **** Hora del anuncio: Como parte del proceso de configuración, esta integración requiere una asignación a una eVar que corresponda al tiempo de una acción posterior al clic. Esto es necesario para transmitir información sobre una acción de destinatario al [!UICONTROL ~socio~] después de que el destinatario haga clic en un vínculo en un correo.

* **** Producto de postclic: Como parte del proceso de configuración, esta integración requiere una asignación a una eVar que corresponda al producto ofrecido que está asociado con una acción posterior al clic. Esto es necesario para transmitir información sobre una acción de destinatario al [!UICONTROL ~socio~] después de que el destinatario haga clic en un vínculo en un correo.

* **** Tipo de acción de postclic: Como parte del proceso de configuración, esta integración requiere una asignación a una eVar que corresponda al tipo de acción de postclic. Esto es necesario para transmitir información sobre una acción de destinatario al [!UICONTROL ~socio~] después de que el destinatario haga clic en un vínculo en un correo.

* **** Cumplimiento de la privacidad: Debe comprender que al habilitar el seguimiento de ID de visitante o destinatario, esta función puede rastrear información personal de los visitantes del sitio. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de su organización, como por ejemplo, notificar a los visitantes del sitio y obtener su consentimiento.

## Precio{#pricing}

 Tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda.

Al activar esta integración, usted declara que es un representante autorizado de su empresa; y como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.

### Consideraciones sobre los precios de Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Los clientes actuales de la solución Adobe Analytics no tienen ningún coste adicional asociado al uso de esta integración de Data Connectors. Los clientes que aún no se hayan trasladado al nuevo producto Adobe Analytics deben ponerse en contacto con su representante de cuentas de Adobe para obtener más información.

### Consideraciones de precios de socio {#section-f8ca71df32224412a5101efb6e356529}

Esta integración está disponible para los clientes [!DNL ~asociados de negocios~] , pero se aplicarán tarifas de integración adicionales. Póngase en contacto con sales@optivo.com para obtener más información sobre los precios. Póngase en contacto con el [!DNL ~socio~] para obtener detalles sobre los precios.

## Variables de Adobe Analytics{#adobe-analytics-variables}

Esta integración requiere variables de Adobe Analytics para rastrear métricas.

Después de identificar el evento y las eVars que se van a usar con esta integración, deben habilitarse en la Consola de administración de Analytics (para obtener instrucciones, consulte Grupos [de informes](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) ).
