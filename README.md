# Template for MuJoCo C++ Development

## How to get this repo running:
- Install MuJoCo using:
    ```
    pip install mujoco
    ```
- Get MuJoCo path using and update path in CMakeLists.txt:
    ```
    pip show mujoco
    ```
- Update xml path in main.cc
- Build project using:
    ```
    mkdir build
    cd build
    cmake ..
    make
    ```
- Run executable generated in build using:
    ```
    ./mjSim
    ```