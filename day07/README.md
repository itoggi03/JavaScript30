# Day07

> Array Cardio Day2

<br>

### 코드 간결화

```bash
const isAdult = people.some(function(person) {
      const currentYear = (new Date()).getFullYear();
      if(currentYear - person.year >= 19) {
        return true;
      }
    })
```

- arrow function을 이용해 위 코드를 아래처럼 간결하게 만들 수 있다.

```bash
const isAdult = people.some(person => (new Date()).getFullYear() - person.year >= 19)
```

<br>

### some, every

- some : 주어진 데이터(배열) 중 하나라도 조건에 만족하면 True
- every: 주어진 데이터(배열)  모두가 조건에 만족해야 True

<br>

### find

- find : 주어진 데이터 중 조건에 만족하는 데이터의 값을 찾아줌

<br>

### 배열에서 특정 인덱스의 값 삭제하는 방법 2가지

여기서 삭제해야할 인덱스: index

1. splice 이용

   ```bash
   comments.splice(index, 1)
   ```

2. slice 이용해서 새 리스트 정의

   ```bash
   const newComments = [
         ...comments.slice(0, index),
         ...comments.slice(index + 1)
       ]
   ```