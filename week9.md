# Woche 9

## JS-Goodie
```
let [a, b] = [1, 2, 3, 4];
console.log(a); // 1
console.log(b); // 2
// der Rest verfällt

let x = [a, b];
console.log(x); // [1, 2]

[a, b] = [b, a];
console.log(a); // 2
console.log(b); // 1
```

## Promise
```
fetch("https://jsonplaceholder.typicode.com/todos/1")
    .then(response => response.json())
    .then(json => console.log(json))
    .catch(error => console.error(error));


const processEven = i => new Promise((resolve, reject) => {
    if (i % 2 === 0) {
        resolve(i);
    } else {
        reject(i);
    }
});
```

```
[1,2,3].map(n => "x" + n)
// ["x1", "x2", "x3"]

[1,2,3].map(n => [n,n]);
// [[1,1], [2,2], [3,3]]

[1,2,3].flatMap(n => [n,n]);
// [1,1,2,2,3,3]
```
