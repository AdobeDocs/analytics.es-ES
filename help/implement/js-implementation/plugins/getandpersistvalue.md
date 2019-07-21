---
description: El complemento getAndPersistValue obtiene un valor que usted elija y lo rellena en una variable de Analytics durante un período determinado. Comúnmente se utiliza para ver cuántas vistas de páginas genera una campaña después de una pulsación, lo que permite ver las páginas más comunes para cada campaña.
keywords: Implementación de Analytics
seo-description: El complemento getAndPersistValue obtiene un valor que usted elija y lo rellena en una variable de Analytics durante un período determinado. Comúnmente se utiliza para ver cuántas vistas de páginas genera una campaña después de una pulsación, lo que permite ver las páginas más comunes para cada campaña.
seo-title: getAndPersistValue
solution: Analytics
subtopic: Complementos
title: getAndPersistValue
topic: Desarrollador e implementación
uuid: ddeab 80 c -260 e -44 b 6-8483-8 b 8 b 369 ec 19 b
translation-type: tm+mt
source-git-commit: ee0cb9b64a3915786f8f77d80b55004daa68cab6

---


# getAndPersistValue

El complemento getAndPersistValue obtiene un valor que usted elija y lo rellena en una variable de Analytics durante un período determinado. Comúnmente se utiliza para ver cuántas vistas de páginas genera una campaña después de una pulsación, lo que permite ver las páginas más comunes para cada campaña.

>[!IMPORTANT]
>
>This plug-in has not been validated to be compatible with [AppMeasurement for JavaScript](../../../implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md#concept_F3957D7093A94216BD79F35CFC1557E8). See [AppMeasurement Plug-in Support](../../../implement/js-implementation/c-appmeasurement-js/plugins-support.md#concept_E31A189BC8A547738666EB5E00D2252A).

For example, you might use this plug-in to set a campaign tracking code from the *`campaign`* variable into a Custom Traffic ( *`s.prop`*) variable on each visitor's page view made for the next 30 days. Este ejemplo le permite determinar cuántas vistas de página ha generado el código de seguimiento como resultado de la pulsación original.

>[!NOTE]
>
>Las instrucciones siguientes requieren modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Implementación y código de complemento {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SECCIÓN CONFIG**: esta sección no requiere ninguna modificación. 

**Configuración de complemento**

Inserte el código siguiente en la función *`s_doPlugins()`* , que se encuentra en el área del *`s_code.js`* archivo rotulada Configuración *de complemento*. Seleccione una variable de tráfico personalizado (término de búsqueda interna s.prop) o una variable de conversión personalizada (s.eVar) que se utilizarán en la captura de datos de valores persistentes. Debe ser una variable que se haya activado mediante Admin Console pero que en la actualidad no se esté utilizando para ningún otro fin. Puede utilizar el ejemplo siguiente y actualizarlo según sus necesidades.

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* tiene tres argumentos:

1. Currently populated variable or value to persist ( *`s.campaign`* shown above).
1. Cookie name, used to store the value ( *`s_getval`* shown above).
1. Período de tiempo de persistencia, expresado en días. “30”, como se indica arriba, hace que el valor se rellene en la variable seleccionada con cada vista de página hecha por el usuario durante los 30 días siguientes. Si se omite, el valor predeterminado es *session*.

**SECCIÓN DE COMPLEMENTOS**: Agregue el siguiente código al área del [!DNL s_code.js] archivo rotulada SECCIÓN DE COMPLEMENTOS. No realice ningún cambio en esta parte del código de complemento.

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

Antes de su implementación en un entorno de desarrollo, realice pruebas exhaustivas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
