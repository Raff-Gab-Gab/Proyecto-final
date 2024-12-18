## Enemigos pequeños

En el laberinto se encuentran múltiples fantasmas, los enemigos, caminando por la estructura hasta llegar a una base localizada en el centro del mapa. Estos fantasmas tienen como estado inicial llevar hacia la base y destruirse cuando llegan a ella. No obstante, si se topa con el jugador, éste lo sigue y le dispara, quitándole vida. Por otro lado, estos fantasmas tienen vida y pueden ser matados por el jugador.

### Los fantasmas 
![Captura de pantalla 2024-12-17 225530](https://github.com/user-attachments/assets/6cd3132a-7a57-4c37-96c5-8027ee8648a2)
![Captura de pantalla 2024-12-17 223819](https://github.com/user-attachments/assets/52b4c2b4-c3cb-443c-8c21-190f75e4d2a0)


### Script para la vida del fantasma
![image](https://github.com/user-attachments/assets/3c56876e-aa49-4440-8033-4bc0faf1bc9a)


La máquina de estados finitos de estos enemigos, las opciones o acciones que puede tomar, consisten en las siguientes: caminar hacia la base, seguir al jugador, atacar al jugador y morir cuando llegan a la base. Se utilizó un componente de inteligencia artificial para crear un mesh de navegación en el terreno y permitir que los fantasmas pudiesen caminar por ella y seguir un camino. 

### El mesh de navegación del laberinto. Lo azul indica las zonas que pueden ser transitadas por los fantasmas. 
![Captura de pantalla 2024-12-17 230255](https://github.com/user-attachments/assets/d416ec19-edd7-48e5-a487-3966d15271d8)

### Script del FSM del fantasma
![Captura de pantalla 2024-12-17 232838](https://github.com/user-attachments/assets/349023c0-0ccb-40c5-925e-2108c70ce782)
![Captura de pantalla 2024-12-17 232906](https://github.com/user-attachments/assets/1e4c15c5-a0ca-47a2-8989-ebdfcefb5cd2)
![Captura de pantalla 2024-12-17 232927](https://github.com/user-attachments/assets/1d5f03cf-dc4d-4ba7-919f-30ed5a0e1cea)
![Captura de pantalla 2024-12-17 232943](https://github.com/user-attachments/assets/53693dc1-1984-4f54-b5c7-37a4ca41a616)
![Captura de pantalla 2024-12-17 233417](https://github.com/user-attachments/assets/89c6a806-4db8-451d-bae8-9cc7cd36751b)
![Captura de pantalla 2024-12-17 233017](https://github.com/user-attachments/assets/1e292e76-899f-4639-94a3-cf2bf93504f6)

Ahora bien, para localizar la base y al jugador, se utilizó un script que determina cuál es la distancia que puede acaparar o cuánto puede detectar o ver el fantasma alrededor de sí. Se determinó el tamaño del círculo de detección del fantasma y un ángulo de visión. Estos elementos son los que se utilizan en el script de la máquina de estados finitos del fantasma para poder localizar los objetos como la base y caminar hacia ella. 

### El script para la visión del fantasma. 
![Captura de pantalla 2024-12-17 232026](https://github.com/user-attachments/assets/dd546a29-4c47-4bb1-86ce-1533d64ddeae)
![Captura de pantalla 2024-12-17 232041](https://github.com/user-attachments/assets/9a92c37c-4465-4aa6-b703-7d1e329bdffb)
![Captura de pantalla 2024-12-17 232058](https://github.com/user-attachments/assets/3aec4d9d-8b69-4db0-bb32-f2e9373174a0)





