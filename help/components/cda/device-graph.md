---
title: Gráfico del dispositivo
description: Comprenda los requisitos previos y las limitaciones de la vinculación de datos mediante el gráfico del dispositivo.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
feature: CDA
role: Admin
source-git-commit: cc0b8703d6b6488adf9a2ea41a51001538d1cbee
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 60%

---


# Gráfico del dispositivo

{{available-existing-customers}}

Los análisis entre dispositivos pueden utilizar Private Graph para vincular los datos. Private Graph es un repositorio de ID de dispositivos con hash específicos de su organización. CDA se comunica regularmente con el gráfico del dispositivo para vincular dispositivos.

## Requisitos previos específicos del gráfico del dispositivo

Si tiene intención de implementar el análisis entre dispositivos mediante el método del gráfico del dispositivo, es necesario lo siguiente. Trabaje con equipos de su organización y con el equipo de cuenta de Adobe para asegurarse de que cumple todos los requisitos siguientes.

>[!WARNING]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda habilitar el análisis entre dispositivos o que se obtengan resultados deficientes al vincular datos.
>

* Todos los requisitos previos enumerados en la [página de información general](overview.md).
* Su organización debe utilizar [Adobe Experience Platform Identity Service Private Graph](https://business.adobe.com/es/products/experience-platform/identity-service.html). Consulte también la [Página principal](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=es) en la guía del usuario del servicio de identidad.
* La implementación debe utilizar la versión más reciente del servicio Experience Cloud ID (ECID). Consulte la [Página de inicio](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es) en la guía del usuario del servicio de ID. Es probable que la mayoría de las implementaciones que usan [Tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es) en Adobe Experience Platform ya hayan implementado el servicio de ID.
* Su implementación debe llamar a la función `setCustomerIDs` (o SDK equivalente) cada vez que se pueda identificar a un individuo, como cuando un usuario inicia sesión o abre un correo electrónico. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan. Consulte [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=es) en la guía de usuario del servicio de ID.

## Limitaciones específicas del gráfico del dispositivo

* Los ID de Analytics heredados no son compatibles. Solo se vinculan los visitantes con Experience Cloud ID.
* Si su organización utiliza un gráfico privado, los nuevos dispositivos tardan hasta 24 horas en vincularse.
* Los gráficos de dispositivos de terceros no son compatibles.

## Pasos siguientes

Una vez que su organización haya cumplido todos los requisitos y haya comprendido las limitaciones, puede empezar a [configurar análisis cruzados de dispositivos](setup.md).
