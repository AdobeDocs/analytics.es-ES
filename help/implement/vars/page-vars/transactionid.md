---
title: transactionID
description: Utilice esta variable para vincular datos en línea y sin conexión.
translation-type: ht
source-git-commit: c4833525816d81175a3446215eb92310ee4021dd
workflow-type: ht
source-wordcount: '394'
ht-degree: 100%

---


# transactionID

La variable `transactionID` identifica de forma exclusiva una transacción para que la visita se pueda enlazar a los datos cargados a través de las fuentes de datos. Esta variable es útil si desea utilizar datos de otros canales y vincularlos a datos recopilados con AppMeasurement.

>[!NOTE]
>
>Asegúrese de que el [!UICONTROL Almacenamiento de ID de transacción] esté habilitado en un grupo de informes antes de utilizar esta variable. Consulte [Configuración general de la cuenta](/help/admin/admin/general-acct-settings-admin.md) en la Guía de administración para obtener más información.

Cuando se configura `transactionID` en caso de una visita, Adobe toma una “instantánea” de todas las variables de Analytics que estaban establecidas o que persistían en ese momento. Los datos cargados a través de fuentes de datos con el mismo ID de transacción están permanentemente vinculados a esos valores de variables.

De forma predeterminada, Adobe registra todos los valores de ID de transacción (vinculados y desvinculados) durante un máximo de 90 días. Si el proceso de interacción sin conexión supera los 90 días, contacte con el Servicio de atención al cliente para ampliar este límite.

## ID de transacción en Adobe Experience Platform Launch

Puede establecer el ID de transacción al configurar la extensión de Analytics (variables globales) o en reglas.

1. Inicie sesión en [launch.adobe.com](https://launch.adobe.com) con sus credenciales de Adobe ID.
2. Haga clic en la propiedad deseada.
3. Vaya a la pestaña [!UICONTROL Reglas] y, a continuación, haga clic en la regla que desee (o cree una regla).
4. En [!UICONTROL Acciones], haga clic en una acción existente de [!UICONTROL Adobe Analytics: Establecer variables] o haga clic en el icono “+”.
5. Establezca el menú desplegable [!UICONTROL Extensión] en Adobe Analytics y el [!UICONTROL tipo de acción] en [!UICONTROL Establecer variables].
6. Busque la sección [!UICONTROL ID de transacción].

Puede establecer el ID de transacción para cualquier valor de cadena, incluidos los elementos de datos.

## s.transactionID en AppMeasurement y el editor de código personalizado de Launch

La variable `s.transactionID` es una cadena que contiene un identificador único para una transacción. Todos los caracteres alfanuméricos de hasta 100 bytes de longitud son valores válidos. Aparece como una cadena vacía de manera predeterminada.

```js
s.transactionID = "ABC123";
```

Si tiene más de un ID de transacción para una visita, puede delimitar cada uno con una coma. Si existen varios ID de transacción, el límite de 100 bytes se sigue aplicando.

```js
s.transactionID = "ABC123,XYZ456";
```

>[!NOTE]
>
>Si integra varios canales sin conexión mediante esta variable, asegúrese de que los distintos canales no se superponen con los ID de transacción. Por ejemplo, si tiene un valor de ID de transacción de centro de llamadas de `1234` y un valor de ID de transacción de cliente potencial de `1234`, pueden entrar en conflicto y provocar resultados inesperados. Compruebe que los ID de transacción tengan formatos únicos del canal sin conexión y diferéncielos si fuera preciso. Por ejemplo, establezca el ID de transacción del centro de llamadas en `call_1234` y el ID de transacción de cliente potencial en `lead_1234` en las fuentes de datos y AppMeasurement.
