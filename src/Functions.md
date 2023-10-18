```plantuml
@startuml

object "inbound message" as m1
object "XML Splitter" as s1

m1 : <img:http://plantuml.com/logo3.png>
s1 : <img:https://cdn.productimages.abb.com/9IBA241268_720x540.jpg>
m2 : <img:MessageIcon.gif>

m1 -> s1
s1 -> m2