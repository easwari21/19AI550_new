# Ex.No: 2  Welcome Script in Unity
### DATE: 27.04.2026                                                                        
### REGISTER NUMBER : 212223240033

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
    // Start is called before the first frame update
    void Start()
    {
        print("Welcome to Unity");
    }

    // Update is called once per frame
    void Update()
    {
        
    }
}
```
### Output:

<img width="1907" height="1015" alt="Screenshot 2026-04-27 140830" src="https://github.com/user-attachments/assets/d5ba82dd-d38e-4e8f-8e08-b27ad56ab623" />

### Result:
Thus the welcome script was printed on Console Window  sucessfully.

