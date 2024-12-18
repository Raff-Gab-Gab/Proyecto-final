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

### El script para la visión de los fantasmas. 
![Captura de pantalla 2024-12-17 232026](https://github.com/user-attachments/assets/dd546a29-4c47-4bb1-86ce-1533d64ddeae)
![Captura de pantalla 2024-12-17 232041](https://github.com/user-attachments/assets/9a92c37c-4465-4aa6-b703-7d1e329bdffb)
![image](https://github.com/user-attachments/assets/0a0ba10e-9874-4317-933d-b2718b303ba5)

Estos fantasmas están constantemente siendo generados en 8 "spawners" distintos alrededor del mapa. Para esto, se creó un EnemyManager donde se mantiene una lista de todas las instancias de fantasmas que se crean. Por otro lado, cuando un enemigo se muere, éste es sacado de la lista. Esto es para controlar y tener en cuenta todos los enemigos en el juego. Cada fantasma tiene un script donde se instancia y se añade a la lista. 

### Script para añadir el fantasma a la lista de enemigos 
![image](https://github.com/user-attachments/assets/f56057f9-3a46-4a96-abcd-8f5e1cf0cce3)

### Script para manejar la lista (Ghost manager)
![Captura de pantalla 2024-12-17 235647](https://github.com/user-attachments/assets/2d30aacf-0b95-494f-875a-468e2ac60c11)

Los "spawners" u olas de enemigos también tienen su propio manejador para saber cúantos "waves" empezaron, continúan o terminaron de generar enemigos. Estos "spawners" toman el prefab del fantasma y los instancian durante un período y razón específico. 

### Script para los spawns de los fantasmas 
![Captura de pantalla 2024-12-17 235905](https://github.com/user-attachments/assets/cd158d1a-2434-4bd7-9e8a-3d3ed1d5490d)

### Script del manejador de olas (spawns) de enemigos 
![Captura de pantalla 2024-12-17 235905](https://github.com/user-attachments/assets/4eda7535-3d90-4226-93df-2b19ecef41f8)

## Enemigos grandes

Además de los fantasmas siendo instanciados en diferentes localizaciones del laberinto, se colocaron dos fantasmas en éste en esquinas opuestas. Este fantasma es más grande, posee más vida y hace más daño. Contrario a los otros que caminan hacia la base, estos fantasmas grandes tienen como estado predeterminado a seguir el jugador durante todo el juego y atacarlo si se le acerca a una distancia específica determinada en la máquina de estados finito. La vida de este enemigo se estableció con el mismo script de LifeFinal utilizada con los otros fantasmas pequeños. También, poseen el navigation mesh para caminar por el mapa. 
![Captura de pantalla 2024-12-17 223837](https://github.com/user-attachments/assets/48dfac7c-eb04-4299-8b45-e7cbf56ceca0)

Al igual que con los otros fantasmas, se estableció el rango de visión del fantasma con el mismo código de sight para que pudiese detectar sus alrededores, pero se realizó otro script de máquina de estados finitas para que solamente cambiara de los dos estados ya mencionados. 

### Script de la máquina de estados finito para el fantasma grande
![Captura de pantalla 2024-12-18 003110](https://github.com/user-attachments/assets/1558c3c5-1308-4cac-b98b-ea0917dd7bec)
![Captura de pantalla 2024-12-18 003123](https://github.com/user-attachments/assets/b3bd9424-e4ca-4d79-b6f6-298550d35483)
![Captura de pantalla 2024-12-18 003138](https://github.com/user-attachments/assets/f9c89abc-e494-420c-85ac-a6d93ffab149)
![Captura de pantalla 2024-12-18 003156](https://github.com/user-attachments/assets/e05f70aa-052c-4391-b9d9-c4fe9094d3e1)

## Ataque de los fantasmas 
Los fantasmas, al igual que el jugador, disparan balas hechas como un prefab. Estas balas poseen un tiempo de vida, lo cual significa que si no chocan con algún otro objecto (collider), se destruyen en un tiempo determinado. Por otra parte, se creó un script para que siguiesen moviéndose hacia delante en línea recta cuando son instanciadas desde el enemigo y/o jugador y también se estableció que destruyeran o le quitasen vida al jugador y/o enemigo. Las balas del enemigo y jugador poseen el mismo script y collider esférico; la única diferencia entre ellas sería qué objetos pueden afectar. En los layers de la escena se estableció que la bala de los enemigos interaccione con los jugadores y les quite vida. 

### Script para quitar vida o destruir 
![Captura de pantalla 2024-12-18 003636](https://github.com/user-attachments/assets/62cd6d21-cde2-4a7e-b0df-470b35185474)

### Layers 
![image](https://github.com/user-attachments/assets/d5882569-9e37-4b0e-96dd-58c4359e3997)









