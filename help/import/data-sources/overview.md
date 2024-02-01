---
title: Resumen de fuentes de datos
description: Importe datos en Adobe Analytics utilizando archivos externos.
exl-id: 5ec8bc51-dfd2-497c-aebc-a32d87efc97e
feature: Data Sources
role: Admin
source-git-commit: 27bcbd638848650c842ad8d8aaa7ab59e27e900e
workflow-type: tm+mt
source-wordcount: '314'
ht-degree: 0%

---

# Resumen de fuentes de datos

Las fuentes de datos de Adobe Analytics le permiten importar datos adicionales en línea o sin conexión para crear informes. Son útiles para comprender las facetas de su negocio fuera del sitio web y cómo interactúan con el sitio. El flujo de trabajo general para utilizar fuentes de datos consta de los siguientes pasos:

1. Su organización recopila datos de otras fuentes. Algunos ejemplos son los datos preclic, los datos del centro de llamadas o información sobre transacciones que se produjeron fuera del sitio.
1. Los datos tienen un formato que Adobe Analytics comprende con un archivo de texto delimitado por tabuladores.
1. El archivo de texto se carga en un sitio FTP que proporciona el Adobe, junto con un `.fin` archivo.
1. El Adobe de ingesta el archivo de texto y muestra esos datos junto con las dimensiones y métricas recopiladas en el sitio.

Existen dos tipos generales de fuentes de datos que ofrece el Adobe. Todas las plantillas de fuentes de datos se basan en uno de estos dos tipos:

* **Fuente de datos de resumen**: proporciona una forma sencilla de importar datos de alto nivel en Adobe Analytics. La marca de tiempo, el valor de la variable y las métricas asociadas se especifican. Estas métricas de cada elemento de dimensión se incrementan en consecuencia. Resulta útil si desea ver datos sin conexión y en línea uno al lado del otro. Sin embargo, no vincula los datos en línea y sin conexión.
* **Fuente de datos de ID de transacción**: Si una visita enviada por el AppMeasurement y una fila de fuentes de datos contiene ID de transacción coincidentes, los valores de dimensión y métrica de la fuente de datos se anexan a esa visita.

**Fuentes de datos de procesamiento completo** ya no se ofrecen como tipo de fuente de datos a partir del 25 de marzo de 2021. Consulte la [Anuncio de fin de vida útil](full-processing-eol.md) para obtener más información.

El Adobe también ofrece [API de fuentes de datos](https://developer.adobe.com/analytics-apis/docs/1.4/guides/data-sources/), que permite crear fuentes de datos y cargar datos sin utilizar la interfaz de usuario del producto ni una ubicación FTP.

## Pasos siguientes

[Introducción a las fuentes de datos](getting-started.md): cargue una fuente de datos sencilla en un grupo de informes de desarrollo.
