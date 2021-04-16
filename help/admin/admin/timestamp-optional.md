---
description: Combine tanto los datos con marcas de hora como los datos sin marcas de hora en un grupo de informes único.
title: Marcas de hora opcionales
feature: Herramientas de administración
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
exl-id: 4d64225a-5eb8-4b7b-ba13-3cdc12dd6651
translation-type: tm+mt
source-git-commit: 78412c2588b07f47981ac0d953893db6b9e1d3c2
workflow-type: tm+mt
source-wordcount: '321'
ht-degree: 100%

---

# Marcas de hora opcionales

Combine tanto los datos con marcas de hora como los datos sin marcas de hora en un grupo de informes único.

Marcas de hora opcionales, permite hacer lo siguiente:

* Mezcle datos con y sin marca de hora en el mismo grupo de informes globales.
* Envíe datos con marca de hora de una aplicación móvil a un grupo de informes globales.
* Actualice aplicaciones para usar el seguimiento sin conexión sin tener que crear un nuevo grupo de informes.

>[!IMPORTANT]
>
>Si usa Marcas de hora opcionales, no configure [s.visitorID](/help/implement/vars/config-vars/visitorid.md) en datos que ya cuenten con marcas de hora. Esto puede generar datos confusos y afectar de forma negativa a los cálculos de hora (como por ejemplo los valores de tiempo empleado), atribución (persistencia de eVar), número de visitas/recuentos de visitas y informes de rutas.

>[!NOTE]
>
>Los datos de sesión con marca de tiempo habilitada se conservan por un período máximo de 92 días. Esto significa que una visita/sesión se “mantendrá abierta” durante 92 días, mientras que cualquier visita individual adicional (que no sea 30 minutos después de la visita individual anterior) se puede incluir en la misma visita/sesión. Cualquier visita “antigua” que se reciba de manera desordenada producirá resultados “desconocidos”, ya que una serie de factores (segmentación, asignación, caducidad, etc.) influyen en si estas visitas se incluirán o no en los informes.

## Nuevos grupos de informes {#section_095A7CFBD280494593B9BEC1592B73A6}

* Si se crea a partir de una plantilla, un nuevo grupo de informes toma como valor predeterminado Marcas de horas opcionales.

   (Puede crear un nuevo grupo de informes desde una plantilla en **Administradores > Grupos de informes > Crear nuevo > Grupo de informes**).
* Si se copia de un grupo de informes existente, entonces el nuevo grupo de informes heredará el ajuste de marca de hora del original, incluido lo siguiente:

   * **No se permiten marcas de hora** (se admite s.visitorID)
   * **Marcas de hora obligatorias** (no se admite s.visitorID)
   * **Marcas de horas opcionales** (se admite el ajuste s.visitorID, pero no en visitas con marca de horas)

## Para cambiar los grupos de informes existentes a Marcas de hora opcionales {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Vaya a **Administradores > Grupos de informes > Editar configuración > General > Configuración de marcas de hora**.
1. Seleccione el cuadro **Convertir los grupos de informes seleccionados a marcas de hora opcional**.

   Esto cambiará el grupo de informes a Marcas de hora opcionales.

>[!NOTE]
>
>Si un grupo de informes está establecido en **Marcas de hora opcionales**, póngase en contacto con el servicio de atención al cliente de Adobe para cambiar esta o cualquier otra opción de configuración.
