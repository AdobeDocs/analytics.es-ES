---
description: Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics® y el software de correo electrónico.
seo-description: Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics® y el software de correo electrónico.
seo-title: Antes de activar esta integración
title: Antes de activar esta integración
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Antes de activar esta integración {#before-you-activate-this-integration}

Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics® y el software de correo electrónico.

Al hacerlo, se asegurará de que se apliquen las prácticas recomendadas o los requisitos previos adecuados antes de la activación, lo que resultará en una integración óptima y exitosa.

## Adobe Analytics Requirements{#adobe-analytics-requirements}

Revise la siguiente información sobre esta integración de conectores de datos en relación con Adobe Analytics:

* **** Específico del grupo de informes: Tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de haber seleccionado el grupo de informes deseado antes de activar la integración y de que el grupo de informes contenga datos.
* **** Variables de Analytics disponibles y configuradas: Esta integración requiere 10 eventos personalizados y 1 eVar personalizada. Consulte Variables [de integración de Analytics](appfigures-before-activation.md#analytics-integration-variables).

* **** Grupo de informes inicializado con datos activos: Si está creando un grupo de informes completamente nuevo para esta integración, debe haber recibido algunos datos (al menos una visita) mediante los requisitos de appFigures de seguimiento activo. Si no se han registrado los datos activos, el grupo de informes no estará listo para recibir los datos integrados de App Store.

* **** Integración existente con App Store: Esta integración devuelve datos durante 13 meses. Para evitar cualquier superposición con cualquier proveedor de datos del almacén de aplicaciones anterior, póngase en contacto con el representante de appFigures. Hágalos saber la última fecha en que recibió los datos. appFigures ajustará el período de relleno posterior en consecuencia.

## appFigures Requirements{#appfigures-requirements}

Revise la siguiente información sobre esta integración de conectores de datos en relación con appFigures:

* **** Cliente actual de appFigures: Esta integración requiere que sea usuario de Adobe y de appFigures. Si actualmente no es usuario de appFigures Enterprise Plan, no tendrá la información necesaria para completar el asistente para la integración. Visite appFigures en la web para obtener más información.
* **** Clave de cuenta de appFigures: Se requiere una clave de cuenta appFigures para activar el conector de datos appFigures. Esta clave de cuenta se puede generar en la sección "Complementos". Consulte [Configurar la integración](../appfigures-overview/t-appfigures-integration.md) para obtener más información.

* **Finalización** de datos: La información de descarga, ventas y clasificación se sincroniza cada día durante los 7 días anteriores. Después de 7 días, los datos se consideran finales y ya no se actualizan.

## Precio{#pricing}

Esta integración de conectores de datos incluye consideraciones de precios que debe tener en cuenta.

Las secciones siguientes contienen más información:

### Consideraciones sobre los precios de Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Actualmente no hay tarifas para activar esta integración. Sin embargo, es posible que vea un ligero aumento de llamadas al servidor debido a la importación de fuentes de datos.

### consideraciones de precios de appFigures {#section-c6afad08c34b43e3a7a3637eea3328c3}

Actualmente no hay tarifas asociadas con esta integración. Actualmente, esta integración solo está disponible para los clientes de Enterprise. Póngase [en contacto con appFigures](https://appfigures.com/support/contact) para obtener más información.

## Analytics Integration Variables{#analytics-integration-variables}

La integración de conectores de datos para appFigures utiliza variables de Analytics para rastrear distintas métricas de appFigures.

En la tabla siguiente se describen las variables de Analytics activadas automáticamente para la integración appFigures.

### Variables requeridas {#section-3ca8dc46bab0436cba0c9ef827c8356a}

> [!NOTE] Esta integración utiliza variables dedicadas para los datos del almacén de aplicaciones, por lo que no es necesario asignar variables y eventos de comercio personalizados.

| Tipo de variable | Nombre | Método de obtención de datos | Descripción |
|---|---|---|---|
| eVar | ID de objeto de App Store | Importado desde appFigures. | Configure esta eVar con caducidad de visita, asignación más reciente y subrelaciones básicas. |
| event (numérico) | Descargas de App Store | Importado desde appFigures. | El número de descargas de aplicaciones móviles. |
| event (numérico) | Compras de App Store (en la aplicación) | Importado desde appFigures. | Número de compras y suscripciones desde la propia aplicación. |
| event (numérico) | Clasificación de App Store | Importado desde appFigures. | Se utiliza para definir la métrica promedio calculada de appFigures. No se utiliza directamente. |
| event (numérico) | Divisor de la clasificación de App Store | Importado desde appFigures. | Se utiliza para definir la métrica promedio calculada de appFigures. No se utiliza directamente. |
| event (numérico) | Clasificación de App Store | Importado desde appFigures. | Se utiliza para definir la métrica promedio calculada de appFigures. No se utiliza directamente. |
| event (numérico) | Divisor de la clasificación de App Store | Importado desde appFigures. | Se utiliza para definir la métrica promedio calculada de appFigures. No se utiliza directamente. |
| evento (moneda) | Ingresos de App Store (en la aplicación) | Importado desde appFigures. | La cantidad de ingresos en la aplicación menos la tarifa de la tienda. |
| evento (moneda) | Ingresos de App Store (uno de descuento) | Importado desde appFigures. | Ingresos totales de compras de aplicaciones menos la tarifa de la tienda. |
| evento (moneda) | Derechos de autor de App Store (en la aplicación) | Importado desde appFigures. | No se utiliza |
| evento (moneda) | Derechos de autor de App Store (uno de ellos no incluido) | Importado desde appFigures. | No se utiliza |
