---
description: Utilice el ID de transacción en las fuentes de datos para vincular datos en línea y sin conexión.
title: ID de transacción y perfiles del visitante
topic-fix: Developer and implementation
uuid: 7a72779c-7f67-4872-ad5e-edf298d53cac
exl-id: ca5f9e8d-853f-4444-a8fd-a20933ef33d7
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 98%

---

# ID de transacción y perfiles del visitante

En esta sección se incluye información importante referente a los datos del perfil del visitante que se utilizan al cargar datos mediante un ID de transacción.

## ID de transacción {#section_B248FA93ECC84F6290D237EB83618070}

Cuando se registra un ID de transacción, se guarda una “captura de pantalla” del perfil del visitante actual y se asocia al ID de transacción. Esta “captura de pantalla” contiene todos los valores de variable que están configurados para el visitante en ese momento, las variables de persistencia (como las eVars y las campañas) entre ellos. Los eventos de éxito, los eventos de compra y los ingresos se atribuyen a los valores de esta “captura de pantalla” y más adelante se cargan con este mismo ID de transacción.

Después de crear la “captura de pantalla” del perfil del visitante, no se actualiza cuando el perfil del visitante actual cambia (debido al comportamiento en línea), sino que solo se actualiza con los datos que se cargan mediante fuentes de datos del ID de transacción. Si configura el mismo valor de ID de transacción en varias páginas durante la misma visita, la carga de fuentes de datos que tenga lugar más adelante estará vinculada a la “captura de pantalla” que se haya creado la primera vez que se configuró el ID.

**Varias cargas**

Se pueden cargar varias filas de datos en el mismo ID de transacción durante el período de caducidad del ID de transacción (véase a continuación).

**Caducidad de la variable**

La caducidad de la variable no se tiene en cuenta en los ID de transacción, ya que los datos del perfil del visitante asociados están diseñados para reflejar el estado del visitante en el momento de la transacción. Por ejemplo, si se ha configurado que eVar1 caduque después de la visita, el valor de la “captura de pantalla” del perfil del visitante recibe reconocimiento aunque el valor haya caducado o se haya sustituido en el perfil del visitante actual cuando se carguen datos del ID de transacción.

**Productos**

Como no hay información sobre productos (de `s.products`) en la “instantánea” del perfil del visitante, es necesario cargar todos los datos de productos asociados al archivo de fuente de datos junto con el ID de transacción. Tenga en cuenta que solo puede especificar un producto por fila, por lo que puede que tenga que cargar varias filas con el mismo ID de transacción para incluir todos los productos.

**Persistencia de eVar cargada**

Las eVars cargadas con fuentes de datos del ID de transacción se añaden a la “captura de pantalla” del perfil del visitante; no se añaden al perfil del visitante actual ni a una cookie virtual. Por lo tanto, el comportamiento en línea que ocurre después de la carga no se atribuye a las eVars cargadas, ya que estos valores no forman parte del perfil del visitante actual.

**Período de caducidad del ID de transacción**

La “captura de pantalla” del perfil del visitante que está asociada con un ID de transacción se puede eliminar después de 90 días, aunque el calendario real de eliminación varía. Si lo necesita, puede ponerse en contacto con el servicio de atención al cliente de Adobe para ampliar el período de vencimiento. Si se carga una fila una vez pasado el período de caducidad del ID de transacción, los datos de la fila se registran, pero si el perfil se ha eliminado, no se reflejará la carga en los datos de la “captura de pantalla” del perfil del visitante.

## Desglose y segmentación mediante ID de transacción {#section_A4D39291200A42C496122FDB9EF6EF68}

Las eVars cargadas mediante fuentes de datos se pueden utilizar para desglosar las eVars incluidas en la “captura de pantalla” del perfil del visitante. Como estos datos no dependen del perfil del visitante actual, no se pueden desglosar según otras eVars que se hayan configurado antes o después de que se configurara el ID de transacción, pero que no formen parte de la “instantánea”.

Hay algunas formas de ver datos de visitante asociados que quizá no estén disponibles en un desglose. En los informes de Data Warehouse puede ver datos del ID de transacción con un ID de visitante que coincida con las otras visitas del visitante. Aunque estas filas de ID de transacción se excluyen de los recuentos de visitas o visitantes por día, se usan al calcular la mayoría de métricas y en los segmentos.

Por eso, puede crear un segmento de visitantes que realicen un evento sin conexión concreto que se haya cargado mediante fuentes de datos del ID de transacción. Estos datos informarán de todo lo que haya hecho el visitante antes y después del evento del ID de transacción.

De igual modo, la participación del visitante le permite ver las proposiciones de ID de transacción y las eVars que han precedido a un evento en línea, o las proposiciones en línea y las eVars que han precedido a un evento del ID de transacción.
