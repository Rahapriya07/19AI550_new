# Ex.No: 10  
# Implementation of 2D Game – Coin Collector Game in Unity

**DATE:**  25-05-2026


**REGISTER NUMBER:**  212224240124

## AIM:
To develop a simple 2D Coin Collector game in Unity using C# scripting and AI-based enemy movement.

---

## Algorithm:
1. Open Unity Hub and create a new 2D project.  
2. Create the player object using a 2D sprite.  
3. Add Rigidbody2D and Collider2D components to the player.  
4. Create collectible coin objects in the scene.  
5. Write a C# script to move the player using keyboard controls.  
6. Detect collision between player and coins.  
7. Increase score whenever a coin is collected.  
8. Create an enemy object with simple AI movement.  
9. End the game when all coins are collected or when the enemy touches the player.  
10. Run and test the game in Unity.

---

## Program:

### PlayerMovement.cs
```csharp
using UnityEngine;

public class PlayerMovement : MonoBehaviour
{
    public float speed = 5f;

    void Update()
    {
        float moveX = Input.GetAxis("Horizontal");
        float moveY = Input.GetAxis("Vertical");

        transform.Translate(new Vector3(moveX, moveY, 0) * speed * Time.deltaTime);
    }
}
```

### CoinCollect.cs

```
using UnityEngine;
using UnityEngine.UI;

public class CoinCollect : MonoBehaviour
{
    public Text scoreText;
    private int score = 0;

    void OnTriggerEnter2D(Collider2D other)
    {
        if (other.gameObject.CompareTag("Coin"))
        {
            Destroy(other.gameObject);
            score++;
            scoreText.text = "Score : " + score;
        }
    }
}

```

### EnemyAI.cs
```
using UnityEngine;

public class EnemyAI : MonoBehaviour
{
    public Transform player;
    public float speed = 2f;

    void Update()
    {
        transform.position = Vector2.MoveTowards(
            transform.position,
            player.position,
            speed * Time.deltaTime
        );
    }
}
```
## Output:



## Result:

Thus the game was developed using Unity and adopted Artificial Intelligence technology.
