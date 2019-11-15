---
description: Esta integración de correo electrónico de Adobe® Data Connectors™ combina la información de comportamiento de Analytics® con la mercadotecnia por correo electrónico para crear una poderosa herramienta que permite redefinir la medición del éxito y dirigir a las audiencias con mensajes más relevantes.
title: Conector de datos de DreamMail para Adobe Analytics
uuid: f6c01bf8-4e6a-4163-9d41-f24fb5f06bdc
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# DreamMail Data Connector for Adobe Analytics{#dreammail-data-connector-for-adobe-analytics}

Esta integración de correo electrónico de Adobe® Data Connectors™ combina la información de comportamiento de Analytics® con la mercadotecnia por correo electrónico para crear una poderosa herramienta que permite redefinir la medición del éxito y dirigir a las audiencias con mensajes más relevantes.

El envío de mensajes de correo electrónico relevantes a estos segmentos de mercado puede generar oportunidades de ingresos completamente nuevas, lo que aumenta la conversión y los ingresos entre las campañas de correo electrónico nuevas y existentes. Por ejemplo: el envío de mensajes de correo electrónico relevantes basados en productos que se vieron durante una visita o productos que quedaron en un carro de compras abandonado ha demostrado tener un impacto dramático en los ingresos, con un impacto mínimo en el costo porque esto simplemente aprovecha los visitantes que el sitio ya está recibiendo.

Este aumento en la eficacia de la mercadotecnia es uno de los beneficios clave de la integración [!DNL Analytics] con el [!DNL ~socio~]. Además, esta integración sincronizará automáticamente las métricas de correo electrónico con [!DNL Analytics] los datos con la misma frecuencia y hora en los informes de bucle cerrado.

## Ventajas y características principales{#key-benefits-and-features}

Esta integración incluye las siguientes ventajas clave:

* Consolide los datos de marketing y análisis de correo electrónico en una interfaz de informes.
* Optimizar las campañas de correo electrónico según la conversión y la contribución a los ingresos y al éxito del sitio.
* Volver a comercializar a visitantes clave y segmentos de mercado según segmentos de mercadotecnia dinámicos.

## Segmentos de marketing dinámico{#dynamic-marketing-segments}

Esta integración incluye los siguientes segmentos dinámicos de marketing:

* **** Perfiles de compra: Aumentar los pedidos repetidos y el valor promedio de los pedidos a través de campañas dirigidas por patrones de compra de visitantes.
* **** Perfil de comportamiento de vista de contenido/producto: Llegar a los clientes potenciales a través de segmentos de marketing basados en vistas de productos y perfiles de acceso a contenido.
* **** Perfil de abandono del carro de compras: Ayudar a los visitantes a convertirse a clientes a través de campañas específicas diseñadas específicamente para aquellos que dudan en completar los carros.
* Los clientes también pueden crear y programar segmentos de remercadotecnia personalizados específicos de las necesidades de sus usuarios.

## Antes de activar{#before-you-activate}

Antes de iniciar la integración de Conectores de datos para , complete los siguientes requisitos:

## Adobe Analytics Requirements {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **** Específico del grupo de informes: Tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración.
* **** Variables de Analytics disponibles y configuradas: Esta integración requiere eventos personalizados y eVars personalizadas, y, opcionalmente, eventos adicionales y eVars adicionales.

* **** Representante autorizado: Tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa; y como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.
* **** Almacén de datos™: Esta integración requiere que el almacén de datos esté habilitado para generar segmentos de remercadotecnia. Si no ha habilitado el almacén de datos, póngase en contacto con Adobe para obtener más información.
* **[!DNL ~~Socio]**: La integración requiere que captemos y almacenemos una dirección de correo electrónico dentro de una variable de Analytics (eVar). El " [!DNL ~socio~]" está asociado con el comportamiento de los visitantes que siguen el flujo en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora al sistema de [!DNL ~socios~] y se puede aprovechar para fines de remercadotecnia. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el Asistente le solicite.
* **** Seguimiento externo: Si actualmente no está siguiendo la práctica recomendada de habilitar el seguimiento externo para cada campaña de correo electrónico que envía, debe hacerlo para garantizar una integración exitosa. Consulte la sección [!DNL ~Socio~] a continuación para obtener más detalles.
* **** Cumplimiento de la privacidad: Debe comprender que, al habilitar el seguimiento de ID de visitante o destinatario, esta función puede rastrear información personal de los visitantes del sitio. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de su organización, como por ejemplo, notificar a los visitantes del sitio y obtener su consentimiento.

## Precio{#pricing}

 Tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda.

Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa; y como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.

### Consideraciones sobre los precios de Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Esta integración podría tener tasas recurrentes y de implementación, incluido el costo de un mayor número de llamadas al servidor realizadas a través de esta integración. Póngase en contacto con su representante de cuentas de Adobe para obtener más información sobre los precios.

### ~Consideraciones de precios de socio~{#section-f8ca71df32224412a5101efb6e356529}

Esta integración podría tener tasas recurrentes y de implementación. Póngase en contacto [!DNL DreamMail] para obtener más información sobre los precios.

## Analytics Integration Variables{#analytics-integration-variables}

Esta integración requiere variables de Analytics para realizar un seguimiento de las métricas.

Después de identificar el evento y las eVars que se van a usar con esta integración, deben habilitarse en la Consola de administración de Analytics (para obtener instrucciones, consulte Grupos [de informes](https://docs.adobe.com/content/help/en/analytics/admin/manage-report-suites/report-suites-admin.html) ).
