# Woche 8

## JS-Goodie 

```
let x = 1;
{x : x}     // {x: 1}
{x}         // {x: 1} -> Kurzschreibweise
```

Verwendung:
```
console.log(x);        // 1 -> viele Logs = unübersichtlich
console.log({x});      // {x: 1} -> übersichtlicher
```

## Type
In Javascript können die Typen mit JsDoc definiert werden.

```
/**
 * @param {number} arg
 * @returns {number}
 */
const foo = arg => arg + 1;

/**
 * @type {number} // definiert den Typ von x
 */
let x = foo(1); // x ist number
```

```
{ Number | String } // Entweder Number oder String
{ * }               // alle Typen
{ !Number }         // nicht number
{ ?Number }         // optional
{ ...Number }       // beliebig viele vom Typ Number
```

## Generic
```
/**
 * @template _T_
 * @param  { _T_ } arg
 * @return { _T_ }
 */

// Ähnlich wie Generics in Java
// Wenn ein String reingegeben wird, kommt auch ein String raus
// wenn ein Number reingegeben wird, kommt eine Number raus
```

## StringLiteralTypes
```
/**
 * @param  { "Hallo" | "Huhu" } arg
 * @return { String }
 */
 const foo = arg => arg;
 
    foo("Hallo"); // "Hallo"
    foo("Huhu");  // "Huhu"
    foo("Hi");    // Fehler
```

## Typedef
```
    /**
     * @typedef { "Hallo" | "Huhu" } HalloHuhuType
     */
    /**
     * @template _T_
     * @param  { HalloHuhuType } arg
     * @return { String }
     */
    const foo = arg => arg;
```

## Built-in-Types
Können mit typeof überprüft werden:
- Boolean
- Number
- String
- Object
- BigInt
- Symbol
- Null
- Undefined
- Function

Object classes: (Keine typen)
- Array
- Date
- RegExp
- Error
- Map
- JSON
- ...

Für bekannte Typen gibt es meist Operatoren (z.B. `===`, `+`,)


## Funktionen Typisierungen
```
@function       // Es ist eine Funktion
@constructor    // Es ist ein Funktion welche ein neues Objekt liefert
@callback       // Es ist eine Funktion welche als Parameter übergeben wird
@param          // Parameter
@returns        // Rückgabewert -> auch klar das es eine Funktion ist
```

## Datentypen
```
Objekte:             @property {Number} age
Array:               {Array<Number>} / { [ Number ] }
Union:               {Number | String}
Intersection:        {Book & Krimi} // eigen Typen Book und Krimi
String literal:      { "Hallo" | "Huhu" }
Capability:          { {a:A, b:Function} }   
```

