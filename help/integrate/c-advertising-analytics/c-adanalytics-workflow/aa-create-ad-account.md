---
title: Configurar una cuenta publicitaria
uuid: 4e37caa3-e4a5-43ad-97c0-12db62ad5283
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Configurar una cuenta publicitaria

Los administradores de Adobe Analytics pueden crear nuevas cuentas de publicidad y asignar varias cuentas a varios grupos de informes (1:1, 1:Many, Many:Many).

Los administradores también pueden [otorgar acceso a usuarios que no sean administradores](/help/integrate/c-advertising-analytics/overview.md#section_FCC58EB635954A32990D4E67B52B4369) para configurar cuentas de publicidad.

![](assets/aa_accounts.png)

1. En Adobe Analytics, vaya a **[!UICONTROL Admin]** > **[!UICONTROL Advertising Accounts]**.
1. (Sólo uso por primera vez) Acepte los términos del contrato de licencia de usuario final.
1. Haga clic en **[!UICONTROL + Add]**.
1. Se muestra el [!UICONTROL New Search Engine Account] cuadro de diálogo:

   ![](assets/aa_new_se_account.png)

1. Llene las **[!UICONTROL Search Engine Settings]** siguientes directrices:

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
      <td colname="col2"> <p>Dispone de 2 opciones: Google AdWords y Microsoft Bing Ads. </p> <p>Nota: El 31 de marzo de 2019, Microsoft Bing absorbió Yahoo Gemini. Como resultado, la opción de cuenta publicitaria de Yahoo Gemini ya no está disponible.  </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Nombre de la cuenta </p> </td> 
      <td colname="col2"> <p>Puede elegir configurar este nombre de cuenta en cualquier nombre que le convenga. Es el nombre descriptivo de la cuenta que aparecerá en la interfaz de usuario. </p> </td> 
      </tr> 
      <tr> 
      <td colname="col1"> <p>Distintivo OAuth </p> </td> 
      <td colname="col2"> <p>Nota: OAuth es un estándar abierto para la delegación de acceso, usado por lo general como una manera de conceder a los sitios web o a las aplicaciones acceso a su información en otros sitios web, pero sin proporcionarles las contraseñas. </p> <p>Nota: Observará que se le dirige a una dirección URL de terceros (efrontier.com). Adobe utiliza efrontier como base del proceso de autenticación de OAuth para los tres motores de búsqueda. </p> <p>Nota: Si utiliza Internet Explorer 11 (o una versión anterior), no podrá recuperar correctamente el autenticador de OAuth para ninguno de los tres motores de búsqueda. En su lugar, utilice otros exploradores web. </p> <p>Al hacer clic<span class="uicontrol"> en Recuperar token</span> se inicia el proceso de autenticación OAuth2. Esto significa que se le pedirá que inicie sesión en su cuenta de búsqueda de Google/Bing con sus credenciales. Según el motor de búsqueda que elija, el proceso es ligeramente diferente: </p> 
        <ul id="ul_FC9B5612F6554495B04C357CB0AB72EB"> 
        <li id="li_CD54231BFF134F83B3B5B14B34A0E1D2">Google Adwords: Proporcione el ID de cuenta de Google. </li> 
        <li id="li_89B9D54BAA914E5DB2959B193489582E">Microsoft Bing: Proporcione el ID de cuenta de Bing y el ID de cliente de Bing. </li> 
        </ul> <p>Refer to <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-locate-account-id.md"  > Locate your Account ID</a> for information on these IDs. </p> <p>Cuando haya iniciado sesión correctamente, en el campo Autenticador de OAuth se mostrará la palabra 
        <systemoutput>
          Recuperado
        </systemoutput>. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. In the **[!UICONTROL Tracking]** section, you provide information on how the Search Engine data is tracked by your Adobe Analytics implementation. Este paso es necesario para incrementar adecuadamente los datos de Adobe Analytics con los datos del motor de búsqueda.
Llene las **[!UICONTROL Tracking Settings]** siguientes directrices:

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
        <li id="li_5736E38286FF494ABDDC6E85281D7F2A"> <span class="uicontrol"> Automático</span>: Permite que el motor de Advertising Cloud decida cómo se adjuntan los parámetros de seguimiento a las plantillas de seguimiento/URL de destino del motor de búsqueda. Este es el enfoque más sencillo, pero es posible que no genere el conjunto de datos mejor integrado. <p>Importante: Para configurar una cuenta de motor de búsqueda en “Modo automático”, debe llevar a cabo las siguientes acciones: 
          <ul id="ul_4FF9D1E3CC4E452BA339E0A725D29FEE"> 
            <li id="li_6F3A6D6259C0420CB7E6FD2C26A1B6E0">El parámetro y el valor "s_kwcid" se agregarán a las plantillas de seguimiento de cuentas o a las direcciones URL de página de aterrizaje de la cuenta que se esté agregando. Esto se insertará al final de la dirección URL. Como resultado, es posible que se requiera una acción adicional por parte del usuario si el servidor web requiere un par key=value determinado al final de la dirección URL O una actualización para admitir cualquier par key=value nuevo en la dirección URL. </li> 
            <li id="li_A04D4AA31A934392808639E46C86573F">Además, las palabras clave se pueden insertar en la dirección URL de aterrizaje como parte del valor "s_kwcid", por lo que si contienen caracteres o símbolos especiales, confirme que el servidor web puede admitir esos caracteres (un ejemplo de caracteres especiales comunes es "+" que se utiliza en palabras clave de "coincidencia amplia modificada"). </li> 
          </ul> </p> </li> 
        <li id="li_EAA7A7CA1E584854A7EC1E43E13B63FE"><span class="uicontrol"> Manual</span>: Le permite administrar cómo se añaden los parámetros de seguimiento a las plantillas de seguimiento o a las direcciones URL de destino del motor de búsqueda. <a href="/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manual-vs-automatic-tracking.md"  > Consulte estos ejemplos de seguimiento manual para cada motor de búsqueda</a>. </li> 
        </ul> </td> 
      </tr> 
    </tbody> 
    </table>

1. En la **[!UICONTROL Mapping]** sección, elija qué grupos de informes vincular a esta cuenta de motor de búsqueda. Debe proporcionar al menos un grupo de informes para poder guardar la cuenta de publicidad. Puede asignar varias cuentas a varios grupos de informes (1:1, 1:Many, Many:Many). Tenga en cuenta que los datos que AMO extrae del motor de búsqueda simplemente se copian en cualquier grupo de informes asignado, por lo que no hay división de datos.

   >[!IMPORTANT]
   >
   >Solo los grupos de informes que se hayan [asignado a una organización de Experience Cloud](https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html) estarán disponibles para su selección. Si su grupo de informes no se incluye en la lista, consulte [Solucionar problemas de Advertising Analytics](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-troubleshooting.md).

   Para las **[!UICONTROL Mapping Settings]** siguientes directrices:

   <table id="table_AF876DC40F97403882C0AA528BD204FF"> 
    <thead> 
      <tr> 
      <th colname="col1" class="entry"> Configuración </th> 
      <th colname="col2" class="entry"> Descripción </th> 
      </tr>
    </thead>
    <tbody> 
      <tr> 
      <td colname="col1"> <p>Report Suite  Asignación </p> </td> 
      <td colname="col2"> <p>La asignación de grupos de informes determina el grupo de informes que se vincula a esta cuenta de motor de búsqueda. En otras palabras, determina en qué grupo o grupos de informes se envían los datos del motor de búsqueda. </p> <p>Si su grupo de informes no se incluye en la lista, puede <a href="https://marketing.adobe.com/resources/help/en_US/mcloud/map-report-suite.html"  >asignar el grupo de informes a una organización de Experience Cloud</a> mediante esta herramienta. </p> </td> 
      </tr> 
    </tbody> 
    </table>

1. Haga clic en **[!UICONTROL Save]**.
1. Después de guardar, una renuncia de responsabilidad muestra una lista de advertencias. Se le pedirá que confirme que ha leído y que comprende este acuerdo. Click the checkbox, then click **[!UICONTROL OK]**.

   Ahora se le dirigirá a la interfaz de usuario [de la](/help/integrate/c-advertising-analytics/c-adanalytics-workflow/aa-manage-ad-accounts.md)administración de cuentas de publicidad, donde debería enumerarse la cuenta recién creada.

>[!NOTE] Los datos del motor de búsqueda suelen tardar un mínimo de 24 horas en propagarse a los informes de Analytics.

