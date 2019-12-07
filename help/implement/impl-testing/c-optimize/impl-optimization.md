---
description: La implementación de Analytics se organiza en tres pasos principales.
keywords: Analytics Implementation
subtopic: Troubleshooting
title: Resumen de optimización
topic: Developer and implementation
uuid: 8e8ecc5b-d4b1-4d13-8525-39e4924df247
translation-type: tm+mt
source-git-commit: 99ee24efaa517e8da700c67818c111c4aa90dc02

---


# Resumen de optimización

La implementación de Analytics se organiza en tres pasos principales.

1. Implica pegar un fragmento de código HTML en cada página (o plantilla de página) de un sitio web. El fragmento de código HTML es muy pequeño (400 a 1.000 bytes) y contiene variables JavaScript y otros identificadores que facilitan el proceso de recopilación de datos.
1. El fragmento de código llama al archivo de biblioteca JavaScript, que contiene funciones JavaScript específicas de Analytics utilizadas durante la recopilación de métricas. Si el código de Analytics se implementa correctamente, el tiempo necesario para que el explorador ejecute el archivo de biblioteca JavaScript suele ser ínfimo.

1. El archivo de biblioteca crea una solicitud de imagen a un servidor de recopilación de datos de Adobe. El servidor recopila los datos que se están enviando y devuelve una imagen transparente de 1x1 al explorador del visitante. Este tercer paso apenas incrementa el tiempo de descarga total de la página.

> [!NOTE] Los clientes pueden realizar otros pasos para minimizar la sobrecarga de Analytics.

