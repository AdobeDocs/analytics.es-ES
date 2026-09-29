---
description: Obtenga información sobre cómo solucionar y solucionar problemas relacionados con segmentos.
title: Resolución de problemas
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
TQID: 'https://experienceleague.adobe.com/-9XPy2cFezGBFnygKW4gbHG2zuNBfn5Z29InEDF58ZM'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: c47a19a5-f47b-4e53-afe0-e230da195ebe
    internal-label: Segmentation
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
    internal-label: Troubleshooting
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '181'
ht-degree: 6%
---
# Resolución de problemas

Este artículo enumera algunos problemas comunes con los segmentos y cómo solucionarlos.

<!--
Looks like this is not part anymore of the current UI.

## Error: "Incompatible elements in this segment" {#incompatible}

This error occurs when you try to save a segment in the Data Warehouse folder where the segment contains elements not compatible with Data Warehouse. To resolve this error, do one of two things:

* Save the segment in a different folder 
* Remove or change the incompatible portions of the segment.
-->

## ¿Por qué no devuelve ningún dato mi segmento? {#no-data}

Posibles razones:

* Anidado inverso: por ejemplo, anidar un contenedor de ![Usuario](/help/assets/icons/User.svg) **[!UICONTROL Visitante]** bajo un contenedor de ![Visita](/help/assets/icons/Visit.svg) **[!UICONTROL Visita]**.
* El informe no admite la segmentación.
* No hay datos que coincidan con los criterios de segmentación.

## ¿Por qué no puedo ver el segmento que he creado en el Administrador de segmentos? {#invisible}

Posibles razones:

* Algunas dimensiones solo están disponibles en Data Warehouse y no en el Administrador de segmentos.
* El segmento solo se comprueba para un grupo de informes específico.
* Es posible que otro usuario haya eliminado un segmento compartido.
* No se han podido cargar los segmentos debido a un problema con el centro de datos o la caché del explorador.
* El segmento no se ha guardado.
* La dirección IP puede bloquearse por parte del usuario.

## ¿Por qué los datos mostrados después de aplicar un segmento parecen incorrectos? {#page-data}

Posibles razones:

* Las reglas u operadores son incorrectos para el resultado requerido.
* Uso incorrecto de contenedores en el segmento.
* Las variables de tráfico utilizadas para segmentar no se han configurado correctamente o han caducado.
