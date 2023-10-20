```plantuml
@startuml

object Functions choice {
  <#lightblue,#black>|=  Functions: Fixating the parts |= Chosen?  |=  Reason  |
  <#white>| Rotating the robot arm | No | The maximum rotation the robotarm is capable of is 400 degrees. Because of the limited rotation the robot needs to release the part and rotate the other way to be able to do the right amount of rotations.|
}
@endulm
```