---
description: Los eventos personalizados permiten definir el tipo de éxito que desea seguir.
keywords: Implementación de Analytics, evento personalizado
seo-description: Los eventos personalizados permiten definir el tipo de éxito que desea seguir.
seo-title: ¿Qué es un evento personalizado?
solution: Analytics
title: ¿Qué es un evento personalizado?
topic: Desarrollador e implementación
uuid: 8e78ba04-9b4c-4566-980c-c24dd9d82236
translation-type: ht
source-git-commit: d7056c233e784a073c75c55f396ff43c9e0d1c71

---


# ¿Qué es un evento personalizado?

Los eventos personalizados permiten definir el tipo de éxito que desea seguir.

Aunque son similares a los eventos [!UICONTROL predefinidos], los eventos [!UICONTROL personalizados] permiten definir su propia métrica de éxito. Por ejemplo, si tiene un boletín, el evento de éxito podría ser _Registro_. Claramente, _Registro_ no forma parte de los eventos [!UICONTROL predefinidos]. Con un evento [!UICONTROL personalizado] puede realizar el seguimiento del número de visitantes que se suscriben al boletín. Los eventos [!UICONTROL personalizados] siguen la sintaxis estándar que se muestra a continuación.

```js
s.events="event3"
```

El código anterior muestra cómo asignar un evento a la variable de _eventos_. Si no modifica el nombre del evento en la interfaz, esta mostrará _event3_.

De forma predeterminada, los eventos de éxito se configuran como eventos de _contador_. Los eventos de contador contabilizan el número de veces que se configura un evento de éxito. Algunos eventos de éxito requieren que se incremente un evento en una cantidad personalizada. Estos eventos se pueden configurar como _numeric_ o _currency_. Puede cambiar el tipo de evento usando Admin Console.
