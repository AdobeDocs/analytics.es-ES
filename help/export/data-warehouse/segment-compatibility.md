---
title: Compatibilidad del segmento con el Almacén de datos
description: Descubra qué definiciones de segmento son válidas para usar en Data Warehouse.
feature: Data Warehouse
exl-id: 66b86226-ef4c-4a1a-abe1-3c3accf419e5
TQID: https://experienceleague.adobe.com/7CrArNYD-8ZXVpfO86d1l42ySkTuv8V04PWJFeNWx3s
product_v2: id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2: id: b069d60e-95f3-44d6-95a8-ddc862a4bc38id: b3f03848-ae12-48b2-8aab-cad18567eb32id: c153fd90-23e1-4614-81d3-3cc7571227f7
subfeature_v2: id: a544b409-2610-410d-a842-474ac1d0d54eid: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2: id: b69b2659-1057-424e-8fc5-ed9e016dc554id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2: id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
source-git-commit: d4db20e3498d54162806b3fdef0b34f45c93a6ff
workflow-type: tm+mt
source-wordcount: 456
ht-degree: 9%

---

# Compatibilidad del segmento con el Almacén de datos

No todos los segmentos creados en el generador de segmentos se pueden usar en Data Warehouse. Utilice esta página para conocer qué definiciones de segmentos son compatibles con Data Warehouse, de modo que esté disponible para seleccionarlas al [crear una solicitud de Data Warehouse](/help/export/data-warehouse/create-request/t-dw-create-request.md).

Un segmento solo es compatible con Data Warehouse cuando **ambas** de las siguientes opciones son verdaderas:

* **Componentes admitidos**: el segmento solo usa dimensiones y métricas compatibles con Data Warehouse.
* **Estructura admitida**: La estructura del segmento sigue las reglas que Data Warehouse aplica.

Si no se cumple alguna de las condiciones, el segmento no aparece como una opción al generar una solicitud de Data Warehouse y se muestra un error si selecciona un grupo de informes virtuales que contiene un segmento incompatible.

## Componentes compatibles

Dado que un segmento se evalúa con los mismos datos que la solicitud a la que se aplica, **cualquier componente que no sea compatible con una solicitud de Data Warehouse tampoco será compatible con un segmento.** Para obtener la lista completa de dimensiones y métricas que Data Warehouse no admite, consulte [Compatibilidad con componentes en Data Warehouse](component-support.md).

Además de las dimensiones y métricas enumeradas en [Compatibilidad con componentes](component-support.md), las siguientes dimensiones están disponibles en una *solicitud* de Data Warehouse, pero **no se pueden usar dentro de una definición de segmento**:

* [[!UICONTROL Día del mes]](/help/components/dimensions/day-of-month.md)
* [[!UICONTROL Día de la semana]](/help/components/dimensions/day-of-week.md)
* [[!UICONTROL Día del año]](/help/components/dimensions/day-of-year.md)
* [[!UICONTROL Hora del día]](/help/components/dimensions/hour-of-day.md)
* [[!UICONTROL Canales de marketing]](/help/components/dimensions/marketing-channel.md) (use [[!UICONTROL Canal de último contacto]](/help/components/dimensions/last-touch-channel.md) en su lugar)
* [[!UICONTROL Mes del año]](/help/components/dimensions/month-of-year.md)
* [[!UICONTROL Páginas no encontradas]](/help/components/dimensions/pages-not-found.md) (use [[!UICONTROL Error de tipo de página]](/help/components/dimensions/pages-not-found.md) en su lugar)
* [[!UICONTROL Trimestre del año]](/help/components/dimensions/quarter-of-year.md)
* [[!UICONTROL Día de la semana/Fin de semana]](/help/components/dimensions/weekday-weekend.md)

## Estructura admitida

Incluso cuando un segmento solo utiliza componentes compatibles, su estructura debe seguir las reglas que aplica Data Warehouse. Las estructuras de segmentos son totalmente compatibles, parcialmente compatibles o no compatibles:

**Compatible**:

* **Apilamiento de segmentos**: se pueden aplicar varios segmentos a una sola solicitud de Data Warehouse.
* **Contenedores anidados**: Compatible, siempre que el ámbito disminuya en cada nivel (visitante → visita → visita). No se admiten contenedores con un ámbito mayor.

**Compatible parcialmente**:

* **Excluir contenedores**: Compatible solo en el nivel superior. Data Warehouse solo admite segmentos expresables como `A AND NOT B`, es decir, **incluir esta característica** y **excluir esta característica**. No se admiten contenedores de exclusión anidados en otros contenedores.
* **Lógica AND/OR**: Compatible con limitaciones. Cuando se usa un contenedor `exclusion` o `without` en combinación con la lógica AND/OR, solo se admiten los segmentos que se pueden reescribir como `A AND NOT B`.

**No compatible**:

* **Segmentos secuenciales**: no se admiten los segmentos que usan el operador THEN para definir secuencias de navegación de visitantes ordenadas.
* **: Operadores &quot;Es igual a cualquiera de&quot; y &quot;No es igual a ninguno de&quot;**: Estos operadores no son compatibles con los segmentos de Data Warehouse.

## Segmentos utilizados como dimensiones

Cuando se usa un segmento como dimensión en un informe de Data Warehouse, el informe devuelve una columna que contiene `"0"` o `"1"`:

* **`"0"`**: El elemento de dimensión no cumplía los criterios del segmento.
* **`"1"`**: El elemento de dimensión cumplía los criterios del segmento.
