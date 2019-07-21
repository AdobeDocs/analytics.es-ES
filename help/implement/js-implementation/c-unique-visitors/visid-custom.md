---
description: Puede implementar un método personalizado para identificar a los visitantes mediante la configuración de la variable s.visitorID.
keywords: Implementación de Analytics
seo-description: Puede implementar un método personalizado para identificar a los visitantes mediante la configuración de la variable s.visitorID.
seo-title: ID de visitante personalizado
solution: Analytics
title: ID de visitante personalizado
topic: Desarrollador e implementación
uuid: 49881 e 27-0418-4 ecf-a 092-dcc 3 db 923 f 40
translation-type: tm+mt
source-git-commit: 86fe1b3650100a05e52fb2102134fee515c871b1

---


# ID de visitante personalizado

Puede implementar un método personalizado para identificar a los visitantes mediante la configuración de la variable s.visitorID.

La ID de visitante personalizada se puede usar en los sitios en los que tenga un solo método para identificar a los visitantes. Puede servir de ejemplo una ID que se genera cuando un usuario inicia sesión en un sitio web con un nombre de usuario y una contraseña.

Si puede derivar y administrar las [!UICONTROL ID de visitantes] de sus usuarios, puede usar los métodos siguientes para configurar la ID:

| Método | Descripción |
|---|---|
| [s.visitorID](/help/implement/js-implementation/c-variables/page-variables.md) | Si se usa JavaScript en el explorador, o si está usando cualquier otra biblioteca de AppMeasurement, puede configurar la ID del visitante en una variable de recopilación de datos. |
| Parámetro de cadena de consulta en la solicitud de imagen | Con este método puede pasar la [!UICONTROL ID de visitante] a Adobe mediante el parámetro de [!UICONTROL cadena de consulta vid] en una solicitud de imagen codificada. |
| API de inserción de datos | On devices using wireless protocols that don't accept JavaScript, you can send an XML post containing the `<visitorid/>` XML element to Adobe collection servers from your servers. |
| Reescritura de direcciones URL y VISTA | Algunas arquitecturas de implementación permiten la reescritura de direcciones URL para mantener el estado de la sesión cuando no se puede configurar una cookie. En estos casos, los servicios de ingeniería de Adobe pueden implementar una regla [!DNL VISTA] para buscar el valor de sesión en la dirección URL de la página y, después, darle formato y colocarla en los valores [!UICONTROL visid]. |
>[!CAUTION]
>**Las ID de visitante personalizadas deben ser lo suficientemente granulares o únicas**: Una implementación no válida de ID de visitante personalizados puede llevar a datos incorrectos y a un bajo rendimiento de informes. Si el ID de visitante personalizado no es único o granular, o se establece incorrectamente en un valor predeterminado común como la cadena «NULL» o «0», Adobe Analytics verá las visitas de muchos visitantes diferentes como un solo visitante. Esta situación produce datos incorrectos, mientras que los visitantes son demasiado bajos y los segmentos no funcionan correctamente para ese visitante. Un ID de visitante personalizado y no suficientemente granular impide que los datos se distribuyan correctamente entre los nodos del clúster de informes de Analytics. En este caso, un nodo se sobrecargará y no puede procesar solicitudes de informes de forma oportuna. Al final, todos los informes del grupo de informes fallarán. <br>Las ID de visitante personalizadas mal implementadas podrían no afectar inmediatamente el rendimiento de los informes porque Analytics generalmente puede manejar varios meses de datos desequilibrados; Sin embargo, a través del tiempo, un valor de ID de visitante personalizado mal implementado puede resultar problemático al exigir que Analytics deshabilite el procesamiento de los grupos de informes afectados.</br><br>Los implementadores deben seguir la pauta de que un único valor de ID de visitante personalizado nunca debe recibir el crédito de más del 1% del tráfico del grupo de informes. Although the 1% guideline is sufficient for most report suites, the actual limit that might cause reporting performance to be impacted may be lower than 1% for very large report suites.</br>
