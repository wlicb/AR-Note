# AR-Note
C# and Shader Tutorials for the Unity Engine

Basics: 
1. Defining class:   
_using Unity Engine_  
_public class <identifier> : MonoBehavior { }_
  * Do not need to restrict the access to the class so it is made "public". The default is "internal".  
  * "MonoBehavior" type should be used to inherite the data and functionality from Unity.  

2. Defining Transform components:  
_[SerializeField]_  
_Transform <identifier1> = <value>, <identifire2> = <value>, ... ;_  
  * "Transform" indicates that it is a Transform component.  
  * Added "[SerializeField]" before to let Unity detect the component and display it in the inspector window of the game object.
  
3. Rotating:
 _<indentifier>.localRotation = Quaternion.Euler(x, y, z);_  
  * "localRotation" property means rotating relative to its parent while "rotation" property means rotating the entire object.  
  * The "Quaternion" struct contains the rotation values. It is based on complex numbers and used to represent 3D rotations.  
 
 4. Getting Current Time:
 _using System;_  
 _Debug.Log(DateTime.Now.Hour);_  
 * "DateTime.Now.Hour" shows current time.
 
 5. Datatype conversion:
 _const float <indentifer> = 0f;_  
 * Adding "f" converts an int to a float.
 
 6. Omitting the type declaration:
 _var <identifer> = <value>;_  
  * Can be used when the data type is clearly mentioned in the statements.
