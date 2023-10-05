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

component Structure_of_the_valve {
    
    [Ring]
    () "concentric outside 17.5mm" -- Ring
    () "thickness 6.8mm" -- Ring

    [Nut_m20]
    () "screw thread m20" -- Nut_m20
    Nut_m20 --> "thickness 6.8mm"

    [Plunger]
    () "fine thread m20" -- Plunger

    [tube]
    () "concentric outside 21.3mm" -- tube
    () "concentric inside 20mm" -- tube

    [Nut_m26]
    () "screw thread m26x1.5" -- Nut_26
     Nut_26 --> "concentric inside 20mm"

    [House]
    House --> "concentric outside 17.5mm"
    House --> "screw thread m20"
    House --> "concentric outside 21.3mm"
    House --> "screw thread m26x1.5"
    House --> "fine thread m20"
}

@enduml
```

