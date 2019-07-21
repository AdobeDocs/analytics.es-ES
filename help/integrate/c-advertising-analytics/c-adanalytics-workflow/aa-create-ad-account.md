---
seo-title: Configurar una cuenta de publicidad
title: Configurar una cuenta de publicidad
uuid: 4 e 37 caa 3-e 4 a 5-43 ad -97 c 0-12 db 62 ad 5283
translation-type: tm+mt
source-git-commit: 463e28e9d710cc41e4ab4ace5e3861b8ae8fbdcc

---


# Configurar una cuenta de publicidad

Los administradores de Adobe Analytics pueden crear nuevas cuentas publicitarias y asignar diversas cuentas a varios grupos de informes (1:1, 1:Muchos, Muchos:Muchos).

Los administradores también pueden [conceder acceso a los usuarios que no son administradores](../../../integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) para que configuren cuentas publicitarias.

![](assets/aa_accounts.png)

1. In Adobe Analytics, navigate to **[!UICONTROL Admin]** &gt; **[!UICONTROL Advertising Accounts]**.
1. (Solo la primera vez que se utilice) Acepte los términos del Contrato de licencia de usuario final.
1. Haga clic en **[!UICONTROL + Añadir]**.
1. Se mostrará el cuadro de diálogo [!UICONTROL Nueva cuenta de motor de búsqueda]:

   ![](assets/aa_new_se_account.png)

1. Siga estas directrices para rellenar **[!UICONTROL Configuración del motor de búsqueda]:**

   <table id="table_B3BE66B7D4C54766B8FFD2C6DCD657AF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Configuración </th> 
      <th colname="col2" class="entry"> Descripción </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> <p>Tiene 2 opciones: Google adwords y Microsoft Bing Ads. </p> <p>Nota: El 31 de marzo de 2019, Microsoft Bing absorbió Yahoo Gemini. Como resultado, la opción de cuenta publicitaria de Yahoo Gemini ya no está disponible.  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nombre de la cuenta </p> </td> 
      <td colname="col2"> <p>Como nombre de esta cuenta, puede elegir el nombre que mejor le parezca. Este es el nombre sencillo de la cuenta que aparecerá en la IU. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Autenticador de OAuth </p> </td> 
      <td colname="col2"> <p>Nota: OAuth es un estándar abierto para la delegación de acceso, usado por lo general como una manera de conceder a los sitios web o a las aplicaciones acceso a su información en otros sitios web, pero sin proporcionarles las contraseñas. </p> <p>Nota: Observará que se le dirige a una dirección URL de terceros (efrontier.com). Adobe utiliza efrontier como base del proceso de autenticación de OAuth para los tres motores de búsqueda. </p> <p>Nota: Si utiliza Internet Explorer 11 (o una versión anterior), no podrá recuperar correctamente el autenticador de OAuth para ninguno de los tres motores de búsqueda. En su lugar, utilice otros navegadores web. </p> <p>Al hacer clic en <span class="uicontrol">Recuperar autenticador</span>, se inicia el proceso de autenticación de OAuth2. Esto significa que se le pedirá que utilice sus credenciales para iniciar sesión en la cuenta de búsqueda de Google/Bing. En función del motor de búsqueda que haya elegido, el proceso es ligeramente diferente: </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google AdWords: proporcione el identificador de la cuenta de Google. </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing: proporcione el identificador de la cuenta de Bing y el identificador de cliente de Bing. </li> 
        </ul> <p>Consulte <a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md#concept_F7F67448F3B44342967E0419E96F384D" format="dita" scope="local"> Localizar el identificador de cuenta</a> para obtener información sobre estos identificadores. </p> <p>Una vez que haya iniciado sesión correctamente, aparecerá el campo Token de oauth. 
        <systemoutput>
          Recuperado
        </systemoutput>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. En la sección **[!UICONTROL Seguimiento], debe proporcionar información sobre cómo la implementación de Adobe Analytics realiza un seguimiento de los datos del motor de búsqueda.** Este paso es necesario para incrementar adecuadamente los datos de Adobe Analytics con los datos del motor de búsqueda.
Siga estas directrices para rellenar **[!UICONTROL Configuración del seguimiento]:**

   <table id="table_1AB4E31456E84ABF8209B02058259C4D"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Configuración </th> 
      <th colname="col2" class="entry"> Descripción </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Tipo </p> </td> 
      <td colname="col2"> 
        <ul id="ul_1C5A0502A4984E57A08417A91CCD6FFE"> 
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol"> Automático</span>: permite que el motor de Advertising Cloud decida cómo se adjuntan los parámetros de seguimiento a las plantillas de seguimiento/URL de destino del motor de búsqueda. Este es el enfoque más sencillo, pero es posible que no genere el conjunto de datos mejor integrado. <p>Importante: Para configurar una cuenta de motor de búsqueda en “Modo automático”, debe llevar a cabo las siguientes acciones: 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">En la cuenta agregada se añadirá el parámetro y valor “s_kwcid” a las plantillas de seguimiento de la cuenta o a las URL de las páginas de destino. Se insertará al final de la URL. Como resultado, es posible que deba llevar a cabo acciones adicionales si su servidor web requiere un determinado par clave-valor al final de la URL o bien una actualización que permita cualquier nuevo par clave-valor en la URL. </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">Además, en la URL de destino pueden insertarse palabras clave como parte del valor “s_kwcid”, de modo que, si contienen caracteres especiales o símbolos, confirme que su servidor web los admite (un ejemplo de carácter especial común es “+”, que se utiliza en las palabras clave “Broad Match Modified”). </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol"> Manual</span>: le permite administrar cómo se añaden los parámetros de seguimiento a las plantillas de seguimiento o a las direcciones URL de destino del motor de búsqueda. <a href="../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md#concept_87B28BA9E7F84BA5972F69E6F3482A33" format="dita" scope="local"> Consulte estos ejemplos de seguimiento manual para cada motor de búsqueda</a>. </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. En la sección **[!UICONTROL Asignación], elija qué grupo(s) de informes va a enlazar a la cuenta de este motor de búsqueda.** Debe proporcionar un grupo de informes como mínimo para guardar la cuenta publicitaria. Puede asignar diversas cuentas a varios grupos de informes (1:1, 1:Muchos, Muchos:Muchos). Recuerde que los datos que AMO obtiene del motor de búsqueda simplemente se copian a cualquier grupo de informes asignado, de modo que los datos no se dividen.

   >[!IMPORTANT]
   >
   >Only report suites that have been [mapped to an Experience Cloud organization](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html) will be available for selection. If you do not see your report suite listed, refer to [Troubleshoot Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Para la **[!UICONTROL configuración de la asignación], siga estas directrices:**

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Configuración </th> 
      <th colname="col2" class="entry"> Descripción </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Asignación de grupos de informes </p> </td> 
      <td colname="col2"> <p>La asignación de grupos de informes determina el grupo de informes que se enlaza a la cuenta de este motor de búsqueda. En otras palabras, determina a qué grupo(s) de informes se envían los datos del motor de búsqueda. </p> <p>Si su grupo de informes no se incluye en la lista, puede <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html" format="html" scope="external">asignar el grupo de informes a una organización de Experience Cloud</a> mediante esta herramienta. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Haga clic en **[!UICONTROL Guardar]**.
1. Después de guardar, se muestra una lista de advertencias en un mensaje de exención de responsabilidad. Se le pedirá que confirme haber leído y entendido este contrato. Haga clic en la casilla de selección y, después, en **[!UICONTROL Aceptar]**.

   Ahora se le dirigirá a la [IU de administración](../../../integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md#concept_531B99165A4E47B4B8849376B532AFDB) de cuentas publicitarias, en que se incluirá su cuenta recién creada.

>[!NOTE]
>
>Debe esperar al menos 24 horas antes de que los datos del motor de búsqueda empiecen a rellenar los informes de Analytics.

