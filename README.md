# Q-Learning_BOMBERMAN
Using Reinforcment Q-learning to teach the agent how to play a simple Video game BomberMan clone   

This is a simple Q-learning algorythm in python to learn how to play a generic bomberman clone.  
The bomberman enviroment was created in pure python and the sprites are created by the user __VOXEL__ to the http://ludumdare.com/compo/2015/05/05/minild-59-swapshop/ gamejam.  



## Enviroment Rules.

  - A bomb takes 3 turns to explode.  
  - A bomba always explode in a cross shaped area (x+1, x-1, y+1 and y-1)
  - A bomb destroy  wall blocks.  
  - A bomb kills agent.  
  - The max number of turns to finish the game is __100__.
  
 ## Loss function

     def get_reward(self):
        if (self.value_after) > 0:
            r =  (self.value_after**2) * (1 - (self.Turn / float(100) )) 
        else:    
            r = -1 * (self.Turn / float(100))
        return r
 
-------
__self.value_after__: Is a delta generated using the number of blocks reamaning in the scenario before and after the agent perform a give action.  
__self.Turn__: Current turn.  
__round(100)__: Total Number of turns.  
------
The reward is bigger case the agent destroy more blocks in a early game phase. (This function forces the Agent to focused in destroy blocks, instead to spams bombs randomly in empty spaces)

If the agent doesn't destroy any block it will be penalized (negative reward) in a time manner (this will become  more expensive each turn).  


-----

Result after __0__ episodes .   

<img src='https://github.com/LucasSilvaFerreira/Q-Learning_BOMBERMAN/blob/master/0_episode__animated.gif'>  

------
Result after __20000__ episodes .   

<img src='https://github.com/LucasSilvaFerreira/Q-Learning_BOMBERMAN/blob/master/20000_episode__animated.gif'>  

-----

Result after __980000__ episodes (The convergence was a lot early but I posted the last episode).  

<img src='https://github.com/LucasSilvaFerreira/Q-Learning_BOMBERMAN/blob/master/980000_episode__animated.gif'>  
