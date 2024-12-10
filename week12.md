# Woche 12

## JS-Goodie (Regex)
Mit / / kann man eine RegexP erstellen
```
"a1 b2 c3".split(" ")        // gleichbedeutend mit
"a1 b2 c3".split(/ /)        // ["a1", "b2", "c3"]

"a1 b2.c3".split(/\b/)      // ["", "a1", " ", "b2", ".", "c3"]
```
```
\b steht für Wortgrenze
\w steht für Wortzeichen
\W steht für kein Wortzeichen
\d steht für Ziffer
\D steht für keine Ziffer

+ steht für 1 oder mehr
* steht für 0 oder mehr
```

Regex können zb in .replace(), .match(), .split() verwendet werden    

### Gruppen
Jede öffnende Klammer erzeugt eine Gruppe diese können danach mit $1, $2, ... referenziert werden
$0 referenziert den gesamten Treffer
```
"a1 b2 c3".replace(/(\w)3/, "$1$1$1")  // "a1 b2 ccc"
```


## Iterator Protokoll
### Iterierbare Objekte
- Array
- String
- Map
- Set
- "argumente"

```
constr str = "the rain in spain stys mainly in the plain";
const matches = str.matchAll(/(\w\w\w)(.*?)\1/g);
for (const match of matches) {
    console.log(match);
}

// Iterator O = the rain in spain stys mainly in the       // ganze Gruppe mit match 
// Iterator 1 = the                                        // match
// index = 0
// input = the rain in spain stys mainly in the plain
```


## Eigenes Iterable machen
```
    let myValue = 0;
    const iterable = {
        [Symbol.iterator] : () => ({
            next : () => ({value: myValue++, done: myValue > 50})
        })
    };
    // const [a, b, c] = iterable; // nur die ersten 3
    // console.log(a, b, c)

    for (const x of iterable) {
        console.log(x);
    }
```
