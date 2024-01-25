### Generate array of numbers from zero or one to n number:

Typescript
```
const makeArrayOfNumbers = (n: number, zeroAllowed?: boolean) => {
  return zeroAllowed
    ? Array.from(Array(n).keys())
    : Array.from(Array(n + 1).keys()).filter(x => x !== 0)
}
```

React
```
const makeArrayOfNumbers = (n, zeroAllowed='true') => {
  return zeroAllowed
    ? Array.from(Array(n).keys())
    : Array.from(Array(n + 1).keys()).filter(x => x !== 0)
}
```
