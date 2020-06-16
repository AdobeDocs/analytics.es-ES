---
description: Preguntas más frecuentes acerca de características, funcionalidades y problemas relativos al reenvío del lado del servidor.
title: Preguntas frecuentes acerca del reenvío del lado del servidor
uuid: ecd0bc9b-ebf7-414e-88a2-ebba3fd75c92
translation-type: ht
source-git-commit: 16ba0b12e0f70112f4c10804d0a13c278388ecc2

---


# Preguntas frecuentes acerca del reenvío del lado del servidor

Preguntas más frecuentes acerca de características, funcionalidades y problemas relativos al reenvío del lado del servidor.

## Servidores de seguimiento {#section_28E5BECC2034484AB9726E513F2CCFB7}

| Pregunta | Respuesta |
|--- |--- |
| P: ¿Qué sucede si utilizo el antiguo reenvío de servidor basado en servidores de seguimiento? | El reenvío de servidor antiguo basado en servidores de seguimiento seguirá reenviando datos de Analytics a Audience Manager, pero si quiere enviar segmentos de Audience Manager a Analytics, necesitará el nuevo reenvío de servidor basado en grupos de informes. Además, no hay ningún problema en habilitar el reenvío del lado del servidor para un grupo de informes existiendo ya una configuración de servidor de seguimiento; cuando exista un conflicto, se utilizará la nueva configuración de reenvío del lado del servidor basada en grupos de informes. |
| P: ¿Debo migrar mi antiguo reenvío de servidor basado en servidor de seguimiento al nuevo, basado en grupos de informes? | Se seguirá admitiendo el reenvío de servidor basado en servidores de seguimiento en el futuro próximo, pero si quiere aprovechar la integración de Audience Manager con Analytics (uso compartido de segmentos en Analytics), tendrá que habilitar el nuevo reenvío de servidor basado en grupos de informes para todos los grupos de informes aplicables. Sin embargo, no existe ningún motivo urgente para deshabilitar el antiguo reenvío de servidor basado en servidores de seguimiento. |

## Etiquetado y realización de informes {#section_71391BA901AC47B9A2286281644FF281}

| Pregunta | Respuesta |
|--- |--- |
| P: ¿Qué pasa si en mi sitio tengo etiquetado multigrupo? ¿Duplicará el reenvío del lado del servidor las llamadas de servidor a Audience Manager? | No, las visitas se reenvían una única vez de Analytics a Audience Manager, con independencia del número de grupos de informes que haya en ellas. Si tiene en Audience Manager fuentes de datos correspondientes para cada grupo de informes de la visita, todas ellas se rellenarán apropiadamente a partir de esa única visita.  Tenga en cuenta, no obstante, que si utiliza la recopilación de datos de lado de clientes (DIL) y habilita el reenvío del lado del servidor sin instalar el módulo Gestión de público, estará duplicando las llamadas de servidor a Audience Manager, independientemente del número de grupos de informes que tenga en su visita de Analytics. |
| P: ¿Qué sucede si tengo grupos de informes etiquetados multigrupo asignados a distintas organizaciones de Experience Cloud? | Nunca debe enviar datos de una misma visita de Analytics a dos grupos de informes que pertenezcan a organizaciones de Experience Cloud diferentes, pero, si esto ocurre, únicamente se reenviará la visita a la organización de Experience Cloud que coincida con la configuración del Servicio de identidad en la página. |
| Q: ¿Qué sucede si tengo etiquetado multigrupo y solo uno de mis grupos de informes está asignado a mi organización de Experience Cloud? | En este caso, se reenvía la visita al servidor de recopilación de datos correspondiente a la organización de Experience Cloud del grupo de informes asignado, aunque, como el grupo de informes no asignado no tendrá asociada una fuente de datos en Audience Manager, no se registrará ningún dato para dicho grupo en Audience Manager. |
| P: ¿Qué sucede si tengo un grupo de informes asignado a varias organizaciones de Experience Cloud? | Analytics considerará que este grupo de informes no está asignado y no permitirá habilitar para él el reenvío de servidor. Póngase en contacto con el Servicio de atención al cliente para resolver este problema de asignación. |
| P: ¿Será más lento el método de reenvío de servidor basado en grupos de informes que el basado en servidores de seguimiento? | No, el tiempo de respuesta es el mismo. |
| P: ¿Qué sucede si tengo dos organizaciones de Experience Cloud (o instancias de AAM) y quiero compartir datos entre ambas? ¿Puedo utilizar el reenvío de servidor para enviar una sola visita de Analytics a varias organizaciones de Experience Cloud? | No. Si necesita compartir datos recopilados por una organización de Experience Cloud con otra, se recomienda enviar las audiencias aplicables de una instancia de Audience Manager a otra mediante el mercado de audiencias. |
| P: ¿Resultará el reenvío del lado del servidor en alguna facturación adicional en Audience Manager o Analytics? | En Analytics no se producirá ninguna facturación adicional. En Audience Manager, las visitas reenviadas se tratan como cualquier otra visita y se facturan.  Por eso es tan importante no tener habilitados al mismo tiempo DIL y el reenvío del lado del servidor, lo que podría provocar dobles facturaciones, además de la duplicación de datos. |

>[!MORELIKETHIS]
>
>* [Reenvío del lado del servidor](/help/admin/admin/c-server-side-forwarding/ssf.md)

