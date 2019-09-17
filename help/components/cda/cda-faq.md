---
title: Preguntas más frecuentes sobre análisis entre dispositivos
description: Preguntas más frecuentes sobre el análisis entre dispositivos
translation-type: tm+mt
source-git-commit: e7a78c2ac21042f57487c1c230e1c96318810429

---


# Preguntas frecuentes

> [!NOTE] La documentación de Análisis entre dispositivos está sujeta a cambios a medida que la función se desarrolla. Vuelva regularmente para ver las actualizaciones.

**¿Cómo puedo usar CDA para ver cómo la gente se mueve de un tipo de dispositivo a otro?**

Puede utilizar una visualización de flujo con la dimensión Tipo de dispositivo móvil.

1. Inicie sesión en Adobe Analytics y cree un nuevo proyecto de espacio de trabajo en blanco.
2. Haga clic en la ficha Visualizaciones de la izquierda y arrastre una visualización de flujo al lienzo de la derecha.
3. Haga clic en la ficha Componentes de la izquierda y arrastre la dimensión 'Tipo de dispositivo móvil' a la ubicación central denominada 'Dimensión o elemento'.
4. Este informe de flujo es interactivo. Haga clic en cualquiera de los valores para expandir los flujos a páginas posteriores o anteriores. Utilice el menú que aparece al hacer clic con el botón derecho para expandir o contraer columnas. También se pueden utilizar distintas dimensiones dentro del mismo informe de flujo.

**¿Puedo ver cómo se mueven las personas entre distintas experiencias de usuario (p. ej., navegador de escritorio vs. navegador móvil vs. aplicación móvil)?**

El uso del tipo de dispositivo móvil, como se ilustra más arriba, permite ver cómo se mueven las personas entre los tipos de dispositivos móviles y los tipos de dispositivos de escritorio. Sin embargo, es posible que desee distinguir los navegadores de escritorio de los navegadores móviles. Una manera de hacerlo es crear una eVar que registre si la experiencia se produjo en un navegador de escritorio, un navegador móvil o una aplicación móvil. A continuación, cree un diagrama de flujo como se ha descrito anteriormente, utilizando la eVar de "experiencia" en lugar de la dimensión Tipo de dispositivo móvil. Esto proporciona una vista ligeramente diferente del comportamiento entre dispositivos.

**¿Hasta dónde llega la CDA a los visitantes?**

* Adobe mantiene los datos de identificación de dispositivos durante aproximadamente 30 días. Si al principio un dispositivo no se identifica mediante el gráfico Co-op o el gráfico privado, pero se identifica posteriormente en un plazo de 30 días, CDA vuelve atrás y vuelve a señalar que pertenece a una persona identificada hasta 30 días antes. Si parte del comportamiento no identificado de un usuario queda fuera de la ventana retrospectiva de 30 días, esa porción del viaje del usuario no está vinculada.
* Adobe mantiene las asignaciones de dispositivos en el Gráfico de cooperación y el Gráfico privado durante aproximadamente 6 meses. Un ECID que no tenga actividad durante más de seis meses se elimina del gráfico. Los datos ya enlazados en CDA no se ven afectados, pero las visitas posteriores para ese ECID se tratan como una persona nueva.

**¿Cómo gestiona CDA las visitas con marca de hora?**

Adobe trata las visitas con marca de hora como si se hubieran recibido en el momento de la marca de hora, no cuando Adobe recibió la visita. Las visitas con marca de hora anteriores a 1 mes no se pueden vincular, ya que se consideran fuera del rango en el que Adobe mantiene los datos utilizados para la identificación.

**¿En qué se diferencia CDA de la ID de visitante personalizada?**

[La ID](../../implement/js-implementation/c-unique-visitors/visid-custom.md) de visitante personalizada es un método heredado para [conectar usuarios entre dispositivos](../../implement/js-implementation/xdevice-visid/xdevice-connecting.md). Con una ID de visitante personalizada, se utiliza la `s.visitorID` variable para establecer explícitamente la ID que se utiliza para la lógica del visitante. La `s.visitorID` variable anula los ID basados en cookies que estén presentes. Consulte [Identificar visitantes](../../implement/js-implementation/c-unique-visitors/visid-overview.md) únicos en la guía Implementar usuario para obtener más información.

Las ID de visitante personalizadas tienen una serie de efectos secundarios no deseados que CDA está diseñado para superar o minimizar. Por ejemplo, la metodología de ID de visitante personalizada no tiene capacidades de retroactividad. Si un usuario se autentica en mitad de una visita, la primera parte de la visita se asocia con un ID de visitante diferente al de la última parte de la visita. Los ID de visitante independientes producen inflación de visitas y visitantes. La ventana retrospectiva de 30 días de CDA le permite retroceder en el tiempo para reafirmar el comportamiento anterior como perteneciente a la misma persona, lo que trae un comportamiento entre dispositivos no autenticado junto con un comportamiento autenticado entre dispositivos con inflación mínima o cero.

**¿Puedo actualizar de ID de visitante personalizado a CDA?**

Los clientes que ya utilicen ID de visitante personalizado pueden actualizar a CDA. El `s.visitorID` sistema aún anula los ID basados en cookies subyacentes en el grupo de informes base. Sin embargo, dentro del grupo de informes virtuales, CDA ignora `s.visitorID` los dispositivos identificados por el gráfico del dispositivo.

**¿Cómo gestiona el gráfico del dispositivo los dispositivos compartidos?**

En algunas situaciones es posible que varias personas inicien sesión desde el mismo dispositivo. Algunos ejemplos son un dispositivo compartido en casa, un equipo compartido en una biblioteca o un quiosco en un punto de venta minorista. En estos casos, el ID se sincroniza con el gráfico del dispositivo desde estos dispositivos compartidos indica que varios usuarios se asocian con ese dispositivo a lo largo del tiempo. El gráfico del dispositivo (ya sea Co-op o Private Graph) no vincula el ECID de ese dispositivo a ninguno de estos usuarios. En su lugar, el gráfico vincula el ECID a un "clúster" que incluye a todos los usuarios asociados. El gráfico intenta mantener este clúster lo más estable posible, en lugar de cambiar continuamente el ECID entre clústeres a lo largo del tiempo. Como resultado, CDA no puede distinguir entre usuarios individuales en un dispositivo compartido. Todos los usuarios del dispositivo compartido se consideran una sola "persona" dentro de CDA.

**¿Cómo gestiona el gráfico de dispositivos las situaciones en las que una sola persona tiene MUCHOS dispositivos/ECID?**

En algunas situaciones, un usuario individual puede asociarse con un gran número de ECID. Esto puede ocurrir si el usuario utiliza muchos navegadores o aplicaciones, y puede exacerbarse si borra las cookies con frecuencia o utiliza el modo de exploración privado o indirecto del explorador. El gráfico del dispositivo limita el número de ECID que se asocia a un ID de usuario determinado a 200. Si un ID de usuario se asocia con demasiados ECID, el gráfico del dispositivo supone que el ID de usuario no es válido y elimina el clúster asociado a dicho ID de usuario. El ID de usuario queda bloqueado para no quedar recluido en el futuro. El resultado de CDA es que el comportamiento del ID de usuario no se vincula entre dispositivos.
