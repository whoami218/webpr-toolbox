# Woche 10

## JS-Goodie
### Spread Operator
```
let arr = [1,2,3];
let a = [8,9, arr];     // [8,9,[1,2,3]]
let b = [8,9, ...arr];  // [8,9,1,2,3]
```
Spread Operator kann verwendet werden für alle Objekt welche
sich auf eine Art aufzählen lassen (iterable).

```
let arr = [a, b, ..."cdef"]; // [a, b, "c", "d", "e", "f"]
const foo = (x, y, z) = console.log(x, y, z);
foo(arr); // [1,2,3] undefined undefined
foo(...arr); // 1 2 3
```


## Module

**Package Manager:**
Kümmert sich darum wie man Packete welche definiert sind laden kann,
und wie man die Abhängigkeiten aufläsen kann.
Bsp: webpack, npm, yarn, bower, ...

**Build Tools:**
Automatisieren den Build Prozess.
Bsp: webpack, npm, gulp, grunt, ...

Module sind asynchron, da sie erst geladen werden müssen.
```
<script type="module" src="./main.js"></script>
import ("./main.js").then(module => ...); // Promise
```

## Import varianten
```
import "module-name"; 
import defaultExport from "module-name";
import * as name from "module-name";
import { export} from "module-name";
import { export as alias} from "module-name";
import { export1, export2 } from "module-name";
const promise = import("module-name");
```

## Export varianten
```
export { name1, name2, ..., nameN };
export function FunctionName() { ... }
export const name1, name2, ..., nameN; // oder let
export class ClassName { ... }
export default expression;
export { name1 as default, ... };
export * from ...;
export { name1, name2, …, nameN } from ...;
```
