# Day04

> filter, map, sort, reduce 사용하기

<br>



## filter

```jsx
const fifteen = inventors.filter(inventor => (
      inventor.year >= 1500 && inventor.year < 1600))
    console.table(fifteen)
```

<br>



## map

```jsx
const fullNames = inventors.map(inventor => `${inventor.first} ${inventor.last}`)
    console.log(fullNames)
```

<br>



## sort

```jsx
const ordered = inventors.sort((a, b) => a.year > b.year ? 1 : -1);
console.table(ordered);
```

<br>



## reduce

```jsx
// 4. How many years did all the inventors live?
    const totalYears = inventors.reduce((total, inventor) => {
      return total + (inventor.passed - inventor.year);
    }, 0);
```