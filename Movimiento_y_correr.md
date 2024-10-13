Personaje:
Abrimos el proyecto de Unity y colocamos el prefab de robot dentro del escenario. Este robot será el objeto principal que controlaremos en el juego.

foto

Al robot, se le añadió un componente Rigidbody, que permite interactuar con las físicas de Unity. Se configuró la mass y el drag en 1, lo que proporciona un peso estándar y resistencia al movimiento lineal y el angular drag se ajustó a 20, para que el robot tenga una alta resistencia a la rotación, evitando que gire de manera brusca o descontrolada. 

foto

Se le agregó un Box Collider al robot, este collider se ajustó y estiró, de manera que el personaje pueda pararse correctamente sobre las plataformas, simulando una base estable.

foto

Se colocó un componente de Player Input, este componente vino preconfigurado con las acciones Look y Fire ya definidas, que se utilizarán más adelante para controlar el movimiento de la cámara y disparar.

foto

script:
Se creó un nuevo script llamado Movement, en el cual se manejará toda la lógica de control del robot. Se declararon las siguientes variables:

speed: Controla la velocidad del movimiento del robot.
rotationSpeed, movementValue, lookValue y
rg. 

foto

Dentro de Update, se añadió la función AddRelativeForce, que se utilizó para que el robot pueda moverse hacia adelante o hacia atrás dependiendo de la dirección en la que esté mirando. También se agregó AddRelativeTorque, permitiendo al robot rotar en el eje correspondiente. Esto fue usado para controlar la rotación del jugador.

foto

Se implementó una función llamada OnMove, que permite capturar las acciones de movimiento definidas en el Player Input component. Esta función se conecta a los inputs del jugador para controlar el movimiento. Dentro de OnMove, se verificó si la tecla Shift está presionada. Si es así, se aplica un sprintMultiplier que aumenta la velocidad del robot temporalmente, permitiendo al jugador correr. Esta lógica nos permitirá más adelante implementar una mecánica de sprint o carrera rápida.

foto

Finalmente, se creó la función OnLook, que se encarga de controlar la rotación del personaje. Esta función toma los valores de entrada del eje X y Y para permitir que el robot mire en diferentes direcciones.

foto

