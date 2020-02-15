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
//
//wfb.wire(...).ef(...)
//
wfb.wire(`
000
010
010
010  //stand center
`).ef('effect1',30) //svg effect class 30ms

//
;(function(root){
 let fn={}; fn.q=(d)=>document.querySelector(d);
 let is={}; is.string = function(obj){return toString.call(obj) === '[object String]'}
 ;
 function setlayer(el){
 }
 function drawwire(ary,el){
  console.log(ary,el)
 }
 ;
 function entry(opt,query){
  ;
  let o={
  '0':'wall'
 ,'1':'road'
 ,'2':'door'
 ,'3':'object'
 ,'4':'upgate'
 ,'5':'downgate'
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
   //ary[4][3] [['0','0','0'],...]
   for(let y=0,y<4;y++)
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



