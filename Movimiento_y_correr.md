# Personaje
Abrimos el proyecto de Unity y colocamos el prefab de robot dentro del escenario. Este robot será el objeto principal que controlaremos en el juego.

![Screenshot 2024-10-13 153325](https://github.com/user-attachments/assets/acc398e8-b069-4e13-ab41-c7ab78525098)

Al robot, se le añadió un componente Rigidbody, que permite interactuar con las físicas de Unity. Se configuró la mass y el drag en 1 y el angular drag se ajustó a 20, para que el robot tenga una alta resistencia a la rotación, evitando que gire de manera brusca o descontrolada. 

![Screenshot 2024-10-13 153416](https://github.com/user-attachments/assets/1c2cde53-5936-4ed5-83d3-d24a7e242c19)

Se le agregó un Box Collider al robot, este collider se ajustó y estiró, de manera que el personaje pueda pararse correctamente sobre las plataformas, simulando una base estable.

![Screenshot 2024-10-13 153407](https://github.com/user-attachments/assets/6bf83096-2ca3-4809-8262-b3dec9d06929)

# Move y Look action
Se colocó un componente de Player Input, este componente vino preconfigurado con las acciones Look y Fire ya definidas, que se utilizarán más adelante para controlar movimiento y disparar.

![Screenshot 2024-10-13 153426](https://github.com/user-attachments/assets/582713a5-419f-488b-aa02-872818404c15)

![Screenshot 2024-10-13 153451](https://github.com/user-attachments/assets/7fa5f300-ca4d-43fb-8d8f-4ccb1219cba6)

# script movimiento
Se creó un nuevo script llamado Movement, en el cual se manejará toda la lógica de control del robot. Se declararon las siguientes variables: speed, rotationSpeed, movementValue, lookValue y rg. 

![image](https://github.com/user-attachments/assets/f7aaf367-0159-4df9-b7ac-7a68f10f45d8)
![image](https://github.com/user-attachments/assets/74d9d265-5a24-4238-98d3-f5b8371fdf38)


# Update
Dentro de Update, se añadió la función AddRelativeForce, que se utilizó para que el robot pueda moverse hacia adelante o hacia atrás dependiendo de la dirección en la que esté mirando. También se agregó AddRelativeTorque, permitiendo al robot rotar en el eje correspondiente. Esto fue usado para controlar la rotación del jugador.

![image](https://github.com/user-attachments/assets/9dd3e36e-227a-4e5a-8a87-df404b905d10)


# Movimiento
Se implementó una función llamada OnMove, que permite capturar las acciones de movimiento definidas en el Player Input component. Esta función se conecta a los inputs del jugador para controlar el movimiento. Dentro de OnMove, se verificó si la tecla Shift está presionada. Si es así, se aplica un sprintMultiplier que aumenta la velocidad del robot temporalmente, permitiendo al jugador correr. Esta lógica nos permitirá más adelante implementar una mecánica de sprint o carrera rápida.

![image](https://github.com/user-attachments/assets/b12e8855-27b6-475d-b266-595552d574f0)

# Rotación 
Finalmente, se creó la función OnLook, que se encarga de controlar la rotación del personaje. Esta función toma los valores de entrada del eje X y Y para permitir que el robot mire en diferentes direcciones.

![image](https://github.com/user-attachments/assets/e3ea969c-663d-49b9-abe8-e00a8eaa074c)

# Sprint action
Abrimos el componente Player Input en el inspector y se añadió una nueva acción 	que se llamó "sprint". 
Se configuró como tipo Value para recibir valores continuos en lugar de acciones discretas. Se configuró el control de tipo Vector, para que se pueda manejar en conjunto con otras acciones de movimiento.

![Screenshot 2024-10-13 154532](https://github.com/user-attachments/assets/07f72622-727b-4fee-b161-64a2ca5d1e94)

# script sprint 
Dentro del script de PlayerMovement, se declaró una variable booleana IsSprinting. También se declaró una variable pública llamada sprintMultiplier que sería utilizada para aumentar la velocidad del jugador cuando esté corriendo.

![image](https://github.com/user-attachments/assets/68a1d4f0-86f5-4c07-9b62-88f6b6ec556b)

Se implementó una nueva función OnSpint que escucha la acción de sprint dentro del input component. Dentro de esta función, se utilizó un condicional para verificar si la tecla Shift está presionada. Si Shift está presionada, se establece IsSprinting en verdadero. (En la función OnMove, como establecimos anteriormente, se verificó el valor de IsSprinting. Si IsSprinting es verdadero, se multiplica la velocidad del jugador por sprintMultiplier para aumentar la velocidad del movimiento. Si no, el jugador se mueve a la velocidad regular.)

![image](https://github.com/user-attachments/assets/4dc819f8-e10d-404a-9127-575f7340e13d)


Después de implementar la función, ajustamos el valor de sprintMultiplier a través del inspector para encontrar el valor que hace que el sprint se note. Se probaron varios valores hasta encontrar la velocidad que mejor se ajusta al diseño del juego.


