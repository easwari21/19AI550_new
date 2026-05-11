<img width="1883" height="998" alt="Screenshot 2026-05-11 144959" src="https://github.com/user-attachments/assets/55682044-8d4d-45d9-865d-83e10f03be42" /># Ex.No: 5  Implementation of Steering behaviour-Pursue and Evade in Unity
### DATE:                                                                            
### REGISTER NUMBER : 
### AIM: 
To write a program to simulate the process of Pursue and Evade behavior in Unity using NavigationMeshAgent. 
### Algorithm:
```
1. Create a New Unity Project by Open the  Unity Hub and create a new 3D Project.
2. Name the project "SteeringBehaviors" and select a location. Click Create.
3.Open Unity Scene (default is SampleScene).
  In the Hierarchy, create a Plane:
  Right-click → 3D Object → Plane (this will be the ground).
  Set its Scale to (10, 1, 10) for a larger surface.
  Create three Capsule for the Player, Pursuer, and Evader:
  Rename them to "Player", "Pursuer", and "Evader".
  Set their Y Position to 0.5 (so they sit on the ground).
  Change their Material for better distinction (optional).
3. Check AI navigation in window.
 Window → AI → Navigation (opens the Navigation tab).  If it is not available then add package by name "com.unity.ai.navigation"
4. Select the Plane, go to the Navigation tab, and mark it as Navigation Static.
   Go to the Bake tab and click Bake.
   or
   Add navMeshSurface to plane and bake 
4. Add NavMeshAgent Component 
    Select Pursuer, and Evader.
    Click Add Component → Search for NavMeshAgent and add it.
    Adjust NavMeshAgent Settings:
    Player: Set Speed = 5.
    Pursuer: Set Speed = 4.
    Evader: Set Speed = 6.
5. Write a script for  Player_movement behavior and save it

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Player_movement : MonoBehaviour
{
    // Start is called before the first frame update
    public float speed;
    void Start()
    {
        float xdir = Input.GetAxis("Horizontal") * speed;
        float zdir = Input.GetAxis("Vertical") * speed;
        transform.position=new Vector3(xdir,zdir);
    }

    // Update is called once per frame
    void Update()
    {
        
    }
}
**Evader script**
public class Evader : MonoBehaviour
{
    // Start is called before the first frame update
    public NavMeshAgent agent;
    public Transform target;
    public float evadespeed;
    void Start()
    {
        agent= GetComponent<NavMeshAgent>();
    }

    void evade()
    {
        Vector3 fleedir = transform.position - target.position;
        Vector3 evadeposition = transform.position + fleedir.normalized * evadespeed;
        agent.SetDestination(evadeposition);

    }
    // Update is called once per frame
    void Update()
    {
        evade();          
     }
}
**Pursuer script**
public class Pursuer: MonoBehaviour
{
    // Start is called before the first frame update
    public NavMeshAgent agent;
    public Transform target;
    public float speed;
    void Start()
    {
        agent=this.GetComponent<NavMeshAgent>();
    }
       // Update is called once per frame
    void pursue()
    {
       Vector3 targetvelocity=target.position-transform.position;
       Vector3 futurepos = transform.position + targetvelocity.normalized*speed;
       agent.SetDestination(futurepos);
    } 
    // Update is called once per frame
    void Update()
    {
        pursue();          
     }
}
7. Attach the Script to each player,pursuer and Evader.
   Drag & Drop the Target from the Hierarchy into the "Target" field in the script component ( For pursuer and Evader).
12. Run the game 
13. Stop the program
    
```
### Output:

<img width="1883" height="998" alt="Screenshot 2026-05-11 144959" src="https://github.com/user-attachments/assets/cfeaf6f6-8c52-4fa8-b28d-0d820a07ece9" />
<img width="1410" height="976" alt="Screenshot 2026-05-11 145037" src="https://github.com/user-attachments/assets/1d9fde1b-6004-473e-ae86-2129f6d8e6b8" />

<img width="1912" height="1036" alt="Screenshot 2026-05-11 145255" src="https://github.com/user-attachments/assets/1ddf564a-39fd-4d32-96cb-d9574accfef3" />
<img width="1907" height="1002" alt="Screenshot 2026-05-11 145316" src="https://github.com/user-attachments/assets/5428d365-9b63-4772-b2ad-dd442b774784" />

<img width="1637" height="1007" alt="Screenshot 2026-05-11 145329" src="https://github.com/user-attachments/assets/861d2924-5d6e-4909-9573-216047634bfd" />

<img width="1211" height="845" alt="Screenshot 2026-05-11 145345" src="https://github.com/user-attachments/assets/3fb5ea6e-3b60-4edb-a506-10ae60b6b7d3" />
<img width="1907" height="1012" alt="Screenshot 2026-05-11 145443" src="https://github.com/user-attachments/assets/1de9a2b6-1102-49c8-96d3-ce8b053d2907" />





### Result:
Thus the simple pursue and evade behavior was implemented successfully.
