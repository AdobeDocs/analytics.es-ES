---
description: La segmentación de rutas por tipo de usuario es una solicitud habitual para intentar comprender las rutas que siguen los tipos de usuarios en su sitio.
keywords: Implementación de Analytics
seo-description: La segmentación de rutas por tipo de usuario es una solicitud habitual para intentar comprender las rutas que siguen los tipos de usuarios en su sitio.
seo-title: Segmentación de rutas por tipo de usuario
solution: Analytics
title: Segmentación de rutas por tipo de usuario
topic: Desarrollador e implementación
uuid: 5c298f39-381d-453b-a608-109e3276b361
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Segmentación de rutas por tipo de usuario

La segmentación de rutas por tipo de usuario es una solicitud habitual para intentar comprender las rutas que siguen los tipos de usuarios en su sitio.

Puede concatenar el tipo de usuario y el nombre de la página en una [!UICONTROL sprop] y habilitar el control de rutas en la [!UICONTROL sprop].

Por ejemplo, supongamos que tiene dos tipos de usuarios: _Registrados_ y _No registrados_. Necesita distinguir entre estos dos tipos de usuarios en cada página y poner estos valores en la [!UICONTROL sprop] designada. Cuando rellene la prop, debe tener el siguiente aspecto:

```js
 s.prop1="Registered : " + s.pageName;
```

Si el usuario está registrado y ha visitado la página de inicio, el valor de la prop muestra lo siguiente:

```js
 "Registered : Home Page"
```

Si hace clic en otra página denominada "Page 2", el valor de esa página muestra lo siguiente:

```js
 "Registered : Page 2"
```

Con el [!UICONTROL control de rutas] activado, verá estos dos valores consecutivos. Si desea saber cómo se mueven los usuarios desde la página de inicio, busque el valor "Registrados : Página de inicio" en uno de los informes de rutas y vea qué páginas visitó después. En este caso, después fue a "Page 2".
