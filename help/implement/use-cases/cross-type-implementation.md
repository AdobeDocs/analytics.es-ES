---
title: Seguimiento en diferentes tipos de implementación
description: Utilice diferentes tipos de implementación y realice un seguimiento de los visitantes.
feature: Implementation Basics
exl-id: 18aa5595-d2a7-4df2-a4ef-a5040c097483
source-git-commit: b3c74782ef6183fa63674b98e4c0fc39fc09441b
workflow-type: tm+mt
source-wordcount: '102'
ht-degree: 100%

---

# Seguimiento en diferentes tipos de implementación

Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente modificar su implementación sin comprender las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización.

Si utiliza más de un tipo de implementación (como JavaScript y solicitudes de imagen codificadas), asegúrese de que las siguientes variables estén especificadas y coincidan entre sí:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (si se usa SSL)

Si cada una de ellas no coincide de una implementación a otra, los usuarios podrían seguirse como visitantes diferentes.
