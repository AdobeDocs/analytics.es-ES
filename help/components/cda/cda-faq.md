---
title: Preguntas más frecuentes sobre análisis entre dispositivos
description: Preguntas más frecuentes sobre análisis entre dispositivos
translation-type: tm+mt
source-git-commit: c104fbda3dc4a6be6b596c60c6e1973407d94f80

---


# Preguntas frecuentes

**¿Cómo puedo utilizar CDA para ver cómo las personas se mueven de un tipo de dispositivo a otro?**

Puede utilizar una visualización de flujo con la dimensión Tipo de dispositivo móvil.

1. Inicie sesión en Adobe Analytics y cree un nuevo proyecto de espacio de trabajo vacío.
2. Haga clic en la ficha Visualizaciones de la izquierda y arrastre una visualización de Flujo al lienzo de la derecha.
3. Haga clic en la ficha Componentes de la izquierda y arrastre la dimensión «Tipo de dispositivo móvil» a la ubicación del centro («Dimensión o Elemento»).
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos con páginas anteriores o anteriores. Utilice el menú de clic derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

**¿Puedo ver cómo se mueven las personas entre distintas experiencias de usuario (p. ej. el navegador de escritorio vs. el navegador móvil vs. la aplicación móvil)?**

El uso de Tipo de dispositivo móvil como se ilustra arriba permite ver cómo se desplazan las personas entre tipos de dispositivos móviles y tipos de dispositivos de escritorio. Sin embargo, es posible que desee distinguir los exploradores de escritorio de los navegadores móviles. Una forma de hacerlo es crear una evar que registre si la experiencia se produjo en un navegador de escritorio, explorador móvil o aplicación móvil. A continuación, cree un diagrama de flujo como se ha descrito anteriormente, utilizando la evar «experiencia» en lugar de la dimensión Tipo de dispositivo móvil. Esto proporciona una vista ligeramente diferente en el comportamiento entre dispositivos.

**¿Cuánto atrás genera CDA visitantes?**

* Adobe mantiene los datos de identificación del dispositivo durante 30 días aproximadamente. Si el gráfico co-op o el gráfico privado, pero posteriormente se identifica en 30 días, no se identifica en un dispositivo, CDA vuelve y vuelve a indicar que ese dispositivo pertenece a personas identificadas de hasta 30 días en el pasado. Si parte del comportamiento no identificado de un usuario cae fuera de la ventana retroactiva de 30 días, esa parte del viaje del usuario no se rastrea.
* Adobe mantiene las asignaciones de dispositivos en Co-op Gráfico y Gráfico privado durante aproximadamente 6 meses. Un ECID sin actividad durante más de seis meses se elimina del gráfico. Los datos ya marcados en CDA no se ven afectados, pero las visitas subsiguientes para ECID se tratan como un nuevo individuo.

**¿Cómo gestiona CDA las visitas con marca de hora?**

Adobe trata las visitas con marca de hora como si se hubieran recibido en el momento de la marca de tiempo, no cuando Adobe recibió la visita. Las visitas con marca de hora anterior a 1 mes no se pueden unir, ya que se consideran fuera del rango que Adobe mantiene los datos utilizados para la vinculación.
