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

https://www.youtube.com/embed/ifUx5B7tlT4

![https://static.wixstatic.com/media/092827_ad27a865a8f543d78f5193261b2bd717~mv2.png](https://static.wixstatic.com/media/092827_ad27a865a8f543d78f5193261b2bd717~mv2.png)

Motion can be inferred through the combination of rotational positioning and translational acceleration. Alternatively, absolute or relative positioning, along with velocity and acceleration values—both translational and rotational—can also be employed.

Incorporating gravitational forces into translational forces/accelerations is another option. The choice between these methods may depend on the underlying physics system implemented within your game engine, with one approach potentially being more straightforward to acquire than the other.

### Rotational Data

When considering rotational axes, it is beneficial to provide both Euler angle data and rotational rate data, rather than relying on just one of these inputs.

#### Pitch

Pitch refers to the forward or backward tilt of the vehicle, expressed in degrees [°].

Think of it as the angle of the vehicle tilting up or down, similar to ascending or descending a hill. This characteristic impacts a variety of vehicle types in similar manners.


#### Roll

Roll pertains to the degree of sideways leaning or tilting of the vehicle to the left or right, expressed in degrees [°].

Visualize this as the angle between the vehicle's side and the horizon. For instance, consider the sensation experienced while navigating a banked curve. This aspect primarily affects airplanes, as cars exhibit minimal horizontal movement.


#### Yaw

Yaw corresponds to the vehicle's orientation in terms of its heading (north, south, east, west), expressed in degrees [°].

Analogous to when rudders are manipulated, causing the aircraft to rotate without rolling or pitching. Additionally, it relates to scenarios in which the rear of a car rotates faster than the front, such as during drifting or encountering traction loss.


### Positional Data

#### Surge

Surge signifies the acceleration of the vehicle along its longitudinal direction, measured in gravitational units [g].

Visualize this as the effect experienced during acceleration or braking. It's responsible for the sensation of gear changes in cars.

#### Sway

Sway represents the vehicle's acceleration in the lateral direction, measured in gravitational units [g].

This force becomes apparent during high-speed turns, causing the vehicle to be "pushed" outward on curves. Among the most significant effects for cars.

#### Heave

Heave denotes the vehicle's vertical acceleration, involving upward and downward movement, measured in gravitational units [g].

For cars, this can be associated with road textures and bumps. In the case of planes, it encompasses turbulence and the sensations felt during takeoff and landing.

### Additional Data

Additional motion effects could benefit from various other state-related information. For instance, data about being on the ground or in the air, the operation of gear (lowering or retracting), motor RPM, wheel slip, and similar factors could prove valuable.

If players have access to pertinent telemetry, they are likely to incorporate it into creating physical gauges for their cockpit setups. Much of the mentioned data would also be relevant for enhancing motion simulation.

## Resources:

* Wikipedia: Six degrees of freedom https://en.wikipedia.org/wiki/Six_degrees_of_freedom
* YouTube: Euler Angles and the Euler Rotation Sequence https://www.youtube.com/embed/GJBc6z6p0KQ
* YouTube: Computing Euler Angles: The Euler Kinematical Equations and Poisson’s Kinematical Equations https://www.youtube.com/embed/9GZjtfYOXao
