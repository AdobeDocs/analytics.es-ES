---
title: Seguimiento en diferentes tipos de implementación
description: Utilice diferentes tipos de implementación y realice un seguimiento de los visitantes.
translation-type: ht
source-git-commit: 819f719c4ce131c04916f3b668bcbda1a1b03651
workflow-type: ht
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
