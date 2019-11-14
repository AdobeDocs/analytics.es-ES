---
description: Captura la configuración de idioma del explorador del visitante y permite averiguar los ingresos y los visitantes únicos relacionados esta. Si se conoce el efecto de los idiomas preferidos en las métricas de éxito de un sitio, puede decidirse cómo presentar dicho sitio en otros idiomas. Por ejemplo, si se detecta que un gran número de clientes germano parlantes genera actividad en el carro de compras de un sitio, puede traducirse al alemán e implementar una campaña de marketing para conducir el tráfico a la versión alemana del sitio.
solution: Analytics
title: Idioma
topic: Reports
uuid: 04f1fc86-2738-4063-8091-772ddc59f9cf
translation-type: tm+mt
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Idioma

Captura la configuración de idioma del explorador del visitante y permite averiguar los ingresos y los visitantes únicos relacionados esta. Si se conoce el efecto de los idiomas preferidos en las métricas de éxito de un sitio, puede decidirse cómo presentar dicho sitio en otros idiomas. Por ejemplo, si se detecta que un gran número de clientes germano parlantes genera actividad en el carro de compras de un sitio, puede traducirse al alemán e implementar una campaña de marketing para conducir el tráfico a la versión alemana del sitio.

**[!UICONTROL Perfil]** del visitante &gt; **[!UICONTROL Idiomas]**

Rellenamos este informe según la parte de idioma de aceptación de la solicitud de encabezado http. El encabezado HTTP de aceptación de idioma se configura como parte de la configuración de preferencias de idioma de cada explorador:

[https://www.w3.org/International/questions/qa-lang-priorities.en.php](https://www.w3.org/International/questions/qa-lang-priorities.en.php)

Si no se especifica ningún idioma en el explorador, o si este devuelve un ID de idioma de 0, en el gráfico del informe aparecerá "No especificado". La compatibilidad del explorador de esta configuración puede afectar al número de retornos que se identifican con "No especificado".

Algunos elementos de línea del informe incluyen regiones. Estas son subetiquetas de región.

> [!NOTE] No se admite la granularidad horaria.

