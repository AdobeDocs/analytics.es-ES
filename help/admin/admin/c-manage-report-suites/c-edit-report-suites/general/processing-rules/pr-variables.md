---
description: Las dimensiones y métricas disponibles que se pueden leer y escribir mediante reglas de procesamiento.
subtopic: Processing rules
title: Dimensiones y métricas disponibles para las reglas de procesamiento
feature: Processing Rules
role: Admin
exl-id: ffd7a1d6-2c9d-41e7-9c75-9e47b6f9c283
source-git-commit: d62d4699418278bc9f0c7d69846ef12b5f2345d1
workflow-type: tm+mt
source-wordcount: '718'
ht-degree: 10%

---

# Dimensiones y métricas disponibles para las reglas de procesamiento

Las dimensiones y métricas disponibles que se pueden leer y escribir mediante reglas de procesamiento.

## Valores personalizados y datos de contexto

| Valor | Estado de lectura y escritura | Descripción |
| --- | --- | --- |
| **Valor personalizado** | Solo lectura | Texto o valores personalizados escritos directamente en la acción de una regla de procesamiento. |
| **Valor concatenado** | Solo lectura | Valores que se crean combinando dos valores. Por ejemplo, se puede combinar canal y nombre de página para crear una subcategoría. |

## Atributos de visita

| Atributo | Estado de lectura y escritura | Descripción |
| --- | --- | --- |
| **URL de la página** | Lectura y escritura | La dimensión [URL de la página](/help/components/dimensions/page-url.md). Las visitas de seguimiento de vínculos eliminan esta dimensión antes de alcanzar las reglas de procesamiento. Si vuelve a insertar un valor de dirección URL de página mediante reglas de procesamiento, la visita se considera una [vista de página](/help/components/metrics/page-views.md) en lugar de un [evento de página](/help/components/metrics/page-events.md). Adobe recomienda comprobar un valor en la dimensión de página antes de modificarla. |
| **Nombre de página** | Lectura y escritura | La dimensión [Página](/help/components/dimensions/page.md). Las visitas de seguimiento de vínculos eliminan esta dimensión antes de alcanzar las reglas de procesamiento. Si vuelve a insertar un valor de página mediante reglas de procesamiento, la visita se considera una [vista de página](/help/components/metrics/page-views.md) en lugar de un [evento de página](/help/components/metrics/page-events.md). Adobe recomienda comprobar un valor en la dimensión de página antes de modificarla. |
| **ID del grupo de informes** | Solo lectura | Grupo de informes en el que se ejecuta la regla de procesamiento. Este grupo de informes puede ser diferente al grupo de informes enviado originalmente a través de AppMeasurement, como cuando se utilizan reglas de VISTA. |
| **Versión de código AppMeasurement** | Solo lectura | Versión de la biblioteca AppMeasurement utilizada para generar la solicitud de imagen. |
| **Dirección IP** | Solo lectura | La dirección IP del visitante. |
| **Agente de usuario** | Solo lectura | El agente de usuario del visitante. |
| **Referente** | Solo lectura | La dimensión [Referente](/help/components/dimensions/referrer.md). |
| **Parámetro de cadena de consulta** | Solo lectura | Valor de un parámetro de cadena de consulta especificado en la dirección URL actual. |
| **Parámetro de cadena de consulta referente** | Solo lectura | El valor de un parámetro de cadena de consulta especificado en la dirección URL referente, o una cadena vacía si no existe ninguna. |
| **Dominio de referencia** | Solo lectura | El dominio de página de la dirección URL de referencia, incluidos los subdominios. |
| **Dominio raíz de referencia** | Solo lectura | El dominio de página de la dirección URL de referencia, excepto los subdominios. |
| **Cadena de consulta de página** | Solo lectura | Todos los parámetros de cadena de consulta y sus valores en la dirección URL actual. |
| **Cadena de consulta referente** | Solo lectura | Todos los parámetros de cadena de consulta y sus valores en la dirección URL de referencia. |
| **Ruta de la página** | Solo lectura | Ruta de página de la dirección URL actual. La ruta de la página no incluye parámetros de protocolo, dominio o cadena de consulta. |
| **Dominio de página** | Solo lectura | El dominio de página de la dirección URL actual, incluidos los subdominios. El dominio de página no incluye parámetros de ruta de página o de cadena de consulta. |
| **Dominio raíz de página** | Solo lectura | El dominio de página de la dirección URL actual, excluidos los subdominios. |
| **Perspectiva del cliente** | Lectura y escritura | Un indicador que determina si la visita es una visita en segundo plano a un dispositivo móvil. |

## Variables de conversión

| Variable | Estado de lectura y escritura | Descripción |
| --- | --- | --- |
| **eVar 1-250** | Lectura y escritura | [eVar](/help/components/dimensions/evar.md) dimensiones. |
| **Campaign** | Lectura y escritura | La dimensión [Código de seguimiento](/help/components/dimensions/tracking-code.md). |
| **ID de compra** | Lectura y escritura | La variable de implementación [`purchaseID`](/help/implement/vars/page-vars/purchaseid.md). |
| **Estado** | Lectura y escritura | (Retirado) La variable de implementación [`state`](/help/implement/vars/page-vars/state.md). |
| **Código postal** | Lectura y escritura | La dimensión [Código postal](/help/components/dimensions/zip-code.md). |
| **Código de divisa** | Lectura y escritura | La variable de implementación [`currencyCode`](/help/implement/vars/config-vars/currencycode.md). IMPORTANTE: Si establece esta variable en un valor no válido, la visita se descarta. |
| **ID de transacción** | Lectura y escritura | La variable de implementación [`transactionID`](/help/import/data-sources/transactionid.md). |

>[!NOTE]
>Adobe no admite la configuración de la variable de implementación [`products`](/help/implement/vars/page-vars/products.md) mediante reglas de procesamiento.

## Variables de tráfico

| Variable | Estado de lectura y escritura | Descripción |
| --- | --- | --- |
| **Prop 1-75** | Lectura y escritura | [Prop](/help/components/dimensions/prop.md) dimensiones. |
| **Jerarquía 1-5** | Lectura y escritura | (Retirado) [Jerarquía](/help/components/dimensions/hierarchy.md) dimensiones. |
| **Servidor** | Lectura y escritura | La dimensión [Servidor](/help/components/dimensions/server.md). |
| **Canal** | Lectura y escritura | La dimensión [sección del sitio](/help/components/dimensions/site-section.md). |

## Variables de contexto

Todas las [variables de datos de contexto](/help/implement/vars/page-vars/contextdata.md) que este grupo de informes ha visto en los últimos 30 días. Consulte [Casos de uso de reglas de procesamiento](pr-use-cases.md) para ver ejemplos de uso.

>[!IMPORTANT]
>
>Si las reglas de procesamiento no asignan una variable de datos de contexto determinada a otra variable (como una prop o eVar), el valor de la variable de datos de contexto se pierde de forma permanente.

## Eventos de éxito

Las reglas de procesamiento pueden definir eventos, pero no pueden leerlos como condiciones. Establezca el menú desplegable de acciones de regla en **[!UICONTROL Definir evento]** para ver las métricas disponibles que se incrementarán.

| Variable | Estado de lectura y escritura | Descripción |
| --- | --- | --- |
| **Pedidos** | Solo escritura | La métrica [Pedidos](/help/components/metrics/orders.md). |
| **Carros de compras** | Solo escritura | La métrica [Carros](/help/components/metrics/carts.md). |
| **Vistas del carro de compras** | Solo escritura | La métrica [Vistas del carro de compras](/help/components/metrics/cart-views.md). |
| **Cierres de compra** | Solo escritura | La métrica [Cierres de compra](/help/components/metrics/checkouts.md). |
| **Adiciones al carro de compras** | Solo escritura | La métrica [Adiciones al carro de compras](/help/components/metrics/cart-additions.md). |
| **Eliminaciones del carro de compras** | Solo escritura | La métrica [Eliminaciones del carro de compras](/help/components/metrics/cart-removals.md). |
| **Evento 1-1000** | Solo escritura | [Eventos personalizados](/help/components/metrics/custom-events.md). |
| **Vistas del producto** | Solo escritura | La métrica [Vistas del producto](/help/components/metrics/product-views.md). |
