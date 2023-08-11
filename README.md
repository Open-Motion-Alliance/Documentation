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


## Techniques of Telemetry Output

### UDP Server

**Note:** Allows the motion software that controls the motion simulator to run on a different device than the game is runing on.

UDP server motion telemetry in gaming refers to the process of collecting and transmitting real-time motion-related data from a game to an external device, often used for motion simulators or other immersive experiences. This data allows the external device, such as a motion platform, to synchronize its movements with the in-game events, enhancing the player's immersion and realism.

Here's how UDP server motion telemetry works in gaming:

1. **Data Generation:** The game's physics engine generates data related to the player's movements, acceleration, rotation, and other relevant motion parameters. This could include data like the player's vehicle position, orientation, velocity, and forces being applied.
2. **UDP Transmission:** The game sends this motion-related data in the form of UDP packets to an external device. UDP is preferred for its low-latency communication, which is crucial for maintaining real-time synchronization between the game and the motion platform.
3. **External Device Interpretation:** The external device, often a motion simulator, receives the UDP packets containing the motion telemetry data. The device interprets this data to determine how it should move and respond to mimic the in-game experience.
4. **Motion Synchronization:** Based on the received data, the motion platform adjusts its movements to match the player's actions in the game. For example, if the player's vehicle accelerates in the game, the motion simulator replicates the sensation of acceleration by tilting or moving the platform accordingly.
5. **Immersive Experience:** This synchronization between the game's actions and the motion simulator's movements enhances the player's immersion and realism. Whether it's flying, driving, or any other activity in the game, the motion simulator provides physical feedback that complements the visual and auditory cues from the game.
6. **Complex Simulations:** Some motion simulators are capable of sophisticated movements like tilting, rolling, pitching, and heaving, allowing players to experience a wide range of in-game motions.

UDP server motion telemetry is particularly popular in racing and flight simulation games, where precise motion replication enhances the sense of speed, g-forces, and the feeling of being in control of a vehicle. However, it can also be used in other genres to provide a more immersive and engaging gaming experience.

It's worth noting that while UDP is great for low-latency and real-time data transmission, it doesn't provide the reliability and error-checking features of TCP (Transmission Control Protocol). Therefore, some telemetry data might be lost or incomplete in cases of network congestion or packet loss.

### Memory Map File

**Note:** Requires the motion software that controls the motion simulator to run on the same device the game is runing on.

Memory-mapped file motion telemetry in gaming involves the use of memory-mapped files to facilitate the exchange of real-time motion-related data between a game and an external device, such as a motion simulator. This approach allows the external device to access and update motion data directly in the game's memory space, enabling synchronized movement with in-game events for an immersive player experience.

Here's how memory-mapped file motion telemetry works in gaming:

1. **Data Sharing:** The game's physics engine generates motion-related data, including information about the player's position, orientation, velocity, acceleration, and other relevant parameters.
2. **Memory Mapping:** The game creates a memory-mapped file in the computer's memory space. This file is used as a shared memory region that both the game and the external device can access.
3. **Data Placement:** The game writes the motion telemetry data directly into the memory-mapped file. The external device, such as a motion platform, can access this data by reading from the same memory-mapped file.
4. **External Device Interaction:** The external device, connected to the computer, reads the motion data from the memory-mapped file in real-time. It interprets this data to determine how it should move or adjust its position to match the player's actions in the game.
5. **Motion Synchronization:** The motion platform adjusts its movements according to the received data from the memory-mapped file. For instance, if the player's in-game vehicle accelerates, the motion platform mirrors this acceleration by adjusting its orientation or movement.
6. **Immersive Gameplay:** By synchronizing the external device's movements with the in-game motion data, players experience a heightened sense of immersion and realism. The physical feedback provided by the motion simulator complements the visual and auditory cues from the game, enhancing the overall gaming experience.
7. **Complex Simulations:** Advanced motion simulators can replicate intricate movements like tilting, pitching, rolling, and more, allowing players to feel the physical sensations of various in-game activities.

Using memory-mapped files for motion telemetry leverages the direct data access benefits of memory mapping, providing a way for the game and external devices to communicate without relying on external protocols like UDP or DLL connections. However, it's important to handle synchronization and potential data conflicts carefully, as multiple processes accessing the same memory-mapped file can lead to issues like race conditions.

It's important to understand that memory-mapped files can be a powerful optimization technique, but they require careful consideration and management. Improper use can lead to memory leaks, performance issues, or crashes. Synchronization mechanisms must be employed when multiple processes or threads access the same memory-mapped resource to prevent data corruption.

The specific implementation of memory-mapped files in games depends on the game engine, programming language, and platform being used. Game developers need to carefully design and implement memory mapping based on the game's requirements and the capabilities of the underlying system.

In summary, memory-mapped file motion telemetry enhances gaming immersion by enabling real-time synchronization between in-game actions and the movements of external devices. It offers a direct communication pathway that can be used to achieve a high level of physical feedback, particularly in racing and flight simulation games, contributing to a more engaging and immersive gameplay experience.

### DLL Connection

**Note:** Requires the motion software that controls the motion simulator to run on the same device the game is runing on.

DLL connection motion telemetry in gaming involves utilizing dynamic link libraries (DLLs) to establish a connection between a game and an external device, like a motion simulator. Through this connection, the game can communicate and exchange real-time motion-related data with the external device, enhancing the player's immersion by synchronizing physical movements with in-game events.

Here's how DLL connection motion telemetry works in gaming:

1. **Data Generation:** The game's physics engine generates motion-related data such as player position, orientation, acceleration, and other parameters relevant to motion simulation.
2. **DLL Integration:** A DLL containing specific code for communication and interaction with the external device is loaded by the game. This DLL acts as an intermediary for exchanging data between the game and the device.
3. **Data Exchange:** The game communicates motion data to the DLL using function calls or other communication mechanisms defined within the DLL. The DLL abstracts the complexities of data exchange, allowing the game to send motion telemetry without directly interfacing with the external device.
4. **DLL Logic:** The DLL interprets the received motion data, translates it into the format expected by the external device, and then sends the data to the device using the appropriate protocols.
5. **External Device Interaction:** The external device, often a motion platform, receives the motion data from the DLL and adjusts its movements accordingly. For instance, if the game's player is driving a car and accelerates, the external device replicates the sensation of acceleration through physical movement.
6. **Motion Synchronization:** As the player's actions in the game trigger motion data, the DLL ensures that the external device's movements remain synchronized with these in-game actions, providing a more immersive experience.
7. **Immersive Gameplay:** The coordinated motion between the game's events and the external device's movements creates a heightened sense of realism for players. The physical feedback from the motion simulator complements the visual and auditory aspects of the game.
DLL connection motion telemetry is a flexible approach that can be used to integrate motion simulation into a wide range of games, such as racing, flight simulation, and virtual reality experiences. It allows for easy integration of external hardware without requiring significant modifications to the core game code.

However, it's important to note that using DLLs involves careful coding to ensure compatibility and proper synchronization between the game, DLL, and external device. Additionally, DLLs must be managed and updated to prevent issues with changes in game versions or compatibility with different devices.

In summary, DLL connection motion telemetry in gaming leverages dynamic link libraries to establish a communication channel between a game and an external motion device. This channel enables real-time data exchange, synchronization, and physical feedback, contributing to a more immersive and realistic player experience.

## Telemetry Structures

@TODO: Add suggested structure for telemetry.

## Resources:

* Wikipedia: Six degrees of freedom https://en.wikipedia.org/wiki/Six_degrees_of_freedom
* YouTube: Euler Angles and the Euler Rotation Sequence https://www.youtube.com/embed/GJBc6z6p0KQ
* YouTube: Computing Euler Angles: The Euler Kinematical Equations and Poisson’s Kinematical Equations https://www.youtube.com/embed/9GZjtfYOXao
