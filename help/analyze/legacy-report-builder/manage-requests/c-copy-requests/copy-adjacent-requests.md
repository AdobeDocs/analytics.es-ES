---
description: Obtenga información sobre cómo copiar, pegar y reubicar solicitudes en otra parte de la hoja de cálculo.
title: Cómo copiar solicitudes adyacentes
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
feature: Report Builder
role: User, Admin
exl-id: 99476ec5-f1f0-49f5-a2d8-354cec63c6b1
source-git-commit: fcecc8a493852f5682fd7fbd5b9bb484a850922c
workflow-type: tm+mt
source-wordcount: '269'
ht-degree: 59%

---

# Copiar solicitudes adyacentes

{{legacy-arb}}

Del mismo modo que se copian y se pegan las solicitudes, también se pueden reubicar las solicitudes en otra parte de la hoja de cálculo, seleccionando [!UICONTROL Cortar solicitud] en el menú contextual.

Al cortar una solicitud, ésta se elimina de su ubicación original y se sitúa en la nueva ubicación tras seleccionar [!UICONTROL Pegar solicitud]. Si se cambia de opinión tras cortar una solicitud determinada y se decide copiar o cortar una solicitud diferente de otra celda, Report Builder deja la primera solicitud en su celda original y solo actúa con la segunda (efectúa la copia o el pegado).

>[!NOTE]
>
>Report Builder no es compatible con el comando Deshacer de Excel para cortar o pegar solicitudes.

No es obligatorio copiar y pegar en la misma hoja del libro. Puede copiar una solicitud en una hoja y pegarla en una ubicación de otra hoja del mismo libro.

No es obligatorio copiar y pegar una solicitud a la vez. Se pueden seleccionar varias solicitudes en la hoja de cálculo y pegarlas en una zona vacía de la hoja. Al igual que sucede al copiar y pegar una solicitud, asegúrese de que la zona de pegado no contenga celdas con solicitudes, ya que se sustituirían con la operación de pegado. Si el sistema detecta que la zona de pegado de destino ya contiene solicitudes, el Report Builder no muestra el menú [!UICONTROL Pegar solicitudes] para ninguna solicitud copiada o cortada. Se debe seleccionar una celda distinta como destino de la operación de pegado para que las solicitudes no se superpongan.
