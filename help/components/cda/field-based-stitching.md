---
title: Vinculación basada en el campo
description: Comprenda los requisitos previos y las limitaciones de la vinculación de datos mediante la vinculación basada en el campo.
translation-type: ht
source-git-commit: 763c1b7405c1a1b3d6dbd685ce796911dd4ce78b
workflow-type: ht
source-wordcount: '226'
ht-degree: 100%

---


# Vinculación basada en el campo

El análisis entre dispositivos proporciona dos métodos distintos para vincular datos. Este método depende de una variable de Analytics, como una [propiedad](/help/implement/vars/page-vars/prop.md) o un [eVar](/help/implement/vars/page-vars/evar.md), para contener un identificador de persona. Utiliza esa variable como base para vincular dispositivos.

## Requisitos previos específicos de la vinculación basada en el campo

Si tiene intención de implementar el análisis entre dispositivos mediante la vinculación basada en el campo, es necesario lo siguiente. Trabaje con equipos de su organización y con el administrador de cuentas de Adobe para asegurarse de que cumple todos los requisitos siguientes.

>[!IMPORTANT]
>
>Si no se cumplen todos los requisitos previos, es posible que no se pueda habilitar el análisis entre dispositivos o que se obtengan resultados deficientes al vincular datos.

* Todos los requisitos previos enumerados en la [página de información general](overview.md).
* La implementación debe establecer una propiedad o un eVar que identifique de forma exclusiva a un individuo siempre que sea posible, como cuando un usuario inicia sesión o abre un correo electrónico. Este requisito se aplica a todas las plataformas, incluidas las aplicaciones móviles, si se utilizan. Comunique la variable de identificación que desee al administrador de cuentas cuando se aprovisione para la vinculación basada en el campo.

## Limitaciones específicas de la vinculación basada en el campo

* La vinculación basada en el campo funciona mejor en los grupos de informes que tienen una alta tasa de identificación del usuario. Si el grupo de informes tiene una tasa baja de identificación o inicio de sesión, considere la posibilidad de utilizar el [gráfico de cooperación](device-graph.md).

## Pasos siguientes

Una vez que su organización haya cumplido todos los requisitos y haya comprendido las limitaciones, puede empezar a [configurar análisis cruzados de dispositivos](setup.md).