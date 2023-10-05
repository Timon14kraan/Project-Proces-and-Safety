```plantuml
@startuml
start
    :Go to home position;
    :Grab cap;
    :Place cap in the cap fastener;
if (cap misplaced?) then (yes)
    #pink: error;
    kill
endif
->no;
    :Go to home position;
    :Grab bolt;
    :Place bolt in the bolt fastener;
if (bolt misplaced?) then (yes)
    #pink: error;
    kill
endif
->no;
    :Go to home position;
    :Grab ring;
    :Place ring on top of the bolt;
if (ring misplaced?) then (yes)
    #pink: error;
    kill
endif
->no;
    :Go to home position;
    :Grab nut;
    :Place nut in the nut fastener;
if (nut misplace?) then (yes)
    #pink: error;
    kill
endif
->no;
    :Go to home position;
    :Grab plunger;
    :Place plunger through the nut;
if (plunger misplaced?) then (yes)
    #pink: error;
    kill
endif
    :Go to home position;    
    :Grab the middle part by the hexagon;
    :Place middle part on top of the cap;
repeat :rotate fastener 360 degrees;
repeat while (rotated 2 times?) is (no)
->yes;
    :lift the middle part out of the cap fastener;
    :Go o home position;
    :Rotate middle part 180 degrees in the x-axis;
    :Place middle part on top of the bolt fastener;
repeat :rotate fastener 360 degrees;
repeat while (rotated 5 times?) is (no)
->yes;
    :lift the middle part out of the bolt fastener;
    :Go to home position;
    :Rotate middle part -90 degrees in the x-axis;
    :Place middle part on top of the nut;
repeat  :rotate fastener 360 degrees;
repeat while (rotated 2 times?) is (no)
->yes;
    :Go to home position;
stop


@enduml