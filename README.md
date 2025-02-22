# NUIX-Studio App

[Link to Tsinghua Gitlab repo](https://git.tsinghua.edu.cn/feij19/NUIX-Studio-APP)

## Table of contents
* [General info](#general-info)
* [Technologies](#technologies)
* [Required software and hardware](#required-software-and-hardware)
* [Setup](#setup)
* [Documentation](#documentation)
* [Contributing to the platform](#contributing-to-the-platform)

## General info

<img align="left" width="200" src="https://github.com/FedorIvachev/IoThingsLab-ReadmeFiles/blob/master/Readme/Files/20201030_173803.jpg">
<img align="left" width="200" src="https://github.com/FedorIvachev/IoThingsLab-ReadmeFiles/blob/master/Readme/Files/20201030_175023.jpg">

By using NUIX-Studio App researchers can connect real and virtual IoT devices, test new IoT devices inside VR environment (and don't even need to buy them!)

![](https://github.com/FedorIvachev/IoThingsLab-ReadmeFiles/blob/master/Readme/Files/v0.6/AppInstances.png)
Currenly, the architecture can be represented by four layers:
1. **IoT real world devices.**
2. **openHAB server.** Provides:
	* Synchronization with IoT real world devices;
	* Storage of IoT data.
3. **NUIX-Studio Unity App** Provides API for interaction with virtual world.

## Technologies
NUIX-Studio uses the features of [Microsoft's Mixed Reality Toolkit](https://github.com/microsoft/MixedRealityToolkit-Unity#feature-areas), such as hand tracking and interaction techniques. 

Connection to real-world IoT devices is performed by REST API calls to [openHAB](https://www.openhab.org/download/) server.

## Required software and hardware:
1. Unity 2020
2. openHAB v3.0+

### Additional hardware:
1. Oculus Quest 1 or 2
2. IoT devices

## Setup

[![Watch the videos](https://github.com/FedorIvachev/IoThingsLab-ReadmeFiles/blob/master/Readme/Files/v0.6/VideoPreview.png)](https://space.bilibili.com/698910893/channel/detail?cid=180284&ctype=0)

### openHAB installation

1. Install [openHAB](https://openhab.org/docs/installation/). Set username to "admin" and password to "password".
### openHAB example device adding
2. The server is accessible at <Your IP Address>:8080
3. Go to Settings - Bindings and add Network Binding
4. Go to Things and add a new thing through Network binding Scan
5. Go to Model - Create Equipment from Things and select the recently created thing

### Unity installation

1. [Download Unity Hub](https://unity3d.com/get-unity/download)
2. Install Unity 2020 through the Installs Tab
3. In the Projects Tab, select Add. Open the dowloaded project (either you cloned it or dowloaded as [zip archive](https://github.com/VRSimulator/NUIX-Studio-Client/archive/master.zip))
4. Download [Environments](https://github.com/VRSimulator/NUIX-Studio-APP/releases/download/v0.6/Environments.unitypackage) package, select Import package - Custom package and then import it.
5. Run a Scene from \Assets\NUIX-Studio-Client\openHABIntegration\Scenes

### Oculus installation

1. 

## Documentation

IoT device in VR = 3D mesh + sensors. Each sensor is a data item + interactable object in Unity. Data items are stored on the openHAB server, interactable objects (Widgets) are located in the Assets/NUIX-Studio-Client/openHABIntegration/Prefabs folder.

1. Add real-world IoT devices into openHAB, and they will automatically appear in the NUIX-Studio App. 
2. Enhance these devices' functionality with extra virtual sensors by adding the [supported tags]().
3. Add fully virtual IoT sensors by dragging the Widgets into the Scene in Unity (from Assets/Resources/Widgets).
4. Work simultaneously with the same IoT data by connecting to the same sever from different devices.
5. [Watch tutorial videos](https://space.bilibili.com/698910893/channel/detail?cid=180284)

Item Basic Widgets:
| Item | Widget | Supported | 
| --- | --- | --- |
| Color | Color information (RGB) - Colorpicker GameObject | :heavy_check_mark: |
| Contact | Status of contacts, e.g. door/window contacts. - Two block GameObjects | :heavy_check_mark: |
| DateTime | Stores date and time |
| Dimmer | Percentage value for dimmers - Pinchslider GameObject | :heavy_check_mark: |
| Group | Nest other items / collect them in groups |
| Image | Binary data of an image - texture on a Plane GameObject | :heavy_check_mark: |
| Location | GPS coordinates |
| Number | Values in number format - TextmeshPro GameObject | :heavy_check_mark: |
| Player | Allows control of players (e.g. audio players) - Buttons GameObjects | :heavy_check_mark: |
| Rollershutter | Roller shutter Item, typically used for blinds |
| String | Stores texts - TextmeshPro GameObject | :heavy_check_mark: |
| Switch | Switch Item, used for anything that needs to be switched ON and OFF - Toggle GameObject | :heavy_check_mark: |


### Input simulation
[Input simulation service Documentation](https://microsoft.github.io/MixedRealityToolkit-Unity/Documentation/InputSimulation/InputSimulationService.html)


## Contributing to the platform
请分享新想法, 谢谢！
