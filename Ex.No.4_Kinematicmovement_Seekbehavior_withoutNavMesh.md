# Ex.No: 4  Implementation of Kinematic movement -seek and Flee behavior in Unity

### DATE:  11.05.2026                  
### REGISTER NUMBER : 212223240033

### AIM: 
To write a program to simulate the process of seek and Flee behavior in Unity without NavigationMeshAgent. 
### Algorithm:
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project,Name the project (e.g., SeekBehaviorDemo).
2. Create the Moving Object
   In the Hierarchy, right-click → 3D Object → Cube (or Sphere).
   Rename it to Seeker and Reset its position:Select the Seeker, go to Inspector → Transform → Set Position to (0,0,0).
3. Create the Target Object
   Right-click in the Hierarchy → 3D Object → Sphere (or any other shape).
   Rename it to Target. Move it away from Seeker, e.g., set Position to (5, 0, 5).
   Select the Target, add a Material, and change the color. (if needed) 
4. Adding the Seek Behavior Script
   Create the Script-In the Project Window, go to the Assets folder.
   Right-click → Create → C# Script.
5. Write a script for seek behavior and save it
6. Attach the Script
   Select Seeker in the Hierarchy - Drag & Drop the SeekBehavior script onto the Inspector Panel.
   Drag & Drop the Target from the Hierarchy into the "Target" field in the script component.
12.  Write a script for flee behavior and attach it to target
13.  Run the game
14. Stop the program
    
### Program:
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class seekScript : MonoBehaviour
{
    // Start is called before the first frame update
    public Transform target;  // The object to seek
    public float speed = 5f;  // Movement speed
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if (target == null) return;  // Exit if no target is assigned

        // Calculate the desired direction
        Vector3 direction = (target.position - transform.position).normalized;

        // Move the object towards the target
        transform.position += direction * speed * Time.deltaTime;
    }
}
```
```
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class fleeScript : MonoBehaviour
{
    // Start is called before the first frame update
    public Transform target;  // The object to seek
    public float speed = 5f;  // Movement speed
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        if (target == null) return;  // Exit if no target is assigned

        // Calculate the desired direction
        Vector3 direction = (transform.position-target.position).normalized;

        // Move the object towards the target
        transform.position += direction * speed * Time.deltaTime;
    }
}
```
### Output:

<img width="1918" height="1000" alt="Screenshot 2026-05-11 210413" src="https://github.com/user-attachments/assets/3ea62cf9-b327-4d3d-9fc8-d08210a62701" />

<img width="1918" height="1003" alt="Screenshot 2026-05-11 210510" src="https://github.com/user-attachments/assets/9fb9ee75-b7a4-41ef-9f33-e56de89a1c6d" />

<img width="1918" height="1017" alt="Screenshot 2026-05-11 210520" src="https://github.com/user-attachments/assets/7b4f1520-c0f6-4d0b-8d90-ac51b190e7d7" />


<img width="1918" height="992" alt="Screenshot 2026-05-11 210536" src="https://github.com/user-attachments/assets/158018ee-25c0-4311-9b36-5d573638ea3f" />

<img width="1902" height="1013" alt="Screenshot 2026-05-11 210558" src="https://github.com/user-attachments/assets/94e7152e-3c98-47de-b4df-22fdb94e3048" />






### Result:
Thus the simple seek behavior was implemented successfully.
