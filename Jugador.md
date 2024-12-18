Nosotros creamos inicialmente un Box Collider como 
colisión del jugador, pero se cambió a un Capsule Collider para adaptarse
mejor a la forma del modelo del personaje y tener colisiones más precisas.
Se le dieron los siguientes valores:

![image](https://github.com/user-attachments/assets/db175069-393e-4788-b8a9-c784ba8e04eb)

![image](https://github.com/user-attachments/assets/95c76b33-cd31-43b5-81fb-e08396dcd9d2)

Se utilizó el componente Player Input, el cual fue conectado al script Player
Input Script para gestionar los movimientos del jugador.

![image](https://github.com/user-attachments/assets/316dade4-6946-4104-8b22-be17afb1c5a3)

![image](https://github.com/user-attachments/assets/684d085f-7b2b-4a0e-bb4b-3101f6d51628)

![image](https://github.com/user-attachments/assets/083a2638-1b23-412c-aefc-3527c8573f88)

![image](https://github.com/user-attachments/assets/6c10118d-6c02-4417-bac4-1dd26b6675b1)

Se implementó un script llamado Life, el cual controla la salud del jugador.
Este script permite que el jugador pierda vida al recibir daño y eventualmente 
muera cuando su salud llega a cero.

![image](https://github.com/user-attachments/assets/66f4fb58-54e1-4df1-92c1-a584b1228006)

![image](https://github.com/user-attachments/assets/ec121877-9f0e-4e02-bf9d-04bb4864753d)

Se añadió un componente RigidBody al jugador, lo que permitió 
la gravedad y dentro del juego.

![image](https://github.com/user-attachments/assets/9662a441-1236-406d-8a3e-4601fce0dd8b)

Para el disparo, se agregó un componente Shooting,
al que se le asignó un Bullet Prefab y
un Shoot Point, que define la posición y dirección desde donde se disparan
los bullets.

![image](https://github.com/user-attachments/assets/5e9b5fce-aa3e-4bc5-97b2-3e6300856bf5)


![image](https://github.com/user-attachments/assets/a26349da-b839-4ecb-b7c0-2dc13ee78346)

El Bullet Prefab recibió un script llamado Damage Script,
que permite a las balas infligir daño a los objetos que poseen un 
componente de vida. Además, las balas se destruyen automáticamente al 
tocar un objeto.

![image](https://github.com/user-attachments/assets/7244b449-5ae5-4cc7-9ade-3ee9052f07d1)

![image](https://github.com/user-attachments/assets/75ae4ee2-0d7a-443e-a16c-01f6e1233f7b)

![image](https://github.com/user-attachments/assets/ff849c7b-c398-4123-9a7c-33061bb10b36)

También se incluyó un script de movimiento Forward Movement para que las balas se impulsen hacia adelante.

![image](https://github.com/user-attachments/assets/a412b18b-458b-43ce-bc92-bfc6423aa632)

![image](https://github.com/user-attachments/assets/856604c6-df1a-43a1-ab83-a2f65b3c0c4e)

se implementó un script que las destruye automáticamente después de un tiempo
determinado. 

![image](https://github.com/user-attachments/assets/2166873d-9897-4d78-995f-04e8c4393530)

![image](https://github.com/user-attachments/assets/a81d05f9-968a-4f48-b2eb-6f179f2d2dee)

En el jugador, se colocó el Shoot Point, que actúa como la posición específica
desde donde salen los disparos, alineado con la orientación del personaje.

Se importó un Prefab de una aspiradora desde la Unity Store, que se 
usó como modelo para representar al jugador y para añadir un poco de humor al juego.

![image](https://github.com/user-attachments/assets/5843ff36-bbff-4cca-8c7d-3d8c04ec6eff)

Finalmente, se le agrego el main camera al jugador y se alineo con el prefab que usamos de aspiradora.

![image](https://github.com/user-attachments/assets/53c878ef-0162-4bc7-919f-f9e758fa2006)
