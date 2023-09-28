```plantuml
@startuml
start

repeat: start up robot;
    :wait 20 seconds;
repeat while (ready?) is (no)
->yes;
    :start moving;

stop

@enduml