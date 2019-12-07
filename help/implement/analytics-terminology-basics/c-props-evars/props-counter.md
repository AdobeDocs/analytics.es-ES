---
description: Un contador almacena (y a veces muestra) el número de veces que se ha producido un evento o proceso determinado.
keywords: Analytics Implementation;props;s.prop;custom traffic;counters
title: Uso de props como contadores
topic: Developer and implementation
uuid: ab83bd7e-10d9-49f9-b9e7-c50397e95c17
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

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

> [!NOTE] Adobe ofrece hasta 75 variables [!UICONTROL s.prop] que puede usar.

Mientras los visitantes llegan al sitio y visitan las páginas que contienen Real Player o el Reproductor de Windows Media, [!DNL Analytics] puede segmentar esos usuarios en función de qué páginas hayan visitado. A continuación, el informe [!UICONTROL Tráfico personalizado] muestra el número de visitas a cada página.

> [!NOTE] El nombre del informe de [!UICONTROL Tráfico personalizado] se puede personalizar. Por ejemplo, se puede cambiar el nombre del informe de [!UICONTROL Tráfico personalizado] por "Informe por tipos de reproductor".

