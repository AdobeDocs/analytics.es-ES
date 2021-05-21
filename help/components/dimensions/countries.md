---
title: Países
description: El país desde donde se originó la visita.
exl-id: 47704b08-215d-4d2d-bcd4-1789e308c1c6
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '307'
ht-degree: 100%

---

# Países

La dimensión “Países” informa del país desde donde se originó la visita. Esta dimensión es útil para determinar de qué países suelen proceder los visitantes del sitio. Puede utilizar estos datos para centrar sus campañas de marketing en estos países o asegurarse de que la experiencia del sitio sea óptima en países que tienen diferentes idiomas principales.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a las reglas de búsqueda internas de Adobe. El valor de búsqueda se basa en la dirección IP enviada con la visita. Adobe se asocia con [Digital Element](https://www.digitalelement.com/es) para mantener búsquedas entre la dirección IP y el país. Esta dimensión funciona de forma predeterminada para todas las implementaciones.

>[!TIP]
>
>Si su organización sigue estrictas normas de privacidad en las que [ofuscar la dirección IP](/help/admin/admin/general-acct-settings-admin.md) no es suficiente, puede solicitar que se deshabiliten los datos de geolocalización por completo. Póngase en contacto con el Servicio de atención al cliente con el ID del grupo de informes y solicite desactivar “Geografía” para el grupo de informes.

## Elementos de dimensión

Los elementos de dimensión incluyen países de todo el mundo. Los valores de ejemplo incluyen `"United States"`, `"United Kingdom"` o `"India"`.

## Diferencias entre la ubicación real y la notificada

Dado que esta dimensión se basa en la dirección IP, algunos escenarios pueden mostrar una diferencia entre la ubicación real y la ubicación registrada:

* **Direcciones IP que representan proxies corporativos**: Estos visitantes pueden aparecer como tráfico proveniente de la red corporativa del usuario, que puede ser una ubicación diferente si el usuario trabaja de forma remota.
* **Direcciones IP móviles**: La segmentación de direcciones IP móviles funciona en diferentes niveles según la ubicación y la red del dispositivo. Algunos operadores pasan el tráfico de IP por puntos de presencia centralizados o regionales.
* **Usuarios de ISP satelitales**: Es difícil identificar la ubicación específica de estos usuarios, ya que normalmente parecen proceder de la ubicación del vínculo superior.
* **IP militares y gubernamentales**: Representa al personal que viaja por todo el mundo y accede a Internet a través de su ubicación local en lugar de la base u oficina en la que esté destinado.
