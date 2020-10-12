# AR-Note
A study note of AR learning
Handheld AR App Development with Unity
1.	To do AR you need three things: World Tracking, Scene Estimation, and Anchored Overlay Rendering.
2.	Spatial Computing & IMU
 * Spatial Computing means that the app is aware of its location in space and aware of movement, device orientation, and its relationship to the environment. 
 * In order to do spatial computing, IMU, which stands for Inertial Measurement Unit, is needed.
 * An IMU contains several miniature gyroscopes and several miniature accelerometers which can measure both linear acceleration and rotational acceleration, and often contains a magnetometer.
 * Sensor Fusion uses the data from multiple sensors to predict where the IMU should be based on just the current measurement and previous measurement. Using a technique called Kalman Filtering, you can produce highly accurate motion tracking using just IMU data. Both solves the problem of the drift of IMU.
 * SLAM stands for Simultaneous Localization and Mapping, which can help to stabilize tracking for AR.
 * An anchored object is a virtual object that has been attached to some feature that the S.L.A.M system has identified so that it can move around realistically.
3.	Computer Vision and Scene Estimation
 *	Computer Vision helps to analyze the lighting in the scene and pass the information to the app to make the scene more realistic in lighting features.
 *	Computer Vision works best when it has the image data from different directions as well as multiple viewpoints so the longer the app runs, the more accuracy could be attained.
4.	ARCore and ARKit
 *	ARCore is Google’s AR platform which supports both iOS and Android with features of plane detection, point clouds, lighting estimation marker-based images and Cloud anchors. Cloud anchors are uploaded to Google servers and other users will be able to use it as mutual anchor points for multi-user AR experiences without leaking any location information to other users. ARCore also contains augmented images which is used to respond to 2D images.
 *	ARKit is Apple’s AR platform which supports iOS with features of plane detection, point clouds, lighting estimation, marker detection, face detection and shared or persistent worlds. ARKit allows the world map and any anchors that have been added to it to be shared with nearby devices.
 *	ARFoundation supports plane detection, point clouds and lighting estimation.
5.	Mars stands for Mixed and Augmented Reality Studio which is built around the concept of spatial computing.
6.	ARSession, ARSessionOrigin and ARCamera
 *	The ARSession component is responsible for controlling the life cycle of an AR experience which can be used to enable and disable AR features on the fly in the app at run time.
 *	ARSubsystemManager is a static class that has methods and callbacks which allow the app to monitor and control the ARSession lifecycle. The system state enumeration in it lets the app to determine whether AR has been initialized and when it is sending valid tracking information, etc.
 *	The component of ARSessionOrigin’s transform could scale of the virtual content to match the world.
 *	ARCamera is a child of ARSessionOrigin. ARCamera also contains an ARCameraBackground, which replaces the normal background with a light background of what the smartphone camera is seen. Multiple ARCamera can be added in a scene switched but only a single ARCameraBackground can be contained.
 *	Tracked Pose Driver is set up to track the position and rotation of the camera.
7.	Managing Trackables
 * Trackables are relatively stable, real-world features the AR system has detected, which includes planes, point clouds and reference points.
 *	The ARPlaneManager component keeps track of planes and gives notification events when planes are added, removed or updated and these events give an ARPlaneObject with information of convex perimeter and the center of the planes.
 *	The ARPointCloudManager manages the point cloud feature that essentially contains rod distance measurements. The get points method returns a list of points in the PointCloudManager. The point cloud doesn’t contain surface normal.	The ARReferencePointManager manages reference points the app decides to create itself to anchor objects either directly in session space or to specific planes. It is recommended to create an AR reference point explicitly and use that to anchor the virtual content to avoid the virtual content jumping around when moving.
8.	Raycasting
 *	Two kinds of AR Raycasts are supported.
 *	One looks for intersections with planes. It takes a screen position as input which makes it well suited to finding planes where the user touches the screen.
 *	The other looks for points in the point cloud. It requires a Ray with 3D position and direction. A pointCloudRaycastAngleInDegrees could be used to search points using a narrow cone.
 *	Both allow to specify a trackable type so the research can be restricted. A restricted type of plane called WithinPolygon should be used so that it will only match a plane if touched within the visualized area.
 *	The point cloud information doesn’t include a collision mesh so it can’t be detected with a Physics Raycast.
9.	Lighting Estimation
 *	Lighting Estimation is a process to analyze the video information to provide an estimate of the average brightness of the video scene.
 *	Lighting Estimation uses significant processing time so it is disabled by default and it can be enabled by toggling the lighting estimation check box in the Inspector or from code by using subsystem manager’s light estimation requested flag. 
 *	The brightness will be a float value between 0 and 1 with 0 means completely dark and 1 means completely washed out.
10.	Physics
 *	One way to increase immersion is to increase interactions between the virtual content and the detected geometry from the real world.
 *	The content should have a collision mesh, and use a physics rigid body component to allow it to move around and being thrown, etc.
11.	Occlusion means that real-world geometry should visually hide virtual geometry and vice versa. 
12.	AR requires a different mindset as the developer has little control over the user’s environment. Proper guides should be added to guide the users as many of them use AR for the first time.
