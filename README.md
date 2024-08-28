# -Interactions-
How to add interaction in Oculus Quest for Unity

---

# Camera

- Add **OVRCameraRig** prefab
- Go to the *Inspector* -> *OVR Manager (Script)* -> *Tracking* -> *Tracking Origin Type =* ***Floor Level***
- Go to the *Inspector* -> *OVR Manager (Script)* -> *Quest Features* -> *Hand Tracking Support =* ***Controllers and Hands***
---

# Rigidbody

In real-world physics, a rigid body is any physical body that does not deform or change shape under physics forces. The distance between any two given points of a rigid body remains constant in time, regardless of external forces exerted on it. To simulate physics-based behavior such as movement, collision, and joints, you need to configure items in your scene as rigid bodies.

 Rigidbody component provides a physics-based way to control the movement and position of a GameObject. Instead of the Transform properties, you can use simulated physics forces and torque to move the GameObject, and let the physics engine
 calculate the results.

 if a GameObject has a Rigidbody, you should use the Rigidbody properties to move the GameObject, instead of the Transform properties. The Rigidbody properties apply forces and torque from the physics system, which change the GameObject’s Transform.

Unity handles physics-based movement globally, not locally. When a GameObject with a Rigidbody moves via physics-based movement, it moves independently of any parent or child GameObject. A child GameObject that has a Rigidbody still uses its parent GameObject to define its local position for initialization, but Unity calculates its physics-based movement in global space.

To control a Rigidbody via script, the primary classes are **AddForce** (to add forces to a GameObject) and **AddTorque** (to apply torque to a GameObject).

---


