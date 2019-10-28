---
description: La implementación de Analytics se organiza en tres pasos principales.
keywords: Implementación de Analytics
seo-description: La implementación de Analytics se organiza en tres pasos principales.
seo-title: Resumen de optimización
solution: Analytics
subtopic: Resolución de problemas
title: Resumen de optimización
topic: Desarrollador e implementación
uuid: 8e8ecc5b-d4b1-4d13-8525-39e4924df247
translation-type: ht
source-git-commit: 6250335d05c8e7799802fce26192896a7a6598fe

---


# Resumen de optimización

La implementación de Analytics se organiza en tres pasos principales.

1. Implica pegar un fragmento de código HTML en cada página (o plantilla de página) de un sitio web. El fragmento de código HTML es muy pequeño (400 a 1.000 bytes) y contiene variables JavaScript y otros identificadores que facilitan el proceso de recopilación de datos.
1. El fragmento de código llama al archivo de biblioteca JavaScript, que contiene funciones JavaScript específicas de Analytics utilizadas durante la recopilación de métricas. Si el código de Analytics se implementa correctamente, el tiempo necesario para que el explorador ejecute el archivo de biblioteca JavaScript suele ser ínfimo.

1. El archivo de biblioteca crea una solicitud de imagen a un servidor de recopilación de datos de Adobe. El servidor recopila los datos que se están enviando y devuelve una imagen transparente de 1x1 al explorador del visitante. Este tercer paso apenas incrementa el tiempo de descarga total de la página.

>[!NOTE]
>
>Los clientes pueden realizar otros pasos para minimizar la sobrecarga de Analytics.

