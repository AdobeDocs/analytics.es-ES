---
description: Conozca las ventajas y limitaciones de utilizar la opción Marcas de hora opcionales.
keywords: Analytics Implementation
title: Usar marcas de hora opcionales
topic: Developer and implementation
uuid: 956aaa16-6ffa-4b63-b022-a659f5143e00
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Usar marcas de hora opcionales

Conozca las ventajas y limitaciones de utilizar la opción Marcas de hora opcionales.

Marcas de hora opcionales es la configuración predeterminada para todos los nuevos grupos de informes.

* Mezcle datos con y sin marca de hora en el mismo grupo de informes globales.
* Envíe datos con marca de hora desde una aplicación móvil a un grupo de informes globales.
* Actualice las aplicaciones para utilizar marcas de hora sin tener que crear un nuevo grupo de informes.

>[!NOTE] Marcas de hora opcionales es la configuración predeterminada para todos los nuevos grupos de informes generados a partir de una plantilla. Los nuevos grupos de informes copiados de un grupo de informes existente heredarán la configuración del original.

Consulte [Marcas de hora opcionales](https://marketing.adobe.com/resources/help/es_ES/reference/timestamp-optional.html) para obtener información adicional sobre la configuración.

## Marcas de hora opcionales: Integración de datos con marca de hora y sin marca de hora {#section_BF17CB593044462B993FD0D28EA56518}

Con la función Marcas de hora opcionales, puede combinar datos sin marca de hora con datos con marca de hora sin provocar pérdidas de datos. Los datos sin conexión con marcas de hora generados desde un dispositivo móvil se pueden combinar con datos activos sin marca de hora de una página web o integrados con datos de cualquier plataforma mediante una llamada de marca de hora del lado del cliente.

* **Datos** de marca de hora. Los datos con marca de hora de cliente se capturan y se envían directamente con los datos del dispositivo utilizando variables timestamp de lado del cliente: JavaScript en una página web, o utilizando una llamada al SDK móvil ([!DNL offlineEnabled=true]) en una aplicación móvil.
* **Datos** sin marca de hora. Adobe establece una marca de hora en los datos sin marca de hora de un grupo de informes cuando los datos llegan a los servidores de recopilación.


Un grupo de informes puede tener una de las siguientes configuraciones de marca de tiempo:

* No se permiten marcas de hora (se admite el ID de visitante)
* Marcas de hora obligatorias (no se admite el ajuste visitorID)
* Marcas de hora opcionales (se admite el ajuste visitorID, pero no en visitas con marca de hora)

## Acerca de las características de Marcas de hora opcionales {#section_63B2FA9A2AB24B3993E84D2C2B4BF2CE}

Marcas de hora opcionales le permite integrar varios grupos de informes y crear informes con o sin marcas de hora del lado del cliente incluidas. Con Marcas de hora opcionales, puede actualizar la aplicación para que utilice marcas de hora y, al mismo tiempo, utilice datos sin marca de hora de la aplicación anterior.

| En versiones anteriores... | Además... |
|--- |--- |
| Los datos con marca de hora no se pudieron enviar a un grupo de informes global sin marca de hora. Por lo tanto, los datos de visitas enviados desde dispositivos sin conexión se perdieron al agregarlos a un grupo de informes sin marca de hora. <br/><br/>Por lo tanto, los datos de visitas enviados desde datos sin conexión se perdieron al agregarlos a un grupo de informes sin marca de hora. | Para actualizar una aplicación para recopilar y utilizar marcas de hora era necesario utilizar un nuevo grupo de informes. <br/>No se podía guardar en el grupo de informes existente ni integrar los datos existentes al actualizar la aplicación para que usara marcas de hora. |

**Con Marcas de hora opcionales**, puede integrar datos sin marca de hora de un sitio web activo con los datos sin conexión de dispositivos móviles, o actualizar su aplicación sin marca de hora a una aplicación con marca de hora.

## Combinar datos en un grupo de informes global {#section_5BE3BDF56007402BB1F5C3144D5FE1E0}

La combinación de datos en un grupo de informes global se puede realizar de varias maneras, incluido el etiquetado de grupos múltiples, las reglas de Vista y archivos por lotes importados de orígenes sin conexión.

>[!IMPORTANT] Planifique cuidadosamente el diseño de cada conjunto de datos componente para que la combinación tenga sentido en un grupo de informes global.

## Prácticas recomendadas para el uso de marcas de hora {#section_9436394E5D7E4F8A8B369B6D11BB2B2B}

A continuación se indican las prácticas recomendadas y algunos requisitos y restricciones que deben tenerse en cuenta al integrar datos con marca de hora y sin marca de hora.

* En general, las marcas de hora de un visitante o visita determinados deben llegar a Adobe en el orden cronológico correcto.

   Los datos desordenados pueden incluir datos que llegan tarde desde la recopilación de datos sin conexión y visitas que llegan tarde, o relojes desincronizados en dispositivos móviles sin conexión. Los datos desordenados pueden afectar negativamente a los informes de cálculos de tiempo (por ejemplo, valores de tiempo invertido), atribuciones (persistencia de eVar), número o recuento de visitas y e informes de rutas.

* No se recomienda el uso de marcas de hora al configurar [s.visitorID](https://marketing.adobe.com/resources/help/es_ES/sc/implement/visid_custom.html) . Puede generar datos desordenados.

* Las aplicaciones híbridas compuestas de una aplicación (datos sin conexión con marca de hora) que abre un navegador web (datos activos sin marca de hora) no deben utilizar marcas de hora. El resultado es un sistema de informes inexacto de la sesión.

   Además, las aplicaciones híbridas no deben establecer un ID de visitante.
