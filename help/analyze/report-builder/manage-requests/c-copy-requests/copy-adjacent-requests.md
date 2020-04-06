---
description: Del mismo modo que se copian y se pegan las solicitudes, también se pueden reubicar las solicitudes en otra parte de la hoja de cálculo, seleccionando Cortar solicitud en el menú contextual.
title: Copiar solicitudes adyacentes
topic: Report builder
uuid: c8abec0d-6fbd-4a98-8672-ede81317487b
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Copiar solicitudes adyacentes

Del mismo modo que se copian y se pegan las solicitudes, también se pueden reubicar las solicitudes en otra parte de la hoja de cálculo, seleccionando Cortar solicitud en el menú contextual.

Cutting a request removes it from its original location and places it in the new location after you select [!UICONTROL Paste Request]. Si se cambia de opinión tras cortar una solicitud determinada y se decide copiar o cortar una solicitud diferente de otra celda, Report Builder deja la primera solicitud en su celda original y solo actúa con la segunda (efectúa la copia o el pegado).

>[!NOTE] Report Builder no es compatible con el comando Deshacer de Excel para cortar o pegar solicitudes. Por lo tanto, tenga cuidado al cortar solicitudes.

No está limitado a copiar y pegar en la misma hoja del libro. Puede copiar una solicitud en una hoja y pegarla en una ubicación de otra hoja del mismo libro.

No está limitado a copiar y pegar una solicitud a la vez. Puede seleccionar más de una solicitud en la hoja de cálculo y pegarla en una región vacía de la hoja de cálculo. Al igual que con copiar y pegar una solicitud, asegúrese de que la zona de pegado no tenga celdas con solicitudes que se sustituirán por la operación de pegado. If the system finds that the target paste region already contains one or more requests, report builder does not display the [!UICONTROL Paste Requests] menu for any copied or cut requests. Debe seleccionar una celda diferente como destino de la operación de pegado para que las solicitudes no se superpongan.
