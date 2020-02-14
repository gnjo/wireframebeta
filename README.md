# wireframebeta

```
//wall road door object upgate downgate //gate like a door
//char:string
//if not match is 0
let wfb=wireframebeta({
  '0':'wall'
 ,'1':'road'
 ,'2':'door'
 ,'3':'object'
 ,'4':'upgate'
 ,'5':'downgate'
},'svg#demo') //querySelector default svg
;
wfb(`
000
010
010
010
`,'effect1') //effect class 30ms

```
