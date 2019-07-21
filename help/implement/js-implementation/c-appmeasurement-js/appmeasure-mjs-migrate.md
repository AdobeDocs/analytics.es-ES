---
description: La siguiente tabla contiene la lista de tareas que debe llevar a cabo para migrar su implementación.
keywords: Implementación de Analytics; appmeasurement; migrate; migrar; javascript
seo-description: La siguiente tabla contiene la lista de tareas que debe llevar a cabo para migrar su implementación.
seo-title: Migrar a AppMeasurement para JavaScript
solution: Analytics
subtopic: JavaScript AppMeasurement
title: Migrar a AppMeasurement para JavaScript
topic: Desarrollador e implementación
uuid: 5 be 345 a 8-5 a 95-4176-a 2 e 6-97139 b 9 b 46 ce
translation-type: tm+mt
source-git-commit: 4e7a8bab956503093633deff0a64e8c7af2d5497

---


# Migrar a AppMeasurement para JavaScript

La siguiente tabla contiene la lista de tareas que debe llevar a cabo para migrar su implementación.

>[!NOTE]
>
>We recommend migrating to the [Identity Service](../../../implement/js-implementation/c-unique-visitors/visid-service.md#concept_230F8759826E47789EA8DEE08FA09B07) when you migrate to [!DNL AppMeasurement] for JavaScript.

![](assets/step1_icon.png) Comprobar la compatibilidad de complementos

Donde: s\_ code. js

Algunos complementos ya no son compatibles. See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A) .

![](assets/step2_icon.png) Descargar el nuevo AppMeasurement

Donde: Administrador &gt; Administrador de códigos

El zip descargado contiene un archivo AppMeasurement.js reducido y archivos JavaScript para los módulos Media e Integrate.

![](assets/step3_icon.png) Copie la `AppMeasurement.js`personalización de s\_ code. js.

Donde: s\_ code. js y appmeasurement. js

Move all code that appears before the `DO NOT ALTER ANYTHING BELOW THIS LINE` section in s\_code.js to the beginning of AppMeasurement.js.

![](assets/step4_icon.png) (Opcional) Actualizar los complementos

Donde: Appmeasurement. js

If you are using the getQueryParam plug-in, update these calls to use the new utility, [Util.getQueryParam](../../../implement/js-implementation/util-getqueryparam.md#concept_763AD2621BB44A3990204BE72D3C9FA5).

![](assets/step5_icon.png) (Opcional) Actualizar los módulos Media e Integrate

Donde: Appmeasurement. js

If you are using either of these modules, copy and paste the code from AppMeasurement\_Module\_Media.js and/or AppMeasurement\_Module\_Integrate.js and paste it just before the `DO NOT ALTER ANYTHING BELOW THIS LINE` in AppMeasurement.js.

![](assets/step6_icon.png) Implementar el nuevo JavaScript

Donde: Su sitio web

Puede implementar el nuevo archivo JavaScript según su proceso estándar. El código de página existente es compatible con esta nueva versión.