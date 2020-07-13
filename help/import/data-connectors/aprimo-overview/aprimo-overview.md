---
description: Esta integración de correo electrónico de Adobe® Data Connectors™ combina la información de comportamiento de Adobe Analytics® con el marketing por correo electrónico para crear una completa herramienta que permite redefinir la medición de éxito y las audiencias de destino con mensajes más relevantes.
title: Data Connectors de Aprimo para Adobe Analytics
uuid: 590ded4b-b250-43b4-9cec-68508b853e00
translation-type: tm+mt
source-git-commit: 0fed9fd179feadae26a364a2ca79ac396251e8f6
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 98%

---


# Data Connectors de Aprimo para Adobe Analytics {#aprimo-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>La tecnología del conector de datos de Adobe estará al final de su vida útil desde mediados hasta finales de 2021. [Más información...](/help/import/data-connectors/data-connectors-eol.md)

Esta integración de correo electrónico de Adobe® Data Connectors™ combina la información de comportamiento de Adobe Analytics® con el marketing por correo electrónico para crear una completa herramienta que permite redefinir la medición de éxito y las audiencias de destino con mensajes más relevantes.

El envío de mensajes de correo electrónico relevantes a estos segmentos de mercado puede generar oportunidades de ingresos completamente nuevas, lo que aumenta la conversión y los ingresos entre las campañas de correo electrónico nuevas y existentes. Por ejemplo: el envío de mensajes de correo electrónico relevantes basados en productos que se vieron durante una visita o productos que quedaron en un carro de compras abandonado ha demostrado tener un impacto significativo en los ingresos, con un impacto mínimo en los costes porque esto simplemente aprovecha los visitantes que el sitio ya está recibiendo.

Este aumento en la eficacia del marketing es uno de las ventajas clave de la integración de [!DNL Adobe Analytics] con Aprimo. Además, esta integración sincroniza automáticamente las métricas de correo electrónico con los datos de [!DNL Adobe Analytics] a cada hora para los informes de bucle cerrado.

## Ventajas y características principales {#key-benefits-and-features}

Esta integración incluye las siguientes ventajas clave:

* Consolidar los datos de análisis y marketing por correo electrónico en una interfaz de informes.
* Optimizar las campañas de correo electrónico según la conversión y la contribución a los ingresos y al éxito del sitio.
* Volver a enviar marketing a visitantes clave y segmentos de mercado según segmentos de marketing dinámicos.

## Segmentos de marketing dinámico {#dynamic-marketing-segments}

Esta integración incluye los siguientes segmentos de marketing dinámico:

* **Perfiles de compra:** aumente los pedidos repetidos y el valor promedio de los pedidos a través de campañas dirigidas por patrones de compra de visitantes.
* **Perfil de comportamiento de vista de contenido/producto:** llegue a clientes potenciales a través de segmentos de marketing basados en vistas de productos y perfiles de acceso a contenido.
* **Perfil de abandono del carro de compras:** convierta a los visitantes en clientes a través de campañas específicas diseñadas para aquellos que dudan en completar la compra.
* Los clientes también pueden crear y programar segmentos de remarketing personalizados específicos para las necesidades de sus usuarios.

## Antes de activar {#before-you-activate}

Antes de iniciar la integración de Data Connectors para , complete los siguientes requisitos:

### Requisitos de Adobe Analytics {#section-960e70fd2eae4a1cb88a2e4b53a97313}

* **Específico del grupo de informes:** tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración.
* **Variables de Adobe Analytics disponibles y configuradas:** esta integración requiere eventos personalizados, además de eVars personalizadas. Opcionalmente, también eVars y eventos adicionales.
* **Representante autorizado:** tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa y, como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.
* **Data Warehouse™:** esta integración requiere que Data Warehouse esté habilitado para generar segmentos de remarketing. Si no ha habilitado Data Warehouse, póngase en contacto con Adobe para obtener más información.
* **[!UICONTROL Partner~]:** la integración requiere que recopilemos y almacenemos un “[!DNL ~socio~]” dentro de una variable de Adobe Analytics (eVar). Este ID es una representación numérica o codificada de una dirección de correo electrónico desde el sistema de[!DNL ~Partner~]. Este “[!DNL ~socio~]” está asociado con el comportamiento de los visitantes que siguen el flujo en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora al sistema de[!DNL ~Partner~]y se puede aprovechar para fines de remarketing. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el asistente lo solicite.
* **Seguimiento externo:** si actualmente no realiza las prácticas recomendadas de habilitar el seguimiento externo para cada campaña de correo electrónico que envía, debe hacerlo para garantizar una integración sin problemas. Consulte la sección [!DNL ~Partner~] más abajo para obtener más información.
* **Respeto de la privacidad:** debe comprender que, al habilitar el seguimiento de ID de visitante o destinatario, esta función puede rastrear información personal de los visitantes del sitio. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de su organización, como por ejemplo, notificar a los visitantes del sitio y obtener su consentimiento.

## Precio {#pricing}

Tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda.

Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa y, como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.

### Consideraciones sobre los precios de Adobe {#section-1f4f46c0d969435db57d38c1c310a05a}

Esta integración podría incluir cobros periódicos y de implementación, incluido el coste de un mayor número de llamadas al servidor realizadas a través de esta integración. Póngase en contacto con su representante de cuentas de Adobe para obtener más información.

### Consideraciones de precios de ~Partner~ {#section-f8ca71df32224412a5101efb6e356529}

Esta integración podría incluir cobros periódicos y de implementación. Póngase en contacto con [!DNL ~Partner~] para obtener más información sobre los precios.

## Variables de Adobe Analytics {#adobe-analytics-variables}

Esta integración requiere variables de Adobe Analytics para realizar un seguimiento de las métricas.

Después de identificar el evento y las eVars que se van a usar con esta integración, deben habilitarse en la Admin Console de Adobe Analytics (para obtener instrucciones, consulte [Grupos de informes](https://docs.adobe.com/content/help/es-ES/analytics/admin/manage-report-suites/report-suites-admin.html)).
