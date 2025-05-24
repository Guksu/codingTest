# 입력값이 하나일 경우

```ts
const input = require("fs")
  .readFileSync(process.platform === "linux" ? "/dev/stdin" : "./input.txt")
  .toString()
  .trim();

//input: hello
//output: hello
```

# 입력값이 띄어쓰기로 구분된 한 줄의 값들인 경우

```ts
const input = require("fs")
  .readFileSync(process.platform === "linux" ? "/dev/stdin" : "./input.txt")
  .toString()
  .trim()
  .split(" ");
//   .map(Number); // 숫자인 경우
//input: hello world
//output: ['hello', 'world']
```

# 입력값이 여러 줄의 값들인 경우

```ts
const input = require("fs")
  .readFileSync(process.platform === "linux" ? "/dev/stdin" : "./input.txt")
  .toString()
  .trim()
  .split("\n");
//   .map(Number);  // 숫자인 경우

//input:
//a
//b
//c
//d
//output: ['a', 'b', 'c', 'd']
```

# 입력값이 여러 줄의 값들이 띄어쓰기로 구분되어 있는 경우

```ts
const input = require("fs")
  .readFileSync(process.platform === "linux" ? "/dev/stdin" : "./input.txt")
  .toString()
  .trim()
  .split("\n")
  .map((el) => el.split(" "));
//    .map((el) => el.split(" ").map(Number)); // 숫자인 경우

//input:
//ab cd
//ef gh
//my name is minjoon
//hi hello
//output: [
//  [ 'ab', 'cd' ],
//  [ 'ef', 'gh' ],
//  [ 'my', 'name', 'is', 'minjoon' ],
//  [ 'hi', 'hello' ]
//]
```

출처: https://minjo0n.tistory.com/2 [민이랑준:티스토리]
