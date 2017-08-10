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
         
         
         
         
