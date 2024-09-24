# Woche 2

## Strings deklarieren
Dies sind alles literale Deklarationen  
String deklarieren mit Doppel- **oder** Einfachstrichen  
Somit funktioniert auch zb etwas wie ```'Ich sagte: "Hallo!"'```  
Ebenfalls kann so das einfache Hochkomma verwendet werden: ```"It's a beautiful day"``` 
Mehrzeilige Strings können mit Backticks deklariert werden, darin sind auch Variblen möglich
```
const name = "Max";
const str = `Hallo
${name}!`;
```
=> Javascript Template String

/text/ -> Regulärer Ausdruck
String("text") -> Funktionale Deklaration

## JS Scopes

**global scope:** window (in Browser)
**function:**     egal wo definiert, variablen sind nur in dieser Funktion sichtbar

### Variablen
**x = 1;** // veränderbar, global scope -> sollte vermieden werden  
**var x = 1;** // veränderbar, "hoisted" scope (wird so erstellt als wäre die Variable von Anfang an erstellt worden nicht an diesem Ort an dem sie steht) -> sollte vermieden werden  
**let x = 1;** // veränderbar, local scope  
**const x = 1;** // unveränderbar, local scope  


## Beispiele
```
let x = 0;
function foo() {
    let x = 1;
    document.writeln(String(x));
}
foo();
document.writeln(String(x));
```
Ausgabe: 1 0

```
x = 0;
function foo() {
    x = 1;
    document.writeln(String(x));
}
foo();
document.writeln(String(x));
```
Ausgabe: 1 1

```
var x = 0;
function foo() {
    // eigentliche Deklaration (var x;) hier, deshalb undefined
    document.writeln(String(x));
    var x = 1; // -> wird gehoisted
}
foo();
document.writeln(String(x));
```
Ausgabe: undefined 0



## Funktionen
IIFE = Immediately Invoked Function Expression  
Sofortige Ausführung der Funktion
```
function foo() {...}; foo(); // Funktion die über einen Namen aufgerufen wird
(function foo() {...})(); // Funktion mit Name, welche direkt ausgeführt wird
(function() {...}()); // Anonyme Funktion, welche direkt ausgeführt wird
(() => {...})(); // Arrow Funktion, welche direkt ausgeführt wird
```

### Lambda Kalkül
alpha: Rename parameter
beta:  Apply argument
eta:   Cancel parameter 

### Alpha Translation
```
const id = x => x;
const id = y => y; // gleiche Funktion, anderer Parametername
```

### Beta Translation
```
(x => x)(1);
(x => 1)(1);
      1;
```
```
( f => x => f(x) ) (id) (1);
(      x => id(x) )     (1);
(           id(1) )     ;
(     (x => x)(1) )        ;
               1
```

### Eta Translation
Rightmost argument equals rightmost parameter => remove both
```
x => foo(x);
foo;
```
```
x => y => both(x)(y);
x =>      both(x);
          both;
```
