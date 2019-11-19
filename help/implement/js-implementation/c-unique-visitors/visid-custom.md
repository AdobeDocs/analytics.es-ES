---
description: Puede implementar un método personalizado para identificar a los visitantes mediante la configuración de la variable s.visitorID.
keywords: Analytics Implementation
solution: Analytics
title: ID de visitante personalizado
topic: Developer and implementation
uuid: 49881e27-0418-4ecf-a092-dcc3db923f40
translation-type: tm+mt
source-git-commit: edf88e40cae8b6886b04257f266666c13a37f88d

---


# ID de visitante personalizado

Puede implementar un método personalizado para identificar a los visitantes mediante la configuración de la variable s.visitorID.

La ID de visitante personalizada se puede usar en los sitios en los que tenga un solo método para identificar a los visitantes. Puede servir de ejemplo una ID que se genera cuando un usuario inicia sesión en un sitio web con un nombre de usuario y una contraseña.

Si puede derivar y administrar las [!UICONTROL ID de visitantes] de sus usuarios, puede usar los métodos siguientes para configurar la ID:

| Método | Descripción |
|---|---|
| [s.visitorID](/help/implement/js-implementation/page-variables/page-variables.md) | Si se usa JavaScript en el explorador, o si está usando cualquier otra biblioteca de AppMeasurement, puede configurar la ID del visitante en una variable de recopilación de datos. |
| Parámetro de cadena de consulta en la solicitud de imagen | Con este método puede pasar la [!UICONTROL ID de visitante] a Adobe mediante el parámetro de [!UICONTROL cadena de consulta vid] en una solicitud de imagen codificada. |
| API de inserción de datos | En dispositivos que usan protocolos inalámbricos que no aceptan JavaScript, puede enviar una publicación XML que contenga el elemento XML `<visitorid/>` a servidores de recopilación de Adobe desde sus servidores. |
| Reescritura de direcciones URL y VISTA | Algunas arquitecturas de implementación permiten la reescritura de direcciones URL para mantener el estado de la sesión cuando no se puede configurar una cookie. En estos casos, los servicios de ingeniería de Adobe pueden implementar una regla [!DNL VISTA] para buscar el valor de sesión en la dirección URL de la página y, después, darle formato y colocarla en los valores [!UICONTROL visid]. |
>[!CAUTION]
>**Los ID de visitante personalizados deben ser suficientemente granulares y únicos**: Una implementación no válida de los ID de visitante personalizados puede provocar que los datos sean incorrectos y que el rendimiento de los informes sea deficiente. Si el ID de visitante personalizado no es lo suficientemente único o granular, o si se establece incorrectamente en un valor predeterminado común como la cadena "NULL" o "0", Adobe Analytics verá las visitas de muchos visitantes diferentes como un solo visitante. Esta situación da como resultado datos incorrectos, con recuentos de visitantes demasiado bajos y segmentos que no funcionan correctamente para ese visitante. Un ID de visitante personalizado insuficientemente granular también evita que los datos se propaguen correctamente entre los nodos del clúster de informes de Analytics. En este caso, un nodo se sobrecarga y no puede procesar las solicitudes de informes de manera oportuna. Finalmente, todos los informes del grupo de informes fallarán. <br>Es posible que las ID de visitante personalizadas mal implementadas no afecten inmediatamente al rendimiento de los informes, ya que Analytics puede con frecuencia gestionar datos desequilibrados en varios meses; sin embargo, con el tiempo un valor de ID de visitante personalizado mal implementado puede resultar problemático, ya que requiere que Analytics deshabilite el procesamiento de los grupos de informes afectados.</br><br>Los implementadores deben seguir la guía de que un solo valor de ID de visitante personalizado nunca debe recibir crédito por más del 1% del tráfico del grupo de informes. Aunque la guía del 1% es suficiente para la mayoría de los grupos de informes, el límite real que podría afectar al rendimiento de los informes podría ser inferior al 1% para los grupos de informes más grandes.</br>
