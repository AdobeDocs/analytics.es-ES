---
title: Fuentes de datos de ID de transacción
description: Obtenga información sobre el flujo de trabajo general de uso de fuentes de datos de ID de transacción.
translation-type: tm+mt
source-git-commit: a5c3d9b2cd02dc7e89abb469e2e0e44985a17638

---


# Fuentes de datos de ID de transacción

Las fuentes de datos de ID de transacción le permiten no sólo ver los datos en línea y sin conexión en paralelo, sino también enlazar los datos. Requiere el uso de la [`transactionID`](/help/implement/vars/page-vars/transactionid.md) variable en la implementación de Analytics.

Cuando envía una visita en línea que contiene un `transactionID` valor, Adobe toma una &quot;instantánea&quot; de todas las variables configuradas o persistentes en ese momento. Si se encuentra un ID de transacción coincidente cargado a través de fuentes de datos, los datos sin conexión y en línea se vinculan. No importa qué fuente de datos se vea primero.

## Flujo de trabajo general de las fuentes de datos de ID de transacción

Utilice el flujo de trabajo genérico siguiente para empezar a utilizar fuentes de datos de ID de transacción:

1. Cree una fuente de datos (categoría &#39;Genérico&#39; y tipo &#39;Fuente de datos genérica (ID de transacción)&#39;).
1. Siga el asistente para la configuración de fuentes de datos para obtener una ubicación de FTP para cargar datos y descargar un archivo de plantilla de fuentes de datos.
1. Actualice la implementación para incluir la `transactionID` variable.
1. Cargue un archivo de fuentes de datos en el sitio FTP con un `.fin` archivo.
