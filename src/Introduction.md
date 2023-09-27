# Introduction

This is the folder for the Process and Safety project. This project is done by Mika Haarhuis, Tim Scholte Lubberink, Matthijs Seinhorst and Timon Kraan.

To give you an idea of our project, a state diagram has been created below:

```plantuml
@startuml Process_and_Safety
skinparam backgroundColor transparent
left to right direction
'skinparam linetype ortho

component Valve_assembly {
    
    [frame]
    () Assemblyplace -u- frame
    () input_0 -- robot
    () output_0 -- robot
    () "end\neffector" -- robot

    [robot]
    () input_0 -- robot
    () output_0 -- robot

    [sensor]
    sensor --> input_0 : connected
    sensor --> "sensor\nposition"
    
    robot -> assemblyplace

    [cabinet]
    () "robot\npower" -- cabinet
    () "storage\npower" -- cabinet
   
    cabinet -u-> assemblyplace
    robot --> "robot\npower"
    cabinet -r-> output_0
    
    [storage]
    () "sensor\nposition" -- storage
    () "ring\nposition" -- storage
    storage -> placement
    storage --> "storage\npower"

    [ring]
    () shape -- ring
    
    [gripper]
    gripper -l-> shape
    
    ring --> "ring\nposition"
    gripper --> "end\neffector"
}

[building]

() energy -l- building
() location -d- building

frame --> location
cabinet -r-> energy

@enduml
```
```plantuml
@startuml Process_and_Safety
skinparam backgroundColor transparent
left to right direction
'skinparam linetype ortho

component Valve_assembly {
    
    [frame]
    () assemble place -u- frame
    [robot]
    () input_0 -- robot
    () output_0 -- robot
    () "end\neffector" -- robot

    [sensor]
    sensor --> input_0 : connected
    sensor --> "sensor\nposition"
    
    robot -> assemble place

    [cabinet]
    () "robot\npower" -- cabinet
    () "storage\npower" -- cabinet
   
    cabinet -u-> assemble place
    robot --> "robot\npower"
    cabinet -r-> output_0
    
    [storage]
    () "sensor\nposition" -- storage
    () "ring\nposition" -- storage
    storage -> assemble place
    storage --> "storage\npower"

    [ring]
    () shape -- ring
    
    [gripper]
    gripper -l-> shape
    
    ring --> "ring\nposition"
    gripper --> "end\neffector"
}

[building]

() energy -l- building
() location -d- building

frame --> location
cabinet -r-> energy

@enduml
```

