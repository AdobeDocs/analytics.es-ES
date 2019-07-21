---
description: Los eventos personalizados permiten definir el tipo de éxito que desea seguir.
keywords: Implementación de Analytics; evento personalizado
seo-description: Los eventos personalizados permiten definir el tipo de éxito que desea seguir.
seo-title: ¿Qué es un evento personalizado?
solution: Analytics
title: ¿Qué es un evento personalizado?
topic: Desarrollador e implementación
uuid: 8 e 78 ba 04-9 b 4 c -4566-980 c-c 24 dd 9 d 82236
translation-type: tm+mt
source-git-commit: d7056c233e784a073c75c55f396ff43c9e0d1c71

---


# ¿Qué es un evento personalizado?

Los eventos personalizados permiten definir el tipo de éxito que desea seguir.

Aunque son similares a los eventos [!UICONTROL predefinidos], los eventos [!UICONTROL personalizados] permiten definir su propia métrica de éxito. For example, if you have a newsletter, your success event could be _Registration_. Clearly, _Registration_ is not part of the [!UICONTROL predefined] events. Con un evento [!UICONTROL personalizado] puede realizar el seguimiento del número de visitantes que se suscriben al boletín. Los eventos [!UICONTROL personalizados] siguen la sintaxis estándar que se muestra a continuación.

```js
s.events="event3"
```

El código anterior muestra cómo asignar un evento a la variable _variables de eventos_ . If you do not modify the event name in the interface, _event3_ would display in the interface.

De forma predeterminada, los eventos de éxito se configuran como eventos de _contador_. Los eventos de contador contabilizan el número de veces que se configura un evento de éxito. Algunos eventos de éxito requieren que un evento aumente con una cantidad personalizada. These events can be set either as _numeric_ events or _currency_ events. Puede cambiar el tipo de evento en la Consola de administración.
