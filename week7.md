# Woche 7

## JS-Goodie (Array.from)
Bei Array.from kann alles verwndet werden, was ein `lenght`-Attribut hat. 

```
Array.from("abc");
// ["a", "b", "c"]

Array.from({length: 3});
// [undefined, undefined, undefined]
```
```
Array.from({length: 3}).map((it, idx) => idx);
// [0, 1, 2]

Array.from({length: 3}, (it, idx) => idx); // Gleich wie oben nur kürzer
```

## class Keyword
Es gibt ein class-Keyword in JavaScript, das es ermöglicht, Klassen zu definieren.
Dies ist ähnlich zu Methode 3 von letzer Woche (Gemischte klassifizierte Objekte)

```
class Person {
    constructor(first, last) {
        this.firstname = first;
        this.lastname = last;
    }
    getName() {
        return this.firstname + " " + this.lastname;
    }
}

// new Person("Max", "Mustermann") instance of Person;
```

## extends Keyword
Mit dem extends-Keyword können Klassen erweitert werden.

```
class Student extends Person {
    constructor(first, last, matrikelnummer) {
        super(first, last); // Nicht vergessen
        this.matrikelnummer = matrikelnummer;
    }
}

const s = new Student("Max", "Mustermann", 123456);
```

## Funktionen <> Objekte
Funktionen sind Objekte
Funktionen haben eine `prototype`-Eigenschaft, die ein Objekt ist.
Funktionen referenzieren auf ein objekt mit
- name (Type)
- constructor (Function)
- hat ebenfalls ein prototype-Objekt


Objekte aber sind keine Funktionen in JavaScript

## Prototypen
Jedes Objekt in JavaScript hat einen Prototypen.
```
const s = new Student();
s.__proto__ === Student.prototype // true
Object.getPrototypeOf(s) === Student.prototype // true
// s instanceof Student
```
Achtung der Prototyp kann geändert werden, das heisst er wird für alle Objekte verändert

```
String.prototype.toString = function() {
    return "hacked!";
}

// "abc".toString() // "hacked!"
```
Jedes toString gibt jetzt "hacked!" zurück
