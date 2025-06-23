---
title: Información general de complementos
description: Pegue código en el sitio para incorporar nuevas funciones.
feature: Appmeasurement Implementation
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
role: Admin, Developer
source-git-commit: 665bd68d7ebc08f0da02d93977ee0b583e1a28e6
workflow-type: tm+mt
source-wordcount: '308'
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
