### Generate array of numbers from zero or one to n number:

```
const makeArrayOfNumbers = (n: number, nullAllowed?: boolean) => {
  return nullAllowed
    ? Array.from(Array(n).keys())
    : Array.from(Array(n + 1).keys()).filter(x => x !== 0)
}
```
