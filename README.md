# OpenGL & GLFW Setup Guide for VS Code

Welcome to this repository! This guide provides a straightforward, logical approach to setting up a modern Computer Graphics environment using OpenGL, GLFW, and GLAD in Visual Studio Code.

## ⚠️ Prerequisites
Before proceeding, ensure your system meets the following requirements:
*   **Operating System:** Windows 10 or 11 (64-bit).
*   **Internet Connection:** Required for downloading MSYS2 packages and GLAD generation.
*   **Editor:** Visual Studio Code installed.

## ⚙️ Installation Steps
1. Install MSYS2 from msys2.org. Run pacman -S mingw-w64-ucrt-x86_64-gcc. Add bin paths to System Envs!
2. Download GLFW from glfw.org. Windows users must select 64-bit binaries. Mac/Linux users can use Homebrew or apt-get. We highly focus on Windows UCRT64 setups for seamless integrations and stability.
3. Generate GLAD at glad.dav1d.de. Select C/C++, OpenGL Core Profile API 3.3+. Click generate, download the ZIP file, and extract the include headers and glad.c source file into your project directory.
4. Install C/C++ and CMake Tools extensions in VS Code. Do not use tasks.json for pro setups; use CMakeLists.txt to automatically link GLFW and GLAD, ensuring a scalable and automated building process.
5. Test the environment by creating main.cpp. Initialize glfwInit() and gladLoadGLLoader(). If a blank window appears without an error, your graphical configuration is perfectly linked and ready to use.

## 📂 Project Structure
To avoid errors, ensure your project directory matches this exact structure. We use a local `dependencies` folder to isolate the library from the global system:

> 📁 Your_Project_Name
> ├── 📁 dependencies
> │   ├── 📁 include
> │   │   ├── 📁 glad
> │   │   ├── 📁 GLFW
> │   │   └── 📁 KHR
> │   ├── 📁 lib
> │   │   └── 📄 libglfw3.a
> │   └── 📁 src
> │       └── 📄 glad.c
> ├── 📁 .vscode (For manual configuration)
> │   ├── 📄 tasks.json
> │   └── 📄 launch.json
> ├── 📄 CMakeLists.txt (For automated builds)
> └── 📄 main.cpp

## 🚀 Build & Run Instructions
Depending on your preferred workflow, choose one of the following methods to run the project:

**Method A: Using Automated CMake (Recommended)**
1. Open the project folder in VS Code.
2. Ensure the `CMake Tools` extension is active.
3. Look at the bottom blue status bar in VS Code, click the **Build** button.
4. Click the **Play (Launch)** icon right next to it to run the application.

**Method B: Using tasks.json (Manual Automation)**
1. Open `main.cpp` so it becomes the active tab on your screen.
2. Go to the left panel, click the **Run and Debug** icon.
3. Select your dynamic configuration from the dropdown.
4. Click the Green Play button.
