---
title: Regiones
description: Región geográfica del visitante.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '320'
ht-degree: 7%

---


# Regiones

La dimensión &#39;Regiones&#39; informa la región geográfica del visitante. Es un área geográfica que es más pequeña que un país pero más grande que una ciudad. En algunos países, una región es un estado, una provincia o una prefectura. En otras zonas, se trata de un país constituyente, departamento o región metropolitana. El uso de esta dimensión es valioso si desea una perspectiva más granular que [los países](countries.md) pero no tan granular como [las ciudades](cities.md).

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a las reglas de búsqueda internas de Adobe. El valor de búsqueda se basa en la dirección IP enviada con la visita. Adobe se asocia con [Digital Element](https://www.digitalelement.com/) para mantener búsquedas entre la dirección IP y el país. Esta dimensión funciona de forma predeterminada para todas las implementaciones.

>[!TIP]
>
>Si su organización sigue estrictas normas de privacidad en las que [confundir la dirección](/help/admin/admin/general-acct-settings-admin.md) IP no es suficiente, puede solicitar que se deshabiliten los datos de geolocalización por completo. Póngase en contacto con el Servicio de atención al cliente con la ID del grupo de informes y solicite desactivar &quot;Geografía&quot; para el grupo de informes.

## Elementos de dimensión

Los elementos de dimensión incluyen regiones y el país en el que reside la región. Los valores de ejemplo incluyen `"California (United States)"`, `"Tokyo (Japan)"`o `"Sao Paulo (Brazil)"`.

## Diferencias entre la ubicación real y la notificada

Dado que esta dimensión se basa en la dirección IP, algunos escenarios pueden mostrar una diferencia entre la ubicación real y la ubicación registrada:

* **Direcciones IP que representan proxies** corporativos: Estos visitantes pueden aparecer como tráfico proveniente de la red corporativa del usuario, que puede ser una ubicación diferente si el usuario trabaja de forma remota.
* **Direcciones** IP móviles: La segmentación por IP móvil funciona en distintos niveles según la ubicación y la red. Una serie de portadoras reorganizan el tráfico IP a través de puntos de presencia centralizados o regionales.
* **Usuarios** de ISP satelitales: Es difícil identificar la ubicación específica de estos usuarios, ya que normalmente parecen proceder de la ubicación del vínculo superior.
* **IPs** militares y gubernamentales: Representa al personal que viaja por todo el mundo y entra por su ubicación en el hogar, en lugar de la base o la oficina donde se encuentra actualmente.
