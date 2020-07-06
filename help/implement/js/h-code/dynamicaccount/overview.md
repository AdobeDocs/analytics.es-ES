---
title: Información general sobre cuentas dinámicas
description: Descubra el flujo de trabajo sobre cómo seleccionar dinámicamente un grupo de informes con el código H.
translation-type: tm+mt
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: tm+mt
source-wordcount: '239'
ht-degree: 100%

---


# Información general sobre cuentas dinámicas

>[!IMPORTANT]
>
>Las cuentas dinámicas solo se admiten mediante implementaciones de JavaScript heredadas (código H). Estas variables no son compatibles con las bibliotecas de AppMeasurement actuales ni con Adobe Experience Platform Launch.

Las cuentas dinámicas son una función de implementación que permite determinar qué grupo de informes utilizar en función de los criterios definidos. Si su organización requiere más de un grupo de informes pero desea utilizar la misma implementación entre sus sitios, las cuentas dinámicas son una buena solución.

>[!TIP]
>
>Adobe recomienda enviar datos a un único grupo de informes y, a continuación, utilizar grupos de informes virtuales para separar los datos si es necesario. Consulte [Consideraciones del grupo de informes globales](../../../prepare/global-rs.md) para obtener más información.

3 variables se utilizan para seleccionar dinámicamente un grupo de informes.

* [`dynamicAccountSelection`](dynamicaccountselection.md): Activar o desactivar la selección dinámica de cuentas.
* [`dynamicAccountMatch`](dynamicaccountmatch.md): Determina qué valor se debe observar. Por ejemplo, la dirección URL o una cadena de consulta.
* [`dynamicAccountList`](dynamicaccountlist.md): Compara los valores con `dynamicAccountMatch`y, si se encuentra una coincidencia, rellena la variable `account`.

Si `dynamicAccountSelection = true`, el valor dentro de `dynamicAccountMatch` se compara con `dynamicAccountList`. Si los valores en `dynamicAccountList` coinciden, la ID del grupo de informes se incluye en la variable `account`.

## Grupo de informes predeterminado

La variable `account` se puede establecer primero y actúa como valor predeterminado en caso de que no se encuentren las cadenas especificadas. Por ejemplo:

```javascript
s_account = "examplersiddefault";
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersiddev=dev.example.com;examplersidprod=example.com";
```

Si `location.hostname` no es `dev.example.com` ni `example.com`, la visita se envía a `examplersiddefault`.

## Etiquetado de grupos múltiples

El etiquetado de grupos múltiples se puede utilizar con la selección dinámica de cuentas. Por ejemplo:

```js
s.dynamicAccountSelection = true;
s.dynamicAccountMatch = location.hostname;
s.dynamicAccountList="examplersid1,examplersid2=example.com";
```

Si `location.hostname` contiene `example.com`, la visita se envía tanto a `examplersid1` como a `examplersid2`.
