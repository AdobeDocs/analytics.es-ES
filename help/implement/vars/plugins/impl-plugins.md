---
title: Información general de complementos
description: Pegue código en el sitio para incorporar nuevas funciones.
exl-id: faae7963-078d-40ad-ba09-71efa0b90df1
translation-type: ht
source-git-commit: 549258b0168733c7b0e28cb8b9125e68dffd5df7
workflow-type: ht
source-wordcount: '400'
ht-degree: 100%

---

# Información general de complementos

Los complementos son fragmentos de código que realizan varias funciones avanzadas que mejoran la implementación de Analytics. Estos complementos amplían las capacidades del archivo JavaScript y aportan una funcionalidad ampliada que no se encuentra disponible con una implementación básica. Adobe ofrece otros complementos como parte de soluciones avanzadas.

>[!IMPORTANT]
>
>Los complementos son cortesía de Adobe Consulting para ayudarle a obtener más valor de Adobe Analytics. El Servicio de atención al cliente de Adobe no ofrece asistencia técnica para ninguno de estos complementos, ni para la instalación ni para la solución de problemas. Si necesita ayuda con algún complemento, póngase en contacto con el administrador de cuentas de su organización. Ellos podrán organizar una reunión con un consultor para ayudarle.

Adobe ofrece varias formas de instalar un complemento determinado:

1. Utilice la extensión “Complementos comunes de Analytics” con Adobe Experience Platform Launch.
2. Pegue el código del complemento con el editor de código personalizado Launch.
3. Pegue el código del complemento en el archivo `AppMeasurement.js`.

Cada organización tiene diferentes necesidades de implementación, por lo que puede decidir cómo desea incluirlas en la implementación. Asegúrese de cumplir los siguientes criterios al incluir el código en el sitio:

1. Primero cree una instancia del objeto de seguimiento de Analytics (use [`s_gi`](../functions/s-gi.md)).
   * Launch automáticamente crea una instancia del objeto de seguimiento al cargar Adobe Analytics.
   * Las implementaciones que utilizan `AppMeasurement.js` suelen inicializar el objeto de seguimiento en la parte superior del archivo JavaScript.
2. Segundo, incluya el código del complemento.
   * La extensión “Complementos comunes de Analytics” tiene una configuración de acción en la que puede inicializar complementos.
   * Si no desea utilizar la extensión, puede pegar el código del complemento en el editor de código personalizado al configurar la extensión de Analytics.
   * Si la implementación no utiliza Launch, puede pegar el código del complemento en `AppMeasurement.js`, en cualquier lugar después de crear la instancia del objeto de seguimiento.
3. Tercero, llame al complemento.
   * Todas las implementaciones, tanto dentro como fuera de Launch, utilizan JavaScript para llamar a los complementos. Llame al complemento con el formato documentado en la página de dicho complemento.
4. Valide la implementación y publíquelo.

Muchas organizaciones llaman a complementos con la función [`doPlugins`](../functions/doplugins.md). Aunque esta función no es obligatoria, Adobe considera que es recomendable utilizarla. AppMeasurement llama a esta función justo antes de compilar y enviar una solicitud de imagen, lo cual es ideal ya que varios complementos dependen de otras variables de Analytics.

## Uso de complementos con objetos de seguimiento no estándar

Los complementos no funcionan de forma predeterminada con objetos de seguimiento que no sean `s`. Sin embargo, puede modificar el código del complemento para que quepa el objeto de seguimiento personalizado. Dentro de un complemento determinado, reemplace todas las referencias a `s` con el objeto de seguimiento deseado.
