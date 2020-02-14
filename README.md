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
 function entry(opt,query){
  let el=fn.q(query)||fn.q('svg')
  if(!el)return console.log('query error'),{}
  ;
  let o={}
  o.el=el
  o.ef=(c,ms)=>{
   ms=ms||30,c=c.replace('.',''),o.el.classList.add(c)   
   return setTimeout(()=>{ o.el.classList.remove(c) },ms), o
  }
  ;
  o.wire=(obj)=>{
   let ary=is.string(obj)?obj.trim().split('\n').map(d=>d.split('')):obj
   //ary[4][3] [['0','0','0'],...]
  }
  ;
  Object.assign(o,opt)
 }
 root.wireframebeta=entry
})(this);

```
