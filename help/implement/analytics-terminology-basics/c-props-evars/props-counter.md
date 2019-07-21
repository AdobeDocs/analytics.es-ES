---
description: Un contador almacena (y a veces muestra) el número de veces que se ha producido un evento o proceso determinado.
keywords: Implementación de Analytics; props; s. prop; custom traffic; contadores
seo-description: Un contador almacena (y a veces muestra) el número de veces que se ha producido un evento o proceso determinado.
seo-title: Uso de props como contadores
solution: Analytics
title: Uso de props como contadores
topic: Desarrollador e implementación
uuid: ab 83 bd 7 e -10 d 9-49 f 9-b 9 e 7-c 50397 e 95 c 17
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# Uso de props como contadores

Un contador almacena (y a veces muestra) el número de veces que se ha producido un evento o proceso determinado.

Puede usar una prop para contabilizar el número de veces que se produce un evento. Por ejemplo, desea realizar el seguimiento del uso de Real Player frente al Reproductor de Windows Media en el sitio. Cada página contiene [!UICONTROL código para pegar], donde puede ver variables [!UICONTROL s.prop]. Utilice [!UICONTROL s.prop] 1 para realizar el seguimiento de los reproductores. Para la página A, introduzca un valor en [!UICONTROL s.prop]1 para representar a Real Player.

```js
s.prop1="RealPlayer"
```

Para la página B, introduzca un valor similar en [!UICONTROL s.prop]1 para el Reproductor de Windows Media, como se muestra a continuación.

```js
s.prop1="WindowsMP"
```

>[!NOTE]
>
>Adobe offers up to 75 [!UICONTROL s.prop] variables for you to use.

Mientras los visitantes llegan al sitio y visitan las páginas que contienen Real Player o el Reproductor de Windows Media, [!DNL Analytics] puede segmentar esos usuarios en función de qué páginas hayan visitado. A continuación, el informe [!UICONTROL Tráfico personalizado] muestra el número de visitas a cada página.

>[!NOTE]
>
>The name of the [!UICONTROL Custom Traffic] report can be customized. Por ejemplo, se puede cambiar el nombre del informe de [!UICONTROL Tráfico personalizado] por "Informe por tipos de reproductor".

