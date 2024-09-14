# -Interactions-
How to add interaction in Oculus Quest for Unity. The interaction SDK allows to use hands or controllers to manipulate objects. There are several type of interactions such as *Grab*, *Poke*, *Teleport*, *Distance Grab*, and *Snap*. The interaction framework is composed of two components: *Interaction* + *Interactable*. Hands and controllers are rendered and tracked in realtime, and the interaction component is assigned to them. The interactable components are assigned to the objects that will be interacted with.

---

### Step 1: Add a *Camera*

- Add **OVRCameraRig** prefab
- Go to the *Inspector* -> *OVR Manager (Script)* -> *Tracking* -> *Tracking Origin Type =* ***Floor Level***
- Go to the *Inspector* -> *OVR Manager (Script)* -> *Quest Features* -> *Hand Tracking Support =* ***Controllers and Hands***
- Add **OVRInteraction** as a child of **OVRCameraRig**
  
---

# -Grab Interactions-

Grab interactions allow to use digital hands to interact with digital objects. In order to render hands real hands can be tracked or a hand is superimposed to controllers.s

---

### Interaction #1: *Grab* interactions with **Hands**.

**Interactor**

- Add **OVRHands** as a child of **OVRInteraction**
- Create rendering component for hands:
  
  - Create new *Game Object* and name it *LeftOVRHand*
  - Add *OVR Hand (Script)* and set *Hand Type=* **Hand Left**
  - Add *OVR Skeleton (Script)* and set *Skeleton Type=* **Hand Left** and set *Update Root Scale=* **True**.
  - Duplicate *LeftOVRHand* and call it *RightOVRHand*, set *Hand Type=* **Hand Right** and *Skeleton Type=* **Hand Right**
  - Go to  **OVRCameraRig** -> **TrackingSpace** -> **LeftHandAnchor** and add *LeftOVRHand as its child.
  - Go to  **OVRCameraRig** -> **TrackingSpace** -> **RightHandAnchor** and add *RightOVRHand as its child.
 
- Go to **OVRHands** -> *LeftHand* -> *HandInteratorsLeft* and add **HandGrabInteractor** prefab as its child.
- Go to **OVRHands** -> *RighttHand* -> *HandInteratorsRight* and add **HandGrabInteractor** prefab as its child.

**Interactable**

- Create new *Game Object*.
- Add  **Rigidbody** component.
- Add  **Grabbable** script.
- Add **Physics Grabbable** script.
- Add **Hand Grab Interactable** script.


---

### Interaction #2: *Grab* interactions with **ControllerHands**.

**Interactor**

- Add **OVRControllerHands** as a child of **OVRInteraction**
- Create rendering component for hands:
  
  - Create new *Game Object* and name it *LeftOVRHand*
  - Add *OVR Hand (Script)* and set *Hand Type=* **Hand Left**
  - Add *OVR Skeleton (Script)* and set *Skeleton Type=* **Hand Left** and set *Update Root Scale=* **True**.
  - Duplicate *LeftOVRHand* and call it *RightOVRHand*, set *Hand Type=* **Hand Right** and *Skeleton Type=* **Hand Right**
  - Go to  **OVRCameraRig** -> **TrackingSpace** -> **LeftHandAnchor** and add *LeftOVRHand as its child.
  - Go to  **OVRCameraRig** -> **TrackingSpace** -> **RightHandAnchor** and add *RightOVRHand as its child.
 
- Go to **OVRControllerHands** -> *LeftControllerHand* -> *ControllerHandInterators* and add **HandGrabInteractor** prefab as its child.
- Go to **OVRControllerHands** -> *RightControllertHand* -> *ControllerHandInterators* and add **HandGrabInteractor** prefab as its child.

**Interactable**

- Create new *Game Object*.
- Add  **Rigidbody** component.
- Add  **Grabbable** script.
- Add **Physics Grabbable** script.
- Add **Hand Grab Interactable** script.

---

### Interaction #3: *Grab* interactions with **Controllers**.

**Interactor**

- Add **OVRControllers** as a child of **OVRInteraction**
-  
- Go to **OVRControllers** -> *LeftController* -> *ControllerInterators* and add **ControllerGrabInteractor** prefab as its child.
- Go to **OVRControllers** -> *RightController* -> *ControllerInterators* and add **ControllerGrabInteractor** prefab as its child.

**Interactable**

- Create new *Game Object*.
- Add  **Rigidbody** component.
- Add  **Grabbable** script.
- Add **Physics Grabbable** script.
- Add **Grab Interactable** script.
  - Drag **Game Object** to **Pointable Element**
  - Drag **Game Object** to **Rigidbody**

---


# Poke Interactions
---

### Interaction #3: *Poke* interactions with **Controllers**.

**Interactor**

- Add **OVRControllerHands** as a child of **OVRInteraction**
- Create rendering component for hands:
  
  - Create new *Game Object* and name it *LeftOVRHand*
  - Add *OVR Hand (Script)* and set *Hand Type=* **Hand Left**
  - Add *OVR Skeleton (Script)* and set *Skeleton Type=* **Hand Left** and set *Update Root Scale=* **True**.
  - Duplicate *LeftOVRHand* and call it *RightOVRHand*, set *Hand Type=* **Hand Right** and *Skeleton Type=* **Hand Right**
  - Go to  **OVRCameraRig** -> **TrackingSpace** -> **LeftHandAnchor** and add *LeftOVRHand as its child.
  - Go to  **OVRCameraRig** -> **TrackingSpace** -> **RightHandAnchor** and add *RightOVRHand as its child.
 
- Go to **OVRControllerHands** -> *LeftControllerHand* -> *ControllerHandInterators* and add **HandGrabInteractor** prefab as its child.
- Go to **OVRControllerHands** -> *RightControllertHand* -> *ControllerHandInterators* and add **HandGrabInteractor** prefab as its child.

**Interactable**

- Create new *Game Object*.
- Add  **Rigidbody** component.
- Add  **Grabbable** script.
- Add **Physics Grabbable** script.
- Add **Hand Grab Interactable** script.

---

# Rigidbody

In real-world physics, a rigid body is any physical body that does not deform or change shape under physics forces. The distance between any two given points of a rigid body remains constant in time, regardless of external forces exerted on it. To simulate physics-based behavior such as movement, collision, and joints, you need to configure items in your scene as rigid bodies.

 Rigidbody component provides a physics-based way to control the movement and position of a GameObject. Instead of the Transform properties, you can use simulated physics forces and torque to move the GameObject, and let the physics engine
 calculate the results.

 if a GameObject has a Rigidbody, you should use the Rigidbody properties to move the GameObject, instead of the Transform properties. The Rigidbody properties apply forces and torque from the physics system, which change the GameObject’s Transform.

Unity handles physics-based movement globally, not locally. When a GameObject with a Rigidbody moves via physics-based movement, it moves independently of any parent or child GameObject. A child GameObject that has a Rigidbody still uses its parent GameObject to define its local position for initialization, but Unity calculates its physics-based movement in global space.

To control a Rigidbody via script, the primary classes are **AddForce** (to add forces to a GameObject) and **AddTorque** (to apply torque to a GameObject).

---


