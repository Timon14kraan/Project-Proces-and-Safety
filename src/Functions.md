```plantuml
@startuml

object "inbound message" as m1
object "XML Splitter" as s1

m1 : <img:MessageIcon.gif>
s1 : <img:SplitterIcon.gif>
m2 : <img:MessageIcon.gif>

m1 -> s1
s1 -> m2