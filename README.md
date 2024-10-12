# Practica_5
## Integrantes:  
- Francisco javier Godinez Lopez
- Pablo Axel Silva Fuentes
- Eduardo David Salas Ayala
## Introducción:  
La práctica tiene como objetivo programar una trayectoria de varios movimientos para el brazo robótico Epson utilizando diferentes comandos de movimientos (Control de punto a punto, Movimiento linealy Curvas) con el fin de escribir una palabra en una hoja. Los comandos utilizados para poder realizar el movimiento necesario para escribir las letras fueron los siguientes: 
-  **Home** -- (Reposo) mueve el robot a una posición de "espera" o "descanso".
-  **Go** -- Se mueve directamente a un punto con un movimiento de punto a punto.
-  **Jump** -- Salta a un punto. Primero se mueve hasta la configuración actual de LimZ, luego hasta el punto de destino y luego al punto. La configuración de la tabla Arch determina el perfil de Jump.
-  **Jump3** -- Salta a un punto en 3 dimensiones. Se mueve en una línea recta con la misma orientación hasta el punto de retroceso. El movimiento entre los puntos de retroceso es un movimiento PTP.
-  **Pass** -- Se mueve cerca de uno o más puntos.
-  **Move** -- Se mueve en una línea recta al punto especificado.
-  **Arc** -- Mueve el robot a través de un punto a otro usando una interpolación circular.
-  **Arc3** -- Mueve el robot en 3D con una interpolación circular.

## Instrucciones

El movimiento del brazo consiste en recoger 4 objetos (fusible 1, fusbible 2, fusible 3 y fusible 4) desde el mismo punto, e ir apilando uno encima de otro en un punto definido por el profesor, haciendo uso del comando "for" para su comprencion.
1. Mover desde el origen hacia una posición sobre el surtidor de fusibles y abrir la garra para, posteriormente, bajar hacia el fusible.
2. Cerrar la garra tomando el fusible 1 y subir a la posición anterior.
3. Dirigirse a la posición donde serán apilados.
4. Bajar la garra hacia donde será colocado el fusible.
5. Abrir la garra para soltar el fusible.
6. Volver a la posición HOME inicial.
7. Repetir del paso 1 al 6 usando el ciclo "for", con una variación en "Z".
8. Completar los 4 ciclos para la apilación de los fusibles.
9. Finalmente, terminar en la posición HOME para concluir el ejercicio.





De tal manera que el codigo desarrollado quedo de la siguiente manera:
```
Function main
	
	Integer i
	For i = 0 To 3
		On 2
		Go Posicion0
		Go Posicion1
		Off 2
		Go Posicion0
		Go Posicion2
		Go Posicion3 +Z(i * 12)
		On 2
		Go Posicion2
	
	Next
	

Fend
```

En el siguiente video se muestra el movimiento realizado utilizando el código anterior, cuyo objetivo fue apilar una serie de fusibles. Este proceso demuestra el correcto funcionamiento del sistema y cumple con los objetivos establecidos para la práctica

https://drive.google.com/drive/folders/1LNkZFlLKDiIUVDZCGS-185doGVwsoqju?usp=drive_link

## Conclusiones:  
### Francisco Javier Godinez Lopez:
La práctica fue esencial para entender cómo utilizar el ciclo 'for' en el programa Epson RC+.Desde el principio, la práctica ha permitido investigar y adquirir conocimientos sobre cómo gestionar y organizar este proceso de forma eficaz. También se encontró una característica extra en la plataforma, la posibilidad de realizar cambios pequeños en la dimensión Z, lo que simplificó la edición de los puntos ya guardados directamente en el código ademas que la apliacion de fusibles fue de gran ayuda, resolviendo el problema eficazmente.


### Pablo Axel Silva Fuentes: 
De primera instancia la práctica resultó fundamental para entender la implementación del ciclo 'for' en el software Epson RC+. El ejercicio inicial ofreció una oportunidad para explorar y aprender cómo estructurar y controlar dicho ciclo. Asimismo, se encontró una nueva característica en la apliacion la posibilidad de realizar pequeñas alteraciones en el eje Z, lo que hizo más sencillo realizar ajustes directamente en el código y cambiar los puntos guardados anteriormente.


### Eduardo David Salas Ayala: 
La práctica fue aprovechada para la comprensión del ciclo 'for' aplicado en el programa Epson RC+. Por lo tanto, el problema inicial fue de gran ayuda para analizar y comprender cómo se puede programar el ciclo. Además, se conoció una nueva posibilidad dentro de la aplicación, que fue hacer pequeñas variaciones en Z, lo que permitió ajustarla desde la sección de programación, pudiendo variar los puntos guardados.

## Referencias bibliográficas
- Localización y planificación de trayectorias - TEKNIKER. (s. f.). https://www.tekniker.es/es/localizacion-y-planificacion-de-trayectorias
