---
title: Dispositivos únicos
description: Número de dispositivos únicos.
exl-id: fa5c860f-bea7-4d03-9632-fa6e025647bf
source-git-commit: 407111f6016fe8595f1d5c3464e36dfd4d314630
workflow-type: tm+mt
source-wordcount: '248'
ht-degree: 6%

---

# Dispositivos únicos

La métrica &quot;Dispositivos únicos&quot; es una métrica [Análisis entre dispositivos](../cda/overview.md) que cuenta el número de dispositivos únicos no identificados y dispositivos virtuales únicos. Los dispositivos no identificados son dispositivos que generaron visitas anónimas. Los dispositivos virtuales únicos son personas distintas identificadas por dispositivo.

## Cálculo de esta métrica

Para cada dispositivo, suma todas las personas distintas vinculadas a él (incluido el anónimo si el dispositivo contiene visitas no vinculadas).

Tenga en cuenta que esta métrica no es igual a [Visitantes únicos](unique-visitors.md) en los grupos de informes que no son de CDA. Por ejemplo, un dispositivo se comparte con 3 cuentas diferentes. Si las 3 cuentas visitan el sitio en una ventana de informes, el informe resultante mostrará 3 dispositivos únicos en CDA. Los mismos datos fuera de CDA mostrarían 1 visitante único.

## Ejemplo

1. Bob llega a su sitio en su teléfono a través de un anuncio, pero no ha iniciado sesión.
1. Bob quiere hacer una compra, pero preferiría hacerlo en el ordenador familiar porque ya ha iniciado sesión allí. En el ordenador de la familia, hace una compra.
1. Al día siguiente, comprueba su pedido por teléfono y se autentica allí.
1. La esposa de Bob, Alice, explora tu sitio mientras inicia sesión en su cuenta en el ordenador familiar.
1. El hermano de Bob, Charles, también explora tu sitio mientras inicia sesión en su cuenta en el equipo familiar.

![Recuento de dispositivos únicos](/help/components/metrics/assets/Unique_Devices_Count.png)

Ver estos datos en un grupo de informes virtuales CDA antes de [Reproducir](/help/components/cda/replay.md) mostraría:

* **5 dispositivos** únicos: 1 para Bob no autenticado + 2 para Bob + 1 para Alice + 1 para Charles
* **4  [Personas](people.md)**: 1  [Personas](unidentified-people.md)  No Identificadas + 3  [Personas](identified-people.md) Identificadas.

