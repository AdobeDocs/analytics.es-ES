---
title: Comparación de datos de Adobe Analytics con productos de terceros
description: Comprenda sus opciones al comparar directamente los datos en Adobe Analytics con los datos recopilados por otras soluciones de Analytics.
feature: Third-party Integration
exl-id: b4f85088-7ffd-45dc-bdd1-c0fc8dc3b332
source-git-commit: 34ba0e09cd909951a777b0ad3da080958633f97e
workflow-type: tm+mt
source-wordcount: '245'
ht-degree: 88%

---

# Comparación de datos de Adobe Analytics con productos de terceros

Hay muchas soluciones de análisis disponibles en línea. Cada una de estas soluciones utiliza sus propios métodos para implementar códigos y recopilar datos. Los distintos productos tienen su propia definición sobre lo que constituye una vista de página, una visita, un visitante único y otras métricas utilizadas en cada producto correspondiente.

Debido a estas definiciones, estructura de datos e implementación extremadamente diferentes, el **Servicio de atención al cliente de Adobe no soluciona las discrepancias con las herramientas de análisis de terceros.**

Si observa una gran discrepancia entre Adobe Analytics y una herramienta de análisis de terceros, puede utilizar los siguientes recursos:

* **Autoauditoría con el depurador**: Puede comprobar las páginas del sitio con el [depurador de Adobe](https://experienceleague.adobe.com/docs/debugger/using/experience-cloud-debugger.html?lang=es) u otro monitor de paquetes. El uso del depurador permite validar la implementación para asegurarse de que las solicitudes de imagen se activan correctamente con las variables correctas.
* **Autoauditoría mediante fuentes de datos**: Adobe ofrece a su organización la opción de recibir [fuentes de datos](/help/export/analytics-data-feed/data-feed-overview.md) que contengan todos los datos sin procesar de cada día. A continuación, su organización puede utilizar estos datos y compararlos con las herramientas de análisis de terceros para determinar cualquier discrepancia.
* **Auditoría asistida y validación de datos con Adobe Consulting**: Si desea que un representante oficial de Adobe realice una auditoría de implementación completa en su sitio, póngase en contacto con el equipo de cuenta de Adobe. Pueden organizar una reunión con un asesor de implementación que pueda auditar el sitio según el contrato de su empresa.
