---
description: La segmentación de rutas por tipo de usuario es una solicitud habitual para intentar comprender las rutas que siguen los tipos de usuarios en su sitio.
keywords: Implementación de Analytics
seo-description: La segmentación de rutas por tipo de usuario es una solicitud habitual para intentar comprender las rutas que siguen los tipos de usuarios en su sitio.
seo-title: Rutas de segmentos por tipo de usuario
solution: Analytics
title: Rutas de segmentos por tipo de usuario
topic: Desarrollador e implementación
uuid: 5 c 298 f 39-381 d -453 b-a 608-109 e 3276 b 361
translation-type: tm+mt
source-git-commit: 76d0ce11d9b560e0df866be9e753804b6fa4bb3d

---


# Rutas de segmentos por tipo de usuario

La segmentación de rutas por tipo de usuario es una solicitud habitual para intentar comprender las rutas que siguen los tipos de usuarios en su sitio.

Puede concatenar el tipo de usuario y el nombre de la página en una [!UICONTROL sprop] y habilitar el control de rutas en la [!UICONTROL sprop].

For example, let's say you have two user types: _Registered_ users and _Non-Registered_ users. Necesita distinguir entre estos dos tipos de usuarios en cada página y poner estos valores en la [!UICONTROL sprop] designada. Cuando rellene la prop, debe tener el siguiente aspecto:

```js
 s.prop1=”Registered : “ + s.pageName;
```

Si el usuario está registrado y ha visitado la página de inicio, el valor de la prop muestra lo siguiente:

```js
 “Registered : Home Page”
```

Si hace clic en otra página denominada "Page 2", el valor de esa página muestra lo siguiente:

```js
 “Registered : Page 2”
```

Con el [!UICONTROL control de rutas] activado, verá estos dos valores consecutivos. Si desea saber cómo se mueven los usuarios desde la página de inicio, busque el valor "Registrados : Página de inicio" en uno de los informes de rutas y vea qué páginas visitó después. En este caso, después fue a "Page 2".
