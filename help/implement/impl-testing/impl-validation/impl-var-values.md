---
description: Asegúrese de que las variables que se rellenan desde scripts o código del servidor no incluyen comillas que pudieran interferir con los valores.
keywords: Analytics Implementation
solution: Analytics
title: Variables y valores
topic: Developer and implementation
uuid: 2ff4857a-9451-4794-9146-f417abd1d1ba
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Variables y valores

Asegúrese de que las variables que se rellenan desde scripts o código del servidor no incluyen comillas que pudieran interferir con los valores.

Por ejemplo:

```js
s.pageName="Article: "Article Name"" 
s.pageName='Company's Information' 
```

Asegúrese de que los valores de las variables no exceden los límites máximos especificados en este documento. Los caracteres adicionales se truncan en los servidores de recopilación de datos. Podrían interferir con la longitud total, aumentar innecesariamente el ancho de banda y provocar otros problemas.

No use $, ™, ®, © ni comas (,) en la variable products. Por lo general, no resultan útiles en ninguna de las variables de [!DNL Analytics] y podrían afectar a la interpretación o exportación de los campos. La práctica recomendada de Adobe limitar los caracteres a los primeros 127 caracteres ASCII.

Asegúrese de que la variable de eventos se rellena con un valor apropiado ([!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen] o event1-event5) siempre que *`products`* se rellene. Asegúrese de mantener las mayúsculas y minúsculas de todas las variables y funciones de [!DNL Analytics], como se indica a continuación.

```js
s.pageName 
s.server 
s.channel 
s.pageType 
s.prop1 - s.prop20 
s.campaign 
s.state 
s.zip 
s.events 
s.products 
s.purchaseID 
s.eVar1 - s.eVar20 
var s_code=s.t();if(s_code)document.write(s_code)//--> 
```

Los nombres de página distinguen entre mayúsculas y minúsculas y, en caso de diferencia, se crean registros de página adicionales. "Home" y "home" son dos páginas diferentes en [!DNL Analytics].

> [!NOTE] No se pueden combinar varios registros de página en los informes.

Compruebe que los vínculos se incluyen en el informe [!UICONTROL Vínculos personalizado]. Asegúrese de que se pasan los parámetros correctos a la función [!UICONTROL tl]. Para obtener más información sobre [!UICONTROL vínculos personalizados], consulte [Seguimiento de vínculos](/help/implement/js-implementation/function-tl.md).
