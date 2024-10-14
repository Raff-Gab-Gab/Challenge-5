# Bullet
Decidimos reutilizar un prefab de bala que teníamos de otro proyecto, ya que nos gustó el diseño que tenía. 

![Screenshot 2024-10-13 154342](https://github.com/user-attachments/assets/1dc97275-27bc-42cd-8a2f-650027cc81d2)

Se le asignó un Rigidbody a la bala para que pudiera interactuar con las físicas de Unity, permitiendo que se mueva y colisione.
Se le agregó también un Capsule Collider, lo que define el área de colisión de la bala, dándole una forma cilíndrica para que las colisiones sean más precisas al disparar. 

![Screenshot 2024-10-13 154359](https://github.com/user-attachments/assets/ac0a38fe-b00f-428d-8e26-64f069127368)

# Scripts
Se colocaron tres scripts diferentes en la bala para manejar su comportamiento:
-Script Forward: Encargado de mover la bala hacia adelante.
-Script Damage: Responsable de aplicar daño a los enemigos al colisionar.
-Script Auto Destroy: Utilizado para autodestruir la bala después de un tiempo determinado.

![Screenshot 2024-10-13 154407](https://github.com/user-attachments/assets/d36f0db7-8ec8-4958-9e01-07f9f963be32)

Dentro del script Forward, se creó una variable  llamada speed que controla la velocidad a la que la bala se moverá.
En la función Update, se utilizó transform.Translate para mover la bala en el eje Z. Esto permite que la bala avance en línea recta desde el punto donde fue disparada.

![image](https://github.com/user-attachments/assets/c434bbcf-4de5-4714-86d1-3c135fb32eca)

En el script Damage, se definió una variable llamada damage, que almacenará el valor de daño que la bala inflige.
Se añadió una función llamada OnTriggerEnter. Esta función se activa cuando la bala colisiona con otro objeto en el juego. Si el enemigo tiene vida, se reduce la cantidad de vida en función del valor de damage que tenga la bala. De esta manera, se asegura que la bala cause daño a los enemigos con los que colisiona.

![image](https://github.com/user-attachments/assets/e0b452cd-fcd4-40d2-823a-5b1192fac45a)

En el script Auto Destroy, utilizamos la función Start para destruir automáticamente la bala después de un tiempo determinado. Se uso Destroy(gameObject, delay (delay siendo una variable creada anteriormente) que se asegura que la bala se elimine tras un tiempo predefinido.

![image](https://github.com/user-attachments/assets/8ce3486f-a630-41cc-afa8-5e3a6450e323)

Se creó un objeto vacío shootPoint y fue asignado como hijo de la pistola del jugador, asegurando que el punto de disparo se mueva junto con la pistola cuando el jugador apunte o se mueva. Este objeto que actuará como el punto desde donde se se colocó en la posición deseada dentro de la pistola del jugador.

![image](https://github.com/user-attachments/assets/ade53687-ce76-4667-ac19-1455510f334b)

En el script PlayerMovement del jugador, se creó una función llamada OnFire. Esta función se encarga de instanciar las balas en el ShootPoint cada vez que el jugador presiona el botón izquierdo del mouse. 

![image](https://github.com/user-attachments/assets/bcb57d0c-7d27-488a-b00f-bf1852376a5c)

[Volver al Readme](README.md)
