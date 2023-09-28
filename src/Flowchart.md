```plantuml
@startuml
start

if (ready?) then (yes)
  :move;
else (no)
  :stay still;
endif

stop

@enduml