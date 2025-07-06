---
description: Obtenga información sobre cómo solucionar y solucionar problemas relacionados con segmentos.
title: Resolución de problemas
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 35f2812c1a1a4eed090e04d67014fcebf88a80ec
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 42%

---

# Resolución de problemas

Este artículo enumera algunos problemas comunes con los segmentos y cómo solucionarlos.

<!-- Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.

-->

## ¿Por qué no devuelve ningún dato mi segmento? {#no-data}

Motivos posibles:

* Anidado inverso: por ejemplo, anidar un contenedor de ![Usuario](/help/assets/icons/User.svg) **[!UICONTROL Visitante]** bajo un contenedor de ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Visita]**.
* El informe no admite la segmentación.
* No hay datos que coincidan con los criterios de segmentación.

## ¿Por qué no puedo ver el segmento que he creado en el Administrador de segmentos? {#invisible}

Motivos posibles:

* Algunas dimensiones solo están disponibles en Data Warehouse y no en el Administrador de segmentos.
* El segmento únicamente se comprueba para un grupo de informes específico.
* Es posible que otro usuario haya eliminado un segmento compartido.
* No se han podido cargar los segmentos debido a un problema con el centro de datos o la caché del explorador.
* El segmento no se ha guardado.
* La dirección IP puede haber sido bloqueada en el terminal del usuario.

## ¿Por qué los datos mostrados después de aplicar un segmento parecen incorrectos? {#page-data}

Motivos posibles:

* Las reglas u operadores son incorrectos para el resultado requerido.
* Uso incorrecto de contenedores en el segmento.
* Las variables de tráfico utilizadas en el segmento no se han configurado correctamente o han caducado.
