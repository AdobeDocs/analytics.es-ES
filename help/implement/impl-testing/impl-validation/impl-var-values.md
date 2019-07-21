---
description: Asegúrese de que las variables que se rellenan desde scripts o código del servidor no incluyen comillas que pudieran interferir con los valores.
keywords: Implementación de Analytics
seo-description: Asegúrese de que las variables que se rellenan desde scripts o código del servidor no incluyen comillas que pudieran interferir con los valores.
seo-title: Variables y valores
solution: Analytics
title: Variables y valores
topic: Desarrollador e implementación
uuid: 2 ff 4857 a -9451-4794-9146-f 417 abd 1 d 1 ba
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

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

Ensure that the events variable is populated with an appropriate value ( [!UICONTROL prodView], [!UICONTROL purchase], [!UICONTROL scAdd], [!UICONTROL scRemove], [!UICONTROL scOpen], or event1-event5) whenever *`products`* is populated. Asegúrese de mantener las mayúsculas y minúsculas de todas las variables y funciones de [!DNL Analytics], como se indica a continuación.

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

>[!NOTE]
>
>No se pueden combinar varios registros de páginas dentro de los informes.

Compruebe que los vínculos se incluyen en el informe [!UICONTROL Vínculos personalizado]. Asegúrese de que se pasan los parámetros correctos a la función [!UICONTROL tl]. Para obtener más información sobre [!UICONTROL vínculos personalizados], consulte [Seguimiento de vínculos](../../../implement/js-implementation/function-tl.md#concept_EA13689CB8EE4F308FC89A1293046D5E).
