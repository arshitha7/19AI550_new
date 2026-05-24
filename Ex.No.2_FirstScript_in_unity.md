# Ex.No: 2  Welcome Script in Unity
### DATE: 27/04/2026                                                                           
### REGISTER NUMBER : 212223240015
### AIM: 
 To learn the basic scripting in Unity and print welcome message in Console window. 
### Procedure:
1. Start the program
2. Open the Unity hub and Create a new 3D project
3. In Assets window, create the new folder and name it as Scripts
4. Create a new script with file name as FirstScript
5. Open the Script and print message "Welcome to Unity" inside the start function
6. Save the script
7. Create a new 3D game object in Hierarchy window and name it as 3DObject.
8. Add the component Firstscript in inspector window of 3Dobject.
9. Run the program
10. Stop the program.
### Program 
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class FirstScript : MonoBehaviour
{
    // Start is called once before the first execution of Update after the MonoBehaviour is created
    
    public Transform object1;
    void Start()
    {
        //print("Welcome to unity");
         print("Welcome to unity");
    }

    // Update is called once per frame
    void Update()
    {
        //print("Welcome to unity");
        //transform.Translate(0.02f, 0, 0);
        //transform.position+=new Vector3(0.02f, 0, 0);
        if(Input.GetKeyDown(KeyCode.Space)){
        object1.position+=new Vector3(0, 0, 2f);
        }
    }
}

```
### Output:

<img width="1918" height="1078" alt="ai for games 2 2" src="https://github.com/user-attachments/assets/81993a33-1eae-4c25-9e26-171fbb832185" />



### Result:
Thus the welcome script was printed on Console Window  sucessfully.

