---
description: La siguiente tabla contiene la lista de tareas que debe llevar a cabo para migrar su implementación.
keywords: Implementación de Analytics, appmeasurement, migrar, migración, javascript
seo-description: La siguiente tabla contiene la lista de tareas que debe llevar a cabo para migrar su implementación.
seo-title: Migrar a AppMeasurement para JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Migrar a AppMeasurement para JavaScript
topic: Desarrollador e implementación
uuid: 5be345a8-5a95-4176-a2e6-97139b9b46ce
translation-type: ht
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Migrar a AppMeasurement para JavaScript

La siguiente tabla contiene la lista de tareas que debe llevar a cabo para migrar su implementación.

>[!NOTE]
>
>Se recomienda migrar al [Servicio de identidad](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) cuando migre a [!DNL AppMeasurement] para JavaScript.

![](assets/step1_icon.png) Comprobar la compatibilidad de complementos

Donde: s\_code.js

Algunos complementos ya no son compatibles. Consulte [Asistencia del complemento de AppMeasurement](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

![](assets/step2_icon.png) Descargar el nuevo AppMeasurement

Donde: Administración &gt; Administrador de códigos

El zip descargado contiene un archivo AppMeasurement.js reducido y archivos JavaScript para los módulos Media e Integrate.

![](assets/step3_icon.png) Copie su personalización de s\_code.js a `AppMeasurement.js`.

Donde: s\_code.js y AppMeasurement.js

Mueva todo el código que aparece antes de la sección `DO NOT ALTER ANYTHING BELOW THIS LINE` de s\_code.js al principio de AppMeasurement.js.

![](assets/step4_icon.png) (Opcional) Actualizar los complementos

Donde: AppMeasurement.js

Si va a usar el complemento getQueryParam, actualice estas llamadas para usar la nueva utilidad [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5)

![](assets/step5_icon.png) (Opcional) Actualizar los módulos Media e Integrate

Donde: AppMeasurement.js

Si va a usar alguno de estos módulos, copie el código de AppMeasurement\_Module\_Media.js o AppMeasurement\_Module\_Integrate.js y péguelo junto antes de `DO NOT ALTER ANYTHING BELOW THIS LINE` en AppMeasurement.js.

![](assets/step6_icon.png) Implementar el nuevo JavaScript

Donde: Su sitio web

Puede implementar el nuevo archivo JavaScript según su proceso estándar. El código de página existente es compatible con esta nueva versión.