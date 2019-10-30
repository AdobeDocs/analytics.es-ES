---
description: Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente modificar su implementación sin comprender las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización.
keywords: Implementación de Analytics
seo-description: Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente modificar su implementación sin comprender las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización.
seo-title: Seguimiento en diferentes tipos de implementación
solution: Analytics
title: Seguimiento en diferentes tipos de implementación
topic: Desarrollador e implementación
uuid: a0a3229a-79a2-4dc2-b0be-4b8fac2efa3a
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Seguimiento en diferentes tipos de implementación

Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente modificar su implementación sin comprender las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización.

Si utiliza más de un tipo de implementación (como JavaScript y solicitudes de imagen codificadas), asegúrese de que las siguientes variables estén especificadas y coincidan entre sí:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (si se usa SSL)

Si cada una de ellas no coincide de una implementación a otra, los usuarios podrían seguirse como visitantes diferentes.
