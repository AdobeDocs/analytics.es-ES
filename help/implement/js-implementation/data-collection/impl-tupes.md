---
description: 'Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente modificar su implementación sin comprender las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización. '
keywords: Implementación de Analytics
seo-description: 'Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente modificar su implementación sin comprender las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización. '
seo-title: Rastrear en diferentes tipos de implementación
solution: Analytics
title: Rastrear en diferentes tipos de implementación
topic: Desarrollador e implementación
uuid: a 0 a 3229 a -79 a 2-4 dc 2-b 0 be -4 b 8 fac 2 efa 3 a
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Rastrear en diferentes tipos de implementación

Esta información está dirigida a usuarios avanzados con amplia experiencia tanto en informes como en implementación. No intente modificar su implementación sin comprender las consecuencias. Si necesita modificar la implementación, póngase en contacto con el administrador de cuentas de su organización. 

Si utiliza más de un tipo de implementación (como JavaScript y solicitudes de imagen codificadas), asegúrese de que las siguientes variables estén especificadas y coincidan entre sí:

* *`s_account`*
* *`s.visitorNamespace`*
* *`s.trackingServer`*
* *`s.trackingServerSecure`* (si se usa SSL)

Si cada una de ellas no coincide de una implementación a otra, los usuarios podrían seguirse como visitantes diferentes.
