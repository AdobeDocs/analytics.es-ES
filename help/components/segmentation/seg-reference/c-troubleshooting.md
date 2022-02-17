---
description: Solucione problemas y cuestiones relacionados con segmentos.
title: Solución de problemas de segmentación
feature: Segmentation
exl-id: ca51110e-1ba7-4182-b5b2-baf9b0c017af
source-git-commit: 7a47d837eeae65f2e98123aca78029bfeb7ffe9d
workflow-type: tm+mt
source-wordcount: '227'
ht-degree: 100%

---

# Solución de problemas de segmentación

## Error: &quot;Elementos incompatibles en este segmento&quot; {#incompatible}

Este error se produce cuando intenta guardar un segmento en la carpeta del Almacén de datos donde el segmento contiene elementos no compatibles con el Data Warehouse. Para corregir este error, puede hacer una de estas dos acciones:

* Guardar el segmento en una carpeta distinta.
* Eliminar o cambiar las partes incompatibles del segmento.

## ¿Por qué no devuelve ningún dato mi segmento? {#no-data}

Motivos posibles:

* Anidación inversa: por ejemplo, anidar un contenedor de Visitante en un contenedor de Visita.
* El informe no admite la segmentación.
* No hay datos que coincidan con los criterios de segmentación.

## ¿Por qué no puedo ver el segmento que he creado en el Administrador de segmentos? {#invisible}

Motivos posibles:

* Algunas dimensiones están disponibles únicamente en el Almacén de datos y no en el Data Warehouse.
* El segmento no es compatible con Reports &amp; Analytics.
* El segmento únicamente se comprueba para un grupo de informes específico.
* Es posible que otro usuario haya eliminado un segmento compartido.
* Los segmentos no se han podido cargar debido a un problema de caché del navegador o del centro de datos.
* El segmento no se ha guardado.
* La dirección IP puede haber sido bloqueada en el terminal del usuario.

## ¿Por qué los datos de página mostrados tras aplicar un segmento parecen incorrectos? {#page-data}

Motivos posibles:

* Las reglas o los operadores son incorrectos para el resultado necesario.
* Aplicación incorrecta de contenedores al segmento.
* Las variables de tráfico utilizadas en el segmento no se han configurado correctamente o han caducado.
