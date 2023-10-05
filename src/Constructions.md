# Constructions

This is the folder for the Process and Safety project. This project was carried out by Mika Haarhuis, Tim Scholte Lubberink, Matthijs Seinhorst and Timon Kraan. During the start of the project we wrote two diagrams. These are shown below. The first diagram is a component diagram showing the construction of the valve. All parts are named and it is shown how everything is connected.

Component diagram:
```plantuml
@startuml Process_and_Safety
skinparam backgroundColor transparent
left to right direction
'skinparam linetype ortho

component Structure_of_the_valve {
    
    [Ring]
    () "concentric\noutside\n17mm" -- Ring
    () "thickness\n6.8mm" -- Ring

    [Small_nut]
    () "screw\nthread\nm20" -- Small_nut
    Small_nut --> "thickness\n6.8mm"

    [Cap]
    () "fine\nthread\nm20" -- Cap

    [Plunger]
    () "concentric\noutside\n21.5mm" -- Plunger
     Plunger --> "concentric\ninside\n21mm"

    [Big_nut]
    () "screw\nthread\nm27x1.5" -- Big_nut
    () "concentric\ninside\n21mm" -- Big_nut

    [House]
    House --> "concentric\noutside\n17mm"
    House --> "screw\nthread\nm20"
    House --> "concentric\noutside\n21.5mm"
    House --> "screw\nthread\nm27x1.5"
    House --> "fine\nthread\nm20"
}

@enduml
```

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

