![Captura de pantalla 2024-10-13 002507](https://github.com/user-attachments/assets/0600c092-1f30-4477-9856-5b3e969f6fe9)
# El enemigo
Se creó una variante del prefab de Sci-Fi Warrior para añadir enemigos al reto. A éste se le colocó un Rigid Body y un Collider con el propósito de que se puedan manipular sus propiedades físicas y movimientos. 

El Collider en forma de cápsula crea una región en el enemigo que permite que interaccione con otros objetos en la escena que también poseen Colliders. Un ejemplo de esto sería que, gracias al Collider, el enemigo es efectado por las balas que el jugador dispara ya que la cápsula del enemigo detecta la cápsula de la bala.

# Scripts del enemigo
![Captura de pantalla 2024-10-13 002316](https://github.com/user-attachments/assets/dc5a57de-479c-4ced-a846-da8b0a726b5d)

Se creó un script de vida para el enemigo, donde, cuando se detecta el impacto de las balas, se le disminuye la vida. La variable amount es la cantidad de puntos de vida que posee el enemigo. Cuando se le acabe la vida, se llegué a 0, el enemigo desaparecerá del juego.

[Volver al Readme](README.md)
