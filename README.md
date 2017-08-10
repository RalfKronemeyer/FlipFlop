# RS FlipFlop 

FlipFlop for Software Simulation purposes

## Requirements

### Idealized Nor-Gate
    
         |------|
    A ---|      |
         | >=1  |O---- C
    B ---|      |
         |------|
         n
         A B | C
         ----|--
         0 0 | 1
         0 1 | 0
         1 0 | 0
         1 1 | 0
         
         
Propagtion delay: __Tp__  
Signal transmit time: __Ts__ ( Tp<__Ts__<2Tp - the time to transfer an Output C to any Input A or B)

Initialization values for simulation purposes:

__A = B = C = 0 __ (this is valid for t<Tp)  
         
### RS FlipFlop Circuit


         |------|
    A ---|      |
         | >=1  |O--+-- C
     +---|      |   |
     |   |------|   |
     |              |
     |____      ____|
          \    /             
           \  /                  
            \/             
            /\
           /  \
     _____/    \_____
     |              |
     |              |
     |   |------|   |
     +---|      |   |
         | >=1  |O--+-- D
    B ---|      |
         |------|
         
Propagtion delay: __2 * Tp__   
         
### Formula         

__C2 = ! (A || D1)__  
    
    general:  C(n) = !( A(n) || D(n-1) )  
    
__D2 = ! (B || C1)__  
    
    general:  D(n) = !( B(n) || C(n-1) )
  
### Truth table
  

    A  B  C1 D1 | C2 D2 | Status     | distance to stable
    ------------|--------------------
     0  0  0  0 |  1  1 | instable   | oo
     0  0  0  1 |  0  1 | stable     | 0
     0  0  1  0 |  1  0 | stable     | 0
     0  0  1  1 |  0  0 | instable   | oo
     0  1  0  0 |  1  0 | transition | 1
     0  1  0  1 |  0  0 | transition | 2
     0  1  1  0 |  1  0 | stable     | 0
     0  1  1  1 |  0  0 | transition | 2
     1  0  0  0 |  0  1 | transition | 1
     1  0  0  1 |  0  1 | stable     | 0
     1  0  1  0 |  0  0 | transition | 2
     1  0  1  1 |  0  0 | transition | 2
     1  1  0  0 |  0  0 | stable     | 0
     1  1  0  1 |  0  0 | transition | 1
     1  1  1  0 |  0  0 | transition | 1
     1  1  1  1 |  0  0 | transition | 1
 
### Switch-On behaviour

A = B = 0

    Tp| A B | C D 
    -------------
     0| 0 0 | 0 0
     1| 0 0 | 1 1
     2| 0 0 | 0 0
     3| 0 0 | 1 1
     4| 0 0 | 0 0
     5| 0 0 | 1 1
     6| 0 0 | 0 0
     7| 0 0 | 1 1
     8| 0 0 | 0 0
     9| 0 0 | 1 1
    10| 0 0 | 0 0
    11| 0 0 | 1 1
    12| 0 0 | 0 0
    13| 0 0 | 1 1

Accounting propagation delay:

    Tp | A  B  | C  D 
   -------------------
     0 | 0  0  | 0  0
     2 | 0  0  | 0  0
     4 | 0  0  | 0  0
     6 | 0  0  | 0  0
     8 | 0  0  | 0  0
    10 | 0  0  | 0  0
    12 | 0  0  | 0  0


### Behaviour of input assignment  

Minimum input assignment duration must be at least 2 * Tp, to get a valid stable storage of A B  

    Tp| A B | C D 
    ------------
    00| 0 0 | 0 0 
    01| 0 0 | 1 1 
    02| 0 0 | 0 0 
    03| 0 0 | 1 1 
    04| 0 0 | 0 0 
    05| 0 0 | 1 1 
    06| 1 0 | 0 0 
    07| 1 0 | 0 1 
    08| 0 0 | 0 1 
    09| 0 0 | 0 1 
    10| 0 0 | 0 1 
    11| 0 0 | 0 1 
    12| 0 0 | 0 1 
    13| 0 0 | 0 1 
    14| 0 1 | 0 0 
    15| 0 1 | 1 0 
    16| 0 0 | 1 0 
    17| 0 0 | 1 0 
    18| 1 1 | 0 0 
    19| 1 1 | 0 0 
    20| 0 0 | 1 1 
    21| 0 0 | 0 0 
    22| 0 0 | 1 1 
    23| 0 0 | 0 0 
    24| 1 0 | 0 1 
    25| 0 0 | 0 1 
    26| 0 0 | 0 1 
    27| 0 0 | 0 1 
    28| 0 0 | 0 1 
    29| 0 0 | 0 1 
    30| 0 0 | 0 1 
    31| 0 0 | 0 1 
    32| 0 0 | 0 1 
    33| 0 1 | 0 0 
    34| 0 0 | 1 1 
    35| 0 0 | 0 0 
    36| 0 0 | 1 1 
    37| 0 0 | 0 0 
    38| 0 0 | 1 1 
    39| 1 1 | 0 0 
    40| 0 0 | 1 1 
    41| 0 0 | 0 0 
    42| 0 0 | 1 1 
    43| 0 0 | 0 0 

    
A B - Combinations can be described as follows

     A B | Description
    -------------------
     0 0 | save
     1 0 | set
     0 1 | reset
     1 1 | instable, if A=0 B=0 follows
    
    
    

Naming convention:

If you set

    S = A
    R = B
    Q1 = D
    Q2 = C

you'll get the naming convention, which is often used

_(c) 2017 Ralf Kronemeyer
