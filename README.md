# Unity-Junior-Programmer-ProjectCode
This first mission in the Junior Programmer pathway will provide you with the core foundation needed to create a wide range of digital experiences in Unity. You’ll learn about fundamental programming concepts such as variables, functions and basic logic through two practical projects.

* most of the codes and the instrustions here are from Unity learn website

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

## Base left/right movement on input

1. From the top menu, click Edit > Project Settings, select Input Manager in the left sidebar, then expand the Axes fold-out to explore the inputs
2. In PlayerController.cs, add a new public float horizontalInput variable
3. In Update, assign horizontalInput = Input.GetAxis("Horizontal");, then test to see it in inspector
4. Add the horizontalInput variable to your left/right Translate method to gain control of the vehicle
5. In the Inspector, edit the turnSpeed and speed variables to tweak the feel

![image](https://github.com/Meshaal-Mouawad/Unity-Junior-Programmer-ProjectCode/assets/72484101/2f9ee291-2f19-46c7-9279-a1b150c06653)

## Take control of the vehicle speed

1. Declare a new public forwardInput variable
2. In Update, assign forwardInput = Input.GetAxis("Vertical");
3. Add the forwardInput variable to the forward Translate method, then test

![image](https://github.com/Meshaal-Mouawad/Unity-Junior-Programmer-ProjectCode/assets/72484101/00af9d40-f0ad-4135-bb2c-f092a20c01ca)

## Make vehicle rotate instead of slide

1. In Update, call transform.Rotate(Vector3.up, horizontalInput), then test
2. Delete the line of code that translates Right, then test
3. Add * turnSpeed * Time.deltaTime, then test

   ![image](https://github.com/Meshaal-Mouawad/Unity-Junior-Programmer-ProjectCode/assets/72484101/ec6f2a4e-47cf-4490-b044-528a6cedc4d5)

## the copmlete code will be like this:

    public class PlayerController : MonoBehaviour
    {
    private float speed = 5.0f;
    private float turnSpeed = 25.0f;
    // Start is called before the first frame update
    private float horizontalInput;
    // to move forward using A S D W of the arrows in the keyboard
    private float forwardInput;

    void Start()
    {
        
    }

    // Update is called once per frame
    void Update()
    {
        horizontalInput = Input.GetAxis("Horizontal");
        forwardInput = Input.GetAxis("Vertical");
        
        // move the vehicle forward
        transform.Translate(Vector3.forward * Time.deltaTime * speed * forwardInput);
        // we turn the vehicle
        transform.Rotate(Vector3.up, horizontalInput * turnSpeed * Time.deltaTime);

    }
    )

