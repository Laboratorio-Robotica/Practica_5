# Practica_5
## Integrantes:  
- Francisco Javier Godinez Lopez
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
6. Usando el comando **Move** mover el plumón al segundo punto de la letra "a".
7. Usando el comando **Arc3** mover el plumón en un arco tomando de referencia el segundo, tercero y cuarto punto para terminar de escribir la letra "a".
8. Regresar a la posición Intermedia para posteriormente continuar con la siguiente letra.
9. Bajar el plumón al primer punto de la letra "c" con el comando **Go**.
10. Usando el comando **Arc3** mover el plumón en un arco tomando de referencia el primer, segundo y tercero punto para escribir la letra "c".
11. Regresar a la posición Intermedia para posteriormente continuar con la última letra.
12. Bajar el plumón al primer punto de la letra "o" con el comando **Go**.
13. Usando el comando **Arc3** mover el plumón en un arco tomando de referencia el primer, segundo y tercero punto para realizar la primer mitad de la letra "o".
14. Posteriormente se sigue usando el comando **Arc3** para mover el plumón en un arco tomando de referencia el tercero, cuarto y primer punto para realizar la segunda mitad de la letra "o".
15. Finalmente regresar a la posicion **Home**.





De tal manera que el codigo desarrollado quedo de la siguiente manera:
```
Function main
	Home
	Go Inicial
	Go T1
	Move T2
	Move T3
	Move T4
	Go Inicial
	Go a1
	Move a2
	Arc3 a3,a4
	Go Inicial
	Go c1
	Arc3 c2,c3
	Go Inicial
	Go o1
	Arc3 o2,o3
	Arc3 o4,o1
	Home

Fend
```
![Practica_5Robotica](https://github.com/user-attachments/assets/1ff865e9-4b88-448d-a87d-3bdb2ecae763)


En el siguiente video se muestra el movimiento realizado utilizando el código anterior, cuyo objetivo fue escribir la palabra "Taco" con el uso de diferentes comandos de movimientos. Este proceso demuestra el correcto funcionamiento del sistema y cumple con los objetivos establecidos para la práctica

https://drive.google.com/drive/folders/1LNkZFlLKDiIUVDZCGS-185doGVwsoqju?usp=drive_link

## Conclusiones:  
### Francisco Javier Godinez Lopez:
La práctica fue importante para comprender la programación de trayectorias del brazo robótico Epson utilizando comandos como Move, Go, y Arc3. El ejercicio permitió aplicar estos comandos de manera secuencial para escribir la palabra "Taco", lo que reforzó el conocimiento de los diferentes tipos de movimientos y cómo  afecta la precisión del robot, cumpliendo satisfactoriamente con los objetivos planteados.


### Pablo Axel Silva Fuentes: 
La práctica fue crucial para entender cómo se pueden combinar los diferentes comandos de movimiento del brazo robótico Epson para lograr una tarea precisa como escribir "Taco". A través del uso de Move y Arc3, se aprendió a controlar los movimientos del robot con exactitud. Además, el descubrimiento de la posibilidad de ajustar directamente los puntos en el código hizo que fuera más fácil optimizar el trabajo en el eje Z, mejorando el proceso de escritura y contribuyendo al éxito del proyecto.


### Eduardo David Salas Ayala: 
Esta práctica permitió una mejor comprensión de cómo se utilizan los comandos básicos y avanzados de movimiento en el software Epson RC+ para controlar el brazo robótico. El uso de Go, Move, y Arc3 para escribir la palabra "Taco" fue un ejercicio clave para aplicar los conocimientos adquiridos. También se aprovechó la función de ajustar la posición Z directamente en el código, lo que simplificó la edición de los puntos y ayudó a refinar los movimientos del robot.

## Referencias bibliográficas
- Epson (2020). EPSON RC+ 7.0 Manual del usuario Administración y desarrollo de proyectos (Ver.7.3). https://files.support.epson.com/far/docs/epson_rc_pl_70_users_guide_spanish_(v73r2).pdf
