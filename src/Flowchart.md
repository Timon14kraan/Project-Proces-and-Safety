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
    :Go back to home position;
    :Grab bolt;
    :Place bolt in the bolt fastener;
if (bolt misplaced?) then (yes)
    #pink error;
    kill
endif
-> no


@enduml