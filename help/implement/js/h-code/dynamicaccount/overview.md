---
title: Información general sobre cuentas dinámicas
description: Descubra el flujo de trabajo sobre cómo seleccionar dinámicamente un grupo de informes con el código H.
feature: Implementation Basics
exl-id: 6f35dd71-29ad-4923-b1f7-9c7d6ca45bd8
role: Developer
TQID: https://experienceleague.adobe.com/PCeDSQpYH3wym7oG5CYbQblnXkiOQRF4YlcHU6zYfKA
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 243
ht-degree: 100%

---

# Información general sobre cuentas dinámicas

>[!IMPORTANT]
>
>Las cuentas dinámicas solo se admiten mediante implementaciones de JavaScript heredadas (código H). Estas variables no son compatibles con las bibliotecas de AppMeasurement actuales o con las etiquetas de Adobe Experience Platform.

Las cuentas dinámicas son una función de implementación que permite determinar qué grupo de informes utilizar en función de los criterios definidos. Si su organización requiere más de un grupo de informes pero desea utilizar la misma implementación entre sus sitios, las cuentas dinámicas son una buena solución.

>[!TIP]
>
>Adobe recomienda enviar datos a un único grupo de informes y, a continuación, utilizar grupos de informes virtuales para separar los datos si es necesario. Consulte [Consideraciones del grupo de informes globales](../../../prepare/global-rs.md) para obtener más información.

3 variables se utilizan para seleccionar dinámicamente un grupo de informes.

* [`dynamicAccountSelection`](dynamicaccountselection.md): Habilitar o deshabilitar la selección dinámica de cuentas.
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
