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

__A=B=C=false__ (this is valid for t<Tp)  
         
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
         
         
### Truth table

__C2 = ! (A || D1)__  
    
    general:  C(n) = !( A(n) || D(n-1) )  
    
__D2 = ! (B || C1)__  
    
    general:  D(n) = !( B(n) || C(n-1) )
 
    A  B  C1 D1 | C2 D2
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
     0  0  0  0 |  1  1
