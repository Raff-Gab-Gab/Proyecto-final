Se agregaron 3 esferas al escenario, las cuales fueron aplanadas para que tuvieran apariencia de botones interactivos. 

![image](https://github.com/user-attachments/assets/298e291b-a69f-414b-bc49-5e099b6d7b7b)

Dentro de cada esfera, se colocó un texto que indica si la respuesta asociada a ese botón es correcta o incorrecta.

![image](https://github.com/user-attachments/assets/a08cf1cc-54fc-410b-814a-87432bb6cfe3)

Cada esfera tiene un valor de 1 de vida y está programada para destruirse automáticamente cuando el jugador le dispara.
Este comportamiento se implementó mediante un script de vida, integrado en cada esfera.

![image](https://github.com/user-attachments/assets/4583877f-a74c-4798-83c8-d95ee2ada220)

Las respuestas correctas e incorrectas tienen un SerializeField que en la escena se conecta con el script de vida del jugador. 
Esto permite que, al disparar a una respuesta, el jugador reciba un efecto en su vida:

![image](https://github.com/user-attachments/assets/dd37cca8-bfd1-4d1e-8ad0-7d6a70c1937d)

se le resta vida si selecciona una respuesta incorrecta 

![image](https://github.com/user-attachments/assets/aa22905b-dec1-497e-bc49-bd8ef729e178)

o se le agrega vida si selecciona una respuesta correcta.


![image](https://github.com/user-attachments/assets/67b69e4e-6698-4b5f-8767-41629ba6e31e)

Entonces, a cada pregunta se le eliminaba el script que no era necesario en la escena, dependiendo de las respuestas.

Encima de cada esfera, se colocó un texto que señala las respuestas posibles, ayudando al jugador a identificar fácilmente qué representa cada botón.
Además, se añadió un texto adicional que indica la categoría de la pregunta y su contenido correspondiente, brindando contexto a las interacciones.


![image](https://github.com/user-attachments/assets/76dfef4e-dbd2-4518-91eb-a7100a98c179)

Se encuentra un esqueleto que actúa como el presentador de las preguntas. 
Este esqueleto es un Prefab que importamos desde la Unity Store, añadiendo un poco mas de humor al juego.


![image](https://github.com/user-attachments/assets/9453c86a-2c33-47fb-b7e5-62e76a14a96b)

Las preguntas correctas están diseñadas para quitarle vida a la salida del laberinto. Este comportamiento permite que, al contestar correctamente, 
el jugador destruya eventualmente la salida, abriendo el camino para escapar del laberinto.

En total, se crearon 4 preguntas principales. Adicionalmente, se añadió una pregunta de bono que el jugador puede responder en caso de necesitar recuperar vida.

![image](https://github.com/user-attachments/assets/04601b8e-693b-43c0-ae36-9a1a447a74be)

![image](https://github.com/user-attachments/assets/d81958eb-f85f-4d3a-b909-3ea70bce8ac0)

![image](https://github.com/user-attachments/assets/c770b2b8-17ce-4406-ba6b-65ae33b81ffd)

![image](https://github.com/user-attachments/assets/1568074d-37c5-4bb5-896f-ecee8144b09a)

![image](https://github.com/user-attachments/assets/d558a2f6-3699-4ac6-bdb8-5a232ee3d289)
