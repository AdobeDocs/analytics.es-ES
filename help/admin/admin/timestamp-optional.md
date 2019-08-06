---
description: Combine tanto los datos con marcas de hora como los datos sin marcas de hora en un grupo de informes único.
seo-description: Combine tanto los datos con marcas de hora como los datos sin marcas de hora en un grupo de informes único.
seo-title: Marcas de hora opcionales
solution: Analytics
title: Marcas de hora opcionales
topic: Herramientas de administración
uuid: 0 fa 63658-1 cc 2-4 adc -8 d 51-a 0662 d 0 aa 941
translation-type: tm+mt
source-git-commit: 2b7644a7af34fff95d7557382abf3d370bd2637c

---


# Marcas de hora opcionales

Combine tanto los datos con marcas de hora como los datos sin marcas de hora en un grupo de informes único.

Marcas de hora opcionales, permite hacer lo siguiente:

* Mezcle datos con y sin marca de hora en el mismo grupo de informes globales.
* Envíe datos con marca de hora de una aplicación móvil a un grupo de informes globales.
* Actualice aplicaciones para usar el seguimiento sin conexión sin tener que crear un nuevo grupo de informes.

Consulte [Uso de marcas de hora opcionales](/help/implement/js-implementation/timestamps-overview.md) para conocer las prácticas recomendadas al usar marcas opcionales en el grupo de informes.

>[!IMPORTANT]
>
>If you are using Timestamps Optional, then do not set [s.visitorID](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=visid_custom) on data that is already timestamped. Esto puede generar datos confusos y afectar de forma negativa a los cálculos de hora (como por ejemplo los valores de tiempo empleado), atribución (persistencia de eVar), número de visitas/recuentos de visitas y informes de rutas.

>[!NOTE]
>
>Los datos de sesión con marca de tiempo habilitada se conservan por un período máximo de 92 días. Esto significa que una visita o sesión se «mantendrá abierta» durante 92 días, mientras que cualquier visita adicional (que no sea 30 minutos después de la visita anterior (en tiempo de visita), podrá incluirse en la misma visita/sesión. Las visitas «antiguas» que se reciben fuera de orden producirán resultados «desconocidos», ya que son varios factores (segmentación, asignación, caducidad, etc.) influir en si estas visitas se incluirán en los informes o no.

## Nuevos grupos de informes {#section_095A7CFBD280494593B9BEC1592B73A6}

* Si se crea a partir de una plantilla, un nuevo grupo de informes toma como valor predeterminado Marcas de horas opcionales.

   (Puede crear un nuevo grupo de informes desde una plantilla en **Administradores &gt; Grupos de informes &gt; Crear nuevo &gt; Grupo de informes**).
* Si se copia de un grupo de informes existente, entonces el nuevo grupo de informes heredará el ajuste de marca de hora del original, incluido lo siguiente:

   * **No se permiten marcas de hora** (se admite s.visitorID)
   * **Marcas de hora obligatorias** (no se admite s.visitorID)
   * **Marcas de horas opcionales** (se admite el ajuste visitorID, pero no en visitas con marca de horas)

## Para cambiar los grupos de informes existentes a Marcas de hora opcionales {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Vaya a **Administradores &gt; Grupos de informes &gt; Editar configuración &gt; General &gt; Configuración de marcas de hora**.
1. Seleccione el cuadro **Convertir los grupos de informes seleccionados a marcas de hora opcional**.

   Esto cambiará el grupo de informes a Marcas de hora opcionales.

>[!NOTE]
>
>If a report suite was set to **Timestamps Optional**, to change this to any other setting, please contact Adobe Client Care.

