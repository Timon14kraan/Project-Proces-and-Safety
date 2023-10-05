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
    () assemble_place -u- frame

    [robot]
    () input_0 -- robot
    () output_0 -- robot
    () "end\neffector" -- robot

    [sensor]
    sensor --> input_0 : connected
    sensor --> "sensor\nposition"
    
    robot -> assemble_place

    [cabinet]
    () "robot\npower" -- cabinet
    () "storage\npower" -- cabinet
   
    cabinet -u-> assemble_place
    robot --> "robot\npower"
    cabinet -r-> output_0
    
    [storage]
    () "sensor\nposition" -- storage
    () "ring\nposition" -- storage
    storage -> assemble_place
    storage --> "storage\npower"

    [ring]
    () shape -- ring
    
    [gripper]
    gripper -l-> shape
    
    ring --> "ring\nposition"
    gripper --> "end\neffector"
}

[building]

() Power -l- building
() location -d- building

frame --> location
cabinet -r-> Power

@enduml
```
```plantuml
@startuml Process_and_Safety
skinparam backgroundColor transparent
left to right direction
'skinparam linetype ortho

component Construction_valve {
    
    [Ring]
    () "concentric outside 10mm" -- Ring
    () "thickness" -- Ring

    [Nut]
    () "screw thread m10" -- Nut
    Nut --> "thickness"

    [cap]
    () "fine thread m10" -- cap

    [tube]
    () "concentric outside 20 mm" -- tube
    () "concentric inside 20 mm" -- tube

    [Nut2]
    () "screw thread m20" -- Nut2
     Nut2 --> "concentric inside 20 mm"


    [House]
    House --> "concentric outside 10mm"
    House --> "screw thread m10"
    House --> "concentric outside 20mm"
    House --> "srew thread m20"
    
}

@enduml
```