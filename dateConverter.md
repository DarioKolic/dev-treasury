### Convert date from type Date to numbers:

```
interface IDateObject {
    day: number
    month: number
    year: number
}

const convertDate = (date: Date): IDateObject => {
  const day = date.getUTCDate()
  const month = date.getUTCMonth() + 1
  const year = date.getUTCFullYear()
  
  return { day, month, year }
}
```
