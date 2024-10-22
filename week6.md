# Woche 6

## JS Goodie
### Array.slice()
```
[0,1,2,3,4].slice(1,3) // [1,2]
[0,1,2,3,4].slice(1,-2) // [1,2]

slice(start, end) 
// end ist exklusiv
// end kann grösser sein als die Länge des Arrays
// end ist optional
// slice() gibt eine Kopie des ganzen Arrays zurück
// wenn end negativ ist, wird die Länge des Arrays + end genommen
```
### Array.splice()
```
let arr = [0,1,2,3,4]
arr.splice(1,2) // [1,2] (start, deleteCount)
arr // [0,3,4]

arr.splice(1,0,1,2) // [] (start, deleteCount, ...items)
arr // [0,1,2,3,4]
```

## JS "Objects"
### Offene dynamische Objekte
````
const good = {
    firstname: "Good",
    lastname : "Boy",
    getName  : function() {
        return this.firstname + " " + this.lastname;
    }
}

good.getName() // "Good Boy"
````
### Geschlossene statische Objekte
```
function Person(firstname, lastname) {
    return {
        getName: () => firstname + " " + lastname 
    }
}
```

### Gemischte klassifizierte Objekte
```
const Person = (() => {
    function Person(firstname, lastname) {
        this.firstname = firstname;
        this.lastname  = lastname;
    }
    Person.prototype.getName = function() {
        return this.firstname + " " + this.lastname;
    }
    return Person;
})(); // IIFE (Immediately Invoked Function Expression)

// new Person("Good", "Boy") instanceof Person // true
```


## This
Die Zuordnung wird immer zum Zeitpunkt des Aufrufs gemacht. 
Es wird jeweils der Wert vor dem Punkt genommen.

```
 const myObject = {
        a   : 1,
        foo : function() { return this.a }
        // foo() { return this.a }              // syntactic sugar
    };
    ok.push(myObject.foo() === 1); 
    // foo() wird aufgerufen von myObject
    // this = myObject
    
    const myFunctions = [ myObject.foo ]; // hier wird der Aufruf noch nicht gemacht
    ok.push(myFunctions[0]() === 1);      // hier passiert der Aufruf
    // links von myFunctions[0] ist kein Punkt, also wird this = undefined

```


