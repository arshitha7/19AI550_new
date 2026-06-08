# Ex.No: 10 Implementation of 3D Endless Runner Game
### DATE: 02-06-2026                                                                           
### REGISTER NUMBER : 212223240015
### AIM: 
To develop a 3D endless runner game using Unity with player movement, obstacle collision, scoring system, and camera follow mechanics.
### Algorithm:
```
1. Open Unity and create a new 3D project.
2. Create the ground using Plane object.
3. Add a Sphere object as the player.
4. Apply Rigidbody component to the player for physics.
5. Create multiple Cube obstacles on the ground.
6. Write C# script for player movement.
7. Implement automatic forward movement.
8. Add collision detection for obstacles.
9. Create UI score system using TextMeshPro.
10. Add Game Over mechanism.
11. Implement camera follow system.
12. Run and test the game in Unity.
```  
### Program:
## BallMovement.cs
```
using UnityEngine;

public class BallMovement : MonoBehaviour
{
    public float sideSpeed = 10f;
    public float forwardSpeed = 12f;

    void Update()
    {
        // Forward Movement
        transform.Translate(0, 0, forwardSpeed * Time.deltaTime);

        // Left and Right Movement
        float move = Input.GetAxis("Horizontal");

        transform.Translate(move * sideSpeed * Time.deltaTime, 0, 0);

        // Game Over when Ball Falls
        if(transform.position.y < -5)
        {
            Debug.Log("GAME OVER");

            Time.timeScale = 0;
        }
    }
}
```

## CameraFollow.cs
```
using UnityEngine;

public class CameraFollow : MonoBehaviour
{
    public Transform player;

    Vector3 offset;

    void Start()
    {
        offset = transform.position - player.position;
    }

    void LateUpdate()
    {
        transform.position = player.position + offset;
    }
}
```

## ScoreManager.cs
```
using UnityEngine;
using TMPro;

public class ScoreManager : MonoBehaviour
{
    public TextMeshProUGUI scoreText;

    float score = 0;

    void Update()
    {
        score += Time.deltaTime * 10;

        scoreText.text = "Score : " + ((int)score).ToString();
    }
}
```

## GameOver.cs
```
using UnityEngine;

public class GameOver : MonoBehaviour
{
    public GameObject gameOverText;

    void OnCollisionEnter(Collision collision)
    {
        if(collision.gameObject.name.Contains("Obstacle"))
        {
            Debug.Log("GAME OVER");

            gameOverText.SetActive(true);

            Time.timeScale = 0;
        }
    }
}
```

### Output:
<img width="1919" height="1079" alt="image" src="https://github.com/user-attachments/assets/b03b1f94-a7e0-4d88-8fb3-7dfe8079456a" />

<img width="1919" height="1078" alt="image" src="https://github.com/user-attachments/assets/cba826be-1634-4d08-9a0b-33e4a1aeab19" />


### Result:
Thus the 3D endless runner game was successfully developed using Unity and adopted basic game AI technology.
