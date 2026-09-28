---
title: Código postal
description: Código postal del visitante.
feature: Dimensions
exl-id: 597619f8-a581-4491-beb2-c14b1f7b7bec
TQID: 'https://experienceleague.adobe.com/XHrUXKHrXiH0wsUr0klmPmA-DEq5T5yu18KLNT7oYeo'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
    internal-label: Analytics
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
    internal-label: Reports
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
    internal-label: Metrics
  - id: e9dbdbc5-3e52-40f0-a7bc-e18542967b7a
    internal-label: Implementations
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
    internal-label: Data configuration and collection
subfeature_v2:
  - id: d2311670-43bd-4c2e-bc98-1da2aaba9cef
    internal-label: Appmeasurement implementation
  - id: f836f655-eebe-4b76-82bc-697955ec1ce3
    internal-label: Calculated Metrics
  - id: b22bc0f7-b089-4966-95a1-31e7b3b69b79
    internal-label: Dimensions
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
    internal-label: User
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
    internal-label: Admin
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
    internal-label: Implementation
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
    internal-label: Measurement
source-git-commit: 9a50beeb0aa51cf9f4baf212566947c14029ce8e
workflow-type: tm+mt
source-wordcount: '330'
ht-degree: 61%
---
# Código postal

El &quot;Código postal&quot; [dimension](overview.md) indica el código postal del visitante. Puede utilizar esta dimensión para comprender mejor el éxito de la publicidad local o para ver en qué parte del mundo su sitio funciona mejor.

## Rellene esta dimensión con datos

Esta dimensión es única, ya que contiene varias formas de rellenarla con datos. Puede utilizar uno o una combinación de ambos:

* Configure el código postal directamente usando la variable [`zip`](/help/implement/vars/page-vars/zip.md).
* Configúrela para extraer de los datos de geolocalización. Cuando se utiliza geo zip, no se establece ninguna variable. Para implementaciones de AppMeasurement, esta dimensión funciona de forma predeterminada. Para implementaciones de Web SDK, habilita [!UICONTROL Búsqueda geográfica] al [configurar una secuencia de datos](https://experienceleague.adobe.com/docs/experience-platform/datastreams/configure.html?lang=es).

La opción [!UICONTROL Código postal] de [Configuración general de cuenta](/help/admin/tools/manage-rs/edit-settings/general/general-acct-settings-admin.md) controla cómo desea rellenar esta dimensión. La tabla de referencia siguiente se aplica cuando establece la variable `zip` directamente.

| Propiedad | Valor |
| --- | --- |
| **variable de AppMeasurement** | [`zip`](/help/implement/vars/page-vars/zip.md) |
| **Campo Web SDK / XDM** | [`placeContext.geo.postalCode`](https://experienceleague.adobe.com/en/docs/experience-platform/xdm/data-types/geo) |
| **Parámetro de consulta** | [`zip`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **etiqueta XML** | [`<zip>`](https://developer.adobe.com/analytics-collection-apis/methods/data-insertion/variable-reference#variables) |
| **Límite de bytes** | 50 bytes |
| **Persistencia** | Hit |

## Elementos de dimensión

Los elementos de dimensión incluyen el código postal del visitante.

## Países con código postal compatibles

* Islas Aland
* Albania
* Argelia
* Argentina
* Armenia
* Austria
* Australia
* Bangladés
* Barbados
* Bélgica
* Brasil
* Bulgaria
* Canadá
* Chile
* China
* Colombia
* Costa Rica
* Croacia
* República Checa
* Dinamarca
* Ecuador
* Egipto
* Estonia
* Finlandia
* Francia
* Georgia
* Alemania
* Gibraltar
* Grecia
* Granada
* Guatemala
* RAE de Hong Kong de China
* Hungría
* India
* Indonesia
* Irlanda
* Israel
* Italia
* Japón
* Jordania
* Kazajistán
* Kirguistán
* Letonia
* Líbano
* Lituania
* Luxemburgo
* Malasia
* Malta
* Mauricio
* México
* Marruecos
* Mozambique
* Nepal
* Países Bajos
* Nueva Zelanda
* Noruega
* Pakistán
* Panamá
* Perú
* Filipinas
* Polonia
* Portugal
* Puerto Rico
* Catar
* Rumanía
* Federación Rusa
* Arabia Saudí
* Senegal
* Serbia
* Singapur
* Eslovenia
* Sudáfrica
* Corea del Sur
* España
* Sri Lanka
* Suecia
* Suiza
* Región de Taiwán
* Tailandia
* Túnez
* Turquía
* Ucrania
* Emiratos Árabes Unidos
* Reino Unido
* Estados Unidos
* Uruguay
* Uzbekistán
* Venezuela
* Vietnam
