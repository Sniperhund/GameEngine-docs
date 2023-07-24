
# Setup

So now you want to actually create a game

### Install OS dependencies

It's only supported on windows (for now)

#### Windows

 * Install Visual Studio 2022 and select `Desktop development with C++` in the Visual Studio installer
 * Install vcpkg
   * Install `glfw, glad, glm, assimp, bullet3`

### Code Editor / IDE

I would recommend you either use Visual Studio 2022 or JetBrains Rider.

### How the `project` folder is structered

Edit this to be better.

```
Project/
├───configs/
│   └───project.json (this is the actual file name)
├───textures/
│   └───test.png
├───models/
│   └───test.obj
├───maps/
│   └───test.map
```

### Create a new game project

 1. Include and link the core dll
 2. Create a new folder called `project` in your projects working directory.
 3. Edit your main.cpp to look something like this:

```cpp
#define API_IMPORTS // <-- Should either be added in project settings or here in the top of the main file.

#include <Imports.h> // <-- Imports most used header files from the engine.

int main(int argc, char* argv[])
{
    ProgramInfo programInfo;
    // Set your start resolutions
    programInfo.width = 1280;
    programInfo.height = 720;
    
	// The default map loaded from the maps folder inside of the project directory.
    programInfo.defaultMapPath = "DefaultMap.map";
    
	// Initialize the engine and renderer and create the window.
    Engine::Init(programInfo);
    
    return 0;
}
```