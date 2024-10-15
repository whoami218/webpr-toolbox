# Woche 5

## Scripting
- Evaluate text
- Compiler sieht man nicht

## Im Code
```
<script>
    document.writeln('<script src="function/function.js"></script>');
</script>
```
Dies funktioniert nicht, da der Browser nach dem </script> Tag denkt, dass der Script-Tag zu Ende ist.
Egal ob dieser in einem String ist oder nicht. Die Ausgabe im Browser ist dann `');`
Es kann aber ausgetrickts werden, indem der Text zusammengesetzt wird.
```
<script>
    document.writeln('<script src="function/functionTest.js"></' + 'script>');
</script>
```

So können auch mehrere Files ausführen mit ein paar Zeilen Code:
```
<script>
    ["function", "lambda"].forEach(function (name) {
        document.writeln('<script src="' + name + '/' + name + '.js"></' + 'script>');
        document.writeln('<script src="' + name + '/' + name + 'Test.js"></' + 'script>');
    });
</script>
```
Im Browser werden nun verschiedene Script-Tags hinzugefügt und diese werden dann auch ausgeführt.


## EVAL
```
eval('some code');
```
Diese Funktion soll so funktionieren, als hätte der Code von Anfang an da gestanden.

So kann zb dynamisch auf Usereingaben direkt reagiert werden:
```
display(canvas, x => eval(userFunction.value));
userFunction.onchange = _ => display(canvas, x => eval(userFunction.value));
``` 

## Function
Seiteneffekte können durch Function vermieden werden auch wenn sie grundsätzlich gleich funktioniert wie eval.
```
const add = Function('x', 'return x + y');
add(1,2);
```
