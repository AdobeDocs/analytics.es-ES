---
description: Instrucciones para localizar los ID de cuenta de Google Ads y Microsoft Advertising.
title: Localización de los ID de su cuenta
feature: Advertising Analytics
exl-id: 2faccfd1-df7b-4b0c-a2f3-23138c39a838
TQID: https://experienceleague.adobe.com/5Z2hL08Ynl9M6abCm2bchArEOIYDz0cPTRIxQeqLbZ8
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: eb9732ab-8232-4b21-bc4c-89de86dbe4d7
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 344
ht-degree: 22%

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
>abstract="El “ID de cuenta” es un valor numérico ubicado en la interfaz de Microsoft Advertising. Para localizarlo, vaya a Configuración > Configuración de la cuenta > ID de cuenta."

>[!CONTEXTUALHELP]
>id="adanalytics_ma_manager_account_id"
>title="ID de cuenta del administrador"
>abstract="El “ID de cuenta del administrador” es un valor numérico ubicado en la interfaz de Microsoft Advertising. Para localizarlo, vaya a Configuración > Configuración de la cuenta del administrador > ID de cuenta del administrador."
