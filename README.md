# Soft Body Simulation

![gif](https://i.imgur.com/rUUmGSK.gif)
![gif](https://i.imgur.com/mUOUfAU.gif)

This is a quick exploration of soft body simulation. I'm interested in simple, procedural methods for deforming meshes in response to their collision with other objects, specifically, character meshes made of jelly (slimes!). All animations in this project are procedural, and result from the soft body simulation.

## Play in Unity Editor
Download and open this project with Unity Editor 2018.2. Then open the simplest scene, under Scenes/OneSlimePrototype, and press play. To view the point mass locations and springs, click the Gizmos button above the Game window to make sure it is highlighted. Be aware that displaying gizmos in scenes with many soft bodies may have a noticeable effect on framerate.

## Code Sample
I have written this code as a personal project. My code can be found in the Assets/Scripts/ directory, as *.cs files (ignore *.meta files).

## My Next Steps
* Create a high performance ECS/Job system version, perhaps without using Unity's collision system
* Create a free form deformation shader that uses the point mass locations, or perhaps just applies shears
* Better enforce the fixed volume of the softbody during compression, modelling a fluid like water, which typically stays close to constant volume

## My Previous Steps
* Simulate lots of soft bodies, with some variety of meshes, in a new test scene. Evaluate frame rate, and check that dimensions of soft body can be configured via the transform's scale
* See how many springs I can remove until the simulation destabilizes
* Experiment with the public coefficient properties to find values that lead to numerically stable simulation, while allowing for a pleasing amount of deformation
* Assemble point masses in a bounding box shape, and create a spring lattice, adding springs and experimenting with coefficients until the simulation doesn't collapse over time
* Combine pressure simulation with the mass spring system, to simulate a volume of air
* Alter the pressure simulation to attempt to maintain constant volume, similar to a water balloon (since water doesn't noticeably compress under typical forces).
* Apply a nonuniform scale on a mesh associated with the soft body simulation
* Give the soft body a periodic jump behavior, to keep things lively
* Create a procedural animation for the build up to the jump by negating the instantaneous jump velocity (impulse) to drive the soft body into the ground, which causes it to compress and then rebound into the air
* Clean up the prototype (MonoBehavior) code a bit
* Write the code

## Author
Chris March
https://github.com/chrismarch

