# Structure
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
The second diagram shows the setup. All important factors are incorporated and linked together. Based on this diagram, components can be found and the system can be further built up.

Component diagram:
```plantuml
@startuml Process_and_Safety
skinparam backgroundColor transparent
left to right direction
'skinparam linetype ortho

component Valve_assembly_setup {
    
    [Storage]
    () "pickup\nposition\nring" -- Storage
    () "pickup\nposition\nplunger" -- Storage
    () "pickup\nposition\ncap" -- Storage
    () "pickup\nposition\nhouse" -- Storage
    () "pickup\nposition\nsmall nut" -- Storage
    () "pickup\nposition\nbig nut" -- Storage 
    () "pickup\nposition\nassembled valve" -- Storage     
    Storage --> "position\nstorage"
    Storage --> "power\nstorage"

    [Ring]
    Ring --> "pickup\nposition\nring"
    
    [Plunger]
    Plunger --> "pickup\nposition\nplunger"

    [Cap]
    Cap --> "pickup\nposition\ncap"
    Cap --> "holder cap"

    [House]
    House --> "pickup\nposition\nhouse"

    [Small_nut]
    Small_nut --> "pickup\nposition\nsmall nut"
    Small_nut --> "holder small nut"

    [Big_nut]
    Big_nut --> "pickup\nposition\nbig nut"
    Big_nut --> "holder big nut"

    [Assembled_valve]
    Assembled_valve --> "pickup\nposition\nassembled valve"

    [Robot]
    () "end\neffector" -- Robot
    Robot --> "position\nrobot"
    Robot--> "power\nrobot"

    [Gripper]
    Gripper --> "pickup\nposition\nring"
    Gripper --> "pickup\nposition\nplunger"
    Gripper --> "pickup\nposition\ncap"
    Gripper --> "pickup\nposition\nhouse"
    Gripper --> "pickup\nposition\nsmall nut"
    Gripper --> "pickup\nposition\nbig nut"
    Gripper --> "end\neffector"

    [Frame]
    () "position\nrobot" -- Frame
    () "position\nstorage" -- Frame
    () "position\nassembly station cap" -- Frame
    () "position\nassembly station small nut" -- Frame
    () "position\nassembly station big nut" -- Frame
    () "position\nvoltage cabinet" -- Frame

    [assembly_station_cap]
    () "holder cap" -- assembly_station_cap
    assembly_station_cap --> "position\nassembly station cap"
    
    [assembly_station_small_nut]
    () "holder small nut" -- assembly_station_small_nut
    assembly_station_small_nut --> "position\nassembly station small nut"
    
    [assembly_station_big_nut]
    () "holder big nut" -- assembly_station_big_nut
    assembly_station_big_nut --> "position\nassembly station big nut"

    [voltage_cabinet]
    voltage_cabinet --> "position\nvoltage cabinet"
    () "power\nrobot" -- voltage_cabinet
    () "power\nstorage" -- voltage_cabinet

}

@enduml
```

```plantuml
@startuml

object IO_list {
  <#lightblue,#black>|= Number  |= Sensors or actuators  |=  Input or output  |
  <#white>| 1 | Storage complete | Input |
  <#white>| 2 | Start button | Input |
  <#white>| 3 | Stop button | Input |
  <#white>| 4 | Holder in right direction (assembly station cap) | Input |
  <#white>| 5 | Holder in right direction (assembly station big nut) | Input |
  <#white>| 6 | Holder in right direction (assembly station small nut) | Input |
  <#white>| 7 | Motor aansturen (assembly station cap) | Output |
  <#white>| 8 | Motor aansturen (assembly station big nut) | Output |
  <#white>| 9 | Motor aansturen (assembly station small nut) | Output |
  <#white>| 10 | Gripper open | Output |
  <#white>| 11 | Gripper dicht | Output |

}
@endulm
```