# Woche 3

## Atomare Lambda-Kalkül Ausdrücke
```
const T = tc => fc => tc; // T(truecase)(falsecase) = truecase
const F = tc => fc => fc; // F(truecase)(falsecase) = falsecase
// const and = a => b => a (b (T) (F)) (b(F) (F));
// const and = a => b => a (b (T) (F)) (F); // b(F)(F) is the same as F
// const and = a => b => a (b) (F); // b (T) (F) is the same as b
const and = a => b => a(b)(a); // F in this case is a bc there a is false

// const or = a => b => a (T) (b (T) (F));
// const or = a => a (T) (b);
const or = a => b => a (a) (b);
```

## Pair
```
const Pair = x => y => f => f(x)(y);
const fst = p => p(T);
const snd = p => p(F);
```

## Triple
```
const Triple = x => y => z => f => f(x)(y)(z);
const fst = p => p(T);
const snd = p => p(F);
const trd = p => p(F)(F)(T);
```

## Pair encoding
```
const Person = 
    firstname => 
    lastname =>
    age => 
    pair(pair(firstname)(lastname)) (age);

const firstn = p => fst(fst(p));
const lastn = p => snd(fst(p));
const age = p => snd(p);
```
## Either
Im Fehlerfall (wenn Divisor 0 ist) wird ein Fehler in der Console ausgegeben mit "schlecht", ansonsten das Ergebnis.
```
const Left = x => f => g => f(x);
const Right = x => f => g => g(x);
const either = e => f => g => e(f)(g);


const safeDiv = num => divisor =>
    divisor === 0
    ? Left("schlecht!")
    : Right(num / divisor);

either( safeDiv(1)(0)  )
      ( x => console.error(x))
      ( x => console.log(x));
```

## Special Case
```
const Nothing = Left ();
const Just = Right;
const maybe = either;

maybe (expressionThatMightFail)
      ( x => console.error(x))
      ( x => console.log(x));
```
