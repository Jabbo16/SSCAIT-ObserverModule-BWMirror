# SSCAIT-ObserverModule-BWMirror

## Description

Ported SSCAIT Observer module to Java and BWMirror API.

Tested with BWMirror 2.6 and BWAPI 4.1.2.

**Original work:**

* <https://github.com/Plankton555/SSCAIT-ObserverModule>

**More information can be found at:**

* SSCAIT website: <http://sscaitournament.com/>
* Technical report describing the original module: <https://arxiv.org/abs/1505.00278>

## Requirements

* Latest BWMirror version (2.6 for example) <https://github.com/vjurenka/BWMirror/>
* BWAPI 4.1.2 <https://github.com/bwapi/bwapi/releases>
* JRE 32 bits

## Usage

**Clone this project and add the source code to a package in your Java bot project:**

```cmd
git clone https://github.com/Jabbo16/SSCAIT-ObserverModule-BWMirror.git
```

**Import and create the CameraModule object:**

```java
import cameraModule.CameraModule;
private CameraModule observer;
```

**Call the following methods in your main class at the onStart() method:**

```java
//self and game are the Player and Game objects extracted from the Mirror object
observer = new CameraModule(self.getStartLocation().toPosition(), game);
observer.toggle(); //Used to enable the observer, by default is disabled
```

**Call the following method in your main class at the onFrame() method:**

```java
//Runs the code determining what the observer should be focusing on and handles camera movement
observer.onFrame();
```

**This method should be called when a unit is completed:**

```java
//Is used to inform the observer about unit-creation events
observer.moveCameraUnitCreated(unit);
```