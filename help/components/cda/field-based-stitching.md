---
title: Vinculación basada en el campo
description: Comprenda los requisitos previos y las limitaciones de la vinculación de datos mediante la vinculación basada en campos.
translation-type: tm+mt
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: tm+mt
source-wordcount: '226'
ht-degree: 23%

---


# Vinculación basada en el campo

Analytics entre dispositivos proporciona dos métodos distintos para unir datos. Este método depende de una variable de Analytics, como una [propiedad](/help/implement/vars/page-vars/prop.md) o un [eVar](/help/implement/vars/page-vars/evar.md), para contener un identificador de persona. Utiliza esa variable como base para vincular dispositivos.

## Requisitos previos específicos de la vinculación basada en campos

Si tiene intención de implementar Análisis entre dispositivos mediante la vinculación basada en campos, es necesario lo siguiente. Trabaje con equipos de su organización y con el administrador de cuentas de Adobe para asegurarse de que cumple todos los requisitos siguientes.

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda habilitar el análisis entre dispositivos o que se obtengan resultados deficientes al vincular datos.

* Todos los requisitos previos enumerados en la página [de](overview.md)información general.
* La implementación debe establecer una propiedad o un eVar que identifique de forma exclusiva a un individuo siempre que sea posible, como cuando un usuario inicia sesión o abre un correo electrónico. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan. Comuníquese con el administrador de cuentas la variable de identificación que desee cuando se aprovisione para la vinculación basada en campo.

## Limitaciones específicas de la vinculación basada en campos

* La vinculación basada en campos funciona mejor en los grupos de informes que tienen una alta tasa de identificación del usuario. Si el grupo de informes tiene una baja tasa de identificación o inicio de sesión, considere la posibilidad de utilizar el gráfico [de](device-graph.md)cooperación.

## Pasos siguientes

Once your organization meets all requirements met and understands the limitations, you can start [Setting up Cross-Device Analytics](setup.md).