---
title: Dispositivos únicos
description: Número de dispositivos únicos.
feature: Metrics
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: d095628e94a45221815b1d08e35132de09f5ed8f
workflow-type: tm+mt
source-wordcount: '264'
ht-degree: 92%

---

# Dispositivos únicos

La métrica [Dispositivos únicos](overview.md) es una métrica de [Análisis entre dispositivos](../cda/overview.md) que cuenta el número de dispositivos únicos no identificados y los dispositivos virtuales únicos. Los dispositivos no identificados son dispositivos que generaron visitas anónimas. Los dispositivos virtuales únicos son las distintas personas identificadas por dispositivo.

## Cálculo de esta métrica

Para cada dispositivo, suma todas las personas distintas vinculadas a él (incluido el anónimo si el dispositivo contiene visitas no vinculadas).

Tenga en cuenta que esta métrica no es igual a [Visitantes únicos](unique-visitors.md) en los grupos de informes que no son de CDA. Por ejemplo, un dispositivo se comparte con tres cuentas diferentes. Si las tres cuentas visitan el sitio en una ventana de informes, el informe resultante mostrará tres dispositivos únicos en CDA. Los mismos datos fuera de CDA mostrarían un visitante único.

## Ejemplo

1. Sally llega al sitio en su teléfono a través de un anuncio, pero no ha iniciado sesión.
1. Sally quiere hacer una compra, pero preferiría hacerlo en el ordenador de la familia porque ya ha iniciado sesión allí. En el ordenador de la familia, hace una compra.
1. Al día siguiente, comprueba su pedido por teléfono y se autentica por ese medio.
1. La esposa de Bob, Alice, explora su sitio mientras inicia sesión en su cuenta en el ordenador familiar.
1. El hermano de Bob, Charles, también explora su sitio mientras inicia sesión en su cuenta en el equipo familiar.

![Recuento de dispositivos únicos](/help/components/metrics/assets/Unique_Devices_Count.png)

Ver estos datos en un grupo de informes virtuales de CDA antes de [Reproducir](/help/components/cda/replay.md) potencialmente vincula las visitas no autenticadas y mostraría lo siguiente:

* **Cinco dispositivos únicos**: uno para Bob no autenticado y dos para Bob y uno para Alice, más uno para Charles
* **Cuatro [personas](people.md)**: una [persona no identificada](unidentified-people.md) más tres [personas identificadas](identified-people.md).
