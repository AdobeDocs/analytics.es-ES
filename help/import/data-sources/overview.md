---
title: Resumen de fuentes de datos
description: Importe datos en Adobe Analytics utilizando archivos externos.
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
role: Admin
TQID: 'https://experienceleague.adobe.com/AOl1PUYf4TL0FrYB8eHL-JLiWvz6ixJYKUPpIZEFqj8'
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
feature_v2:
  - id: b069d60e-95f3-44d6-95a8-ddc862a4bc38
  - id: b3f03848-ae12-48b2-8aab-cad18567eb32
  - id: fd307ce7-56f5-4ee3-af68-a7833ff6e85e
  - id: b8734a57-d5fb-44a8-8ee1-65225cecaeae
subfeature_v2:
  - id: f46a60da-b0b2-4ca3-bd91-271173f4123d
role_v2:
  - id: c66ffd68-0f65-42bb-aa23-b4020f12e0bd
topic_v2:
  - id: aa2f3246-cb95-4b30-8899-fdf7d73550cc
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 38cd05960c27b0bec0a713cb833907f4a658013e
workflow-type: tm+mt
source-wordcount: 327
ht-degree: 4%

---

# Resumen de fuentes de datos

Las fuentes de datos de Adobe Analytics le permiten importar datos adicionales en línea o sin conexión para la creación de informes. Son útiles para comprender las facetas de su negocio fuera del sitio web y cómo interactúan con el sitio. El flujo de trabajo general para utilizar fuentes de datos consta de los siguientes pasos:

1. Su organización recopila datos de otras fuentes. Algunos ejemplos son los datos preclic, los datos del centro de llamadas o información sobre transacciones que se produjeron fuera del sitio.
1. Los datos tienen un formato que Adobe Analytics comprende con un archivo de texto delimitado por tabuladores.
1. El archivo de texto se carga en un sitio FTP que proporciona Adobe, junto con el archivo `.fin` correspondiente.
1. Adobe ingiere el archivo de texto y muestra esos datos junto con las dimensiones y métricas recopiladas en el sitio.

Existen dos tipos generales de fuentes de datos que ofrece Adobe. Todas las plantillas de fuentes de datos se basan en uno de estos dos tipos:

* **Origen de datos de resumen**: proporciona una manera sencilla de importar datos de alto nivel en Adobe Analytics. La marca de tiempo, el valor de la variable y las métricas asociadas se especifican. Estas métricas de cada elemento de dimensión se incrementan en consecuencia. Resulta útil si desea ver datos sin conexión y en línea uno al lado del otro. Sin embargo, no vincula los datos en línea y sin conexión.
* **Origen de datos del ID de transacción**: si una visita enviada por AppMeasurement y una fila de orígenes de datos contienen ID de transacción coincidentes, los valores de dimensión y métrica del origen de datos se anexan a esa visita.

**Las fuentes de datos de procesamiento completo** ya no se ofrecen como tipo de fuente de datos a partir del 25 de marzo de 2021. Consulte [Anuncio de fin de vida útil](full-processing-eol.md) para obtener más información.

Adobe también ofrece la [API de fuentes de datos](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que le permite crear fuentes de datos y cargar datos sin usar la interfaz de usuario del producto ni una ubicación FTP.

## Pasos siguientes

[Introducción a las fuentes de datos](getting-started.md): Cargue una fuente de datos sencilla en un grupo de informes de desarrollo.
