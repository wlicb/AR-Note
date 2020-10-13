# AR-Note
C# and Shader Tutorials for the Unity Engine - Basics

Game Objects and Scripts  

1. Defining class:   
_using UnityEngine_  
_public class Clock : MonoBehavior { }_
  * Do not need to restrict the access to the class so it is made "public". The default is "internal".  
  * "MonoBehavior" type should be used to inherite the data and functionality from Unity.  

2. Defining Transform components:  
_[SerializeField]_  
_Transform hoursPivot = value, minutesPivot = value, ... ;_  
  * "Transform" indicates that it is a Transform component.  
  * Added "[SerializeField]" before to let Unity detect the component and display it in the inspector window of the game object.
  
3. Rotating:  
 _hoursPivot.localRotation = Quaternion.Euler(x, y, z);_  
  * "localRotation" property means rotating relative to its parent while "rotation" property means rotating the entire object.  
  * The "Quaternion" struct contains the rotation values. It is based on complex numbers and used to represent 3D rotations.  
 
 4. Getting Current Time:  
 _using System;_  
 _Debug.Log(DateTime.Now.Hour);_  
 * "DateTime.Now.Hour" shows current time.
 
 5. Datatype conversion:  
 _const float identifier = 0f;_  
 * Adding "f" converts an int to a float.
 
 6. Omitting the type declaration:  
 _var time = DateTime.Now;_  
  * Can be used when the data type is clearly mentioned in the statements.
 
 Building a Graph
 
 1. Prefabs:  
 * Create an object and drag it into the project window to create a prefab.
 * The prefab scene can be accessed by the "Open Prefab" button.
 * Prefabs are handy ways to configure game objects and it is useful to change asset of all instances of the prefab in the same way by changing the prefab asset.
 
 2. Instantiating Prefabs:  
 _Instantiate(Prefab)_   
 * This will result in an instance being added to current scene.
 
 3. Changing position:  
 _point.localPosition = Vector3.<vector>;_  
 _point.localPosition = Vector3.zero;_  
 * "localPosition" is similar to "localRotation".
 * "Vector3" is a 3D vector to be input to "localPosition".
 * Moving the object along x axis for 1 unit without changing other coordinates can be realized by "right".
 * "right" can be mutiplied.
 * "zero" means zero factor.
 
 4. Changing scale:  
 _point.localScale = Vector3.one / 5f;_  
* "one" means all corrdinates have size of 1 unit, which can be divided by 5 to scale the point to 1/5.

5. Adjusting x, y, z coordinates:  
_Vector3 position;_  
_position.x = 1;_  
* Vector3 enables accessing the three coordinate components independently.

6. Resolution range:  
_[SerializeField, Range(10,100)]_  
_int resolution = 10;_  
* "Range(10,100)" instruct the inspector to use a slider with that range.

7. Set Parent:  
_point.SetParent(transform, false);_  
* "false" will disable the feature that Unity will keep the objectat the original world position, rotation and scale.

8. Defining Array:  
_points = new Transform[resolution]_  
* "points" is the name of the array.
* "Transform" is the type of the array.
* "resolution" is the length of the array.

