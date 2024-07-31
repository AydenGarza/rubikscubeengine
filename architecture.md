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

    class CubeEngine{
        -CubeScrambler : scambler
        -CubeSolver : solver
        -Cube : cube

        +Engine(cube)
        +scambleCube (Cube cube) Cube
        +solveCube (Cube cube) Cube
        +generateScramble() string
    }

    class CubeSolver{
        -Cube : cube

        -SolveCube(Cube cube) Cube
        -SolveCross(Cube cube, string crossColor) Cube
        -SolveF2L(Cube cube) Cube
        -SolveOLL(Cube cube) Cube
        -SolvePLL(Cube cube) Cube
        -FindCrossPieces(Cube cube) : map(string color, vector(vector(int)) positions)
        -EvaluateCrosses(map(string color, vector(vector(int)) positions) crosspieces) string
    }
    
    class CubeScrambler{

    }

    class Cube{

    }

    class AlgorithmsOLL{
        <<enum>>
    }

    class AlgorithmsPLL{
        <<enum>>
    }

    class AppGUI{
        
    }

    Driver *-- CubeEngine
    CubeEngine *-- CubeSolver
    CubeEngine *-- CubeScrambler
```