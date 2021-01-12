---
description: Esta integración de correo electrónico de Adobe® Data Connectors combina la información de comportamiento de Adobe Analytics® con el marketing por correo electrónico de Datran para crear una herramienta potente que permite redefinir la medición de éxito y las audiencias de destino con mensajes más relevantes.
title: Data Connectors de Datran para Adobe Analytics
uuid: f97655c4-9623-4d06-a3c6-894246eba80f
translation-type: tm+mt
source-git-commit: 3850dc3503ca57ba4f13f0de63e8420e484db501
workflow-type: tm+mt
source-wordcount: '952'
ht-degree: 98%

---


# Data Connectors de Datran para Adobe Analytics {#datran-data-connector-for-adobe-analytics}

>[!IMPORTANT]
>
>El 1 de agosto de 2021 terminaremos de usar la tecnología del conector de datos de Adobe. [Más información...](/help/import/data-connectors/data-connectors-eol.md)

Esta integración de correo electrónico de Adobe® Data Connectors combina la información de comportamiento de Adobe Analytics® con el marketing por correo electrónico de Datran para crear una herramienta potente que permite redefinir la medición de éxito y las audiencias de destino con mensajes más relevantes.

El envío de mensajes de correo electrónico relevantes a estos segmentos de mercado puede generar oportunidades de ingresos completamente nuevas, lo que aumenta la conversión y los ingresos entre las campañas de correo electrónico nuevas y existentes. Por ejemplo: el envío de mensajes de correo electrónico relevantes basados en productos que se vieron durante una visita o productos que quedaron en un carro de compras abandonado ha demostrado tener un impacto significativo en los ingresos, con un impacto mínimo en los costes porque esto simplemente aprovecha los visitantes que el sitio ya está recibiendo. Este aumento en la eficacia del marketing es una de las ventajas clave de la integración de Adobe Analytics con Datran. Además, esta integración sincroniza automáticamente las métricas de correo electrónico con los datos de Adobe Analytics a cada hora para los informes de bucle cerrado.

## Ventajas principales {#key-benefits}

Esta integración incluye las siguientes ventajas clave:

* Consolidar los datos de análisis y marketing por correo electrónico en una interfaz de informes.
* Optimizar las campañas de correo electrónico según la conversión y la contribución a los ingresos y al éxito del sitio.
* Volver a enviar marketing a visitantes clave y segmentos de mercado según segmentos de marketing dinámico.

## Segmentos de marketing dinámico {#dynamic-marketing-segments}

Esta integración de correo electrónico de Data Connectors admite segmentos de marketing dinámico para ayudarle a dirigir sus objetivos empresariales.

Esta integración incluye los siguientes segmentos de marketing predeterminados:

* **Perfiles de compra:** aumente los pedidos repetidos y el valor promedio de los pedidos a través de campañas dirigidas por patrones de compra de visitantes.
* **Perfil de comportamiento de vista de contenido/producto:** llegue a clientes potenciales a través de segmentos de marketing basados en vistas de productos y perfiles de acceso a contenido.
* **Perfil de abandono del carro de compras:** convierta a los visitantes en clientes a través de campañas específicas diseñadas para aquellos que dudan en completar la compra.
* Los clientes también pueden crear y programar segmentos de remarketing personalizados específicos para las necesidades de sus usuarios.

## Procedimiento de integración y requisitos previos {#integration-procedure-and-prerequisites}

Mediante el uso de un asistente de “Plug and Play”, los procesos intuitivos paso a paso le guían por los puntos de sincronización del sistema e inicializarán la integración.

Esta integración de Data Connectors requiere lo siguiente:

### Requisitos previos de Adobe {#section-bce14015fb7f41b3bc754da0eb7567bc}

* Data Warehouse.
* Cuenta de Adobe Analytics.
* Variables de Adobe Analytics disponibles y configuradas, incluidas eVars y eventos personalizados.

### Requisitos previos de Datran {#section-bcb904574ccf42308bcf7a15e45b4d58}

* Cuenta de StormPost activa con correo electrónico habilitado y credenciales de usuario en uso.

Revise la siguiente información sobre esta integración de Data Connectors en relación con Datran:

* **Cuenta válida de Datran:** para utilizar la integración de correo electrónico de Data Connectors, un cliente debe tener una cuenta de Datran válida.
* **Cliente actual de Datran:** esta integración requiere que sea cliente de Adobe y de Datran. Si actualmente no es cliente de Datran, no dispone de la información necesaria para completar el asistente de integración. Si actualmente es cliente de Datran, necesita su ID de cuenta de Datran o el identificador único asignado a su organización, para completar el asistente de integración.
* Póngase en contacto con el administrador de su cuenta para obtener instrucciones sobre la configuración de StormPost.

## Precio {#pricing}

Esta integración de Data Connectors incluye consideraciones de precios que debe tener en cuenta.

Las secciones siguientes contienen más información:

### Consideraciones sobre los precios de Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Esta integración podría incluir cobros periódicos y de implementación. Póngase en contacto con su representante de cuentas de Adobe para obtener más información.

### Consideraciones de precios de Datran {#section-c6afad08c34b43e3a7a3637eea3328c3}

Esta integración podría incluir cobros.

* Envíenos un correo electrónico para obtener información sobre precios a esp@datranmedia.com.

## Qué debe saber antes de activar esta integración {#what-you-should-know-before-activating-this-integration}

Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics® y del software de correo electrónico.

Al hacerlo, se asegura de que las prácticas recomendadas y los requisitos previos adecuados estén implementados antes de la activación, lo que supone una integración óptima y sin problemas.

### Adobe Analytics {#adobe-analytics}

Revise la siguiente información sobre esta integración de Data Connectors en relación con Adobe Analytics:

* **Específico del grupo de informes:** tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración.
* **Representante autorizado:** tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa y, como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.
* **Omniture Data Warehouse™:** esta integración requiere que Data Warehouse esté habilitado para generar segmentos de remarketing. Si no ha habilitado Data Warehouse, póngase en contacto con Adobe para obtener más información.
* **ID de destinatario:** la integración requiere que recopilemos y almacenemos un “ID de visitante” dentro de una variable de Adobe Analytics (eVar). El ID de visitante (denominada con frecuencia como “ID de destinatario”) es una representación numérica o codificada de una dirección de correo electrónico del sistema de Datran. Este “ID de destinatario” está asociado al comportamiento de los visitantes que siguen el flujo de navegación en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora al sistema de Datran y se puede aprovechar para fines de remarketing. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el asistente lo solicite.
* **Seguimiento externo:** si actualmente no realiza las prácticas recomendadas de habilitar el seguimiento externo para cada campaña de correo electrónico que envía, debe hacerlo para garantizar una integración sin problemas. Consulte la sección Datran más abajo para obtener más información.
* **Respeto de la privacidad:** debe comprender que, al habilitar el seguimiento de ID de visitante o destinatario, esta función puede rastrear información personal de los visitantes del sitio. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de su organización, como por ejemplo, notificar a los visitantes del sitio y obtener su consentimiento.
