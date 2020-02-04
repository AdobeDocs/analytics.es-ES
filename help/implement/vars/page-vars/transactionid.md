---
title: transactionID
description: Utilice esta variable para vincular datos en línea y sin conexión.
translation-type: tm+mt
source-git-commit: f75c6759feb6576017733f1aac5bff2e21d4b0af

---


# transactionID

La `transactionID` variable identifica de forma exclusiva una transacción para que la visita se pueda enlazar a los datos cargados a través de las fuentes de datos. Esta variable es valiosa en los casos en los que desee utilizar datos de otros canales y vincularlos a datos recopilados con AppMeasurement.

> [!NOTE] Asegúrese de que Almacenamiento [!UICONTROL de ID de] transacción esté habilitado en un grupo de informes antes de utilizar esta variable. See [General Account Settings](/help/admin/admin/general-acct-settings-admin.md) in the Admin user guide for more information.

Cuando se configura `transactionID` en una visita, Adobe toma una &quot;instantánea&quot; de todas las variables de Analytics establecidas o persistentes en ese momento. Los datos cargados a través de fuentes de datos con un ID de transacción coincidente están permanentemente vinculados a esos valores de variables.

De forma predeterminada, Adobe recuerda todos los valores de ID de transacción (vinculados y desvinculados) durante un máximo de 90 días. Si el proceso de interacción sin conexión dura más de 90 días, póngase en contacto con el Servicio de atención al cliente para ampliar este límite.

## ID de transacción en Adobe Experience Platform Launch

Puede establecer el ID de transacción al configurar la extensión de Analytics (variables globales) o en reglas.

1. Log in to [launch.adobe.com](https://launch.adobe.com) using your AdobeID credentials.
2. Haga clic en la propiedad que desee.
3. Vaya a la ficha [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics - Establecer variables] o haga clic en el icono &#39;+&#39;.
5. Defina el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el tipo [!UICONTROL de] acción en [!UICONTROL Establecer variables].
6. Busque la sección ID [!UICONTROL de transacción] .

Puede establecer el ID de transacción en cualquier valor de cadena, incluidos los elementos de datos.

## s.transactionID en el editor de código personalizado AppMeasurement e Launch

La `s.transactionID` variable es una cadena que contiene un identificador único para una transacción. Los valores válidos incluyen caracteres alfanuméricos de hasta 100 bytes de longitud. Su valor predeterminado es una cadena vacía.

```js
s.transactionID = "ABC123";
```

Si tiene más de un ID de transacción para una visita, puede delimitar cada una con una coma. Varios ID de transacción siguen sujetos al límite de 100 bytes.

```js
s.transactionID = "ABC123,XYZ456";
```

> [!NOTE] Si integra varios canales sin conexión mediante esta variable, asegúrese de que los distintos canales no se superponen con los ID de transacción. Por ejemplo, si tiene un valor de ID de transacción de centro de llamadas de `1234` y un valor de ID de transacción de cliente potencial de ventas de `1234`, pueden entrar en conflicto y provocar resultados inesperados. Asegúrese de que los ID de transacción contienen formatos únicos por canal sin conexión y diferenciarlos si es necesario. Por ejemplo: configure el ID de transacción del centro de llamadas en y el ID de transacción de posibles clientes `call_1234` de ventas `lead_1234` en las fuentes de datos y AppMeasurement.
