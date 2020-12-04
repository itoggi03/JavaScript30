# Day06

>  Ajax Type Ahead
>
> 검색창에 검색어를 입력 시, 데이터베이스에서 검색어를 포함한 결과들이 나오게 됨

<br>

## data 넣기

```jsx
fetch(endpoint)
  .then(blob => blob.json())
  .then(data => cities.push(...data));
```

<br>



## 검색어와 맞는 데이터 찾기

```jsx
function findMatches(wordToMatch, cities) {
  return cities.filter(place => {
    // here we need to figure out if the city or state matches what was searched
    const regex = new RegExp(wordToMatch, 'gi');
    return place.city.match(regex) || place.state.match(regex)
  });
}
```

<br>



## 검색결과 보여주기

```jsx
function displayMatches() {
  const matchArray = findMatches(this.value, cities);
  const html = matchArray.map(place => {
    const regex = new RegExp(this.value, 'gi');
    const cityName = place.city.replace(regex, `<span class="hl">${this.value}</span>`);
    const stateName = place.state.replace(regex, `<span class="hl">${this.value}</span>`);
    return `
      <li>
        <span class="name">${cityName}, ${stateName}</span>
        <span class="population">${numberWithCommas(place.population)}</span>
      </li>
    `;
  }).join('');
  suggestions.innerHTML = html;
}
```