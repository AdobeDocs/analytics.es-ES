---
description: Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente modificar su implementación sin comprender las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización.
keywords: Analytics Implementation
title: Seguimiento en diferentes tipos de implementación
topic: Developer and implementation
uuid: a0a3229a-79a2-4dc2-b0be-4b8fac2efa3a
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Seguimiento en diferentes tipos de implementación

Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente modificar su implementación sin comprender las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización.

Si utiliza más de un tipo de implementación (como JavaScript y solicitudes de imagen codificadas), asegúrese de que las siguientes variables estén especificadas y coincidan entre sí:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (si se usa SSL)

Si cada una de ellas no coincide de una implementación a otra, los usuarios podrían seguirse como visitantes diferentes.
