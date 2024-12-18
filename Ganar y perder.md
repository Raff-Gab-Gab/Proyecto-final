# Ganar y perder

## Arte

### Perder

Se empezó el lose screen con un boceto de la imagen.

![image](https://github.com/user-attachments/assets/ac34dfb8-3fe1-4a23-8498-ee3faefceae5)

Luego se creó el outline más refinado.

![image](https://github.com/user-attachments/assets/8b606dba-6c9f-4756-b882-acb5ba2d2e23)

Una vez hecho se empezó a colorear. Se colocó un gris de fondo y la calavera de amarillo grisáceo.

![image](https://github.com/user-attachments/assets/aa628bee-03e5-4419-aeec-8b77323ec490)

A la calavera se le aplicaron las sombras.

![image](https://github.com/user-attachments/assets/8d1a6d29-8904-4518-8cfc-b8f216eed11e)

Entonces se coloreó el papel con la nota.

![image](https://github.com/user-attachments/assets/4f62e7cd-dbab-4ee7-a5ee-889c5da62d81)

Se colocó las sombras del papel sobre la calavera.

![image](https://github.com/user-attachments/assets/14b4a333-acfc-4af3-bf95-8cec0d38b54d)

De allí se pintó el fondo, empezando con la grama.

![image](https://github.com/user-attachments/assets/bb8915fb-8334-483b-aa8c-791d86e1a36c)

Se le añaden detalles a la grama para que sobresalga.

![image](https://github.com/user-attachments/assets/df92b4a9-9ac7-44be-a9cb-fa15a1ac09ed)

Además se pintan árboles a lo lejos en el bosque.

![image](https://github.com/user-attachments/assets/7027db32-7eaa-4016-a8ee-9b563b2dbf7b)

Finalmente se le coloca neblina.

![image](https://github.com/user-attachments/assets/e863f2c2-fdc0-42c4-bfce-2003273093f7)

La imagen final:

![Lose Screen](https://github.com/user-attachments/assets/9f3617c9-21b9-4080-a7f3-950210a9b95c)

### Ganar

Se empezó con el boceto de la imagen.

![image](https://github.com/user-attachments/assets/a713da3e-49ae-4e35-aa9c-2a6fc51e677a)

Para el birrete utilizé esta imagen de una tela tomada de [Unsplash](https://unsplash.com/)

![premium_photo-1675802518675-d1c455e396be](https://github.com/user-attachments/assets/096711e8-efca-42f9-bbba-4cd775ffcb64)

De allí dibuje cada pedazo con un color

![image](https://github.com/user-attachments/assets/23efe358-ff73-4832-8072-35c31663d7a1)

y le apliqué la textura por encima.

![image](https://github.com/user-attachments/assets/d72c013a-9eb9-49b0-8924-25a6609de05b)

El birrete con todas las partes se vé así.

![image](https://github.com/user-attachments/assets/1646d6e4-1062-464d-bd4a-a9fc0d8026c0)

Además le coloqué sombras para distinguir entre los distintos elementos y la borla.

![image](https://github.com/user-attachments/assets/a5c7e600-f1ed-4cfb-9ee8-871d9b723272)

Entonces empecé a colocar el fondo. Dibujé los contornos de las cortinas,

![image](https://github.com/user-attachments/assets/a54df160-ed13-46bb-a7b5-d4637b72ee83)

las coloreé de rojo

![image](https://github.com/user-attachments/assets/d9ea2130-abd9-4449-9341-0459a824c4cc)

añadí un fondo violeta (el cual quedó mucho mejor de fondo para las cortinas)

![image](https://github.com/user-attachments/assets/104f8dfc-e85c-4c9a-9201-67d2c27e9cf8)

y finalmente puse el fondo en el medio de color crema.

![image](https://github.com/user-attachments/assets/922a25b7-92b4-4abd-be65-17e0b623afc3)

La imagen final:

![Win Screen](https://github.com/user-attachments/assets/5ebb417d-6c0f-4f68-9345-4ecc9cfe8448)

## Código

Para aregurarse de que el jugador pierda hay un script que está conectado al evento de la muerte del jugador, el cual cambia la escena a `Loser`.

El script `DeathScreenMover.cs`
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.Events;
using UnityEngine.SceneManagement;

public class DeathScreenMover : MonoBehaviour
{
    [SerializeField] LifeFinal playerlife;

    void Start()
    {
        playerlife.onDeath.AddListener(PlayerDied);

    }

    private void PlayerDied() {
        SceneManager.LoadScene("Loser");
    }
}
```

Este script se colocó en un objeto vacío en la escena.

Para ganar colocamos una plataforma justo afuera de la salida del laberinto, para que cuando el jugador saliera pudiera caer encima y cuando colosionara se moviera a la escena `Winner`. Nos aseguramos que la plataforma `isTrigger`.

![image](https://github.com/user-attachments/assets/c20cd67c-d02f-48e0-a2d5-0bc31515a93e)


El script `EndingMover.cs`
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using UnityEngine.SceneManagement;

public class EndingMover : MonoBehaviour
{
    void OnTriggerEnter(Collider Other)
    {
        SceneManager.LoadScene("Winner");
    }
}
```

## Conectar las escenas y el build settings

Se crearon tres escenas totales en el juego: la escena principal, el Win Screen y el Lose Screen.

![image](https://github.com/user-attachments/assets/d2dbe915-9c5b-492b-9bc6-b2b0ee867865)

En la escena `Winner` se colocó un canvas con la imagen dibujada.

![image](https://github.com/user-attachments/assets/deec1d66-f475-4621-8877-e9f36b1a001f)

Se hizo lo mismo para la escena `Loser`.

![image](https://github.com/user-attachments/assets/e14a08f5-8015-4006-9935-fe0a0667f29d)

Una vez hecho se abrieron los `Build Settings` de Unity para añadir las escenas nuevas y que puedan funcionar con el código provisto.

![image](https://github.com/user-attachments/assets/6b15186f-fc1c-4d87-834e-44bd4ccb8316)
