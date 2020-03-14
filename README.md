# Shader Graphs MToon for URP VR

![main](README/ShaderGraphsMToon.jpg)  

## Requirements
- Unity 2019.3.5f1  
    - Universal RP 7.1.8  

## Getting Started

Open SimplestarGame/ShaderGraphsMToon/Scenes/SampleScene  

Play VR Single Pass Stereo Rendering Mode.

A cube GameObject has the MToon Shader.  

![graph](README/shadergraph.jpg)  

## Check Example VRM Scene

1. Find VRMMaterialImporter if you use [UniVRM package](https://github.com/vrm-c/UniVRM)  
    Edit lines as follows.
 ```cs
 // 1 select shader
 var shaderName = item.shader;
 ↓
 var shaderName = "Shader Graphs/MToon";//item.shader;

 // 2 use geometry queue
 material.renderQueue = item.renderQueue;
 ↓
 material.renderQueue = (int)UnityEngine.Rendering.RenderQueue.GeometryLast < item.renderQueue ? (int)UnityEngine.Rendering.RenderQueue.GeometryLast : item.renderQueue;
 ```
Load Result in SimpleViewer scene of [UniVRM Sample package](https://github.com/vrm-c/UniVRM).

You should learn about [MToon](https://www.slideshare.net/VirtualCast/vrm-mtoon) (Japanese).
