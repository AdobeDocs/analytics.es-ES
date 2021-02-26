---
description: Los grupos de informes virtuales segmentan los datos de Adobe Analytics de modo que pueda controlar el acceso a cada segmento.
title: Resumen de los grupos de informes virtuales
uuid: 51c63c56-dd58-4c23-a997-ea6942480d22
translation-type: tm+mt
source-git-commit: d0fe97b9368cbc4c9e79f9e56adf9786b58dce1a
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 98%

---


# Resumen de los grupos de informes virtuales

Los grupos de informes virtuales segmentan los datos de Adobe Analytics de modo que pueda controlar el acceso a cada segmento.

Muchos clientes mantienen un flujo de datos hacia un grupo de informes global, pero también hacia grupos de informes menores. Establecen una variable en varios grupos de informes y envían sus datos a más de uno de estos grupos. Esto se denomina *etiquetado multigrupo* o *grupos de informes base/superior*.

Por ejemplo, todos los datos podrían recopilarse en un grupo de informes, pero luego puede establecer grupos de informes secundarios para que los empleados de la empresa tengan acceso a parte de estos datos, pero no a todos. Los datos podrían dividirse por regiones. Podrían tenerse distintos sitios web para distintos países. Otro ejemplo puede ser un grupo de marcas específicas que pertenecen a una misma empresa superior, aunque cada una con sus propios equipos de marketing.

Un *grupo de informes virtuales* (VRS) le permite reproducir este concepto de ramificación, empleando segmentos en lugar de múltiples grupos de informes. Los datos se envían a un grupo de informes y luego se dividen en segmentos. Siguiendo el ejemplo de las distintas marcas, podría establecerse un prop para la marca a la que pertenece un artículo. Mediante segmentos, se podría realizar un informe con los artículos asignados a cada prop. Cada uno de estos segmentos se convierte en su propia visualización, lo que crea un nuevo grupo de informes. No se envían datos específicamente a los segmentos, sino al grupo de informes global, pero en los informes funciona como si fuera un grupo de informes diferente.

Un grupo de informes virtuales hereda la mayoría de los niveles de servicio del grupo de informes base, como la configuración de eVar, las reglas de procesamiento, las clasificaciones, etc. NO se heredan las siguientes opciones de configuración:

* ID de grupo de informes (RSID)
* Nombre del grupo de informes
* Grupos de permisos (los grupos de informes virtuales se pueden asignar a sus propios grupos de permisos)

## Ventajas de los grupos de informes virtuales {#section_3420422FE6DF46EAB151FD9442AAFDC4}

Los clientes pagan las llamadas del servidor secundario, así que eliminarlas puede conllevar un ahorro significativo. Un grupo de informes virtuales también es completamente retroactivo. Si el grupo de informes global ya contiene datos, los datos relevantes se incluyen automáticamente en un nuevo grupo de informes virtuales. Un nuevo grupo de informes secundario solo comenzaría a recopilar datos tras su creación, por lo que no incluiría ningún dato histórico. Cuando se implementa Analytics, solo es necesario enviar datos a un grupo de informes, no hace falta crear implementaciones para el grupo de informes global y para cada grupo de informes secundario.

Los grupos de informes virtuales ayudan a:

* Simplificar la implementación permitiéndole utilizar un solo ID de grupo de informes (RSID) en todos los sitios o dominios. Tener todos los datos en un único grupo de informes permite el análisis de clientes conforme se avanza a la siguiente generación de Adobe Analytics.
* Los usuarios empresariales de su organización ven solo los segmentos de datos que les son relevantes.
* Mejorar la seguridad permitiendo a los usuarios administradores controlar el acceso a los datos más fácilmente y con más granularidad después de la implementación.
* Proporcionar la capacidad de participar en la cooperación entre dispositivos
* Métrica Personas
* Una visualización de datos de un solo cliente (en el futuro)
* La capacidad para crear grupos de informes virtuales ilimitados con los que segmentar datos

## Limitaciones de los grupos de informes virtuales  {#section_F22A6DEBDC9848429E446F4CC2C4EEDE}

Los grupos de informes virtuales tienen las siguientes limitaciones :

* Cualquier limitación de los segmentos se aplica a los grupos de informes virtuales

   Un grupo de informes virtuales no es más que un segmento aplicado a un grupo de informes. Como cada grupo de informes cuenta con su propio Data Warehouse y sus fuentes de datos, el uso de varios grupos de informes presenta algunas ventajas que los segmentos no ofrecen.
* Informe en tiempo real
* Los ajustes y los nombres de variables no se pueden personalizar como en un grupo de informes completo

## Grupos de informes virtuales o etiquetado multigrupo  {#section_317E4D21CCD74BC38166D2F57D214F78}

| Función | Grupo de informes virtuales | Etiquetado multigrupo |
|--- |--- |--- |
| Ofrece informe en tiempo real o de datos actuales | No | Sí |
| Funciona en todas las herramientas de Analytics (Analysis Workspace, Report Builder, etc.) | Sí. **Nota:** Solo puede editar e identificar los grupos de informes virtuales en Reports &amp; Analytics. Sin embargo, puede seleccionarlos en los menús desplegables del propio grupo de informes en las otras herramientas. | Sí |
| Puede cargar datos en él (a través de clasificaciones, fuente de datos, etc.) | No | Sí |
| Admite la creación de informes DL, marcadores, tableros, objetivos, alertas, segmentos, métricas calculadas... | Sí | Sí |
| Se puede añadir individualmente a los grupos de permisos | Sí | Sí |
| Se pueden utilizar funciones de administrador para modificar opciones de configuración individuales en este grupo de informes (Administración > Grupos de informes) | No (la configuración se hereda de un grupo superior) | Sí |

## Combinación de grupos de informes virtuales y etiquetado multigrupo {#section_026FA3FCD7314DD18220E73EC5702AFF}

En algunos casos es conveniente utilizar tanto los grupos de informes virtuales como el etiquetado multigrupo.

Por ejemplo, una tienda minorista podría utilizar un grupo de informes para cada marca y, luego, grupos de informes virtuales para cada marca con el fin de dividir los datos por región. Igualmente, una organización deportiva podría utilizar un grupo de informes para cada equipo y, luego, grupos de informes virtuales para diferenciar entre los aficionados residentes en la región del equipo y todos los demás.
