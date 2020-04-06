---
description: Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics® y del software de correo electrónico.
title: Antes de activar esta integración
uuid: b911edc6-2265-48ed-9e3c-c79cc20dd9b2
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Antes de activar esta integración {#before-you-activate-this-integration}

Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics® y del software de correo electrónico.

Al hacerlo, se asegura de que las prácticas recomendadas y los requisitos previos adecuados estén implementados antes de la activación, lo que supone una integración óptima y sin problemas.

## Adobe Analytics {#adobe-analytics}

Revise la siguiente información sobre esta integración de Data Connectors en relación con Adobe Analytics:

* **Específico del grupo de informes:** tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de seleccionar el grupo de informes deseado antes de activar la integración.
* **Variables de Analytics disponibles y configuradas:** esta integración requiere 5 eventos personalizados y 2 eVars personalizadas y, opcionalmente, 3 eventos y 3 eVars adicionales. Consulte [Variables de integración de Analytics](/help/import/data-connectors/silverpop-overview/silverpop-variables.md).

* **Representante autorizado:** tenga en cuenta que la activación de esta integración puede provocar que su empresa incurra en gastos de acuerdo con el contrato de servicio con Adobe, Inc. o con el contrato de servicio con uno de los socios de confianza de Adobe, según corresponda. Al activar esta integración, usted declara por la presente que es un representante autorizado de su empresa y, como tal, su empresa se compromete a pagar las tarifas, si las hubiere, establecidas en el contrato de servicio descrito anteriormente.
* **Data Warehouse™:** esta integración requiere que Data Warehouse esté habilitado para generar segmentos de remarketing. Si no ha habilitado Data Warehouse, póngase en contacto con Adobe para obtener más información.
* **ID de destinatario:** la integración requiere que recopilemos y almacenemos un “ID de visitante” dentro de una variable de Analytics (eVar). El ID de visitante (denominada con frecuencia como “ID de destinatario”) es una representación numérica o codificada de una dirección de correo electrónico del sistema de Silverpop. Este “ID de destinatario” está asociado al comportamiento de los visitantes que siguen el flujo de navegación en el sitio (abandonos del carro de compras, compras, etc.) que se incorpora al sistema de Silverpop y puede aprovecharse para fines de remarketing. Como parte del proceso de configuración, debe identificar una eVar para este fin cuando el asistente lo solicite.
* **Seguimiento externo:** si actualmente no realiza las prácticas recomendadas de habilitar el seguimiento externo para cada campaña de correo electrónico que envía, debe hacerlo para garantizar una integración sin problemas. Consulte la sección Silverpop más abajo para obtener más información.
* **Respeto de la privacidad:** debe comprender que, al habilitar el seguimiento de ID de visitante o destinatario, esta función puede rastrear información personal de los visitantes del sitio. Esto tiene implicaciones para la privacidad que requieren la implementación de los procedimientos apropiados por parte de su organización, como por ejemplo, notificar a los visitantes del sitio y obtener su consentimiento.

## Integración de Data Connectors de Silverpop {#silverpop-data-connector-integration}

Revise la siguiente información sobre esta integración de Data Connectors en relación con Silverpop:

* **Cuenta válida de Silverpop:** para utilizar la integración de correo electrónico de Data Connectors, un cliente debe tener una cuenta activa de Silverpop con correo electrónico habilitado y credenciales de usuario activas.
* **Póngase en contacto con su representante de Silverpop**. Silverpop no activa automáticamente esta integración. Debe ponerse en contacto con su representante de Silverpop para iniciar la configuración de Silverpop antes de importar o exportar datos desde Analytics.

>[!NOTE] Esta integración solo funciona con organizaciones de Engage (no con Transact).

## Precio {#pricing}

Esta integración de Data Connectors incluye consideraciones de precios que debe tener en cuenta antes de la activación.

### Consideraciones sobre los precios de Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Esta integración podría incluir cobros periódicos y de implementación. Póngase en contacto con su representante de cuentas de Adobe para obtener más información.

### Consideraciones de precios de Partner {#section-c6afad08c34b43e3a7a3637eea3328c3}

Esta integración podría incluir cobros. Póngase en contacto con su administrador de relaciones para obtener información sobre los precios.
