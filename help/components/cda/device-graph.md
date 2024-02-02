---
title: Gráfico del dispositivo
description: Comprenda los requisitos previos y las limitaciones de la vinculación de datos mediante el gráfico del dispositivo.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
feature: CDA
role: Admin
source-git-commit: be5a73347d417c8dc6667d4059e7d46ef5f0f5cd
workflow-type: tm+mt
source-wordcount: '296'
ht-degree: 60%

---

# Gráfico del dispositivo

Los análisis entre dispositivos pueden utilizar Private Graph para vincular los datos. Private Graph es un repositorio de ID de dispositivos con hash específicos de su organización. CDA se comunica regularmente con el gráfico del dispositivo para vincular dispositivos.

## Requisitos previos específicos del gráfico del dispositivo

Si tiene intención de implementar el análisis entre dispositivos mediante el método del gráfico del dispositivo, es necesario lo siguiente. Trabaje con equipos de su organización y con el equipo de cuenta de Adobe para asegurarse de que cumple todos los requisitos siguientes.

>[!WARNING]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda habilitar el análisis entre dispositivos o que se obtengan resultados deficientes al vincular datos.

* Todos los requisitos previos enumerados en la [página de información general](overview.md).
* Su organización debe utilizar el [Gráfico privado del servicio de identidad de Adobe Experience Platform](https://business.adobe.com/products/experience-platform/identity-service.html). Consulte también la [Página principal](https://experienceleague.adobe.com/docs/experience-platform/identity/home.html?lang=es) en la guía del usuario del servicio de ID.
* La implementación debe utilizar la última versión del servicio de ID de Experience Cloud (ECID). Consulte la [Página principal](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=es) en la guía del usuario del servicio de ID. La mayoría de las implementaciones que utilizan [Etiquetas](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=es) en Adobe Experience Platform probablemente ya tengan implementado el servicio de ID.
* Su implementación debe llamar a la función `setCustomerIDs` (o SDK equivalente) cada vez que se pueda identificar a un individuo, como cuando un usuario inicia sesión o abre un correo electrónico. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan. Consulte [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html?lang=es) en la guía del usuario del servicio de ID.

## Limitaciones específicas del gráfico del dispositivo

* Los ID de Analytics heredados no son compatibles. Solo se vinculan los visitantes con Experience Cloud ID.
* Si su organización utiliza un gráfico privado, los nuevos dispositivos tardan hasta 24 horas en vincularse.
* Los gráficos de dispositivos de terceros no son compatibles.

## Pasos siguientes

Una vez que su organización haya cumplido todos los requisitos y haya comprendido las limitaciones, puede empezar a [configurar análisis cruzados de dispositivos](setup.md).
