---
description: Combine tanto los datos con marcas de hora como los datos sin marcas de hora en un grupo de informes único.
title: Configuración de marcas de hora
feature: Admin Tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
role: Admin
source-git-commit: 2d5348a4a6377313f5aab229214d97a02c826939
workflow-type: tm+mt
source-wordcount: '430'
ht-degree: 5%

---

# Configuración de marcas de hora

La página de administración &#39;[!UICONTROL Configuración de marcas de hora]&#39; le permite habilitar **[!UICONTROL Marcas de hora opcionales]** para uno o más grupos de informes. Esta configuración le permite combinar datos con y sin marca de tiempo en un único grupo de informes.

**[!UICONTROL Analytics]** > **[!UICONTROL Administrador]** > **[!UICONTROL Grupos de informes]** > **[!UICONTROL Editar configuración]** > **[!UICONTROL General]** > **[!UICONTROL Marcas de hora opcionales]**

## Configuración de marca de tiempo actual

Esta sección muestra la configuración actual de la marca de tiempo para el grupo de informes seleccionado. Puede ser uno de los tres valores posibles:

* No se permiten **marcas de hora (se admite la configuración `visitorID`)**
* Se requieren **marcas de hora (no se admite la configuración `visitorID`)**
* **Marcas de hora opcionales (se admite la configuración `visitorID`, pero no en las visitas con marca de hora)**

Debajo de este texto hay una casilla de verificación denominada **[!UICONTROL Convertir los grupos de informes seleccionados a marcas de hora opcionales]**. Si selecciona esta casilla de verificación y luego selecciona **[!UICONTROL Guardar]**, se habilitarán [!UICONTROL Marcas de hora opcionales] para los grupos de informes seleccionados.

## Marcas de hora no permitidas

Cuando envía datos a un grupo de informes utilizando esta configuración de marca de tiempo, la marca de tiempo se utiliza cuando los servidores de procesamiento de Adobe reciben la visita. Si intenta establecer la variable [`timestamp`](/help/implement/vars/page-vars/timestamp.md), la visita se eliminará de forma permanente.

## Marcas de hora obligatorias

Cuando envía datos a un grupo de informes utilizando esta configuración de marca de tiempo, cada visita debe incluir la variable [`timestamp`](/help/implement/vars/page-vars/timestamp.md). Si a alguna visita le falta una variable de implementación `timestamp`, la visita se eliminará de forma permanente.

Los datos de sesión con marca de tiempo habilitada se conservan por un período máximo de 92 días. Es decir, una visita se &quot;mantiene abierta&quot; durante 92 días, lo que permite incluir cualquier visita individual adicional en la misma visita o sesión. Aunque puede agregar datos a sesiones existentes, Adobe recomienda agregar visitas en orden por visitante. Las visitas que se reciben de forma desordenada por visitante pueden producir resultados de informes inesperados, aunque muchas de estas limitaciones se mitigan con el procesamiento de intervalos del informe.

## Marcas de hora opcionales

La configuración &#39;[!UICONTROL Marcas de hora opcionales]&#39; le permite integrar y crear informes en varios grupos de informes con o sin la variable [`timestamp`](/help/implement/vars/page-vars/timestamp.md). Los casos de uso ideales para [!UICONTROL Marcas de hora opcionales] incluyen:

* Mezcle datos con y sin marca de tiempo en el mismo grupo de informes globales
* Envío de datos con marca de hora desde una aplicación móvil a un grupo de informes globales
* Actualice aplicaciones para utilizar el seguimiento sin conexión sin tener que crear un nuevo grupo de informes

Esta opción está habilitada de forma predeterminada para todos los grupos de informes nuevos, a menos que el nuevo grupo de informes se copie de un grupo de informes con una configuración de marca de hora diferente.

>[!WARNING]
>
>Si usa [!UICONTROL Marcas de hora opcionales], no configure [`visitorID`](/help/implement/vars/config-vars/visitorid.md) en datos con marca de hora. Esta acción puede generar datos desordenados y afectar de forma negativa a los cálculos de hora (como el tiempo empleado), la atribución, el número de visitas/recuentos de visitas y los informes de rutas.

Una vez que habilites [!UICONTROL Marcas de hora opcionales], no podrás deshabilitarlas en esta interfaz. En el improbable caso de que quiera volver a cambiar a otra configuración de marca de tiempo, póngase en contacto con el Servicio de atención al cliente de Adobe.
