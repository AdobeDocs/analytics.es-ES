---
description: Las variables de página rellenan directamente un informe, como pageName, Props de lista, Variables de lista, etc.
keywords: Analytics Implementation
subtopic: Variables
title: Variables de página
topic: null
uuid: null
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# transactionID

[!UICONTROL Las fuentes de datos de integración] utilizan una [!UICONTROL ID de transacción] para enlazar los datos sin conexión a una transacción en línea (como un cliente o una compra generados en línea).


<!-- 

transactionID.xml

 -->

Cada *`transactionID`* único enviado a Adobe se registrará a fin de prepararlo para una carga de [!UICONTROL fuentes de datos] de información sin conexión sobre esa transacción. Consulte [Fuentes de datos](https://marketing.adobe.com/resources/help/en_US/sc/datasources/).

| Tamaño máximo | Parámetro depurador | Informes rellenados | Valor predeterminado |
|---|---|---|---|
| 100 bytes | xact | n.d. | "" |

**Habilitar el almacenamiento del ID de transacción** {#section_3EA2C9DC9D4C4F0FBE4AB67981BCB52E}

Antes de registrar los valores de *`transactionID`*, el [!UICONTROL almacenamiento del ID de transacción] debe estar habilitado para el grupo de informes seleccionado en el Administrador del grupo de informes. Esta opción se encuentra en

```
Analytics > Admin > Report Suites > Edit Settings > General > General Account Settings.
```

Para ver si *`transactionID Storage`* está habilitado para un grupo de informes, vaya a

```
Analytics > Admin > Data Sources > Manage
```

**Sintaxis y valores posibles** {#section_0C18329203DC45E989DBAE70C0FB4801}

```js
s.transactionID="unique_id"
```

El *`transactionID`* solo puede contener caracteres alfanuméricos. Si debe registrar varias variables [!UICONTROL transactionID] para una sola visita, delimite los valores correspondientes con una coma.

**Ejemplos** {#section_A4C1F0E54CB54AD7B86A22147E9B5FEF}

```js
s.transactionID="11123456"
```

```js
s.transactionID="lead_12345xyz"
```

```js
s.transactionID=s.purchaseID
```

**Problemas, preguntas y consejos** {#section_4299BAD5D0154DBC88A9EF0E2C252BB4}

* Si el registro de *`transactionID`* no está habilitado, los valores de *`transactionID`* se descartarán y no estarán disponibles para su uso con las [!UICONTROL fuentes de datos de integración]. Asegúrese de establecer una variable de conversión o un evento (una eVar o la variable events) en la página donde se configure *`transactionID`*. De lo contrario, no se registrarán datos para *`transactionID`*.

* Si está registrando [!UICONTROL transactionIDs] para varios sistemas, como compras y posibles clientes, asegúrese de que el valor de *`transactionID`* siempre sea único. Esto puede conseguirse agregando un prefijo a la ID, por ejemplo, lead_1234 y purchase_1234. Las [!UICONTROL Fuentes de datos de integración] no funcionan de la manera esperada (los datos de [!UICONTROL fuentes de datos] se enlazarán a los datos incorrectos) si un mismo *`transactionID`* aparece dos veces.

* De forma predeterminada, los valores de *`transactionID`* se conservan durante 90 días. Si el proceso de interacción sin conexión supera los 90 días, póngase en contacto con el Servicio de atención al cliente para ampliar el límite.

> [!NOTE] La variable *`transactionID`* puede contener cualquier carácter que no sea una coma. Debe estar en la misma ubicación donde se especifica el límite de caracteres (100 bytes). Si se utilizan caracteres de bytes múltiples, debe habilitarse la compatibilidad con caracteres de bytes múltiples para evitar problemas con caracteres imprevistos en *`transactionID`*.
