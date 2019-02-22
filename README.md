# The Oklahoma Virtual Academic Laboratory (OVAL)
## Table of contents:
- [Overview](#overview)
- [Known Issues and Bugs](#issues)
- [OVAL Configuration File](#config)
  - [Keywords](#config:keywords)
    - [`Rooms`](#config:keywords:rooms)
    - [`Color`](#config:keywords:color)
    - [`UserName`](#config:keywords:username)
    - [`ModelPath`](#config:keywords:modelpath)
    - [`ScreenshotPath`](#config:keywords:screenshotpath)
    - [`VROffset`](#config:keywords:vroffset)
    - [`DefaultPanels`](#config:keywords:defaultpanels)
<a name="overview"></a>

# Overview
The Oklahoma Virtual Academic Laboratory (OVAL) is a VR-Classroom application designed to encourage remote collaboration between acdaemics. Up to twenty users can inhabit the same VR space, import 3D content, and analyze 3those models with built-in tools.

Please contact Matt Cook (mncook@ou.edu) with any questions, concerns, or recommendations. Enjoy OVAL!
<a name="issues"></a>

# Known Issues and Bugs
- Disable all 3D mouse drivers from 3Dconnexion, or problems with the user interface panels can. This typically manifests as spurious joystick input that interferes with the dropdown menu items and scroll lists.
- Sometimes the Oculus controllers simply disappear. This can be most easily remedied by restarting Windows; restarting the Oculus application alone does not seem to fix this problem.
<a name="config"></a>

# OVAL Configuration File
By default, OVAL looks for a file called `OVAL.config.txt` in the directory from which the program was run. This file consists of *comments* and *keyword lines*, with the latter describing additional configuration details that are passed to the OVAL system at startup.
*Comments* are any line starting with a hash character (`#`), and are ignored by the OVAL software.
*Keywords* are the first word of a non-comment line, and are used to pass information into the OVAL system at startup.
<a name="config:keywords"></a>
## Keywords
- Keywords are *case insensitive*, but any following text is assumed to be *case sensitive*.
- To include a space in a sequence of characters on a keyword line (for e.g. file paths etc.), enclose the text in quotation marks `"like this"`.
<a name="config:keywords:rooms"></a>
### `Rooms`
A `Rooms` line specifies a list of one or more default OVAL group rooms presented to the user for convenience. Room names can also be entered by the user at runtime via the OVAL user interface. Example:
`Rooms Edge iHub "My room name" TestRoom`
<a name="config:keywords:color"></a>
### `Color`
A `Color` line specifies a user-defined color for use in the system. The color is specified by a name, along with red, green, and blue components (with an optional alpha value for transparency). All components are normalized, with values between 0.0 and 1.0; a completely opaque color has an alpha value of 1.0, and a completely transparent color has an alpha value of 0.0. Examples:
`Color MyRed 0.8 0.0 0.0'
'Color "Transparent Blue" 0.0 0.0 1.0 0.5 `
<a name="config:keywords:username"></a>
### `UserName`
The `UserName` line specifies the name assigned to the OVAL user at runtime. If no `UserName` line is present in the config file, OVAL uses the name of the current user account on the local computer. The current `UserName` can be overridden at runtime via the OVAL user interface. Example:
`UserName Me`
`UserName "Humpty Dumpty"`
<a name="config:keywords:modelpath"></a>
### `ModelPath`
The `ModelPath` line specifies the default directory in which OVAL looks for 3D models (a trailing slash character is optional). This approach ensures that all OVAL clients in a networked session can load the same model files, even where the local file systems differ, provided that the model files are located at the same relative path to `ModelPath`. Where not specified, `ModelPath` defaults to the directory from which the OVAL program was run. Example:
`ModelPath C:\Desktop\Models\`
`ModelPath "C:\Desktop\My new models\subdirectory"`
<a name="config:keywords:screenshotpath"></a>
### `ScreenshotPath`
The `ScreenshotPath` line specifies the default directory in which OVAL places screenshots (a trailing slash character is optional). Where not specified, `ScreenshotPath` defaults to [Unity's default output directory](https://docs.unity3d.com/ScriptReference/Application-dataPath.html). Example:
`ScreenshotPath C:\Desktop\Screenshots\`
`ScreenshotPath "C:\Desktop\My Screenshots\OVAL\"`
<a name="config:keywords:vroffset"></a>
### `VROffset`
The `VROffset` line can be used to reposition the starting location (i.e., Cartesian x,y,z position) of the user interface. Example:
`VROffset 1.0 0.0 -2.0`
<a name="config:keywords:networkregion"></a>
### `NetworkRegion`
The `NetworkRegion` line specifies the default geographical server region that OVAL uses to coordinate clients in networked OVAL sessions. This server name corresponds to those used by the [Photon](https://doc.photonengine.com/en-us/realtime/current/connection-and-authentication/regions) middleware. The default value is `us` (specifying a server on the east coast of the U.S.A.). Examples:
`NetworkRegion us`
`NetworkRegion cae`
<a name="config:keywords:defaultpanels"></a>
### `DefaultPanels`
The `DefaultPanels` line specifies the OVAL UI panels that are visible to the user by default. Where not specified, the default panels are those visible in the Unity editor when the OVAL software was built. Panel names include:
- `MoveUIPanel` : Move and show/hide the user interface panels.
- `NetworkPanel` : Allows the user to join networked OVAL sessions.
- `MovePanel` : Changes whether the player, model(s), or lights are currently being moved using the controllers.
- `ModePanel` : Allows the user to select from one of several different modes of operation (e.g. annotate, indicate, measure, etc.)
- `ModelPanel` : Allows loading, hiding, showing etc. different 3D models.
Important note: *A `DefaultPanels` line with no panel names specified will show no panels at all*.
Examples:
`DefaultPanels MoveUIPanel NetworkPanel ModelPanel MovePanel ModePanel`

# OVAL-related Publications
- [Multi-Campus VR Session Tours Remote Cave Art](https://campustechnology.com/articles/2017/10/09/multi-campus-vr-session-tours-remote-cave-art.aspx)
- [Library Journal - University of Oklahoma Expands Networked Virtual Reality Lab](http://lj.libraryjournal.com/2016/08/academic-libraries/university-of-oklahoma-expands-networked-virtual-reality-lab/)
- [Library Journal - Virtual Reality and How to Build an Interdisciplinary Hub](http://lj.libraryjournal.com/2017/09/academic-libraries/carl-grant-virtual-reality-build-interdisciplinary-hub/#_)
- [The Design & Development of an Immersive Learning System for Spatial Analysis and Visual Cognition](http://static1.squarespace.com/static/532b70b6e4b0dca092974dbe/t/5755e2df20c647f04c95598a/1465246433366/pobercook_text+(1).pdf)
- [Virtual Serendipity: Preserving Embodied Browsing Activity in the 21st Century Research Library](http://www.sciencedirect.com/science/article/pii/S0099133317301520)
- [A Hub for Innovation and Learning](https://campustechnology.com/Articles/2018/01/31/A-Hub-for-Innovation-and-Learning.aspx?Page=1)
****************************************************

# OVAL Quickstart Guide
For a video introduction to OVAL, check out 

## Compatible File Types
OVAL can be used to view .obj, .stl, .blend, .fbx, and .dae.

## Controls

### Head Movement
The movement of the field of view is tied to the movement of your head. If you want to look at something, just turn your head.

### Changing Modes
In OVAL, different modes are used for different types of model inspection. The modes can be changed by hitting the drop down menu seen here: 
### Oculus Rift Controls

### HTC Vive Controls
### Annotate Mode

#### Color Selection


### Indicate Function
The indicate function will cause a ping noise and a dot to alert other participants to whatever is pointed to.

## Video Capture

### Utilizing Kaltura and MyMedia
In order to utilize voice capture, OU students/faculty/staff should

## Instructions for Multiplayer Sessions
Up to 100 users can inhabit the same VR space, import any 3D model on the fly, and analyze 3D models with built-in tools. To set up a multiplayer session, each user will need to ensure that the room name on their OVAL session matches with all other users they would like to work with in the same VR space. 

### Voice Chat
When you enter into a room with another user, voice chat is automatically enabled. If you aren’t hearing the other person, check your sound source in windows. Make sure the sound is being pushed to the Rift Headphones and that it is turned up. 

