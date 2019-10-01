---
description: This Adobe® Data Connectors™ email integration combines behavioral information from Analytics® with email marketing to create a powerful tool to redefine success measurement and target audiences with more relevant messaging.
seo-description: Esta integración de correo electrónico de Adobe® Data Connectors™ combina la información de comportamiento de Analytics® con la mercadotecnia por correo electrónico para crear una poderosa herramienta que permite redefinir la medición del éxito y dirigir a las audiencias con mensajes más relevantes.
seo-title: Conector de datos de DreamMail para Adobe Analytics
title: Conector de datos de DreamMail para Adobe Analytics
uuid: f6c01bf8-4e6a-4163-9d41-f24fb5f06bdc
translation-type: tm+mt
source-git-commit: 34b18e7769e0850283fd3840c2557818d5d742f0

---


# DreamMail Data Connector for Adobe Analytics{#dreammail-data-connector-for-adobe-analytics}

Esta integración de correo electrónico de Adobe® Data Connectors™ combina la información de comportamiento de Analytics® con la mercadotecnia por correo electrónico para crear una poderosa herramienta que permite redefinir la medición del éxito y dirigir a las audiencias con mensajes más relevantes.

El envío de mensajes de correo electrónico relevantes a estos segmentos de mercado puede generar oportunidades de ingresos completamente nuevas, lo que aumenta la conversión y los ingresos entre las campañas de correo electrónico nuevas y existentes. Por ejemplo: el envío de mensajes de correo electrónico relevantes basados en productos que se vieron durante una visita o productos que quedaron en un carro de compras abandonado ha demostrado tener un impacto dramático en los ingresos, con un impacto mínimo en el costo porque esto simplemente aprovecha los visitantes que el sitio ya está recibiendo.

Este aumento en la eficacia de la mercadotecnia es uno de los beneficios clave de la integración [!DNL Analytics] con el [!DNL ~socio~]. Additionally, this integration will automatically synchronize email metrics with [!DNL Analytics] data as frequently as hourly for closed-loop reporting.

## Principales ventajas y características{#key-benefits-and-features}

Esta integración incluye las siguientes ventajas clave:

* Consolide los datos de marketing y análisis de correo electrónico en una interfaz de informes.
* Optimizar las campañas de correo electrónico según la conversión y la contribución a los ingresos y al éxito del sitio.
* Re-market to key visitors and market segments based on dynamic marketing segments.

## Segmentos de marketing dinámico{#dynamic-marketing-segments}

Esta integración incluye los siguientes segmentos dinámicos de marketing:

* **** Purchase Profiles: Increase repeat orders and average order value through campaigns targeted by visitor purchase patterns.
* **** Perfil de comportamiento de vista de contenido/producto: Llegar a los clientes potenciales a través de segmentos de marketing basados en vistas de productos y perfiles de acceso a contenido.
* **** Perfil de abandono del carro de compras: Ayudar a los visitantes a convertirse a clientes a través de campañas específicas diseñadas específicamente para aquellos que dudan en completar los carros.
* Los clientes también pueden crear y programar segmentos de remercadotecnia personalizados específicos de las necesidades de sus usuarios.

## Antes de activar{#before-you-activate}

Antes de iniciar la integración de Conectores de datos para , complete los siguientes requisitos:

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **** Específico del grupo de informes: Tenga en cuenta que esta integración es específica del grupo de informes. Ensure that you have selected the desired report suite prior to activating the integration.
* **** Variables de Analytics disponibles y configuradas: Esta integración requiere eventos personalizados y eVars personalizadas, y, opcionalmente, eventos adicionales y eVars adicionales.

* **** Representante autorizado: Tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara que es un representante autorizado de su empresa; y como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.
* **** Almacén de datos™: Esta integración requiere que el almacén de datos esté habilitado para generar segmentos de remercadotecnia. Si no ha habilitado el almacén de datos, póngase en contacto con Adobe para obtener más información.
* **[!DNL ~~Socio]**: La integración requiere que captemos y almacenemos una dirección de correo electrónico en una variable de Analytics (eVar). El " [!DNL ~socio~]" está asociado con el comportamiento de los visitantes que siguen el flujo en el sitio (abandonos del carro de compras, compras, etc.) that is pulled into the Partner system and can be leveraged for remarketing purposes. [!DNL ~~] As part of the setup process, you must identify an eVar for this purpose when prompted by the Wizard.
* **** External Tracking: If you’re not currently following the best practice of enabling external tracking for each email campaign you send, you must do so to ensure a successful integration. See the Partner section below for details.[!DNL ~~]
* **** Privacy Compliance: You should understand that by enabling Recipient or Visitor ID tracking, this feature may track personally identifiable information of your site visitors. This has privacy implications requiring the implementation of appropriate procedures by your organization, such as providing notice to, and consent of, your site visitors.

## Precio{#pricing}

 Be advised that the enablement of this integration might cause your company to incur fees in accordance with your service agreement with Adobe, Inc. or your service agreement with one of Adobe's trusted partners, as applicable.

By activating this integration, you hereby represent that you are an authorized representative of your company; and as such, your company agrees to pay the fees, if any, set forth in the service agreement described above.

### Adobe Pricing Considerations {#section-1f4f46c0d969435db57d38c1c310a05a}

There might be recurring and implementation fees associated with this integration, including cost for an increased number of server calls incurred through this integration. Póngase en contacto con su representante de cuentas de Adobe para obtener más información sobre los precios.

### ~Consideraciones de precios de socio~{#section-f8ca71df32224412a5101efb6e356529}

Esta integración podría tener tasas recurrentes y de implementación. Póngase en contacto [!DNL DreamMail] para obtener detalles sobre los precios.

## Analytics Integration Variables{#analytics-integration-variables}

Esta integración requiere variables de Analytics para realizar un seguimiento de las métricas.

Después de identificar el evento y las eVars que se van a usar con esta integración, deben habilitarse en la Consola de administración de Analytics (para obtener instrucciones, consulte Grupos [de informes](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) ).
