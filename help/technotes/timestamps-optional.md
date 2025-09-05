---
description: Conozca las ventajas y limitaciones de utilizar la opción Marcas de hora opcionales.
keywords: Implementación de Analytics
title: Marcas de hora opcionales
topic-fix: Developer and implementation
feature: Implementation Basics
exl-id: c6a232d1-d7ce-4f21-9e8a-45703992bc6e
source-git-commit: fcc165536d77284e002cb2ba6b7856be1fdb3e14
workflow-type: tm+mt
source-wordcount: '599'
ht-degree: 96%

---

# Marcas de hora opcionales

Conozca las ventajas y limitaciones de utilizar la opción Marcas de hora opcionales.

<!-- Hide video as it is not adding a lot according to feedback from customer in feedback report January 2025.

>[!BEGINSHADEBOX]

See ![VideoCheckedOut](/help/assets/icons/VideoCheckedOut.svg) [Timestamps Optional](https://video.tv.adobe.com/v/3418612?quality=12&learn=on&captions=spa){target="_blank"} for a demo video.

>[!ENDSHADEBOX]
-->


Marcas de hora opcionales es la configuración predeterminada para todos los grupos de informes nuevos.

* Mezcle datos con y sin marca de hora en el mismo grupo de informes globales.
* Envíe datos con marca de hora de una aplicación móvil a un grupo de informes globales.
* Actualice las aplicaciones para usar marcas de hora sin tener que crear un nuevo grupo de informes.

>[!NOTE]
>
>Marcas de hora opcionales es la configuración predeterminada para todos los nuevos grupos de informes generados a partir de una plantilla. Los nuevos grupos de informes copiados de un grupo de informes existente heredarán la configuración del original.

Consulte [Marcas de hora opcionales](/help/technotes/timestamps-optional.md) para obtener información adicional sobre configuración.

## Marcas de hora opcionales: integrar datos con y sin marca de tiempo {#integrate}

Con la característica Marcas de hora opcionales, puede combinar datos sin marca de hora con datos con marca de hora sin provocar una pérdida de datos. Los datos sin conexión con marca de hora generados en un dispositivo móvil se pueden combinar con datos activos sin marca de hora de una página web, o integrarse con datos de cualquier plataforma utilizando una llamada a la variable timestamp de lado del cliente.

* **Datos con marca de hora**. Los datos con marca de hora de cliente se capturan y se envían directamente con los datos del dispositivo utilizando variables timestamp de lado del cliente: JavaScript en una página web, o utilizando una llamada al SDK móvil ([!DNL offlineEnabled=true]) en una aplicación móvil.
* **Datos sin marca de hora**. Adobe establece una marca de hora en los datos sin marca de hora de un grupo de informes cuando los datos llegan a los servidores de recopilación de datos.

Un grupo de informes puede tener una de las siguientes configuraciones de marca de hora:

* Marcas de hora no permitidas (opción visitorID admitida)
* Marcas de hora necesarias (opción visitorID no admitida)
* Marcas de hora opcionales (opción visitorID admitida pero no en visitas con marca de hora)

## Acerca de las Marcas de hora Funciones opcionales {#features}

Marcas de hora opcionales permite integrar varios grupos de informes, y crear informes de ellos, con o sin incluir marcas de hora de lado del cliente. Con Marcas de hora opcionales, puede actualizar su aplicación para utilizar marcas de hora y, al mismo tiempo, utilizar datos sin marca de hora de la aplicación anterior.

| En versiones anteriores... | Además... |
|--- |--- |
| No se pudieron enviar los datos con marca de hora a un grupo de informes global sin marca de hora. Por lo tanto, los datos de visitas enviados desde dispositivos sin conexión se perdieron al agregarlos a un grupo de informes sin marca de hora. <br/><br/>Por lo tanto, los datos de visitas enviados desde datos sin conexión se perdieron al agregarlos a un grupo de informes sin marca de hora. | Para actualizar una aplicación para recopilar y utilizar marcas de hora era necesario utilizar un nuevo grupo de informes. <br/>No se podía guardar en el grupo de informes existente ni integrar los datos existentes al actualizar la aplicación para que usara marcas de hora. |

**Con Marcas de hora opcionales**, puede integrar datos sin marca de hora de un sitio web activo con los datos sin conexión de dispositivos móviles, o actualizar su aplicación sin marca de hora a una aplicación con marca de hora.

## Combinación de datos en un grupo de informes global {#combine}

La combinación de datos en un grupo de informes global se puede realizar de varias maneras, incluido el etiquetado de grupos múltiples, las reglas de Vista y archivos por lotes importados de orígenes sin conexión.

>[!IMPORTANT]
>
>Planifique cuidadosamente el diseño de cada conjunto de datos componente para que la combinación tenga sentido en un grupo de informes global.

## Prácticas recomendadas al utilizar marcas de tiempo {#best-pratices}

Los siguientes son las prácticas recomendadas y algunos requisitos y limitaciones que hay que tener en cuenta al integrar datos con marca de hora y sin marca de hora.

* Por lo general, las marcas de hora de un visitante o visita determinados deben llegar a Adobe con el orden cronológico correcto.

  Los datos desordenados pueden ser datos que llegan tarde desde una recopilación de datos sin conexión y visitas que llegan tarde, o relojes desincronizados en dispositivos móviles sin conexión. Los datos desordenados pueden afectar negativamente a los informes de cálculos de tiempo (por ejemplo, valores de tiempo invertido), atribuciones (persistencia de eVar), número o recuento de visitas y e informes de rutas.

* No se recomienda utilizar marcas de hora cuando se establece [s.visitorID](/help/implement/vars/config-vars/visitorid.md). Puede producir datos desordenados.

* Las aplicaciones híbridas compuestas por una aplicación (datos sin conexión con marca de hora) que abre un explorador web (datos activos sin marca de hora) no deben utilizar marcas de hora. Produce informes inexactos acerca de la sesión.

  Además, las aplicaciones híbridas no deberían establecer un ID de visitante.
