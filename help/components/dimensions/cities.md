---
title: Ciudades
description: Ciudad en la que se originó la visita.
feature: Dimensions
exl-id: c04525bb-50d6-4d28-b5dc-335d089e184b
source-git-commit: 146d622f370fd7469a8e5f0f2fe68cb31fa91844
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 89%

---

# Ciudades

La dimensión “Ciudades” indica la ciudad desde la que se originó la visita. Esta dimensión es útil para determinar de qué ciudades suelen proceder los visitantes del sitio. Puede usar estos datos para centrarse en la publicidad local en estas ciudades, como carteleras o anuncios.

## Rellene esta dimensión con datos

Esta dimensión hace referencia a las reglas de búsqueda internas de Adobe. El valor de búsqueda se basa en la dirección IP enviada con la visita. Adobe se asocia con [Digital Element](https://www.digitalelement.com/es/) para mantener búsquedas entre la dirección IP y la ciudad. Esta dimensión funciona de forma predeterminada para todas las implementaciones.

## Elementos de dimensión

Los elementos de dimensión incluyen ciudades de todo el mundo. Los valores de ejemplo incluyen `"New York (New York, United States)"`, `"Bangalore (Karnataka, India)"` o `"London (London, United Kingdom)"`.

Algunos elementos de dimensión pueden incluir `"AOL"`, un proveedor de servicio de acceso telefónico a Internet. A los suscriptores de este servicio se les asigna un punto de acceso basado en el país donde se establece su número de cuenta. Los usuarios de AOL utilizan la dirección IP de este punto de acceso. Dado que esta dimensión se basa en la dirección IP, se utiliza la geolocalización del punto de acceso en lugar de la ubicación real del visitante.

## Diferencias entre la ubicación real y la notificada

Dado que esta dimensión se basa en la dirección IP, algunos escenarios pueden mostrar una diferencia entre la ubicación real y la ubicación registrada:

* **Direcciones IP que representan proxies corporativos**: Estos visitantes pueden aparecer como tráfico proveniente de la red corporativa del usuario, que puede ser una ubicación diferente si el usuario trabaja de forma remota.
* **Direcciones IP móviles**: La segmentación de direcciones IP móviles funciona en diferentes niveles según la ubicación y la red del dispositivo. Algunos operadores pasan el tráfico de IP por puntos de presencia centralizados o regionales.
* **Usuarios de ISP satelitales**: Es difícil identificar la ubicación específica de estos usuarios, ya que normalmente parecen proceder de la ubicación del vínculo superior.
* **IP militares y gubernamentales**: Representa al personal que viaja por todo el mundo y accede a Internet a través de su ubicación local en lugar de la base u oficina en la que esté destinado.
* **Proxies que oscurecen las direcciones IP por motivos de privacidad**: los servicios como Private Relay de Apple ocultan la dirección IP real enviando datos aleatoriamente a través de un intermediario o proxy. A continuación, este proxy sustituye una dirección IP diferente antes de reenviarla al Adobe.
