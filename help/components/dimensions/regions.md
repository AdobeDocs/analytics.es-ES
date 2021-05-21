---
title: Regiones
description: Región geográfica del visitante.
exl-id: 95ab4c7e-71e8-490f-88a4-25201331d848
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '381'
ht-degree: 100%

---

# Regiones

La dimensión “Regiones” indica la región geográfica del visitante. Es una zona geográfica más pequeña que un país, pero más grande que ciudad. En algunos países, una región es un estado, una provincia o una prefectura. En otras zonas, se trata de un país constituyente, departamento o región metropolitana. El uso de esta dimensión es ideal si desea obtener una perspectiva más granular que [Países](countries.md) pero no tan granular como [Ciudades](cities.md).

## Rellene esta dimensión con datos

Esta dimensión hace referencia a las reglas de búsqueda internas de Adobe. El valor de búsqueda se basa en la dirección IP enviada con la visita. Adobe se asocia con [Digital Element](https://www.digitalelement.com/es) para mantener búsquedas entre la dirección IP y el país. Esta dimensión funciona de forma predeterminada para todas las implementaciones.

>[!TIP]
>
>Si su organización sigue estrictas normas de privacidad en las que [ofuscar la dirección IP](/help/admin/admin/general-acct-settings-admin.md) no es suficiente, puede solicitar que se deshabiliten los datos de geolocalización por completo. Póngase en contacto con el Servicio de atención al cliente con el ID del grupo de informes y solicite desactivar “Geografía” para el grupo de informes.

## Elementos de dimensión

Los elementos de dimensión incluyen regiones y el país en el que reside la región. Los valores de ejemplo incluyen `"California (United States)"`, `"Tokyo (Japan)"` o `"Sao Paulo (Brazil)"`.

Algunos elementos de dimensión pueden incluir `"AOL"`, un proveedor de servicio de acceso telefónico a Internet. A los suscriptores de este servicio se les asigna un punto de acceso basado en el país donde se establece su número de cuenta. Los usuarios de AOL utilizan la dirección IP de este punto de acceso. Dado que esta dimensión se basa en la dirección IP, se utiliza la geolocalización del punto de acceso en lugar de la ubicación real del visitante.

## Diferencias entre la ubicación real y la notificada

Dado que esta dimensión se basa en la dirección IP, algunos escenarios pueden mostrar una diferencia entre la ubicación real y la ubicación registrada:

* **Direcciones IP que representan proxies corporativos**: Estos visitantes pueden aparecer como tráfico proveniente de la red corporativa del usuario, que puede ser una ubicación diferente si el usuario trabaja de forma remota.
* **Direcciones IP móviles**: La segmentación de direcciones IP móviles funciona en diferentes niveles según la ubicación y la red del dispositivo. Algunos operadores pasan el tráfico de IP por puntos de presencia centralizados o regionales.
* **Usuarios de ISP satelitales**: Es difícil identificar la ubicación específica de estos usuarios, ya que normalmente parecen proceder de la ubicación del vínculo superior.
* **IP militares y gubernamentales**: Representa al personal que viaja por todo el mundo y accede a Internet a través de su ubicación local en lugar de la base u oficina en la que esté destinado.
