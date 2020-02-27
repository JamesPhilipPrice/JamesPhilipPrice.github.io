## 2D Boat racing game
### (For module CMP4264 2D Game Programming)

**Project description:** The given task given was to create a 2D side scrolling game that revolved around boat racing. The theme of the game was to be chosen from a list given and this game's theme is speedboats. The brief for the game sets out the following requirements for the final version of the game:
```
- Scrolling background and foregrounds with discernible parallaxing being implemented.
- Boat can move forward, backwards as well as rotating left and right.
- Fully functioning user interface displaying player lives, health, scores and timer.
- Penalty system which is displayed in fully working UI.
- Playable with keyboard as well as Xbox controller or equivalent.
- Four uniquely different randomly timed obstacles / challenges.
- Playable by two players.
- Implementation of two unique rewards, bonuses or power ups which are correctly displayed in fully working UI.
- Opponent sabotage mechanics.
- Weather condition / physics implemented which are relevant to the theme.
```
The editor used to create the game was Unity (version 2019.1.10f1), as required by the brief and the rationale for this module was to give and introduction to Unity.
The resulting game is the first game created by myself in the Unity engine.
---
### Game description

**Game premise:** The game is a speedboat racing game that is playable by two players, with either keyboard or Xbox controls. The objective of the game is to either be the first to reach the target distance or to be the only player remaining alive, by avoiding the oncoming obstacles.

<img src="images/2DBoatRacing/Overview.jpg?raw=true"/>

**Specific highlights:** A particular component of the game that stood out to me as it was developed was the way of controlling the players, as it taught me that small additions to simple mechanics can go a long way to make the overall experience more satisfying for the player. In this case I am reffering to the speed and turning controls of the boat.
In the game the player sets a target speed for the boat to travel out and the boat accelerates to that target and then holds at that speed, and an example of how I programmed that is below.
```csharp
//Check if boat needs to accelerate
if (CurrentSpeed < CurrentTargetSpeed)
{
    //Check if the difference between the current and target speed is smaller than the acceleration per frame value
    if (CurrentTargetSpeed - CurrentSpeed < AccelerationPerFrame)
    {
        //If the difference is smaller, just set the current speed to the target
        CurrentSpeed = CurrentTargetSpeed;
    }
    else
    {
        //If the difference is bigger, just add the acceleration
        CurrentSpeed += AccelerationPerFrame;
    }
}
else if (CurrentSpeed > CurrentTargetSpeed) //If boat needs to deccelerate
{
    //Check if the difference between the current and target speed is smaller than the acceleration per frame value
    if (CurrentSpeed - CurrentTargetSpeed < AccelerationPerFrame)
    {
        //If the difference is smaller, just set the current speed to the target
        CurrentSpeed = CurrentTargetSpeed;
    }
    else
    {
        CurrentSpeed -= AccelerationPerFrame;//Deccelerate
    }
}
```
Though this adds a relatively small change to the handling mechanics, it made the control of the boat feel much smoother and was an improvement over the sharp start-stop speed controls.
