---
title: Ciudades
description: Ciudad de donde se originó la visita.
translation-type: tm+mt
source-git-commit: d3f92d72207f027d35f81a4ccf70d01569c3557f
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 0%

---


# Ciudades

La dimensión &#39;Ciudades&#39; informa de la ciudad de donde se originó la visita. Esta dimensión es útil para determinar de qué proceden los visitantes de ciudades más populares al visitar el sitio. Puede usar estos datos para centrarse en la publicidad local en estas ciudades, como carteleras o comerciales.

## Rellenar esta dimensión con datos

Esta dimensión hace referencia a las reglas de búsqueda internas de Adobe. El valor de búsqueda se basa en la dirección IP enviada con la visita. Adobe se asocia con [Digital Element](https://www.digitalelement.com/) para mantener búsquedas entre la dirección IP y la ciudad. Esta dimensión funciona de forma predeterminada para todas las implementaciones.

>[!TIP]
>
>Si su organización sigue estrictas normas de privacidad en las que [confundir la dirección](/help/admin/admin/general-acct-settings-admin.md) IP no es suficiente, puede solicitar que se deshabiliten los datos de geolocalización por completo. Póngase en contacto con el Servicio de atención al cliente con la ID del grupo de informes y solicite desactivar &quot;Geografía&quot; para el grupo de informes.

## Elementos de dimensión

Los elementos de dimensión incluyen ciudades de todo el mundo. Los valores de ejemplo incluyen `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"`o `"London (London, United Kingdom)"`.

## Diferencias entre la ubicación real y la notificada

Dado que esta dimensión se basa en la dirección IP, algunos escenarios pueden mostrar una diferencia entre la ubicación real y la ubicación registrada:

* **Direcciones IP que representan proxies** corporativos: Estos visitantes pueden aparecer como tráfico proveniente de la red corporativa del usuario, que puede ser una ubicación diferente si el usuario trabaja de forma remota.
* **Direcciones** IP móviles: La segmentación por IP móvil funciona en distintos niveles según la ubicación y la red. Una serie de portadoras reorganizan el tráfico IP a través de puntos de presencia centralizados o regionales.
* **Usuarios** de ISP satelitales: Es difícil identificar la ubicación específica de estos usuarios, ya que normalmente parecen proceder de la ubicación del vínculo superior.
* **IPs** militares y gubernamentales: Representa al personal que viaja por todo el mundo y entra por su ubicación en el hogar, en lugar de la base o la oficina donde se encuentra actualmente.
