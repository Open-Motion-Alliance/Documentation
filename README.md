# Motion Telemetry

Motion telemetry is a concept that plays a crucial role in enhancing the realism and immersion of games and motion simulators. It involves providing data related to the movement and position of objects, vehicles, or characters within a virtual environment. This data is typically converted by motion software to recreate realistic motion and physics effects via a motion simulator.

In the context of games and motion simulators, motion telemetry serves several key purposes:

1. **Realism and Immersion:** Motion telemetry helps create a more immersive experience for players by accurately replicating the movements and physics of the virtual world. This enhances the feeling of being present in the game or simulation and can lead to a more engaging and entertaining experience.
    
2. **Enhanced Gameplay:** In racing games and flight simulators, motion telemetry can provide players with realistic feedback about their vehicle's movement, speed, and orientation. This enables players to make more informed decisions and improve their skills by reacting appropriately to changing conditions.
    
3. **Training and Skill Development:** Motion simulators, often used in professional training settings (such as pilot training or driver education), rely heavily on motion telemetry. By accurately replicating real-world scenarios and vehicle dynamics, these simulators help individuals develop and refine their skills in a safe and controlled environment.
    
4. **Motion Simulation:** Motion simulators use telemetry data to drive the physical movements of the simulator platform. For example, a driving simulator might tilt, turn, and vibrate to mimic the sensations of acceleration, braking, and cornering. This helps users feel as if they are actually driving a vehicle.
    
5. **Customization and Tuning:** Motion telemetry data can be used to customize the experience for different users. For example, in racing games, players might have the ability to adjust the sensitivity of their steering or the intensity of vibrations based on their preferences and skill level.
    
6. **Integration with VR and AR:** When combined with virtual reality (VR) or augmented reality (AR), motion telemetry can create a seamless blend of the physical and virtual worlds. This further enhances immersion by synchronizing the user's movements with their in-game or in-simulation actions.
    

In summary, motion telemetry is a critical technology that bridges the gap between virtual experiences and real-world sensations. It enhances the realism, engagement, and educational value of games and motion simulators by providing accurate data and feedback about movement and position.


## Basics of Motion Telemetry

Here is a simple animation that basically shows the 6 degree of freedom (6-DOF) axes of movement

<iframe width="560" height="315" src="https://www.youtube.com/embed/ifUx5B7tlT4" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

![https://static.wixstatic.com/media/092827_ad27a865a8f543d78f5193261b2bd717~mv2.png](https://static.wixstatic.com/media/092827_ad27a865a8f543d78f5193261b2bd717~mv2.png)

### Rotational Axes

For rotation axes it valuable to supply both Euler angle data and rotational rate data instead of having just one.

#### Pitch

Pitch is the tilt of the vehicle forwards or backwards in degrees [°]

Simply the angle of the vehicle up or down like when you go up a hill or down a hill. Affects most vehicle types in similar ways.


#### Roll

Roll is how much the vehicle is dipped to the left or right in degrees [°]

Think of this as angle of the vehicle side to side vs the horizon. Imagine when you are in a banked curve. Mostly affects planes as cars move very little horizontally.


#### Yaw

Yaw is the heading of the vehicle (north, south, east, west) in degrees [°] 

Like when you press the rudders and the plane twist without rolling or pitching, or when the back part of your car is rotating quicker than the front part. Like for example, when you are drifting or experiencing traction loss in a car.


### Positional Axes

#### Surge

Surge is the acceleration of the vehicle in longitudinal direction [g]

Imagine when you are accelerating or breaking. This is the effect that makes you feel gear changes on cars.

#### Sway

Sway is the acceleration of the vehicle in the lateral direction [g]

This is the gravitational force when you are in a high speed curve and your car is been "pushed" to the outside of the curve. One of the most important effects for cars.

#### Heave

Heave is the acceleration of the vehicle up and down [g]

Imagine for a car, the road texture and bumps. For planes, turbulence, when you lift off and land on the ground



## Resources:

* Wikipedia: Six degrees of freedom https://en.wikipedia.org/wiki/Six_degrees_of_freedom
* YouTube: Euler Angles and the Euler Rotation Sequence https://www.youtube.com/embed/GJBc6z6p0KQ
* YouTube: Computing Euler Angles: The Euler Kinematical Equations and Poisson’s Kinematical Equations https://www.youtube.com/embed/9GZjtfYOXao
