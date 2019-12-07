---
description: Número de veces que se ha establecido un valor para una variable.
keywords: instances
title: Instancias
topic: Metrics
uuid: fec94bdd-a1dc-4cb0-8983-ea575b69589f
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Instancias

Número de veces que se ha establecido un valor para una variable.

Instancias se contabilizan para todos los tipos de visitas, pero no se cuentan cuando se registra un valor para una variable en una visita posterior debido a la persistencia.

Por ejemplo, si un usuario llega a un sitio a través de [!DNL example.com], la primera solicitud de imagen del sitio contendrá el referente de [!DNL example.com]. Si este valor está establecido, se atribuye una instancia a [!DNL example.com] aunque este referente esté registrado para todas las páginas visualizadas durante la visita.

Las instancias de las variables de conversión del almacén de datos se agregaron a mediados de 2011, y permiten al almacén de datos enviar solicitudes para tratar instancias de variables de conversión específicas como métricas. Estas métricas no están disponibles para generar informes anteriores a su fecha de introducción.
