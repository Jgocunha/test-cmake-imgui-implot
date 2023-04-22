# test-cmake-imgui-implot
Building imgui and implot using cmake.

---

## Dependencies

1. Make sure you have **git** installed in your computer;
1. Make sure you have **cmake** installed in your computer;
2. Make sure you have your **intended graphics API** installed in your computer (e.g. OpenGL or DirectX).

## Instructions

You **do not** have to clone this repo. Simply follow the guidelines below:

1. Create your project folder (let's call it ```root```);
2. In ```root``` create a ```lib``` folder where you will add external dependecies for your project (in this case ```imgui``` and ```implot```);
3. Go to the ```lib``` folder and git clone ```imgui``` and ```implot```;
4. **Optional** if your project is setup as a git repo, it might be a good practice to setup the ```imgui``` and ```implot``` with git submodules by running ```git submodule add <repository_url> <path>```;
5. **Optional** you might want to checkout the docking branch of ```imgui``` by running ```git checkout docking``` (it has interesting functionalities not present in the ```master``` branch);
6.  Still in your ```lib``` folder create a ```CMakeLists.txt``` file, like the one in the ```lib``` folder of this repo;
7.  To finish create another ```CMakeLists.txt``` file in the  ```root``` dir;
8.  In this file add:
   ```
   add_subdirectory(lib)
   target_link_libraries(<your-project-name> PUBLIC imgui)
   target_link_libraries(<your-project-name> PUBLIC implot)
   ```
9. When you build, you will still get an error:
```
Cannot open include file: 'imgui.h': No such file or directory
```
10.  To fix this (assuming you are using win32 dx12) substitute the header paths:
     - ```#include "..\imgui.h"``` in ```imgui_impl_win32.h```, ```imgui_impl_dx12.h```;
     - ```#include "..\imgui\imgui.h"``` in ```implot.h```;
     - ```#include "..\imgui\imgui_internal.h"``` in ```implot_internal.h```.

Your project should now build and run successfuly. To test this you might want to add the code present in ```cmake-imgui-implot/cmake-imgui-implot.cpp``` source file of this repo (taken from demos of ``imgui`` and ```implot```), to your ```main.cpp```.