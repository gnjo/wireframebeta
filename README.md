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
},'svg#demo') //querySelector default svg
;
//
//wfb.wire(...).ef(...)
//
wfb.wire(`
010
010
010  //stand center
`).ef('effect1',30) //svg effect class 30ms

//
;(function(root){
 let fn={}; fn.q=(d)=>document.querySelector(d);
 fn.gi=(d,el)=>el.getElementById(d)
 let is={}; is.string = function(obj){return toString.call(obj) === '[object String]'}
 ;
 function setlayer(el){
 }
 function drawwire(ary,el){
  console.log(ary,el)
  let s='wall',v='none'
  //
  s=ary[2][0]
  if(s==='wall') v='none'
  else v='inline'
  fn.gi('D0').style.display=v
  //  
  s=ary[2][1]
  if(s==='wall') v='none'
  else v='inline'
  fn.gi('D1').style.display=v
  //
  s=ary[2][2]
  if(s==='wall') v='none'
  else v='inline'
  fn.gi('D2').style.display=v  
  //
  //
  s=ary[1][0]
  if(s==='wall') v='none'
  else v='inline'
  fn.gi('D3').style.display=v  
  s=ary[1][1]
  if(s==='wall') v='none'
  else v='inline'
  fn.gi('D4').style.display=v  
  s=ary[1][2]
  if(s==='wall') v='none'
  else v='inline'
  fn.gi('D5').style.display=v  
  //
  s=ary[0][0]
  if(s==='wall') v='none'
  else v='inline'
  fn.gi('D6').style.display=v  
  s=ary[0][1]
  if(s==='wall') v='none'
  else v='inline'
  fn.gi('D7').style.display=v  
  s=ary[0][2]
  if(s==='wall') v='none'
  else v='inline'
  fn.gi('D8').style.display=v
 }
 ;
 function entry(opt,query){
  ;
  let o={
  '0':'wall'
 ,'1':'road'
 ,'2':'door'
 ,'3':'object'
 ,'4':'event'
 ,'5':'downstair'
 ,'6':'upstair'
 //
 ,'query':query||'svg'
 ,'first':true
 }
  o.el=fn.q(o.query)
  if(!o.el)return console.log('query error'),{}
  ;
  o.ef=(c,ms)=>{
   ms=ms||30,c=c.replace('.',''),o.el.classList.add(c)   
   return setTimeout(()=>{ o.el.classList.remove(c) },ms), o
  }
  ;
  o.wire=(obj,c,ms)=>{
   if(o.first)return setlayer(o.el),o.first=false,o.wire(obj,c,ms)
   ;
   let ary=is.string(obj)?obj.trim().split('\n').map(d=>d.split('')):obj
   //ary[3][3] [['0','0','0'],...]
   for(let y=0,y<3;y++)
    for(let x=0,x<3,x++)
     ary[y][x]=o[ary[y][x]]||'wall' //default wall
   ;
   if(c)o.ef(c,ms)
   return drawwire(ary,o.el), o
  }
  ;
  return Object.assign(o,opt)
 }
 root.wireframebeta=entry
})(this);

```

## svg eidt
```
snapping on
snapping 1

```



