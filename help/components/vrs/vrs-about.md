---
description: Los grupos de informes virtuales segmentan los datos de Adobe Analytics de modo que pueda controlar el acceso a cada segmento.
title: Resumen de los grupos de informes virtuales
feature: VRS
exl-id: 45d18d14-d95a-42fe-b00a-cfce5f936e37
TQID: https://experienceleague.adobe.com/gEs8c9pIUGbbPx7DBAwFhSvT-C6W2vfosgMkrO-32ic
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: c153fd90-23e1-4614-81d3-3cc7571227f7
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
  - id: f73667dc-d296-4875-8975-ac3fdc3adc42
subfeature_v2:
  - id: ac8a38fa-dec3-4581-8f64-178fde9f64e8
  - id: b0a1f9d5-5795-42a3-a6d0-bd0e2748fd06
  - id: c069c44e-5426-4c1a-accc-8028662f2fde
  - id: e93b8c4c-c5f7-45f8-9abe-9b710f53f502
  - id: ef60b66e-5984-4336-ba72-6d978b1b6f87
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: ff16e07c7a2b75e9c6cc09e8255a7ea7e4c6f0c8
workflow-type: tm+mt
source-wordcount: 812
ht-degree: 36%

---

# Resumen de los grupos de informes virtuales

Los grupos de informes virtuales segmentan los datos de Adobe Analytics de modo que pueda controlar el acceso a cada segmento.

Muchos clientes tienen datos que fluyen a un grupo de informes globales, pero también datos que fluyen a grupos de informes más pequeños. Configuran una variable en varios grupos de informes y envían sus datos a más de un grupo de informes. Esto se denomina *etiquetado de grupos múltiples*, o *grupos de informes base/principal*.

Por ejemplo, es posible que todos los datos se recopilen en un grupo de informes, pero luego puede configurar grupos de informes secundarios para que otras personas de su empresa tengan acceso a parte de los datos, pero no a todos. Los datos pueden dividirse por región. Puede tener diferentes sitios web para diferentes países. Otros ejemplos pueden ser marcas específicas que pertenecen a una compañía más grande, pero que cada una tiene sus propios equipos de marketing.

Un *grupo de informes virtuales* le permite reproducir este concepto de ramificación, empleando segmentos en lugar de múltiples grupos de informes. Los datos se envían a un solo grupo de informes que luego se dividen en segmentos. En el ejemplo de varias marcas, puede establecer una propiedad para la marca a la que pertenece un elemento. Mediante segmentos, puede crear informes sobre los elementos asignados a cada propiedad. Cada uno de estos segmentos se convierte en su propia vista y crea, de hecho, un nuevo grupo de informes. Los datos no se envían específicamente a ese segmento, solo al grupo de informes globales, sino que funcionan en los informes como si se tratara de un grupo de informes diferente.

Un grupo de informes virtuales hereda la mayoría de los niveles de servicio del grupo de informes base, como la configuración de eVar, las reglas de procesamiento, las clasificaciones, etc. NO se heredan las siguientes opciones de configuración:

* ID del grupo de informes (RSID)
* Nombre del grupo de informes
* Grupos de permisos (los grupos de informes virtuales se pueden asignar a sus propios grupos de permisos)

## Ventajas de los grupos de informes virtuales {#section_3420422FE6DF46EAB151FD9442AAFDC4}

Los clientes pagan por llamadas secundarias al servidor, por lo que si se eliminan estas llamadas se pueden obtener ahorros significativos. Un grupo de informes virtuales también es completamente retroactivo. Si el grupo de informes globales ya contiene datos, estos se incluyen automáticamente en un nuevo grupo de informes virtuales. Un nuevo grupo de informes secundarios solo empezaría a recopilar datos una vez creado, por lo que no incluiría ningún dato histórico. Al implementar Analytics, solo es necesario enviar datos a un grupo de informes, en lugar de tener que crear implementaciones para el grupo de informes globales y cada grupo de informes secundarios.

Los grupos de informes virtuales ayudan a:

* Simplifique la implementación permitiéndole utilizar un único ID del grupo de informes (RSID) en todos los sitios o dominios. Tener todos los datos en un único grupo de informes habilita el análisis de clientes a medida que avanzamos hacia la siguiente generación de Adobe Analytics.
* Los usuarios empresariales de su organización siempre ven solo los segmentos de datos que les interesan.
* Mejore la seguridad permitiendo a los usuarios administradores controlar el acceso a los datos de forma más sencilla y granular después de la implementación.
* Métrica de usuarios
* Una vista de datos de un solo cliente (en el futuro)
* La capacidad de crear grupos de informes virtuales ilimitados para segmentar datos

## Limitaciones de los grupos de informes virtuales {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Los grupos de informes virtuales tienen las siguientes limitaciones :

* Cualquier limitación de los segmentos se aplica a los grupos de informes virtuales

  Un grupo de informes virtuales no es más que un segmento aplicado a un grupo de informes. Como cada grupo de informes cuenta con su propio Data Warehouse y sus fuentes de datos, el uso de varios grupos de informes presenta algunas ventajas que los segmentos no ofrecen.
* Informe en tiempo real
* La configuración y los nombres de variables no se pueden personalizar como en un grupo de informes completo

## Grupos de informes virtuales frente al etiquetado de grupos múltiples {#section_317E4D21CCD74BC38166D2F57D214F78}

| Compatibilidad | Grupo de informes virtuales | Etiquetado de grupos múltiples |
|--- |--- |--- |
| Ofrece informes en tiempo real o de &quot;datos actuales&quot; | No | Sí |
| Funciona en todas las herramientas de Analytics (Analysis Workspace, Report Builder, etc.) | Sí. **Nota:** Solo puede editarlos e identificarlos como grupos de informes virtuales en [!UICONTROL Analytics] > [!UICONTROL Componentes] > [!UICONTROL Grupos de informes virtuales]. Sin embargo, puede seleccionarlos en los menús desplegables del propio grupo de informes en las otras herramientas.<p>**Importante**: Los grupos de informes virtuales con procesamiento en tiempo de informe y personalización de variables no son compatibles actualmente con Adobe Report Builder. | Sí |
| Puede cargar datos en él (a través de clasificaciones, fuentes de datos, etc.) | No | Sí |
| Admite la creación de informes DL, marcadores, tableros, destinos, alertas, segmentos, métricas calculadas... | Sí | Sí |
| Se puede añadir individualmente a los grupos de permisos | Sí | Sí |
| Puede utilizar las funciones de administración para modificar la configuración individual de este grupo de informes (Administración > Grupos de informes) | No (la configuración se hereda del elemento principal) | Sí |

{style="table-layout:auto"}

## Combinación de grupos de informes virtuales y etiquetado de grupos múltiples {#section_026FA3FCD7314DD18220E73EC5702AFF}

En algunos casos, es conveniente utilizar tanto los grupos de informes virtuales como el etiquetado de grupos múltiples.

Por ejemplo, una retailer podría utilizar un grupo de informes para cada marca y grupos de informes virtuales para cada marca para desglosar los datos por región. Del mismo modo, una organización atlética puede utilizar un grupo de informes para cada equipo y, a continuación, grupos de informes virtuales para dividir los aficionados de la región del equipo entre los de fuera de la región.
