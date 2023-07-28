# Unity-Junior-Programmer-ProjectCode
This first mission in the Junior Programmer pathway will provide you with the core foundation needed to create a wide range of digital experiences in Unity. You’ll learn about fundamental programming concepts such as variables, functions and basic logic through two practical projects.

# Code explination
basically the code is devided into 4 sections:
1. setting the system which  is biult automatically by Unity once yopu created the script like this:

using System.Collections;

using System.Collections.Generic;

using UnityEngine;

2. the variable decleration which is inside the "public" class (example the PlayerController) we can set up the varibles
   the public class has:
   
   - void start: where we coding for the begining of our project ( game).
     void Start()
     
   - void update: where we coding while the player(for example) if in the moving status.
  void Update()

Here is an example:

public class PlayerController : MonoBehaviour
{
   
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        
    }
}

3. inside the public class we can use the functions or methods that already biult in Unity, an axample of this is if we wanted to move a car.


## to move the car (player) right and left with respect to the speed

![image](https://github.com/Meshaal-Mouawad/Unity-Junior-Programmer-ProjectCode/assets/72484101/35cc10e1-f494-4f40-9099-0fae20c13478)

public class PlayerController : MonoBehaviour
{
    private float speed = 5.0f;
    private float turnSpeed = 25.0f;
    private float horizontalInput;
    
    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        horizontalInput = Input.GetAxis("Horizontal");
        // move the vehicle right and left
        transform.Translate(Vector3.right * Time.deltaTime * turnSpeed);
    }
}

## To rotate the vehicle, we may add this:


