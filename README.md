# Unity-Junior-Programmer-ProjectCode
This first mission in the Junior Programmer pathway will provide you with the core foundation needed to create a wide range of digital experiences in Unity. You’ll learn about fundamental programming concepts such as variables, functions and basic logic through two practical projects.

# Code explination
basically the code is devided into 4 sections:
1. setting the system which  is biult automatically by Unity once yopu created the script like this:

using System.Collections;
using System.Collections.Generic;
using UnityEngine;

2. the variable decleration which is inside the "public" class.
   the public class has
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
        // from the Edit>input Manager we now wnat to use the inputs which is shortcut for ( Input Manager)
        horizontalInput = Input.GetAxis("Horizontal");

        forwardInput = Input.GetAxis("Vertical");
        // move the vehicle forward
        transform.Translate(Vector3.forward * Time.deltaTime * speed * forwardInput);
        // move the vehicle right and left
        //transform.Translate(Vector3.right * Time.deltaTime * turnSpeed);
        //transform.Translate(Vector3.right * Time.deltaTime * turnSpeed * horizontalInput);

        // we turn the vehicle
        transform.Rotate(Vector3.up, horizontalInput * turnSpeed * Time.deltaTime);


        //transform.Translate(Vector3.forward * Time.deltaTime * 20);  //  The transform (class) attached to this GameObject
        // the Translate (method) from transform class is used
        // we want to use Translate method to translate (move the position of our vehicle)
        // Vector3: Creates a new vector with given x, y, z components
    }
}

## to move the car (player) right and left

        horizontalInput = Input.GetAxis("Horizontal");

