### Is Alpha Numeric:

Check if string contains:
- numeric values (numbers from 0 to 9)
- letters (upper case & lower case)

```
const code = string.charCodeAt(index)

code > 47 && code < 58  // numeric (0-9)
code > 64 && code < 91  // upper alpha (A-Z)
code > 96 && code < 123 // lower alpha (a-z)
```

