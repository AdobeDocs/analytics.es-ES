---
description: 'Ayuda a responder la pregunta: "Después de que un usuario hace clic en mi sitio desde una campaña, ¿a qué lugar del sitio va?"'
keywords: Analytics Implementation
title: Control de rutas por campaña o código de seguimiento
topic: Developer and implementation
uuid: eb6e3484-1b40-4ec6-8017-ac1003cdf636
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Control de rutas por campaña o código de seguimiento

Ayuda a responder la pregunta: "Después de que un usuario hace clic en mi sitio desde una campaña, ¿a qué lugar del sitio va?"

Para responder a esta pregunta, debe apartar una [!UICONTROL sprop] que se utilizará para este informe. Después, debe estructurar los datos que se rellenarán en la prop de manera que tengan sentido cuando se habilite el control de rutas.

En este ejemplo vamos a utilizar [!UICONTROL prop1] como prop de control de rutas de la campaña. Ahora, rellenará esta [!UICONTROL sprop] con el mismo valor que introdujo en la variable [!UICONTROL pageName]. Vea lo siguiente:

```js
s.prop1=s.pageName;
```

Debe hacer esto en todas las páginas a menos que el usuario haya hecho clic desde una campaña. Si han hecho clic desde una campaña y están en la página de aterrizaje de la campaña, rellene la prop con una concatenación de la campaña y [!UICONTROL pageName]. Vea lo siguiente:

```js
 s.prop1=s.campaign + ' : ' + s.pageName;
```

Si el nombre de la campaña donde hicieron clic es "banner1234" y el nombre de la página donde aterrizaron es "Home Page", el valor de esa prop sería "banner1234 : Home Page". En todas las páginas posteriores, ponga [!UICONTROL pageName] en la prop como se indicó antes.

Cuando un usuario hace clic en esta campaña y ve un total de cuatro páginas en esa visita, obtendrá los siguientes valores en la sprop en este orden:

```js
"banner1234 : Home Page" > "Page 2" > "Page 3" > "Page 4"
```

Con los datos capturados en [!UICONTROL prop1] de esta manera y con el control de rutas habilitado en esta prop, podemos consultar uno de los diferentes informes de rutas para comprender las rutas que siguen por el sitio desde que hacen clic en una campaña.

Puede especificar la página con la que desea iniciar el informe de rutas. En este caso, seleccionó "banner1234 : Home Page" porque quería saber dónde iban los usuarios después de hacer clic en "banner 1234" en una campaña. Este informe es solo un ejemplo de los numerosos informes de rutas.
