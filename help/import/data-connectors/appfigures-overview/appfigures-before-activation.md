---
description: Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics® y del software de correo electrónico.
title: Antes de activar esta integración
uuid: fdc762bc-24e3-4c0a-904d-d4be2a4f3a20
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Antes de activar esta integración {#before-you-activate-this-integration}

Antes de activar esta integración, revise los siguientes elementos en relación con las implementaciones de Adobe Analytics® y del software de correo electrónico.

Al hacerlo, se asegura de que las prácticas recomendadas y los requisitos previos adecuados estén implementados antes de la activación, lo que supone una integración óptima y sin problemas.

## Requisitos de Adobe Analytics {#adobe-analytics-requirements}

Revise la siguiente información sobre esta integración de Data Connectors en relación con Adobe Analytics:

* **Específico del grupo de informes:** tenga en cuenta que esta integración es específica del grupo de informes. Asegúrese de haber seleccionado el grupo de informes deseado antes de activar la integración y de que el grupo de informes contenga datos.
* **Variables de Analytics disponibles y configuradas:** esta integración requiere 10 eventos personalizados, además de 1 eVar personalizada. Consulte [Variables de integración de Analytics](appfigures-before-activation.md#analytics-integration-variables).

* **Grupo de informes inicializado con datos activos:** si está creando un grupo de informes completamente nuevo para esta integración, debe haber recibido algunos datos (al menos una visita) mediante los requisitos de appFigures de seguimiento activo. Si no se han registrado los datos activos, el grupo de informes no está listo para recibir los datos integrados de la tienda de aplicaciones.

* **Integración existente con la tienda de aplicaciones:** esta integración completa los datos durante 13 meses. Para evitar sobrescribir la información de cualquier proveedor de datos anterior de la tienda de aplicaciones, póngase en contacto con el representante de appFigures. Informe de la última fecha en que recibió los datos. appFigures ajusta el período de relleno posterior en consecuencia.

## Requisitos de appFigures {#appfigures-requirements}

Revise la siguiente información sobre esta integración de Data Connectors en relación con appFigures:

* **Cliente actual de appFigures:** esta integración requiere que sea usuario de Adobe y de appFigures. Si actualmente no es usuario de appFigures Enterprise Plan, no dispone de la información necesaria para completar el asistente de integración. Visite la web de appFigures para obtener más información.
* **Clave de cuenta de appFigures:** se necesita una clave de cuenta de appFigures para activar Data Connectors en appFigures. Esta clave de cuenta se puede generar en la sección “Complementos”. Consulte [Configurar la integración](../appfigures-overview/t-appfigures-integration.md) para obtener más información.

* **Finalización de datos:** la información de descarga, ventas y clasificación se sincroniza cada día durante los 7 días anteriores. Después de 7 días, los datos se consideran finales y ya no se actualizan.

## Precio {#pricing}

Esta integración de Data Connectors incluye consideraciones de precios que debe tener en cuenta.

Las secciones siguientes contienen más información:

### Consideraciones sobre los precios de Adobe {#section-2d1c79c895a5479bad8fdd97961ba6a3}

Actualmente no existen tarifas para activar esta integración. Sin embargo, es posible que vea un ligero aumento de llamadas al servidor debido a la importación de fuentes de datos.

### Consideraciones de precios de appFigures {#section-c6afad08c34b43e3a7a3637eea3328c3}

Actualmente no existen tarifas asociadas a esta integración. Actualmente, esta integración solo está disponible para los clientes de Enterprise. Póngase [en contacto con appFigures](https://appfigures.com/support/contact) para obtener más información.

## Variables de integración de Analytics {#analytics-integration-variables}

La integración de Data Connectors para appFigures usa variables de Analytics para rastrear distintas métricas de appFigures.

La siguiente tabla describe las variables de Analytics que se activan automáticamente para la integración de appFigures.

### Variables requeridas {#section-3ca8dc46bab0436cba0c9ef827c8356a}

>[!NOTE] Esta integración usa variables específicas para los datos de tiendas de aplicaciones, por lo que no es necesario asignar variables y eventos de comercio personalizados.

| Tipo de variable | Nombre | Método de población | Descripción |
|---|---|---|---|
| eVar | ID de objeto de la tienda de aplicaciones | Importado desde appFigures. | Configure esta eVar con caducidad de visita, asignación más reciente y subrelaciones básicas. |
| Evento (numérico) | Descargas de la tienda de aplicaciones | Importado desde appFigures. | El número de descargas de aplicaciones móviles. |
| Evento (numérico) | Compras de la tienda de aplicaciones (en la aplicación) | Importado desde appFigures. | Número de compras y suscripciones desde la propia aplicación. |
| Evento (numérico) | Clasificación de la tienda de aplicaciones | Importado desde appFigures. | Se utiliza para definir la métrica promedio calculada de appFigures. No se utiliza directamente. |
| Evento (numérico) | Divisor de la clasificación de la tienda de aplicaciones | Importado desde appFigures. | Se utiliza para definir la métrica promedio calculada de appFigures. No se utiliza directamente. |
| Evento (numérico) | Clasificación de la tienda de aplicaciones | Importado desde appFigures. | Se utiliza para definir la métrica promedio calculada de appFigures. No se utiliza directamente. |
| Evento (numérico) | Divisor de la clasificación de la tienda de aplicaciones | Importado desde appFigures. | Se utiliza para definir la métrica promedio calculada de appFigures. No se utiliza directamente. |
| Evento (moneda) | Ingresos de la tienda de aplicaciones (en la aplicación) | Importado desde appFigures. | La cantidad de ingresos en la aplicación menos la tarifa de la tienda. |
| Evento (moneda) | Ingresos de la tienda de aplicaciones (únicos) | Importado desde appFigures. | Ingresos totales de compras en la aplicaciones menos la tarifa de la tienda. |
| Evento (moneda) | Derechos de autor de la tienda de aplicaciones (en la aplicación) | Importado desde appFigures. | No se usa. |
| Evento (moneda) | Derechos de autor de la tienda de aplicaciones (únicos) | Importado desde appFigures. | No se usa. |
