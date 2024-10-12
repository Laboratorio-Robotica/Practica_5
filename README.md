# Practica_5
## Integrantes:  
- Francisco javier Godinez Lopez
- Pablo Axel Silva Fuentes
- Eduardo David Salas Ayala
## Introducción:  
La práctica tiene como objetivo programar una trayectoria de varios movimientos para el brazo robótico Epson utilizando diferentes comandos de movimientos (Control de punto a punto, Movimiento linealy Curvas) con el fin de escribir una palabra en una hoja con un plumón que la pinza está sujetando. Los comandos utilizados para poder realizar el movimiento necesario para escribir las letras fueron los siguientes: 
-  **Home** -- (Reposo) mueve el robot a una posición de "espera" o "descanso".
-  **Go** -- Se mueve directamente a un punto con un movimiento de punto a punto.
-  **Jump** -- Salta a un punto. Primero se mueve hasta la configuración actual de LimZ, luego hasta el punto de destino y luego al punto. La configuración de la tabla Arch determina el perfil de Jump.
-  **Jump3** -- Salta a un punto en 3 dimensiones. Se mueve en una línea recta con la misma orientación hasta el punto de retroceso. El movimiento entre los puntos de retroceso es un movimiento PTP.
-  **Pass** -- Se mueve cerca de uno o más puntos.
-  **Move** -- Se mueve en una línea recta al punto especificado.
-  **Arc** -- Mueve el robot a través de un punto a otro usando una interpolación circular.
-  **Arc3** -- Mueve el robot en 3D con una interpolación circular.

## Instrucciones

El movimiento del brazo consiste en escribir la palabra "Taco" con el uso de los comandos de movimeinto previamente establecidos.
1. Mover desde el origen hacia una posición cercana (Intermedia) a la hoja para agilizar el proceso.
2. Bajar el plumón al primer punto de la letra "T" con el comando **Move**.
3. Usando el comando **Move** mover el plumón a los puntos necesarios para terminar de escribir la letra T.
4. Regresar a la posición Intermedia para posteriormente continuar con la siguiente letra.
5. Bajar el plumón al primer punto de la letra "a" con el comando **Go**.
6. Usando el comando **Go** mover el plumón al segundo punto de la letra "a".
7. Usando el comando **Arc** mover el plumón en un arco tomando de referencia el segundo, tercero y cuarto punto para terminar de escribir la letra "a".
8. Regresar a la posición Intermedia para posteriormente continuar con la siguiente letra.
9. Bajar el plumón al primer punto de la letra "c" con el comando **Go**.
10. Usando el comando **Arc** mover el plumón en un arco tomando de referencia el primer, segundo y tercero punto para escribir la letra "c".
11. Regresar a la posición Intermedia para posteriormente continuar con la última letra.
12. Bajar el plumón al primer punto de la letra "o" con el comando **Go**.
13. Usando el comando **Arc** mover el plumón en un arco tomando de referencia el primer, segundo y tercero punto para realizar la primer mitad de la letra "o".
14. Posteriormente se sigue usando el comando **Arc** para mover el plumón en un arco tomando de referencia el tercero, cuarto y primer punto para realizar la segunda mitad de la letra "o".
15. Finalmente regresar a la posicion **Home**.





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

En el siguiente video se muestra el movimiento realizado utilizando el código anterior, cuyo objetivo fue escribir la palabra "Taco" con el uso de diferentes comandos de movimientos. Este proceso demuestra el correcto funcionamiento del sistema y cumple con los objetivos establecidos para la práctica

https://drive.google.com/drive/folders/1LNkZFlLKDiIUVDZCGS-185doGVwsoqju?usp=drive_link

## Conclusiones:  
### Francisco Javier Godinez Lopez:
La práctica fue esencial para entender cómo utilizar el ciclo 'for' en el programa Epson RC+.Desde el principio, la práctica ha permitido investigar y adquirir conocimientos sobre cómo gestionar y organizar este proceso de forma eficaz. También se encontró una característica extra en la plataforma, la posibilidad de realizar cambios pequeños en la dimensión Z, lo que simplificó la edición de los puntos ya guardados directamente en el código ademas que la apliacion de fusibles fue de gran ayuda, resolviendo el problema eficazmente.


### Pablo Axel Silva Fuentes: 
De primera instancia la práctica resultó fundamental para entender la implementación del ciclo 'for' en el software Epson RC+. El ejercicio inicial ofreció una oportunidad para explorar y aprender cómo estructurar y controlar dicho ciclo. Asimismo, se encontró una nueva característica en la apliacion la posibilidad de realizar pequeñas alteraciones en el eje Z, lo que hizo más sencillo realizar ajustes directamente en el código y cambiar los puntos guardados anteriormente.


### Eduardo David Salas Ayala: 
La práctica fue aprovechada para la comprensión del ciclo 'for' aplicado en el programa Epson RC+. Por lo tanto, el problema inicial fue de gran ayuda para analizar y comprender cómo se puede programar el ciclo. Además, se conoció una nueva posibilidad dentro de la aplicación, que fue hacer pequeñas variaciones en Z, lo que permitió ajustarla desde la sección de programación, pudiendo variar los puntos guardados.

## Referencias bibliográficas
- Epson (2020). EPSON RC+ 7.0 Manual del usuario Administración y desarrollo de proyectos (Ver.7.3). https://files.support.epson.com/far/docs/epson_rc_pl_70_users_guide_spanish_(v73r2).pdf
