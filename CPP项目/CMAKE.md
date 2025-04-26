  ### cmake
  CMake 是一个开源、跨平台的构建系统，用于管理 C++（及其他语言）项目的编译过程。它通过编写简单的配置文件（`CMakeLists.txt`）来生成特定平台的构建文件（如 Makefile 或 Visual Studio 项目文件），从而简化跨平台开发和构建。

---

### 核心特点

1. **跨平台**：支持 Linux、Windows、macOS 等，生成适合目标平台的构建脚本。
    
2. **声明式配置**：用 `CMakeLists.txt` 描述项目结构、依赖和编译规则，无需手动编写复杂的 Makefile。
    
3. **灵活性**：支持多种编译器（如 GCC、Clang、MSVC）和构建工具（如 Make、Ninja）。
    
4. **模块化**：通过 `find_package()` 集成第三方库（如 Boost、libhv），便于管理依赖。
    

---

### 基本工作流程

1. **编写 CMakeLists.txt**：定义项目名、源文件、目标文件等。
    
2. **生成构建文件**：运行 `cmake` 命令生成 Makefile 或其他构建系统文件。
    
3. **编译项目**：用 `make`（或其他工具）执行构建。
    

---

### 简单示例

假设有一个简单的 C++ 项目：

```
project/
├── main.cpp
└── CMakeLists.txt
```

#### main.cpp

```cpp
#include 
int main() {
    std::cout << "Hello, CMake!" << std::endl;
    return 0;
}
```

#### CMakeLists.txt

```cmake
# 设置最低 CMake 版本
cmake_minimum_required(VERSION 3.10)

# 项目名称
project(HelloCMake)

# 指定 C++ 标准
set(CMAKE_CXX_STANDARD 11)

# 添加可执行文件
add_executable(Hello main.cpp)
```

#### 构建步骤

1. 创建构建目录：`mkdir build && cd build`
    
2. 生成构建文件：`cmake ..`
    
3. 编译：`make`
    
4. 运行：`./Hello`
    

输出：`Hello, CMake!`

---

### 常用命令

- `cmake_minimum_required(VERSION x.x)`：指定最低 CMake 版本。
    
- `project(name)`：定义项目名。
    
- `add_executable(name sources)`：生成可执行文件。
    
- `add_library(name sources)`：生成库文件。
    
- `target_link_libraries(target libraries)`：链接库。
    
- `find_package(name)`：查找并使用外部库。
    

---

### 优点与用途

- **简化构建**：无需为每个平台手动调整编译脚本。
    
- **适合大型项目**：支持子目录、多个目标和依赖管理。
    
- **集成性强**：常用于 C++ 网络编程项目（如搭配 libhv）。
    

例如，在网络编程中，你可以用 CMake 集成 libhv：

```cmake
find_package(hv REQUIRED)
target_link_libraries(your_target hv)
```

---

### 总结

CMake 是 C++ 开发中的强大工具，初学者可以用它快速构建简单项目，进阶开发者则能利用其管理复杂依赖。它特别适合你的后端开发学习目标