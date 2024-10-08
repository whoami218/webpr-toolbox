# Woche 4

## JS Goodie
```
[0,1,2,3].forEach( elem => console.log(elem) ); // Jedes Element des Arrays wird geloggt
[0,1,2,3].every(elem => elem > 1); // Every Function erwartet Boolschen Wert (Prädikat) -> schaut ob Prädikat für alle gilt
[0,1,2,3].some(elem => elem > 1); // Gibt es ein Element für welches das Prädikat zutrifft

---
[0,1,2,3,4].some(elem => {console.log(elem); return elem > 1});
// 0
// 1
// 2
// true
// Kann ausgenutzt werden um für alle auf welche das Prädikat nicht zutrifft etwas zu machen
```

## Funktionen definition
```
// multiple Parameters
const add = (a,b) => a + b;
add(2); // NaN

// parameter chain
const add = a => b => a + b; 
add(2); // [Function] -> kann weiterverwendet werden
```

## Partial Application
Funktionen werden nur teilweise angewendet, die restlichen Parameter werden erst später übergeben. 
Meist in Kombination mit Higher Order Functions. (map, filter, reduce)
```
// MAP
const times = a => b => a * b;
const twoTimes = times(2);
[1,2,3].map(x => times(2)(x)); // [2,4,6]
[1,2,3].map(times(2));         // Eta Reduktion [2,4,6]
[1,2,3].map(twoTimes);         // Verwendung der Variablen [2,4,6]

// FILTER
const isEven = x => x % 2 === 0;
[1,2,3,4].filter(x => x % 2 === 0);   // [2,4]
[1,2,3,4].filter(x => isEven(x));     // [2,4]
[1,2,3,4].filter(isEven);             // [2,4]

// REDUCE
reduce((acc, elem) => acc + elem); // Accumulator und jetziges Element => Ergebnis ist neuer Accumulator

const plus = (acc, elem) => acc + elem;
[1,2,3,4].reduce((acc, elem) => acc + elem); // 10
[1,2,3,4].reduce(plus); // 10

[1,2,3,4].reduce(plus, 0); // 10 -> 0 ist der Startwert des Accumulators (meist neutrales Element)
[].reduce(plus, 0); // 0 -> kein Element im Array 
[].reduce(plus); // Error -> kein Startwert
```

## Konzepte
```
pair + pair == pair // -> Monoid  
map (f) (pair) == pair // -> Functor
```

