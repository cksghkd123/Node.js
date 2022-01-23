# require




node에서는 각 파일 하나하나가 모듈이되고 모듈을 가져오는 함수

## (1) module의 경로를 읽어주는 방법

```
const {path, paths, filename} = module



console.log({

  path,

  paths,

  filename,

})
```

## (2) CommonJS방식 : require      <= nodejs에서는 require 사용

```
const animals = require("./animals")

console.log(require("./animals"))

console.log(module.require("./animals"))
```



## (3) ECMAScript방식 : import, export
```
import animals from './animals.js'

console.log(animals)
````

## (4) 한번 require한 모듈은 계속 쓰임

```
const animalsA = require('./animals')

const animalsB = require('./animals')

const animalsC = require('./animals')



console.log(animalsA === animalsB)

console.log(animalsB === animalsC)
```

```
True
True
```
같은 객체를 공유


## (5) node standard library에 있는 모듈은 절대 경로를 지정해 가져온다.

이 프로젝트 내의 다른 파일은 상대경로를 지정해 가져온다.

절대경로를 지정하면 module.paths의 경로들을 순서대로 검사하여 해당 모듈이 있으면 가장 첫 번째 것을 가져온다.

```
const http = require('http')

console.log(http)
```

