---
title: Área de mercado designada (DMA) de EE.UU.
description: Área de mercado designada de la visita.
exl-id: 156d5755-2e93-4240-bde3-1d537422b7bf
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '306'
ht-degree: 100%

---

# Área de mercado designada (DMA) de EE.UU.

La dimensión “DMA de EE. UU.” informa de la zona de mercado designada (DMA) del visitante. Se basa en los mercados de medios recopilados por [Nielsen](https://www.nielsen.com/us/en/intl-campaigns/dma-maps/).

## Rellene esta dimensión con datos

Esta dimensión hace referencia a las reglas de búsqueda internas de Adobe. El valor de búsqueda se basa en la dirección IP enviada con la visita. Adobe se asocia con Nielsen para mantener búsquedas entre la dirección IP y DMA. Esta dimensión funciona de forma predeterminada para todas las implementaciones.

>[!TIP]
>
>Si su organización sigue estrictas normas de privacidad en las que [ofuscar la dirección IP](/help/admin/admin/general-acct-settings-admin.md) no es suficiente, puede solicitar que se deshabiliten los datos de geolocalización por completo. Póngase en contacto con el Servicio de atención al cliente con el ID del grupo de informes y solicite desactivar “Geografía” para el grupo de informes.

## Elementos de dimensión

Los elementos de dimensión incluyen el código DMA y DMA del visitante. El código de 3 dígitos no es un código postal, sino el código DMA de Nielsen. Los valores de ejemplo incluyen `"Dallas-Ft. Worth (623)"`, `"New York (501)"` o `"Los Angeles (803)"`. El elemento de dimensión `"No Metro (0)"` incluye todo el tráfico internacional fuera de los Estados Unidos.

## Diferencias entre la ubicación real y la notificada

Dado que esta dimensión se basa en la dirección IP, algunos escenarios pueden mostrar una diferencia entre la ubicación real y la ubicación registrada:

* **Direcciones IP que representan proxies corporativos**: Estos visitantes pueden aparecer como tráfico proveniente de la red corporativa del usuario, que puede ser una ubicación diferente si el usuario trabaja de forma remota.
* **Direcciones IP móviles**: La segmentación de direcciones IP móviles funciona en diferentes niveles según la ubicación y la red del dispositivo. Algunos operadores pasan el tráfico de IP por puntos de presencia centralizados o regionales.
* **Usuarios de ISP satelitales**: Es difícil identificar la ubicación específica de estos usuarios, ya que normalmente parecen proceder de la ubicación del vínculo superior.
* **IP militares y gubernamentales**: Representa al personal que viaja por todo el mundo y accede a Internet a través de su ubicación local en lugar de la base u oficina en la que esté destinado.
