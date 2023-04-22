# test-cmake-imgui-implot

This repository contains an example project that builds imgui and implot using cmake.

---

## Getting Started

### Dependencies

- git
- cmake
- Your intended graphics API (e.g. OpenGL or DirectX)

### Building the Project

You **do not** have to clone this repo. Simply follow the guidelines below:

1. Create a project folder and a `lib` folder inside it.
2. Inside the `lib` folder, clone the `imgui` and `implot` repositories.
3. ***Optional***: Set up the `imgui` and `implot` repositories as git submodules if your project is also a git repository.
4. ***Optional***: Switch to the `docking` branch of `imgui` for additional functionality.
5. Create a `CMakeLists.txt` file in the `lib` folder, using the example provided in this repository.
6. Create another `CMakeLists.txt` file in the root directory of your project.
7. In this file, add the following code (replace `<your-project-name>` with the name of your project):
```
add_subdirectory(lib)
target_link_libraries(<your-project-name> PUBLIC imgui)
target_link_libraries(<your-project-name> PUBLIC implot)
```
8. Build your project.

### Troubleshooting

If you get an error saying "Cannot open include file: 'imgui.h': No such file or directory", replace the header paths as follows:
- `#include "..\imgui.h"` in `imgui_impl_win32.h` and `imgui_impl_dx12.h`.
- `#include "..\imgui\imgui.h"` in `implot.h`.
- `#include "..\imgui\imgui_internal.h"` in `implot_internal.h`.

### Testing

Your project should now build and run successfuly. To test this you might want to add the code present in ```cmake-imgui-implot/cmake-imgui-implot.cpp``` source file of this repo (taken from demos of ``imgui`` and ```implot```), to your ```main.cpp```.