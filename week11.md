# Woche 11

## JS-Goodie

```
[0,1,2,3].forEach ( i => {console.log(i); return i+1;}); // 0 1 2 3
// Achtung return springt immer nur aus dem innersten raus nicht komplett.

var arr = [3,5,7,{foo:"hello"}]
for (var i in arr) {console.log(i);} // 0 1 2 3
for (var i of arr) {console.log(i);} // 3 5 7 {foo: "hello"}
// for .. in .. gibt den Index zurück
// for .. of .. gibt den Wert zurück
```
