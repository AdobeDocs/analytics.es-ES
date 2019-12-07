---
description: El complemento getAndPersistValue obtiene un valor que usted elija y lo rellena en una variable de Analytics durante un período determinado. Comúnmente se utiliza para ver cuántas vistas de páginas genera una campaña después de una pulsación, lo que permite ver las páginas más comunes para cada campaña.
keywords: Analytics Implementation
subtopic: Plug-ins
title: getAndPersistValue
topic: Developer and implementation
uuid: ddeab80c-260e-44b6-8483-8b8b369ec19b
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# getAndPersistValue

El complemento getAndPersistValue obtiene un valor que usted elija y lo rellena en una variable de Analytics durante un período determinado. Comúnmente se utiliza para ver cuántas vistas de páginas genera una campaña después de una pulsación, lo que permite ver las páginas más comunes para cada campaña.

>[!IMPORTANT]
>
>Este complemento no se ha validado para que sea compatible con [AppMeasurement para JavaScript](/help/implement/js-implementation/c-appmeasurement-js/appmeasure-mjs.md). Consulte [Asistencia del complemento de AppMeasurement](/help/implement/js-implementation/c-appmeasurement-js/plugins-support.md).

Por ejemplo: puede utilizar este complemento para establecer un código de seguimiento de campaña de la variable *`campaign`* en una variable de tráfico personalizado (*`s.prop`*) en la vista de página de cada visitante realizada durante los próximos 30 días. Este ejemplo le permite determinar cuántas vistas de página ha generado el código de seguimiento como resultado de la pulsación original.

> [!NOTE] Las instrucciones siguientes exigen modificar el código de recopilación de datos en el sitio. Esto puede afectar a la recopilación de datos en el sitio y solamente debe hacerlo un desarrollador con experiencia en el uso y la implementación de [!DNL Analytics].

## Implementación y código de complemento {#section_92E94A96A4764113B5588F1B83E3DE2C}

**SECCIÓN CONFIG**: esta sección no requiere ninguna modificación.

**Configuración de complemento**

Inserte el siguiente código en la función *`s_doPlugins()`*, que está ubicada en el área del archivo *`s_code.js`con el nombre* Configurar complemento *.* Seleccione una variable de tráfico personalizado (término de búsqueda interna s.prop) o una variable de conversión personalizada (s.eVar) que se utilizarán en la captura de datos de valores persistentes. Debe ser una variable que se haya activado mediante Admin Console pero que en la actualidad no se esté utilizando para ningún otro fin. Puede utilizar el ejemplo siguiente y actualizarlo según sus necesidades.

`s.prop1=s.getAndPersistValue(s.campaign,'s_getval',30);`

*`s.getAndPersistValue`* tiene tres argumentos:

1. Variable o valor rellenados actualmente para conservarlos (*`s.campaign`*, se muestra arriba).
1. Nombre de la cookie, utilizado para almacenar el valor (*`s_getval`*, se muestra arriba).
1. Período de tiempo de persistencia, expresado en días. “30”, como se indica arriba, hace que el valor se rellene en la variable seleccionada con cada vista de página hecha por el usuario durante los 30 días siguientes. Si se omite, el valor predeterminado es *session*.

**SECCIÓN DE COMPLEMENTOS**: Agregue el código siguiente al área del archivo [!DNL s_code.js] con el nombre SECCIÓN DE COMPLEMENTOS. No realice ningún cambio en esta parte del código de complemento.

```js
/* 
 * Plugin: getAndPersistValue 0.3 - get a value on every page 
 */ 
s.getAndPersistValue=new Function("v","c","e","" 
+"var s=this,a=new Date;e=e?e:0;a.setTime(a.getTime()+e*86400000);if(" 
+"v)s.c_w(c,v,e?a:0);return s.c_r(c);");
```

Antes de su implementación en un entorno de desarrollo, realice pruebas exhaustivas de las instalaciones de complementos para asegurarse de que la recopilación de datos se comporta según lo esperado.
