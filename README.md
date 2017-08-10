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
         
         
### Truth table

__C2 = ! (A || D1)__  
    
    general:  C(n) = !( A(n) || D(n-1) )  
    
__D2 = ! (B || C1)__  
    
    general:  D(n) = !( B(n) || C(n-1) )
 
    A  B  C1 D1 | C2 D2
    ------------|-------
     0  0  0  0 |  1  1
     0  0  0  1 |  0  1
     0  0  1  0 |  1  0
     0  0  1  1 |  0  0
     0  1  0  0 |  1  0
     0  1  0  1 |  0  0
     0  1  1  0 |  1  0
     0  1  1  1 |  0  0
     1  0  0  0 |  0  1
     1  0  0  1 |  0  1
     1  0  1  0 |  0  0
     1  0  1  1 |  0  0
     1  1  0  0 |  0  0
     1  1  0  1 |  0  0
     1  1  1  0 |  0  0
     1  1  1  1 |  0  0
 
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

Minimum input assignment duration must be at least 2 * Tp  

    Tp| A B | C D 
    ------------
    00| 0 0 | 0 0 
    01| 0 0 | 1 1 
    02| 0 0 | 0 0 
    03| 0 0 | 1 1 
    04| 0 0 | 0 0 
    05| 0 0 | 1 1 
    06| 1 0 | 0 0 
    07| 1 0 | 1 0 
    08| 0 0 | 1 0 
    09| 0 0 | 1 0 
    10| 0 0 | 1 0 
    11| 0 0 | 1 0 
    12| 0 0 | 1 0 
    13| 0 0 | 1 0 
    14| 0 1 | 0 0 
    15| 0 1 | 0 1 
    16| 0 0 | 0 1 
    17| 0 0 | 0 1 
    18| 1 1 | 0 0 
    19| 1 1 | 0 0 
    20| 0 0 | 1 1 
    21| 0 0 | 0 0 
    22| 0 0 | 1 1 
    23| 0 0 | 0 0 
    24| 0 1 | 0 1 
    25| 0 1 | 0 1 
    26| 0 0 | 0 1 
    27| 0 0 | 0 1 
    28| 0 0 | 0 1 
    29| 0 0 | 0 1 
    
Accounting propagation delay:

    Tp| A B | C D 
    ------------
    01| 0 0 | 1 1 
    03| 0 0 | 1 1 
    05| 0 0 | 1 1 
    07| 1 0 | 1 0 
    09| 0 0 | 1 0 
    11| 0 0 | 1 0 
    13| 0 0 | 1 0 
    15| 0 1 | 0 1 
    17| 0 0 | 0 1 
    19| 1 1 | 0 0 
    21| 0 0 | 0 0 
    23| 0 0 | 0 0 
    25| 0 1 | 0 1 
    27| 0 0 | 0 1 
    29| 0 0 | 0 1 
    
    
    
    
    
    
 _(c) 2017 by Ralf Kronemeyer_  
 


