# URP-Oculus-Integration-
Adaptation of URP for Oculus Quest in Unity

---

# Resources

Youtube Video:

[2020, TensorFlow 2.2 NVIDIA GPU (CUDA)/CPU, Keras, & Python 3.7 in Linux Ubuntu](https://www.youtube.com/watch?v=dj-Jntz-74g&t=357s)

---

# Required Software versions:

+ **Unity 2021 or 2022**

---

# Installation Steps

1.- Create new project in Unity. 

2.- Choose template: **3D Sample Scene (URP)**

3.- Switch to Android Platform: go to **file** -> **Build Settings** -> **Android** -> **Switch Platform**

4.- Create a new folder named **URP** and move all the installed asset folders.

5.- Install **Oculus Integration** package: go to **Window** -> **Package Manager** -> **Packages: in Project** -> **My Assets** -> **Oculus Integration** -> **Import**

6.- Modify Project Setting: **Edit** -> **Project Settings**

+ **XR Plugin Managment:** -> **Install XR Plugin Managment**
  +  **Android = Oculus**

+ **Player:**
  +  **Color Space = Linear**
  +  **Color Gamut = sRGB**
  +  **Minimum API Level = Android 10 (API Level 29)**
  +  **Scripting Backend = IL2CPP**
  +  **Target Architectures = ARM64**

+ **Graphics**
  + **Select Render Pipeline Settings** box
  + Go to Project Folder and select **UniversalRP-MediumQuality**
  + Go to Inspector Tab and change **Anti Aliasing (MSAA)=4x**
  + Drag **UniversalRP-MediumQuality** file to **Select Render Pipeline Settings** box

 7.- Change all Assets to URP
   +  Go to **Windows** --> **Rendering** --> **Rendering Pipeline Converter**
   +  Change drop down menu to **Built-in to URP**
   +  Select all boxes and click **Initialize Converters**
   +  After finishing click **Convert Assets**


# Activate Passthrough:

1.- Go to **Window** -> **Rendering** -> **Lighting**

2.- Select **Environment**

+ **Skybox Material = None**

3.- Select **OVRCamera** Prefab, then go to the **Inspector**

+ Click **Add Component**
+ Type **OVR Passthrough Layer** and Select it.
+ Go to **Compositing**
    + **Placement = Overlay**

4.- Select **OVRCamera** Prefab, then go to the **Inspector**

+ Go to **OVRManager** Script

  + **Quest Features** -> **General**

      + **Passthrough Support = Supported**
      + **Enable Passthrough = True**
 
  + **Quest Features** -> **Experimental**

      + **Experimental Features Enabled = True**
      + **Enable Passthrough = True**

5.- Select **OVRCamera** ->  **TrackingSpace** -> **CenterEyeAnchored**, then go to the **Inspector**

+ Go to **Camera** Script

  + **Environment**
    + **Background Type = Solid Color**
    + **Background = RGBa(0,0,0,0)** (black color with alpha=0)


