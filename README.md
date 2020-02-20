# wireframebeta
```
script(src="https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js")

let tex=`
 <defs>
  <!--need https://cdnjs.cloudflare.com/ajax/libs/geopattern/1.2.3/js/geopattern.min.js -->
    <pattern id="tile" x="0" y="0" width="100%" height="100%" patternUnits="userSpaceOnUse">
     <image x="0" y="0" width="100%" height="100%"></image>
    </pattern>
 </defs>
<!---<rect x="10" y="10" width="320" height="240" stroke="#630" stroke-width="0px" fill="url(#tile)" />-->
`;
function maketile(seed){
 let query="#tile>image"
 if(!fn.q(query)) fn.q('svg').innerHTML+=tex
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
 fn.q(query).setAttributeNS("http://www.w3.org/1999/xlink", "xlink:href",src);//
  //xlink:href 
}
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
