---
title: Gráfico de dispositivos
description: Comprenda los requisitos previos y las limitaciones de la vinculación de datos mediante el gráfico del dispositivo.
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 41%

---


# Gráfico de dispositivos

Analytics entre dispositivos proporciona dos métodos distintos para unir datos. Este método utiliza Adobe Experience Platform Identity Service Co-op Graph o Private Graph para unir datos. CDA se comunica regularmente con el gráfico del dispositivo para vincular dispositivos.

## Diferencias entre gráficos de cooperación y gráficos privados

Adobe oferta dos tipos de gráficos de dispositivos como parte del servicio de ID:

* **Gráfico** de cooperación: Repositorio de ID de dispositivos con hash a los que cualquier cliente puede contribuir y hacer referencia. Dado que este tipo de gráfico de dispositivos es colaborativo, generalmente coincide con más dispositivos que un gráfico privado.
* **Gráfico** privado: Repositorio de ID de dispositivos con hash al que solo hace referencia su organización.

## Requisitos previos específicos del gráfico de dispositivos

Si desea implementar Análisis entre dispositivos mediante el método de gráfico de dispositivos, es necesario lo siguiente. Trabaje con equipos de su organización y con el administrador de cuentas de Adobe para asegurarse de que cumple todos los requisitos siguientes.

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda habilitar el análisis entre dispositivos o que se obtengan resultados deficientes al vincular datos.

* Todos los requisitos previos enumerados en la página [de](overview.md)información general.
* Su organización debe utilizar el gráfico colaborativo o el gráfico privado de Adobe Experience Platform Identity Service. Consulte la página [principal](https://docs.adobe.com/content/help/es-ES/device-co-op/using/home.html) en la guía del usuario de Device Co-op.
* La implementación debe utilizar la versión más reciente del servicio de ID de Experience Cloud. Consulte la [página principal](https://docs.adobe.com/content/help/es-ES/id-service/using/home.html) en la guía del usuario del servicio de Experience Cloud ID. Es probable que la mayoría de las implementaciones que utilizan Adobe Experience Platform Launch ya hayan implementado ECID.
* Your implementation must call the `setCustomerIDs` function (or SDK equivalent) whenever an individual can be identified, such as when a user logs in or opens an email. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan. Consulte [`setCustomerIDs`](https://docs.adobe.com/content/help/es-ES/id-service/using/id-service-api/methods/setcustomerids.html) en la guía del usuario del servicio de Experience Cloud ID.

## Limitaciones específicas del gráfico de dispositivos

* Los ID de Analytics heredados no son compatibles. Solo se vinculan los visitantes con Experience Cloud ID.
* Si su organización utiliza Private Graph, los nuevos dispositivos tardan hasta 24 horas en vincularse.
* Si su organización utiliza Co-op Graph, los nuevos dispositivos que visiten el sitio pueden tardar hasta dos semanas en ser vinculados. El nivel de vinculación en CDA para las dos últimas semanas es generalmente inferior al de los intervalos de fechas de más de dos semanas.
* Los gráficos de dispositivos de terceros no son compatibles.

## Pasos siguientes

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).

