# EightPuzzle
State space search program on the 8-puzzle problem in which the goal is to rearrange 8 square blocks in order. These blocks have numbers 1 through 8 and a blank square. Uses different heuristics and techniques to create different searching algorithms. 

board.py
  a class for an object representing an eight puzzle board; to create one: initialize with a string permuation of the digits     0-9
  # includes heurisitc functions like the number of misplaced tiles and the distances from the correct position to be used in     the search algorithms
  
state.py
  a class for objects that represent a state in the state-space search tree of an eight puzzle, includes attributes:
    1.) Current Board class
    2.) Previous Board class (predecessor)
    3.) Number of moves it took to get to the current Board state
   # Includes a function that puts the potential children (in the state-space search tree) of the current Board state into a        list
   
searcher.py
  a class for objects that performs different types of state-space search algorithms on an Eight Puzzle
  
  Searcher class:
    class for objects that perform random state-space search on an Eight Puzzle
    
  BFSearcher class:
      class for objects that perform breadth-first
        search (always chooses one of the untested states
        that has the smallest depth (i.e., the smallest
        number of moves from the initial state) on an Eight
        Puzzle; a subclass of the Searcher class
        
  DFSeacher class:
      class for objects that perform depth-first
       search (always chooses one of the untested states
       that has the largest depth (i.e., the largest number
       of moves from the initial state) on an Eight
       Puzzle; a sublclass of the Searcher class
       
  GreedySearcher class:
       class for objects that perform greedy search (an informed search algorithm
       that uses a heuristic function to estimate the remaining cost needed to get
       from a given state to the goal state (how many additional moves are needed);
       uses this heuristic function to assign a priority to each state, and it selects
       the next state based on those priorities
       # in this case, if the heuristic attribute is assigned 1, it uses the distance heuristic; otherwise, it uses the                misplaced tiles heuristic
       
  AStarSearcher class:
        class for objects that perform A search (an informed search algorithm that
       assigns a priority to each state based on a heuristic function, and that selects
       the next state based on those priorities; when A* assigns a priority to a state,
       it also takes into account the cost that has already been expended to get to that
       state (i.e. the number of moves to that state))
       # in this case, if the heuristic attribute is assigned 1, it uses the distance heuristic; otherwise, it uses the                misplaced tiles heuristic
       
eightpuzzle.py
  driver code for solving state-space search on Eight Puzzles
  to run:
    >>> board = Board('045823716')
    >>> eight_puzzle(board, 'BFS', 1)
        inputs:
          * init_boardstr - a string of digits specifying the configuration
            of the board in the initial state
          * algorithm - a string specifying which algorithm you want to use
          * extra - an optional extra parameter that can be used to
            specify either a depth limit or the number of a heuristic function
  This gives information such as the number of moves, the number of states tested for a particular algorithm, and can even give the option to print the solution of every moves. 
   
# Can even process the input text file filename, the input string algorithm that specifies which state-space search algorithm should be used to solve the puzzles, and the input integer extra that can be used to specify an optional parameter for the algorithm being used - either a depth limit or a choice of heuristic:
  This gives information such as the number of puzzles solved, average moves, and average states tested for a particular algorithm
