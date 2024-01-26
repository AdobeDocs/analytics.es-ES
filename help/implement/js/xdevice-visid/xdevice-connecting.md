---
description: La identificación de visitantes entre dispositivos ayuda a conectar los visitantes a varios dispositivos. La identificación de visitantes entre dispositivos utiliza la variable de ID de visitante, s.visitorID, para asociar un visitante a varios dispositivos.
keywords: Implementación de Analytics
subtopic: Visitors
title: Conectar usuarios entre dispositivos
feature: Implementation Basics
exl-id: dfe278db-01de-4bba-b07a-66d52de1dbe2
role: Developer
source-git-commit: 7d8df7173b3a78bcb506cc894e2b3deda003e696
workflow-type: tm+mt
source-wordcount: '398'
ht-degree: 95%

---

# Conectar usuarios entre dispositivos

>[!IMPORTANT]
>
>Ya no se recomienda este método de identificación de visitantes entre dispositivos. Consulte [Cross-Device Analytics](/help/components/cda/overview.md) en la guía del usuario Componentes.

La identificación de visitantes entre dispositivos ayuda a conectar los visitantes a varios dispositivos. La identificación de visitantes entre dispositivos utiliza la variable `visitorID` para asociar un visitante a varios dispositivos. La variable `visitorID` tiene la prioridad más alta al identificar visitantes únicos.

Cuando envía una visita con un ID de visitante personalizado, Adobe comprueba si hay algún perfil de visitante que tenga un ID de visitante coincidente. Si existe uno, a partir de ese momento se utilizará un perfil del visitante almacenado en el sistema, mientras que el perfil anterior dejará de usarse.

Generalmente, la variable `visitorID` se configura tras la autenticación o después de que un visitante realice alguna otra acción que permita identificarlo de manera única independientemente del dispositivo que se emplee. Los identificadores efectivos incluyen un hash de su nombre de usuario, dirección de correo electrónico o un ID interno que no contiene información personal.

Una vez que el cliente inicia sesión desde cada dispositivo, todos están vinculados al mismo perfil de usuario. Si posteriormente el visitante cierra sesión en un dispositivo, seguirá perteneciendo al mismo perfil de visitante porque Adobe reconoce que la cookie del explorador en cada dispositivo pertenece al mismo perfil de visitante. Adobe recomienda usar la variable `visitorID` siempre que sea posible en caso de que se elimine la cookie del explorador.

## Limitaciones

El uso de su propio ID de visitante personalizado le proporciona más control sobre cómo se identifican los visitantes, pero viene con sus limitaciones.

* **La deduplicación de visitantes no es retroactiva**: Si un visitante accede al sitio por primera vez y luego se autentica, se cuentan dos visitantes únicos. Un visitante único cuenta para el ID de Analytics genérico generado automáticamente y otro cuenta para el ID de visitante personalizado cuando inicia sesión. Esta duplicación de visitantes únicos está presente cada vez que un visitante utiliza un nuevo dispositivo o borra sus cookies.
* **Incompatibilidad con el servicio Experience Cloud ID**: Desde la introducción de la identificación de visitantes entre dispositivos, Adobe ha publicado formas más potentes y fiables de rastrear a los visitantes entre dispositivos. Estos nuevos métodos de identificación no son compatibles con la anulación de ID de visitante personalizada. Si planea utilizar el servicio de ID o el análisis entre dispositivos (CDA), Adobe recomienda encarecidamente no utilizar `visitorID` variable.
