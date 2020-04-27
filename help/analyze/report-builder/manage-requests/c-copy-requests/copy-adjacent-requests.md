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

>[!NOTE] Report Builder no es compatible con el comando Deshacer de Excel para cortar o pegar solicitudes. Por lo tanto, se debe ser cuidadoso al cortar las solicitudes.

No existe limitación a la hora de copiar y pegar en la misma hoja del libro. Es posible copiar una solicitud de una hoja y pegarla en una ubicación de otra hoja del mismo libro.

No existe limitación a la hora de copiar y pegar una solicitud cada vez. Se pueden seleccionar varias solicitudes en la hoja de cálculo y pegarlas en una zona vacía de la hoja. Al igual que sucede al copiar y pegar una solicitud, asegúrese de que la zona de pegado no contenga celdas con solicitudes, ya que se sustituirían con la operación de pegado. If the system finds that the target paste region already contains one or more requests, report builder does not display the [!UICONTROL Paste Requests] menu for any copied or cut requests. Se debe seleccionar una celda distinta como destino de la operación de pegado para que las solicitudes no se superpongan.
