## 자주 쓰는 자바스크립트 내장함수/메서드 정리 (test1 기준)

### 1. Array.prototype.filter

- **사용법**: `arr.filter((v, i, o) => 조건)`
- **동작**: 배열에서 조건을 만족하는 요소만 추출하여 새 배열 반환
- **예시**: 중복 제거: `arr.filter((v, i) => arr.indexOf(v) === i)`
- **코딩테스트 팁**: 중복 제거, 조건에 맞는 값 추출에 자주 사용

```ts
// 중복 제거 예시
const arr = [1, 2, 2, 3, 4, 4];
const uniqueArr = arr.filter((v, i) => arr.indexOf(v) === i);
console.log(uniqueArr); // [1, 2, 3, 4]
```

### 2. Array.prototype.map

- **사용법**: `arr.map((v, i, o) => 반환값)`
- **동작**: 배열의 각 요소를 변환하여 새 배열 반환
- **예시**: 문자열 길이 구하기: `arr.map(v => v.length)`
- **코딩테스트 팁**: 변환, 가공, 새로운 배열 생성에 활용

```ts
// 문자열 길이 구하기
const words = ['apple', 'banana', 'kiwi'];
const lengths = words.map((v) => v.length);
console.log(lengths); // [5, 6, 4]
```

### 3. Array.prototype.reduce

- **사용법**: `arr.reduce((acc, cur) => 누적값, 초기값)`
- **동작**: 배열의 모든 요소를 누적하여 하나의 값으로 반환
- **예시**: 합계 구하기: `arr.reduce((a, b) => a + b, 0)`
- **코딩테스트 팁**: 합계, 곱, 최대/최소 등 누적 계산에 자주 사용

```ts
// 합계 구하기
const nums = [1, 2, 3, 4];
const sum = nums.reduce((a, b) => a + b, 0);
console.log(sum); // 10
```

### 4. Array.prototype.forEach

- **사용법**: `arr.forEach((v, i, o) => { ... })`
- **동작**: 배열의 각 요소에 대해 반복 실행 (반환값 없음)
- **코딩테스트 팁**: 단순 반복, 출력, 조건별 처리에 사용

```ts
// 배열 요소 출력
const arr = ['a', 'b', 'c'];
arr.forEach((v, i) => {
  console.log(i, v);
});
// 0 'a', 1 'b', 2 'c'
```

### 5. Array.prototype.indexOf

- **사용법**: `arr.indexOf(값)` 또는 `str.indexOf(문자)`
- **동작**: 값이 처음 등장하는 인덱스 반환, 없으면 -1
- **코딩테스트 팁**: 중복 체크, 포함 여부 확인, 위치 찾기

```ts
// 값 포함 여부 확인
const arr = [10, 20, 30];
console.log(arr.indexOf(20)); // 1
console.log(arr.indexOf(40)); // -1
```

### 6. Array.prototype.sort

- **사용법**: `arr.sort((a, b) => a - b)`
- **동작**: 배열을 정렬 (기본은 문자열 기준, 숫자 정렬시 비교함수 필요)
- **코딩테스트 팁**: 최대/최소, 순서 정렬 문제에 필수

```ts
// 숫자 오름차순 정렬
const arr = [5, 2, 9, 1];
arr.sort((a, b) => a - b);
console.log(arr); // [1, 2, 5, 9]
```

### 7. Array.prototype.splice

- **사용법**: `arr.splice(시작, 개수)`
- **동작**: 배열에서 요소 삭제/추가, 원본 배열 변경
- **코딩테스트 팁**: 특정 위치 요소 제거, 배열 조작에 사용

```ts
// 배열에서 두 번째 요소 제거
const arr = [1, 2, 3, 4];
arr.splice(1, 1);
console.log(arr); // [1, 3, 4]
```

### 8. String.prototype.split

- **사용법**: `str.split(구분자)`
- **동작**: 문자열을 구분자로 나눠 배열로 반환
- **코딩테스트 팁**: 문자열 파싱, 단어/문자 분리 문제에 자주 등장

```ts
// 문자열을 공백 기준으로 분리
const str = 'hello world';
const arr = str.split(' ');
console.log(arr); // ['hello', 'world']
```

### 9. String.prototype.replace

- **사용법**: `str.replace(/A/g, '#')`
- **동작**: 정규식/문자에 맞는 부분을 다른 값으로 치환
- **코딩테스트 팁**: 특정 문자/패턴 치환, 정규식 활용 문제에 자주 사용

```ts
// 모든 A를 #으로 치환
const str = 'ABACAD';
const result = str.replace(/A/g, '#');
console.log(result); // '#B#C#D'
```

### 10. String.prototype.toUpperCase / toLowerCase

- **사용법**: `str.toUpperCase()`, `str.toLowerCase()`
- **동작**: 문자열을 모두 대문자/소문자로 변환
- **코딩테스트 팁**: 대소문자 변환, 비교, 정규화에 활용

### 11. String.prototype.substring / substr

- **사용법**: `str.substring(시작, 끝)`, `str.substr(시작, 개수)`
- **동작**: 문자열의 일부를 추출
- **코딩테스트 팁**: 부분 문자열 추출, 가운데 문자, 슬라이싱 문제에 사용

### 12. Math.min / Math.max / Math.ceil

- **사용법**: `Math.min(...arr)`, `Math.max(...arr)`, `Math.ceil(값)`
- **동작**: 배열의 최소/최대값, 올림값 반환
- **코딩테스트 팁**: 최솟값/최댓값, 올림 계산에 자주 등장

### 12. Math.min / Math.max / Math.ceil / Math.floor

- **사용법**: `Math.min(...arr)`, `Math.max(...arr)`, `Math.ceil(값)`, `Math.floor(값)`
- **동작**: 배열의 최소/최대값, 올림값, 내림값 반환
- **코딩테스트 팁**: 최솟값/최댓값, 올림/내림 계산에 자주 등장

```ts
// 최솟값, 최댓값, 올림, 내림 예시
const arr = [1.2, 3.7, 2.5];
console.log(Math.min(...arr)); // 1.2
console.log(Math.max(...arr)); // 3.7
console.log(Math.ceil(2.3)); // 3 (올림)
console.log(Math.floor(2.7)); // 2 (내림)
```

### 13. document.write / console.log

- **사용법**: `document.write(값)`, `console.log(값)`
- **동작**: 결과 출력, 디버깅
- **코딩테스트 팁**: 결과 확인, 디버깅에 필수

### 14. 추가로 자주 쓰는 함수/메서드 (코테 유용)

아래는 코딩 테스트에서 자주 쓰이지만 원래 파일에 누락되어 있을 수 있는 유용한 함수/메서드 모음입니다. 사용법과 간단한 팁을 함께 적었습니다.

- Array.prototype.push / pop / shift / unshift
  - push: 배열 끝에 추가. pop: 끝에서 삭제 및 반환.
  - shift: 앞에서 삭제 및 반환. unshift: 앞에 추가.
  - 팁: 큐/스택 구현에 자주 사용.

```js
const a = [1, 2];
a.push(3); // [1,2,3]
const last = a.pop(); // 3, a -> [1,2]
```

- Array.prototype.find / findIndex
  - 특정 조건을 만족하는 첫 요소(또는 인덱스)를 찾습니다.

```js
const arr2 = [1, 2, 3, 4];
arr2.find((x) => x > 2); // 3
arr2.findIndex((x) => x > 2); // 2
```

- Array.prototype.includes
  - 배열에 값이 포함되어 있는지 확인합니다. (원시값 체크)

```js
[1, 2, 3].includes(2); // true
```

- Array.prototype.some / every
  - some: 조건을 한 요소라도 만족하면 true.
  - every: 모든 요소가 조건을 만족하면 true.

```js
[1, 2, 3].some((x) => x > 2); // true
[1, 2, 3].every((x) => x > 0); // true
```

- Array.prototype.join / slice
  - join: 배열을 문자열로 결합.
  - slice: 배열의 일부를 복사(원본 변경 X).

```js
['a', 'b', 'c'].join('-'); // 'a-b-c'
[1, 2, 3, 4].slice(1, 3); // [2,3]
```

- Array.prototype.flat / flatMap
  - flat(depth): 중첩 배열을 평탄화.
  - flatMap: map + flat(1)

```js
[
  [1, 2],
  [3, [4]],
].flat(1); // [1,2,3,[4]]
```

- Set (중복제거) / Map
  - Set: 유일한 값 컬렉션 — 중복 제거에 유용.
  - Map: 키/값 쌍 저장(객체보다 안전한 키 사용 가능).

```js
const unique = [...new Set([1, 2, 2, 3])]; // [1,2,3]
```

- String.prototype.trim / padStart / padEnd
  - trim: 앞뒤 공백 제거.
  - padStart/padEnd: 고정 길이 문자열 만들기.

```js
'  hi  '.trim(); // 'hi'
'5'.padStart(2, '0'); // '05'
```

- parseInt / parseFloat / Number / isNaN
  - 문자열 → 숫자 변환. parseInt는 진수 지정 가능.

```js
parseInt('10', 10); // 10
parseFloat('3.14'); // 3.14
Number('5'); // 5
isNaN(Number('a')); // true
```

- Object.keys / Object.values / Object.entries
  - 객체 순회 및 변환에 유용.

```js
const o = { a: 1, b: 2 };
Object.keys(o); // ['a','b']
Object.entries(o); // [['a',1],['b',2]]
```

- JSON.parse / JSON.stringify

  - 문자열 ↔ 객체 변환.

- RegExp (정규식) 관련: test / replace / match
  - /pattern/.test(str): true/false 확인.
  - str.replace(/.../g, ''): 치환(전역).
  - str.match(/.../g): 매칭 결과 배열.

### 코테에서의 사용 팁 (요약)

- 빈 배열/빈 문자열 처리, parseInt의 NaN 처리에 주의하세요.
- 반복문에서의 시간복잡도: sort O(n log n), nested loop O(n^2).
- 문자열 → 숫자 변환 시 불필요한 공백/문자 제거를 먼저 하세요 (정규식 활용).
- 정규식은 편리하지만 가독성을 해칠 수 있으니 필요하면 주석이나 예시를 같이 남기세요.

(작은 개선) 예시 코드와 짧은 팁을 파일 내에 적어두면 실전에서 빠르게 참고 가능합니다.
