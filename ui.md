# Interfaz del jugador (UI)

Para el UI del juego primero se dibujó una textura que se pudiera repetir.

![CandyCaneHP_1](https://github.com/user-attachments/assets/21215f82-1667-4ec3-aeb0-a22b89868ec2)

Luego se creó una versión más larga de la imagen.

![CandyCaneHP_2](https://github.com/user-attachments/assets/8bc9b1ee-2f5d-4517-9843-3b0050295cc5)

Dentro de Unity se creó un canvas para acomodar todo. Dentro se le colocó la imagen larga (teniendo en cuenta que el recurso está puesta en modalidad `Sprite 2d/UI`) y al lado una caja de texto con el texto preliminar "0/4".

![image](https://github.com/user-attachments/assets/9f9b3709-466a-42ea-b337-aa4f240f1196)

Para que UI fuera funcional se creo un script `UIchecker.cs` para el objecto canvas. El script tiene referencia a la vida del jugador y mantiene una variable con la cantidad de preguntas respuestas. Hay una función update que chequea siempre el estado de la vida del jugador y mantiene la barra al día. Ademas contiene una funcion `AddOne()` que cuando se llama aumenta la variable para la cantidad de preguntas respuestas y actualiza el texto. Para que pueda funcionar bien depende de que otros scripts puedan utilizar su función `AddOne()` así que además es un singleton para que el script `RightAnswer.cs`, activado cada vez que el jugador tenga una respuesta correcta, la pueda utilizar.

Script `UIchecker.cs`
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;
using TMPro;
using UnityEngine.UI;

public class UIchecker : MonoBehaviour
{
    public static UIchecker instance; // Variable for WaveManager

    [SerializeField] LifeFinal playerlife;

    [SerializeField] Image HPBarImage;
    [SerializeField] TextMeshProUGUI texter;

    private int done;

    void Awake()
    {
        if (instance == null) // Check if another instance of WaveManager was created
            instance = this; // If there's not another instance, then instantiate this one

            else // When another instance of WaveManager already exists, display message
                Debug.LogError("Instance duplicated, ignore this");
    }

    // Start is called before the first frame update
    // void Start()
    // {
    //     HPBarImage = GetComponent<Image>();
    //     texter = GetComponent<TextMeshProUGUI>();
    // }

    // Update is called once per frame
    void Update()
    {
        HPBarImage.fillAmount = playerlife.amount / 100;
    }

    public void AddOne() {
        done += 1;
        texter.text = done.ToString() + "/4";
    }
}
```

Pedazo de `RightAnswer.cs` que utiliza `AddOne()`
```
public class RightAnswer : MonoBehaviour
{
    {...}
    void OnTriggerEnter(Collider other)
    {
        {...}
        UIchecker.instance.AddOne();
        {...}    
    }
}
```
