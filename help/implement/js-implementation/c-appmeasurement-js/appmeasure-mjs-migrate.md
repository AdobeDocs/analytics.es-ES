---
description: La siguiente tabla contiene la lista de tareas que debe llevar a cabo para migrar su implementación.
keywords: Analytics Implementation;appmeasurement;migrate;migrating;javascript
subtopic: JavaScript AppMeasurement
title: Migrar a AppMeasurement para JavaScript
topic: Developer and implementation
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Migrar a AppMeasurement para JavaScript

La siguiente tabla contiene la lista de tareas que debe llevar a cabo para migrar su implementación.

>[!NOTE]
>
>Se recomienda migrar al [Servicio de identidad](/help/implement/js-implementation/c-unique-visitors/visid-service.md) cuando migre a [!DNL AppMeasurement] para JavaScript.

![](assets/step1_icon.png) Comprobar la compatibilidad de complementos

Donde: s\_code.js

Algunos complementos ya no son compatibles. Consulte [Asistencia del complemento de AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

![](assets/step2_icon.png) Descargar el nuevo AppMeasurement

Donde: Administración &gt; Administrador de códigos

El zip descargado contiene un archivo AppMeasurement.js reducido y archivos JavaScript para los módulos Media e Integrate.

![](assets/step3_icon.png) Copie su personalización de s\_code.js a `AppMeasurement.js`.

Donde: s\_code.js y AppMeasurement.js

Mueva todo el código que aparece antes de la sección `DO NOT ALTER ANYTHING BELOW THIS LINE` de s\_code.js al principio de AppMeasurement.js.

![](assets/step4_icon.png) (Opcional) Actualizar los complementos

Donde: AppMeasurement.js

Si va a usar el complemento getQueryParam, actualice estas llamadas para usar la nueva utilidad [Util.getQueryParam](/help/implement/js-implementation/util-getqueryparam.md)

![](assets/step5_icon.png) (Opcional) Actualizar los módulos Media e Integrate

Donde: AppMeasurement.js

Si va a usar alguno de estos módulos, copie el código de AppMeasurement\_Module\_Media.js o AppMeasurement\_Module\_Integrate.js y péguelo junto antes de `DO NOT ALTER ANYTHING BELOW THIS LINE` en AppMeasurement.js.

![](assets/step6_icon.png) Implementar el nuevo JavaScript

Donde: Su sitio web

Puede implementar el nuevo archivo JavaScript según su proceso estándar. El código de página existente es compatible con esta nueva versión.
