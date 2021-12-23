# Mobile Behavior Modeling

Liddle bit of domain modeling. Mobiles have behavior, and they have states: asleep, angry, afraid, etc. I'm thinking of modeling mobile behavior like so: 

1. Define a number of states: DEFAULT, ASLEEP, ANGRY, AFRAID will do for starters. 
2. Define a number of behaviors, to be modeled as a sealed interface of records, e.g., Wander, RunAway, Attack, each with any needed parameters. The number of behaviors can grow as needed; and over time, in theory at least, I would expect to add Custom (which references a custom behavior implemented in Java) and possibly Scripted, which references a behavior script. 
3. Each Mobile has a default behavior (associated with the DEFAULT state) and can optionally have behaviors for the other states. 
4. The Planner system determines the behavior of a mobile based on the behavior for its current state, or its default state if the current state defines no specific behavior. 
5. The logic for the different behaviors is part of the Planner system (except for Custom/Scripted behaviors, which would be associated with the kind of Mobile.) 
 
Gonna be more complicated than that, I'm sure; among other things, I need to handle reactions to being attacked/damaged. But it's a direction.
    
**A Cool Thing:** This applies to the player characters as well. A player character's DEFAULT behavior is to respond to user input, if any. But a character that's AFRAID will follow its behavior for that state.

_Created on 2021-12-22._