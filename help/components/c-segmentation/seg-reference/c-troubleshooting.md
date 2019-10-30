---
description: 'null'
seo-description: 'null'
seo-title: Solución de problemas de segmentación
title: Solución de problemas de segmentación
uuid: 8476d617-4b44-4ff2-9b3a-02685f666afc
translation-type: tm+mt
source-git-commit: a2c38c2cf3a2c1451e2c60e003ebe1fa9bfd145d

---


# Solución de problemas de segmentación

## Error: "Elementos incompatibles en este segmento" {#section_B167EE10A0844E649DD7E14D0BAEDA17}

Este error se produce cuando intenta guardar un segmento en la carpeta del Almacén de datos donde el segmento contiene elementos no compatibles con el Almacén de datos. Para corregir este error, puede hacer una de estas dos acciones:

* Guardar el segmento en una carpeta distinta.
* Eliminar o cambiar las partes incompatibles del segmento.

## ¿Por qué no devuelve ningún dato mi segmento? {#section_999749CBBE984142AEA49A6E68E6730A}

Motivos posibles:

* Anidación inversa: por ejemplo, anidar un contenedor de Visitante en un contenedor de Visita.
* El informe no admite la segmentación.
* No hay datos que coincidan con los criterios de segmentación.

## ¿Por qué no puedo ver el segmento que he creado en el Administrador de segmentos? {#section_BE0A0930A2694A23BB32DA71696D52CE}

Motivos posibles:

* Algunas dimensiones están disponibles únicamente en el Almacén de datos y no en el Administrador de segmentos.
* El segmento no es compatible con Informes y análisis.
* El segmento únicamente se comprueba para un grupo de informes específico.
* Es posible que otro usuario haya eliminado un segmento compartido.
* Los segmentos no se han podido cargar debido a un problema de caché del navegador o del centro de datos.
* El segmento no se ha guardado.
* La dirección IP puede haber sido bloqueada en el terminal del usuario.

## ¿Por qué los datos de página mostrados tras aplicar un segmento parecen incorrectos? {#section_B226AF69FE06463A8BC5337FDA8D4949}

Motivos posibles:

* Las reglas o los operadores son incorrectos para el resultado necesario.
* Aplicación incorrecta de contenedores al segmento.
* Las variables de tráfico utilizadas en el segmento no se han configurado correctamente o han caducado.

