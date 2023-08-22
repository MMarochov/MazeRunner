# Introduction

```
        *                )         
      (  `     (      ( /(              
      )\))(    )\     )\()) (            
     ((_)()\((((_)(  ((_)\  )\            
     (_()((_))\ _ )\  _((_)((_)          
     |  \/  |(_)_\(_)|_  / | __|  
     | |\/| | / _ \   / /  | _|
     |_|  |_|/_/ \_\ /___| |___|
  ________________________________
 |         ___________   ______   |
 |  MAZE  |   _____   |_____   |  |
 |________|  |      ___________|  |
 |___________|  |________   |  |  |
 |  |   ___________|   _____|  |  |
 |  |  |   __         |     |  |__|
 |  |_____   |  |__|  |  RUNNER   |
 |___________|____________________|

 | _ \| | | || \| || \| || __|| _ \  
 |   /| |_| || .` || .` || _| |   /
 |_|_\ \___/ |_|\_||_|\_||___||_|_\
```

Welcome Adventurer. 

Your aim is to navigate the maze and reach the finish point without touching any walls. Doing so will kill you instantly!

## Task

You will be given a 2D array of the maze and an array of directions. Your task is to follow the directions given. If you reach the end point before all your moves have gone, you should return `Finish`. If you hit any walls or go outside the maze border, you should return `Dead`. If you find yourself still in the maze after using all the moves, you should return `Lost`.

The Maze array might look like this:

```
maze = [[1,1,1,1,1,1,1],
        [1,0,0,0,0,0,3],
        [1,0,1,0,1,0,1],
        [0,0,1,0,0,0,1],
        [1,0,1,0,1,0,1],
        [1,0,0,0,0,0,1],
        [1,2,1,0,1,0,1]]
```
..with these directions:
```
directions = ["N","N","N","N","N","E","E","E","E","E"] == "Finish"
```
..and the following key:

```      
0 = Safe place to walk
1 = Wall
2 = Start Point
3 = Finish Point
```



## Rules
1. The Maze array will always be square i.e. N x N but its size and content could alter from test to test.

2. The start and finish positions may change.

3. The directions array will always be in upper case and will be in the format of N = North, E = East, W = West and S = South.

4. If you reach the end point before all your moves have gone, you should return Finish.

5. If you hit any walls or go outside the maze border, you should return Dead.

6. If you find yourself still in the maze after using all the moves, you should return Lost.

## Not sure where to begin?

- Try finding the start point! What's the index of the number 2 in the maze array?

## Example tests

```
@test.describe('Example Tests')

def example_tests():
    maze = [[1,1,1,1,1,1,1],
            [1,0,0,0,0,0,3],
            [1,0,1,0,1,0,1],
            [0,0,1,0,0,0,1],
            [1,0,1,0,1,0,1],
            [1,0,0,0,0,0,1],
            [1,2,1,0,1,0,1]]
    
    @test.it("Should return Finish")
    def example_test_case1():
        test.assert_equals(maze_runner(maze,["N","N","N","N","N","E","E","E","E","E"]), "Finish")
        test.assert_equals(maze_runner(maze,["N","N","N","N","N","E","E","S","S","E","E","N","N","E"]), "Finish")
        test.assert_equals(maze_runner(maze,["N","N","N","N","N","E","E","E","E","E","W","W"]), "Finish")
    
    
    @test.it("Should return Dead")
    def example_test_case2():
        test.assert_equals(maze_runner(maze,["N","N","N","W","W"]), "Dead")
        test.assert_equals(maze_runner(maze,["N","N","N","N","N","E","E","S","S","S","S","S","S"]), "Dead")
    
    
    @test.it("Should return Lost")
    def example_test_case3():
        test.assert_equals(maze_runner(maze,["N","E","E","E","E"]), "Lost")

```

Kata Sensei: adrian.eyre [Codewars](https://www.codewars.com/kata/58663693b359c4a6560001d6)
