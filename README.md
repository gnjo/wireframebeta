# wireframebeta
```
wall="0" //face side
road="1" //ground
door="2" //face side
object="3" //ground
event="4" //ground
downstair="5" //ground
upstair="6" //ceiling
```
```
//wall road door object upgate downgate //gate like a door
//char:string
//if not match is 0
let wfb=wireframebeta({
  '0':'wall'
 ,'1':'road'
 ,'2':'door'
 ,'3':'object'
 ,'4':'event'
 ,'5':'downstair'
 ,'6':'upstair'
},'svg') //querySelector default svg
;
//
//wfb.wire(...).ef(...)
//
wfb.wire(`
010
010
010  //stand center
`).ef('effect1',30) //svg effect class 30ms
```
```
//svg editor
snapping 10
```
