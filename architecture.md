# Rubik's Cube Engine Project Architecture

``` mermaid
classDiagram

    class Driver{
        -CubeEngine : engine
        -Cube : cube
        -AppGUI : gui

        +Driver(CubeEngine engine, Cube cube, AppGUI gui)
        +runApp() void
    }

    class Engine{
        -CubeScrambler : scambler
        -CubeSolver : solver
        -Cube : cube

        +Engine(cube)
        +scambleCube (Cube cube) Cube
        +solveCube (Cube cube) Cube
        +generateScramble() string
    }

    class Solver{
        -Cube : cube

        -SolveCross(Cube cube, string crossColor) Cube
        -SolveF2L(Cube cube) Cube
        -SolveOLL(Cube cube) Cube
        -SolvePLL(Cube cube) Cube
        -FindCrossPieces(Cube cube) map<string color, vector<vector<int>> positions>
    }

    
```