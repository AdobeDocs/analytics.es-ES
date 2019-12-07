---
description: 'null'
title: Tiempo de procesamiento de las fuentes de datos
uuid: d7cd679a-f9e3-4740-87cf-6171f3fe5cd9
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Tiempo de procesamiento de las fuentes de datos

>[!Note]
>Cualquier período de tiempo de procesamiento de datos debe considerarse aproximado y no constituye un contrato de nivel de servicio (SLA).

El tiempo de procesamiento de los datos varía en función de las siguientes directrices:

* Datos del día actual: El procesamiento finaliza aproximadamente dos horas después de la carga de los datos.
* Datos del día anterior: el procesamiento se completa en 3 horas tras la carga de los datos, aproximadamente.

Cada día adicional en la carga añade aproximadamente 1 hora al tiempo de procesamiento, hasta un máximo de 17 horas.

Por ejemplo, si carga datos del día anterior, dichos datos serán visibles en Analytics al cabo de 2 horas, aproximadamente. Si carga datos del mes anterior, dichos datos serán visibles en Analytics al cabo de 17 horas, aproximadamente.
