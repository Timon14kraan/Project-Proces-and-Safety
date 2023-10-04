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
    :Go back to home position
    :Grab the middle part by the hexagon;
    :Place middle part on top of the cap;
repeat
    :rotate fastener 2 times;
repeat while (rotated 2 times?) is (no)
-> yes
    :lift the middle part out of the fastener;


stop

@enduml