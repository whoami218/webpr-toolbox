# Woche 1

Jedes Statement in Javascript endet mit einem Semikolon!

## Funktionen
Funktionen sind eigentlich nur Wertzuweisungen. Der Name ist die Referenz auf die Funktion
erst mit den runden Klammern beim Aufruf wird die Funktion dereferenziert.

```
function fun1()    { return 1; }

fun1()   === 1; // true
fun1(42) === 1 // true, funtkioniert auch obwohl es keinen Parameter erwartet
```

```
function fun2()    { return 1; }
function fun2(arg) { return arg; } // überschriftet die erste Funktion
```

```
function fun1()    { return 1; }
const myfun = fun1;
myfun() === 1; // true
```
--> Javascript hat keinen Compiler deshalb können solche Fehler passieren

## Ausdruck in String umwandeln
document.writeln(0 === 0); --> Argumenttype boolean is not assignable to parameter type string  
document.writeln((0 === 0).toString()); --> etwas hacky, da es zuerst in einen boolean umgewandelt wird und dann in einen string
document.writeln(String(0 === 0)); --> besser, da es direkt in einen string umgewandelt wird

## nützliche Funktionen
**pop()** entfernt das letzte Element eines Arrays und gibt es zurück.
```
const nums = [0,1,2,3];
nums.pop();  
console.log(nums);  
// Expected output: Array [0,1,2]
```
**push()** fügt Element(e) am Ende eines Arrays hinzu und gibt die neue Länge des Arrays zurück.
```
const nums = [0,1,2,3];
nums.push(4);  
console.log(nums);  
// Expected output: Array [0,1,2,3,4]
```

**shift()** entfernt das erste Element eines Arrays und gibt es zurück.
```
const nums = [0,1,2,3];
nums.shift();  
console.log(nums);  
// Expected output: Array [1,2,3]
```

**unshift()** fügt Element(e) am Anfang eines Arrays hinzu und gibt die neue Länge des Arrays zurück.
```
const nums = [0,1,2,3];
nums.unshift(5);  
console.log(nums);  
// Expected output: Array [5,0,1,2,3]
```

**slice()** Kopie eines Teils des Arrays (start, end) start inklusiv, end exklusiv.
```
const nums = [0,1,2,3];
console.log(nums.slice(1,3));  
// Expected output: Array [1,2]
```

## Lambda Funktionen =>
```
function noReturn()    { 1; } // keine Rückgabe
const noReturn2 = () => { 1; }; // keine Rückgabe
const noReturn3 = () => 1; // Rückgabe von 1
```
