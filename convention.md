# convention

## (1) Syntex Style_
- 변수, 함수명, 파일명
```
camelCase, snake_case, kebab-case, UPPER_CASE, lower_case
```

- 변수 선언시 var대신 let이나 const를 사용

- 들여쓰기는 탭이나 4칸공백보다는 2칸 공백을 권유


- 문장의 끝에 세미콜론 기재를 유무 


- Arrow Function으로 표현
```
// good
[1, 2, 3, 4, 5].map((x) => x * x);

//bad
[1, 2, 3, 4, 5].map(function(x) {
    return x * x; 
});
```

- 문자열 연결시 + 보다는 탬플릿 문자열로 표현 (따옴표 모양 유심히 볼 것)
```
let name = "itholic";

// good
console.log(`My name is ${name}`);

// bad
console.log("My name is " + name);
```

- 큰따옴표(“), 작은따옴표(‘)를 사용, 문자열에 작은따옴표 포함시 탬플릿 문자열 사용 (`)
## (2) Code Style
- Callback-Style
```
fs.readFile(FILENAME, 'utf-8', (err, result)) => {
  if (err) {
    console.error(err)
  } else {
    console.log(result)
  }
}
```

- Sync-Style
```
try {
  const result = fs.readFileSync(FILENAME, 'utf-8')
  console.log(result)
} catch (error) {
  console.error(error)
}
```

- Promise-Style
```
async function main(){
  try {
    await fs.promises.readFile(FILENAME, 'utf-8')
  } catch (error) {
    console.error(error)    
  }
}

main()
```