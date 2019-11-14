---
description: Número de veces que se ha establecido un valor para una variable.
keywords: instances
solution: Analytics
title: Instancias
topic: Metrics
uuid: fec94bdd-a1dc-4cb0-8983-ea575b69589f
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Instancias

Número de veces que se ha establecido un valor para una variable.

Las instancias se cuentan para todos los tipos de visitas, pero no se cuentan si se registra un valor para una variable en una visita subsiguiente debido a una persistencia.

For example, if a user arrives on your site via [!DNL example.com], the first image request on your site contains the referrer of [!DNL example.com]. Si este valor está establecido, se atribuye una instancia a [!DNL example.com] aunque este referente esté registrado para todas las páginas visualizadas durante la visita.

Las instancias de las variables de conversión del almacén de datos se agregaron a mediados de 2011, y permiten al almacén de datos enviar solicitudes para tratar instancias de variables de conversión específicas como métricas. Estas métricas no están disponibles para generar informes anteriores a su fecha de introducción.
