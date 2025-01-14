# Woche 15

## Crazy JS
### Nullwerte
```
0 == "0" // true
0 == []  // true
"0" == [] // false
0 == false // true
```

### Rechnen
```
"2" + 1 = "21"
"2" - 1 = 1
"2" - - 1 = 3
1 + 2 + "3" = "33"
```

### Objekte
```
+true           // 1
+false          // 0
true + true     // 2
[] == []        // false
[] == ![]       // true
+[]             // 0
2 == [2]        // true
[] + {}         // "[object Object]"
{} + []         // 0
{} + {}         // NaN
```

### Numbers
```
Number("-0")                        // -0
JSON.parse("-0")                    // -0
JSON.stringify(-0)                  // "0"
String(-0)                          // "0"
typeof null                         // "object"
null instanceof Object              // false
typeof NaN                          // "number"
typeof (1/0)                        // "number"
0.1 + 0.2 === 0.3                   // false
9999999999999999                    // 10000000000000000
Number.MAX_VALUE > 0                // true
Number.MIN_VALUE < 0                // false
Math.min(1,2,3) < Math.max(1,2,3)   // true
Math.min() < Math.max()             // false
```

## == vs ===
=== ist ein Instanzvergleich  
== ist ein Wertevergleich

Es ist eigentlich immer besser den === Operator zu verwenden!  
Einzige Ausnahme kann sein:
```
(a == null) statt
(a === null || a === undefined)
```
