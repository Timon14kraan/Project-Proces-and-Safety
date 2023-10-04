```plantuml
@startuml
start
    :Grab cap;
    :Place cap in the cap fastener;
if (cap misplaced?) then (yes)
    #pink: error;
    kill
endif
-> no

stop


@enduml