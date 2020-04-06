---
description: Combine tanto los datos con marcas de hora como los datos sin marcas de hora en un grupo de informes único.
title: Marcas de hora opcionales
topic: Admin tools
uuid: 0fa63658-1cc2-4adc-8d51-a0662d0aa941
translation-type: tm+mt
source-git-commit: dabaf6247695bc4f3d9bfe668f3ccfca12a52269

---


# Marcas de hora opcionales

Combine tanto los datos con marcas de hora como los datos sin marcas de hora en un grupo de informes único.

Marcas de hora opcionales permite:

* Mezcle datos con y sin marca de hora en el mismo grupo de informes globales.
* Envíe datos con marca de hora desde una aplicación móvil a un grupo de informes globales.
* Actualice las aplicaciones para utilizar el seguimiento sin conexión sin tener que crear un nuevo grupo de informes.

>[!IMPORTANT] Si utiliza Marcas de hora opcionales, no configure [s.visitorID](/help/implement/vars/config-vars/visitorid.md) en datos que ya tengan una marca de hora. Esto puede generar datos confusos y afectar de forma negativa a los cálculos de hora (como por ejemplo los valores de tiempo empleado), atribución (persistencia de eVar), número de visitas/recuentos de visitas y informes de rutas.

>[!NOTE] Los datos de sesión con marca de tiempo habilitada se conservan por un período máximo de 92 días. Esto significa que una visita/sesión se “mantendrá abierta” durante 92 días, mientras que cualquier visita individual adicional (que no sea 30 minutos después de la visita individual anterior) se puede incluir en la misma visita/sesión. Cualquier visita “antigua” que se reciba de manera desordenada producirá resultados “desconocidos”, ya que una serie de factores (segmentación, asignación, caducidad, etc.) influyen en si estas visitas se incluirán o no en los informes.

## Nuevos grupos de informes {#section_095A7CFBD280494593B9BEC1592B73A6}

* Si se crea a partir de una plantilla, un nuevo grupo de informes toma como valor predeterminado Marcas de hora opcionales.

   (Puede crear un nuevo grupo de informes a partir de una plantilla en **Administración > Grupos de informes > Crear nuevo > Grupo** de informes).
* Si se copia desde un grupo de informes existente, el nuevo grupo de informes hereda la configuración de marca de tiempo del original, incluyendo:

   * **Marcas de hora no permitidas** (se admite s.visitorID)
   * **Marcas de hora requeridas** (no se admite la configuración de s.visitorID)
   * **Marcas de hora opcionales** (se admite s.visitorID pero no en visitas con marca de hora)

## Para cambiar los grupos de informes existentes a Marcas de hora opcionales {#section_40BCD3B4639241DEA716F7640ED33E72}

1. Vaya a **Administración > Grupos de informes > Editar configuración > General > Configuración** de marca de hora.
1. Seleccione el cuadro **Convertir los grupos de informes seleccionados en Marcas de hora opcionales** .

   Esto cambiará el grupo de informes a Marcas de hora opcionales.

>[!NOTE] Si un grupo de informes está establecido en **Marcas de hora opcionales**, póngase en contacto con el servicio de atención al cliente de Adobe para cambiar esta o cualquier otra opción de configuración.

