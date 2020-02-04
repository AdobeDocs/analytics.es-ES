---
title: Introducción a los complementos
description: Pegue el código en el sitio para introducir nuevas funciones.
translation-type: tm+mt
source-git-commit: 365944140bb1dfc9bc8669ae530c631e8ff1629b

---


# Introducción a los complementos

Los complementos son fragmentos de código que realizan varias funciones avanzadas para ayudar a la implementación de Analytics. Estos complementos amplían las capacidades del archivo JavaScript y aportan una funcionalidad ampliada que no se encuentra disponible con una implementación básica. Adobe ofrece otros complementos como parte de soluciones avanzadas.

> [!IMPORTANT] Los complementos los proporciona Adobe Consulting de forma gratuita para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no proporciona asistencia técnica con ninguno de estos complementos, incluida la instalación o la solución de problemas. Si necesita ayuda con un complemento, póngase en contacto con el administrador de cuentas de su organización. Pueden organizar una reunión con un consultor para obtener ayuda.

Adobe ofrece varias formas de instalar un complemento determinado:

1. Utilice la extensión &#39;Complementos comunes de Analytics&#39; con Adobe Experience Platform Launch
2. Pegar código de complemento mediante el editor de código personalizado Iniciar
3. Pegue el código del complemento en el `AppMeasurement.js` archivo

Cada organización tiene diferentes necesidades de implementación, por lo que puede decidir cómo desea incluirlas en la implementación. Asegúrese de cumplir los siguientes criterios al incluir el código en el sitio:

1. Cree una instancia del objeto de seguimiento de Analytics (usando `s_gi`) primero.
   * Launch crea automáticamente una instancia del objeto de seguimiento cuando se carga Adobe Analytics.
   * Las implementaciones que utilizan `AppMeasurement.js` generalmente inicializan el objeto de seguimiento en la parte superior del archivo JavaScript.
2. Incluir código de complemento en segundo lugar.
   * La extensión &#39;Complementos comunes de Analytics&#39; tiene una configuración de acción en la que puede inicializar complementos.
   * Si no desea utilizar el complemento, puede pegar código de complemento en el editor de código personalizado al configurar la extensión de Analytics.
   * Si la implementación no utiliza Launch, puede pegar el código del complemento en `AppMeasurement.js` cualquier lugar después de crear la instancia del objeto de seguimiento.
3. Llame al complemento tercero.
   * Todas las implementaciones, tanto dentro como fuera de Launch, utilizan JavaScript para llamar a los complementos. Llame al complemento utilizando el formato documentado en la página del complemento.
4. Valide la implementación y publique.

Muchas organizaciones llaman a complementos con la [`doPlugins`](../functions/doplugins.md) función . Aunque esta función no es obligatoria, Adobe considera que es recomendable utilizarla. AppMeasurement llama a esta función justo antes de compilar y enviar una solicitud de imagen, lo cual es ideal ya que varios complementos dependen de otras variables de Analytics.
