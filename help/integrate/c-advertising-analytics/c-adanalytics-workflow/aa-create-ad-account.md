---
title: Configuración de una cuenta de publicidad en Advertising Analytics
description: Permite crear nuevas cuentas de publicidad y asignar varias cuentas a varios grupos de informes.
feature: Advertising Analytics
exl-id: f593c714-e85f-4000-85b2-6294cad81e25
source-git-commit: 79294cfc6f86e5a41a39504099cd730f53668725
workflow-type: tm+mt
source-wordcount: '819'
ht-degree: 100%

---

# Configurar una cuenta publicitaria

Los administradores de Adobe Analytics pueden crear nuevas cuentas publicitarias y asignar diversas cuentas a varios grupos de informes (1:1, 1:Muchos, Muchos:Muchos).

Los administradores también pueden [conceder acceso a los usuarios que no son administradores](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) para que configuren cuentas publicitarias.

![](assets/aa_accounts.png)

1. En Adobe Analytics, vaya a **[!UICONTROL Administración]** > **[!UICONTROL Cuentas publicitarias]**.
1. (Solo la primera vez que se utilice) Acepte los términos del Contrato de licencia de usuario final.
1. Haga clic en **[!UICONTROL + Añadir]**.
1. Se mostrará el cuadro de diálogo [!UICONTROL Nueva cuenta de motor de búsqueda]:

   ![](assets/aa_new_se_account.png)

1. Siga estas directrices para rellenar **[!UICONTROL Configuración del motor de búsqueda]**:

   | Configuración | Descripción |
   | --- | --- |
   | Tipo | Dispone de 2 opciones: Google AdWords y Microsoft Bing Ads.  Nota: El 31 de marzo de 2019, Microsoft Bing absorbió Yahoo Gemini. Como resultado, la opción de cuenta publicitaria de Yahoo Gemini ya no está disponible. |
   | Nombre de la cuenta | Como nombre de esta cuenta, puede elegir el nombre que mejor le parezca. Este es el nombre sencillo de la cuenta que aparecerá en la IU. |
   | Autenticador de OAuth | **Nota:** OAuth es un estándar abierto para la delegación de acceso, usado por lo general como una manera de conceder a los sitios web o a las aplicaciones acceso a su información en otros sitios web, pero sin proporcionarles las contraseñas. Observará que se le dirige a una dirección URL de terceros (efrontier.com). Adobe utiliza efrontier como base del proceso de autenticación de OAuth para los tres motores de búsqueda. Si utiliza Internet Explorer 11 (o una versión anterior), no podrá recuperar correctamente el token de OAuth para ninguno de los tres motores de búsqueda. En su lugar, utilice otros exploradores web.<p>Al hacer clic en **[!UICONTROL Recuperar token]**, se inicia el proceso de autenticación de OAuth2. Se le pedirá que utilice sus credenciales para iniciar sesión en la cuenta de búsqueda de Google/Bing. En función del motor de búsqueda que haya elegido, el proceso es ligeramente diferente: <ul><li>Google AdWords: proporcione el identificador de la cuenta de Google</li><li>Microsoft Bing: proporcione el identificador de la cuenta de Bing y el identificador de cliente de Bing.</li></ul>Consulte [Localice el identificador de cuenta](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md) para obtener información sobre estos identificadores. Cuando haya iniciado sesión correctamente, en el campo **[!UICONTROL Token de OAuth]** se mostrará la palabra **[!UICONTROL Recuperado]**. |

1. En la sección **[!UICONTROL Seguimiento]**, debe proporcionar información sobre cómo la implementación de Adobe Analytics realiza un seguimiento de los datos del motor de búsqueda. Este paso es necesario para incrementar adecuadamente los datos de Adobe Analytics con los datos del motor de búsqueda.
Siga estas directrices para rellenar **[!UICONTROL Configuración del seguimiento]**:

   | Configuración | Descripción |
   | --- | --- |
   | Tipo | <ul><li>**Automático:** Permite que el motor de Advertising Cloud decida cómo se adjuntan los parámetros de seguimiento a las plantillas de seguimiento/URL de destino del motor de búsqueda. Este es el enfoque más sencillo, pero es posible que no genere el conjunto de datos mejor integrado.<br>**Importante:** Para configurar una cuenta de motor de búsqueda en “Modo automático”, usted es responsable de realizar las siguientes acciones:<br> El parámetro y valor “s_kwcid” se agregará a las plantillas de seguimiento de cuentas o a las direcciones URL de página de aterrizaje en la cuenta que se agrega. Se insertará al final de la URL. Como resultado, es posible que deba llevar a cabo acciones adicionales si su servidor web requiere un determinado par clave-valor al final de la URL o bien una actualización que permita cualquier nuevo par clave-valor en la URL. **Nota:** Obtenga más información sobre si debe agregar este parámetro a la [política de seguridad de contenido](https://experienceleague.adobe.com/docs/id-service/using/reference/csp.html?lang=es).<br>Además, en la URL de destino pueden insertarse palabras clave como parte del valor “s_kwcid”, de modo que, si contienen caracteres especiales o símbolos, confirme que su servidor web los admite (un ejemplo de carácter especial común es “+”, que se utiliza en las palabras clave “Broad Match Modified”).</li><li>**Manual:** Le permite administrar cómo se añaden los parámetros de seguimiento a las plantillas de seguimiento o a las direcciones URL de destino del motor de búsqueda. [Consulte estos ejemplos de seguimiento manual para cada motor de búsqueda](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md).</li></ul> |

1. En la sección **[!UICONTROL Asignación]**, elija qué grupo(s) de informes va a enlazar a la cuenta de este motor de búsqueda. Debe proporcionar un grupo de informes como mínimo para guardar la cuenta publicitaria. Puede asignar diversas cuentas a varios grupos de informes (1:1, 1:Muchos, Muchos:Muchos). Recuerde que los datos que AMO obtiene del motor de búsqueda simplemente se copian a cualquier grupo de informes asignado, de modo que los datos no se dividen.

   >[!IMPORTANT]
   >
   >Solo los grupos de informes que se hayan asignado a una organización de Experience Cloud están disponibles para su selección. Si su grupo de informes no se incluye en la lista, consulte [Solucionar problemas de Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Para la **[!UICONTROL configuración de la asignación]**, siga estas directrices:

   | Configuración | Descripción |
   | --- | --- |
   | Asignación de grupos de informes | La asignación de grupos de informes determina el grupo de informes que se enlaza a la cuenta de este motor de búsqueda. En otras palabras, determina a qué grupo(s) de informes se envían los datos del motor de búsqueda. |


1. Haga clic en **[!UICONTROL Guardar]**.
1. Después de guardar, se muestra una lista de advertencias en un mensaje de exención de responsabilidad. Se le pedirá que confirme haber leído y entendido este contrato. Haga clic en la casilla de selección y, después, en **[!UICONTROL Aceptar]**.

   Ahora se le dirigirá a la [IU de administración](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md) de cuentas publicitarias, en que se incluirá su cuenta recién creada.

>[!NOTE]
>
>Los datos del motor de búsqueda suelen tardar un mínimo de 24 horas en propagarse a los informes de Analytics.
