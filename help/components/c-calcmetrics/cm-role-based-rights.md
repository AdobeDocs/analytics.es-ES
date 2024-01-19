---
description: Los derechos de las métricas calculadas difieren entre los usuarios a nivel de administrador y los usuarios no administradores.
title: 'Métricas calculadas:  derechos basados en funciones'
feature: Calculated Metrics
exl-id: 018d9ef5-5a6f-4ebc-a241-c1291ba6b561
source-git-commit: 93099d36a65ca2bf16fbd6342f01bfecdc8c798e
workflow-type: tm+mt
source-wordcount: '237'
ht-degree: 81%

---

# Derechos de las métricas calculadas basados en funciones

Los derechos de las métricas calculadas difieren entre los usuarios a nivel de administrador y los usuarios no administradores.

|  | Crear | Compartir | Ver/Administrar | Aprobar | Aplicar |
|--- |--- |--- |--- |--- |--- |
| Usuarios de nivel de administrador | Los administradores pueden crear métricas calculadas y perfiles de producto en Admin Console para limitar los derechos de los usuarios en la creación de métricas calculadas. | Pueden compartir con toda la empresa, con grupos de usuarios y con usuarios individuales. | Report Builder: puede ver, editar, eliminar, etc. sus propias métricas calculadas y las que se han compartido con ellos. | Pueden aprobar métricas calculadas como canónicas. | Pueden aplicar cualquier métrica calculada en toda la organización. |
| Usuarios que no son administradores | De forma predeterminada, los usuarios pueden crear métricas calculadas. Sin embargo, los administradores pueden limitar estos derechos. | Pueden compartir únicamente con usuarios individuales. | Pueden ver, editar, eliminar, etc. solo sus propias métricas calculadas. Los usuarios no administradores deben tener acceso a todos los eventos del componente para poder ver una métrica compartida (los permisos de la Admin Console siguen en vigor).  Si un tablero o informe programado se comparte con un usuario no administrador y no se ha compartido la métrica con él, el informe se ejecutará con la métrica aplicada (siempre que tenga los permisos para ver los eventos). Sin embargo, no podrán ver la definición ni editar la métrica. | Solo pueden consumir métricas calculadas aprobadas; no pueden marcar como aprobado. | Pueden aplicar sus propias métricas calculadas y segmentos que se han compartido con ellos. |