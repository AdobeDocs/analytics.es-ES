---
description: Instrucciones para localizar los ID de cuenta de Google Ads y Microsoft Advertising.
title: Localización de los ID de su cuenta
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
source-git-commit: 586459d99674f01a3b18f84f975a3365ddf2fcd9
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 3%

---

# Localización de los ID de su cuenta {#locate-your-account-ids}

Obtenga información sobre cómo localizar los ID de cuenta para Google Ads y Microsoft Advertising.

## Google Ads (AdWords) {#google}

>[!IMPORTANT]
>
>Google Ads utiliza dos tipos de cuentas:
>
>- Cuenta de MCC (My Client Center) y
>- Cuenta estándar.
>
>Para esta integración con Adobe Analytics, **debe iniciar sesión con una cuenta Estándar**, no con una cuenta MCC. El motivo es que una cuenta MCC actúa como un &quot;paraguas&quot; que puede acceder a varias cuentas de Google Ads con un solo inicio de sesión, mientras que el inicio de sesión con una cuenta Estándar solo puede acceder a una cuenta por cada inicio de sesión. Aunque Google admite la vinculación de un correo electrónico para administrar 5 cuentas, Advertising Analytics aún no admite esta función. Un correo electrónico solo se puede vincular con una cuenta de Google Ads.

Haga clic en el icono Cuenta en la parte superior derecha para ver el número de cuenta de Google Ads (ID de cliente).

![Cuenta de administrador de Google Ads](assets/google-account.png)

## Microsoft Advertising (Bing) {#microsoft}

>[!NOTE]
>
>Si su cuenta de Microsoft Advertising (anteriormente conocida como Bing) utiliza la función de importación de Google, asegúrese de actualizar la cadena de seguimiento correcta. La cadena de seguimiento no se actualiza automáticamente de la versión de Google a la cadena de seguimiento correcta de Microsoft Advertising y puede generar datos no especificados. Consulte [Qué se importa desde Google Ads](https://help.ads.microsoft.com/apex/index/3/en/50851/) en la ayuda de Microsoft Advertising para obtener más información.

Se requieren **[!UICONTROL Account ID]** y **[!UICONTROL Manager account ID]**.

- La **[!UICONTROL ID de cuenta]** se encuentra en **[!UICONTROL Configuración]** > **[!UICONTROL Configuración de cuenta]** > **[!UICONTROL ID de cuenta]**. Asegúrese de usar [!UICONTROL ID de cuenta] y NO [!UICONTROL número de cuenta].
- El **[!UICONTROL Id. de cuenta de administrador]** se encuentra en **[!UICONTROL Configuración]** > **[!UICONTROL Configuración de cuenta de administrador]** > **[!UICONTROL Id. de cuenta de administrador]**. Asegúrese de usar [!UICONTROL Id. de cuenta de responsable] y NO [!UICONTROL Número de cuenta de responsable].

![Navegación de Microsoft Advertising](assets/bing-id.png)

>[!CONTEXTUALHELP]
>id="adanalytics_ma_account_id"
>title="ID de cuenta"
>abstract="El &quot;ID de cuenta&quot; es un valor numérico ubicado en la interfaz de Advertising de Microsoft. Para localizarla, vaya a Configuración > Configuración de la cuenta > ID de cuenta."

>[!CONTEXTUALHELP]
>id="adanalytics_ma_manager_account_id"
>title="ID de cuenta del responsable"
>abstract="El &quot;ID de cuenta del responsable&quot; es un valor numérico ubicado en la interfaz de Advertising de Microsoft. Para localizarla, vaya a Configuración > Configuración de la cuenta del administrador > ID de cuenta del administrador."
