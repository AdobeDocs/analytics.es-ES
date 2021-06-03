---
title: Gráfico del dispositivo
description: Comprenda los requisitos previos y las limitaciones de la vinculación de datos mediante el gráfico del dispositivo.
exl-id: b8408a7d-6aff-4fff-b535-f10d422bcf0d
source-git-commit: f669af03a502d8a24cea3047b96ec7cba7c59e6f
workflow-type: tm+mt
source-wordcount: '424'
ht-degree: 95%

---

# Gráfico del dispositivo

Cross-Device Analytics proporciona dos métodos distintos para unir datos. Este método utiliza el gráfico de cooperación o el gráfico privado de Adobe Experience Platform Identity Service para vincular los datos. CDA se comunica regularmente con el gráfico del dispositivo para vincular dispositivos.

## Diferencias entre gráficos de cooperación y gráficos privados

Adobe ofrece dos tipos de gráficos de dispositivos como parte del servicio de ID:

* **Gráfico de cooperación**: Repositorio de ID de dispositivos con hash a los que cualquier cliente puede contribuir y hacer referencia. Dado que este tipo de gráfico de dispositivos es colaborativo, generalmente coincide con más dispositivos que un gráfico privado.
* **Gráfico privado**: Repositorio de ID de dispositivos con hash al que solo hace referencia su organización.

## Requisitos previos específicos del gráfico del dispositivo

Si tiene intención de implementar el análisis entre dispositivos mediante el método del gráfico del dispositivo, es necesario lo siguiente. Trabaje con equipos de su organización y con el administrador de cuentas de Adobe para asegurarse de que cumple todos los requisitos siguientes.

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda habilitar el análisis entre dispositivos o que se obtengan resultados deficientes al vincular datos.

* Todos los requisitos previos enumerados en la [página de información general](overview.md).
* Su organización debe utilizar el gráfico colaborativo o el gráfico privado de Adobe Experience Platform Identity Service. Consulte la página [principal](https://experienceleague.adobe.com/docs/device-co-op/using/home.html) en la guía del usuario de Device Co-op.
* La implementación debe utilizar la versión más reciente del servicio de Experience Cloud ID. Consulte la [página principal](https://experienceleague.adobe.com/docs/id-service/using/home.html) en la guía del usuario del servicio de Experience Cloud ID. Es probable que la mayoría de las implementaciones que utilizan Adobe Experience Platform Launch ya hayan implementado ECID.
* Su implementación debe llamar a la función `setCustomerIDs` (o SDK equivalente) cada vez que se pueda identificar a un individuo, como cuando un usuario inicia sesión o abre un correo electrónico. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan. Consulte [`setCustomerIDs`](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/setcustomerids.html) en la guía del usuario del servicio de Experience Cloud ID.

## Limitaciones específicas del gráfico del dispositivo

* Los ID de Analytics heredados no son compatibles. Solo se vinculan los visitantes con Experience Cloud ID.
* Si su organización utiliza un gráfico privado, los nuevos dispositivos tardan hasta 24 horas en vincularse.
* Si su organización utiliza un gráfico de cooperación, los nuevos dispositivos que visiten el sitio pueden tardar hasta dos semanas en vincularse. El nivel de vinculación en CDA para las dos últimas semanas es generalmente inferior al de los intervalos de fechas de más de dos semanas.
* Los gráficos de dispositivos de terceros no son compatibles.

## Pasos siguientes

Una vez que su organización haya cumplido todos los requisitos y haya comprendido las limitaciones, puede empezar a [configurar análisis cruzados de dispositivos](setup.md).
