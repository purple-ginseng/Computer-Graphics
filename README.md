# Computer-Graphics
GLEW and GLM setups

To set up the required libraries on Windows for the provided OpenGL program (`GLEW`, `GLFW`, and `GLM`), follow these steps:

---

### Step 1: **Install Required Libraries**

1. **Install MinGW (Compiler for C++)**:
    
    - Download [MinGW](https://osdn.net/projects/mingw/releases/).
    - Install MinGW with `gcc`, `g++`, and `make` packages.
2. **Download GLEW**:
    
    - Go to [GLEW official website](http://glew.sourceforge.net/).
    - Download the latest GLEW binary package for Windows.
    - Extract the archive to a directory, e.g., `C:\OpenGL\glew`.
3. **Download GLFW**:
    
    - Visit the [GLFW website](https://www.glfw.org/download.html).
    - Download the precompiled binaries for Windows.
    - Extract to a directory, e.g., `C:\OpenGL\glfw`.
4. **Download GLM**:
    
    - Go to [GLM GitHub page](https://github.com/g-truc/glm).
    - Download the ZIP or clone the repository using:
        
        ```
        git clone https://github.com/g-truc/glm.git
        ```
        
    - Extract or place the folder in `C:\OpenGL\glm`.

---

### Step 2: **Configure Environment Variables**

1. **Set Library Paths**:
    
    - Open "Environment Variables" from the System Settings (`Windows Key + Pause/Break > Advanced System Settings > Environment Variables`).
    - Add the following to the `Path` system variable:
        
        ```
        C:\OpenGL\glew\bin
        C:\OpenGL\glfw\lib-mingw
        ```
        
2. **Define Global Variables for Libraries**: Add the following environment variables in "Environment Variables > System Variables":
    
    - **GLEW_PATH**:
        
        ```
        C:\OpenGL\glew
        ```
        
    - **GLFW_PATH**:
        
        ```
        C:\OpenGL\glfw
        ```
        
    - **GLM_PATH**:
        
        ```
        C:\OpenGL\glm
        ```
        

---

### Step 3: **Set Up Compiler Flags**

When compiling the program, you need to specify the library and include paths. Use the following flags:

- **Include Paths**:
    
    ```
    -IC:\OpenGL\glew\include -IC:\OpenGL\glfw\include -IC:\OpenGL\glm
    ```
    
- **Library Paths**:
    
    ```
    -LC:\OpenGL\glew\lib\Release\x64 -LC:\OpenGL\glfw\lib-mingw
    ```
    
- **Linking Libraries**:
    
    ```
    -lglfw3 -lglew32 -lopengl32
    ```
    

---

### Step 4: **Compile Your Program**

Use the following command to compile your program in `g++`:

```bash
g++ -o OpenGLApp main.cpp -IC:\OpenGL\glew\include -IC:\OpenGL\glfw\include -IC:\OpenGL\glm -LC:\OpenGL\glew\lib\Release\x64 -LC:\OpenGL\glfw\lib-mingw -lglfw3 -lglew32 -lopengl32
```

---

### Step 5: **Test Your Setup**

1. Run the compiled executable `OpenGLApp.exe`.
2. If any error occurs, verify that:
    - The paths to the libraries are correct.
    - The correct `glew32.dll` file is placed in the executable directory.

---
