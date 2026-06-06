# AR Furniture Placement App

## Overview
An Augmented Reality (AR) mobile application developed using Unity and ARCore that allows users to visualize furniture in real-world environments before purchase.

## Features
- Plane detection using ARCore
- Real-time furniture placement
- Multiple 3D furniture models
- Interactive AR experience
- Android application support

## Technologies Used
- Unity
- ARCore
- C#
- 3D Models (.glb)

## Project Description
This application enables users to place virtual furniture in their real environment using their smartphone camera. The app detects surfaces and allows real-scale placement of furniture models such as sofas, chairs, tables, and beds.

## Status
Completed as a personal learning project.

## AR Placement Algorithm (Pseudocode)
```text
FUNCTION initARSession():
  START camera feed
  INITIALIZE ARCore/ARKit session with PLANE_DETECTION = HORIZONTAL
  ENABLE depth estimation and light estimation
  SET onPlaneDetected callback → showPlacementIndicator()

FUNCTION onTap(screenCoord):
  raycastResult ← ARSession.raycast(screenCoord, PLANE)

  IF raycastResult EXISTS:
    pose ← raycastResult.hitPose
    PLACE 3DModel at pose.position with pose.rotation
    APPLY PBR material from selectedMaterial
    ENABLE gesture recognizers (translate, rotate, scale)
  ELSE:
    SHOW "No surface detected. Move camera to scan floor."

FUNCTION onMaterialChange(material, color):
  LOAD PBR texture set for (material, color)
  APPLY to active 3D model via GPU shader uniform update
  RE-RENDER current frame with updated material
```

### Technical Concepts Used

* ARCore Plane Detection
* Raycasting for Surface Detection
* Real-World Pose Estimation
* 3D Model Placement
* Physically Based Rendering (PBR)
* Material & Texture Swapping
* Gesture-Based Object Manipulation


Google Drive APK link : https://drive.google.com/file/d/1z_2P6jBn8JDRUf8mBSYXipediLdvIzI8/view?usp=sharing
