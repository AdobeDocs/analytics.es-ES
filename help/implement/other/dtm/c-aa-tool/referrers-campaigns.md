---
description: Descripciones de los campos de Dynamic Tag Management para opciones de referentes y campañas al implementar Dynamic Tag Management en Adobe Analytics.
keywords: Dynamic Tag Management;referrers;campaigns;referrer override;campaign variable;query param
solution: Experience Cloud,Analytics,Dynamic Tag Management
title: Referentes y campañas
uuid: 56580206-a382-4993-9bba-a488da65cf89
translation-type: tm+mt
source-git-commit: 5e47974fcf95625def21a9011ad981197ae39c99

---


# Referentes y campañas

Field descriptions in [!UICONTROL Dynamic Tag Management] for referrers and campaign options when deploying [!UICONTROL Dynamic Tag Management] in Adobe [!DNL Analytics].

**[!UICONTROL  *`Property`*]** > ![Icono](assets/settings_gear.png) de engranaje **[!UICONTROL Edit Tool]** > **[!UICONTROL Referrers & Campaigns]**

<table id="table_09AE3BFF0F12442F9C19CD96451F93E4">
 <thead>
  <tr>
   <th colname="col1" class="entry"> Elemento </th>
   <th colname="col2" class="entry"> Descripción </th>
  </tr>
 </thead>
 <tbody>
  <tr>
   <td colname="col1"> Anulación de Remitente del reenvío </td>
   <td colname="col2"> <p>Anula el valor configurado en la variable La variable <span class="varname"> s.referrer</span>, que suele completar el referente configurado en el explorador. </p> <p>Consulte <a href="../../../vars/page-vars/referrer.md">remitente del reenvío</a>. </p> </td>
  </tr>
  <tr>
   <td colname="col1"> Campaign </td>
   <td colname="col2"> <p>Variable que identifica las campañas de mercadotecnia utilizadas para llevar visitantes a su sitio. El valor de la campaña se toma generalmente de un parámetro de cadena de consulta. </p> <p>Consulte <a href="../../../vars/page-vars/campaign.md">campaña</a>. </p> </td>
  </tr>
 </tbody>
</table>

Utilice la interfaz de la DTM para elegir si desea utilizar un valor o una cadena de consulta (que se puede extraer de un elemento de datos):

![Parámetro de consulta](assets/dtm-queryparam.png)

Puede introducir la cadena de consulta directamente en la interfaz o hacer referencia a un elemento de datos independiente si dispone de otro medio para rastrear una campaña.
