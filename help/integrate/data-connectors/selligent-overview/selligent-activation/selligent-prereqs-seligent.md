---
description: Enumera la información necesaria para proporcionar desde su cuenta de Selligent antes de poder implementar la integración.
seo-description: Enumera la información necesaria para proporcionar desde su cuenta de Selligent antes de poder implementar la integración.
seo-title: Requisitos previos de Selligent
solution: Analytics
title: Requisitos previos de Selligent
uuid: 3 a 43 a 1 c 0-5 f 51-4 bc 8-b 6 b 9-0 c 46 aa 00 ba 9 f
index: y
internal: n
snippet: y
translation-type: tm+mt
source-git-commit: 5e22d080398d74df29b1f849258e6500168cd5aa

---


# Prerequisites for Selligent{#prerequisites-for-selligent}

Enumera la información necesaria para proporcionar desde su cuenta de Selligent antes de poder implementar la integración.

**Cuenta válida de Selligent**

Para utilizar esta integración de Conectores de datos, debe tener una cuenta válida de Selligent.

**Información de la cuenta**

Necesitará la siguiente información sobre su cuenta de Selligent durante esta configuración de integración:

* **URL del servicio de Adobe**:

   La URL puede derivarse de la dirección URL utilizada para iniciar sesión en la solución Selligent Marketing. Reemplazar la parte «/simweb/login. aspx» de la dirección URL con «/automation/omniture. asmx»

   P. ej.: http://<client-specific install url>/automation/omniture.asmx

* **Parámetros de cadena de consulta:** Se anexan en la URL de la página de aterrizaje para ID de mensaje y ID de destinatario (ID de visitante). Siempre son MID y RID para ID de mensaje y ID de destinatario respectivamente.

* **Autentificador** de integración Inicie la herramienta Administrador desde Simweb y vaya a **[!UICONTROL Configuración]** &gt; **[!UICONTROL Configuración del sistema]** &gt; **[!UICONTROL ficha General]** &gt; **[!UICONTROL Sistema]**. Under **[!UICONTROL Security]**, you can find the Integration token.

   ![](assets/selligent-integration_token.png)

