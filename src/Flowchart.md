```plantuml
@startuml
start
:start up robot;
if (ready?) then (yes)
  :move;
else (no)
  :start up robot;
endif

stop

@enduml