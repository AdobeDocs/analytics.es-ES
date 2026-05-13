---
title: Información general de complementos
description: Pegue código en el sitio para incorporar nuevas funciones.
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
TQID: https://experienceleague.adobe.com/ImzoBRU0DajPc99vRlu1698CteFNk9dOS2OZrN9DBZs
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
subfeature_v2: id: c069c44e-5426-4c1a-accc-8028662f2fdeid: df312454-73c4-43f6-a90e-18f5043f074cid: e7d92df1-c5ba-4e93-85df-f83171b889be
role_v2: id: c66ffd68-0f65-42bb-aa23-b4020f12e0bdid: ff6a42d2-313e-452e-93a6-792e4fad9ff8
topic_v2: id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87cid: c1579802-ddd4-4214-8a91-97b2066abe11id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 328
ht-degree: 96%

---

# Información general de complementos

Los complementos son fragmentos de código que realizan varias funciones avanzadas que mejoran la implementación de Analytics. Estos complementos amplían las capacidades del archivo JavaScript y aportan una funcionalidad ampliada que no se encuentra disponible con una implementación básica. Adobe ofrece otros complementos como parte de soluciones avanzadas.

{{plug-in}}

Adobe ofrece varias formas de instalar un complemento determinado:

* Utilice la extensión Complementos comunes de Analytics con la extensión de Adobe Analytics
* Pegue el código del complemento con el editor de código personalizado
* Pegue el código del complemento en el archivo `AppMeasurement.js`.

Cada organización tiene diferentes necesidades de implementación, por lo que puede decidir cómo desea incluirlas en la implementación. Asegúrese de cumplir los siguientes criterios al incluir el código en el sitio:

1. Primero cree una instancia del objeto de seguimiento de Analytics (use [`s_gi`](../functions/s-gi.md)).
   * El sitio con etiquetas automáticamente crea una instancia del objeto de seguimiento cuando se carga Adobe Analytics.
   * Las implementaciones que utilizan `AppMeasurement.js` suelen inicializar el objeto de seguimiento en la parte superior del archivo JavaScript.
2. Segundo, incluya el código del complemento.
   * La extensión “Complementos comunes de Analytics” tiene una configuración de acción en la que puede inicializar complementos.
   * Si no desea utilizar la extensión, puede pegar el código del complemento en el editor de código personalizado al configurar la extensión de Analytics.
   * Si la implementación no utiliza etiquetas en Adobe Experience Platform, puede pegar el código del complemento en `AppMeasurement.js`, en cualquier lugar después de crear la instancia del objeto de seguimiento.
3. Tercero, llame al complemento.
   * Todas las implementaciones, tanto dentro como fuera del sitio con etiquetas, utilizan JavaScript para llamar a los complementos. Llame al complemento con el formato documentado en la página de dicho complemento.
4. Valide la implementación y publíquelo.

Muchas organizaciones llaman a complementos con la función [`doPlugins`](../functions/doplugins.md). Aunque esta función no es obligatoria, Adobe considera que es recomendable utilizarla. AppMeasurement llama a esta función justo antes de compilar y enviar una solicitud de imagen, lo cual es ideal ya que varios complementos dependen de otras variables de Analytics.
