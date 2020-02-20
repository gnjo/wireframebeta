# wireframebeta
```
script(src="https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js")

 seed=Date.now()
 ;
 let p=[
	'octogons',
	'overlappingCircles',
	'plusSigns',
	'xes',
	//'sineWaves',
	//'hexagons',
	'overlappingRings',
	//'plaid',
	'triangles',
	'squares',
	'concentricCircles',
	'diamonds',
	'tessellation',
	'nestedSquares',
	'mosaicSquares',
	'chevrons'
]; 
 let opt={}
 opt.generator=p[seed%p.length]
 opt.baseColor='#789'
 let pattern=GeoPattern.generate(seed+'',opt);
 let src=pattern.toDataUri()
 fn.q('img').src=src
```
```
//pug
script(src="https://gnjo.github.io/wireframebeta/wireframebeta.js")

```
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
## ttf
```
@font-face {
 font-family: 'mapsy';
 src: url('https://gnjo.github.io/wireframebeta/mapsy.ttf?v=3') format('truetype');
    font-weight: normal;
    font-style: monospace;
}

pre{
 font-family:mapsy;
 color:white;
 line-height:0.9;
}
```
