**_ Default Setting _**

```
make a folder on cmd
>mkdir typechain

open vsc's project on cmd
>code typechain

install typescript
>npm i -D typescript

initialize package.json
>npm init -y

```

---

### tsconfig.json

A TSConfig file in a directory indicates that the directory is the root of a TypeScript or JavaScript project. When compiling, A TSConfig file designate the root file and the compile option that we need.

디렉터리에 tsconfig.json 파일이 있으면 해당 디렉터리가 TypeScript 프로젝트의 루트임을 나타냅니다. tsconfig.json 파일은 프로젝트를 컴파일하는 데 필요한 루트 파일과 컴파일러 옵션을 지정합니다.

[What is a tsconfig.json?](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html#handbook-content)

#### Root Fields

Starting up are the root options in the TSConfig
These options relate to how your TypeScript or JavaScript project is set up.

Target (기본값: ES3)
최신 브라우저는 모든 ES6 기능을 지원하므로 ES6는 좋은 선택입니다. 코드가 이전 환경에 배포된 경우 더 낮은 target을 설정하거나 최신 환경에서 코드 실행이 보장되는 경우 더 높은 target을 설정하도록 선택할 수 있습니다.
ex) 화살표 함수() => this는 ES5 이하이면 함수 표현식으로 바뀝니다.

특별한 ESNext 값은 TypeScript 버전이 지원하는 가장 높은 버전을 나타냅니다. 이 설정은 다른 TypeScript 버전 간에 동일한 의미가 아니며 업그레이드를 예측하기 어렵게 만들 수 있으므로 주의해서 사용해야 합니다.
https://www.typescriptlang.org/tsconfig#target

"build": "tsc" 또는 "npx tsc"

lib
타입스크립트에게 어떤 API를 사용하고 어떤 환경에서 코드를 실행하는 지를 지정할 수 있습니다.
(target 런타임 환경이 무엇인지를 지정합니다.)
프로그램이 브라우저에서 실행되면 lib에 "DOM" 유형 정의를 할 수 있습니다.
DOM: window, document 등
ex) "lib": ["ES6","DOM"]

https://www.typescriptlang.org/tsconfig#lib

타입스크립트는 자바스크립트와는 다르게 strongly-typed 이기 때문에 타입스크립트에서 사용할 자바스크립트 라이브러리의 함수 모양을 설명해야하군요. 그리고 이 타입 정의를 서술한 파일이 Declaration File 이군요.

https://github.com/microsoft/TypeScript/tree/main/lib : 여기에 정의된 d.ts 파일 목록이 있네요. TS에서 사전에 DOM 이나 ES 관련된 내용을 정의해두고 이를 필요한 것만 끌어다 쓰는 방식이라고 이해해도 될까요?

Typescript는 처음부터 DOM API에 대한 정보를 가지고 있지 않기에, 이를 사용하기 위해 lib에서 유형을 정의해주는 것이군요.. 감사합니다.

strict

모든 엄격한 타입 검사 옵션을 활성화합니다.
strict 플래그는 프로그램 정확성을 더 강력하게 보장하는 광범위한 타입 검사 동작을 가능하게 합니다.

https://www.typescriptlang.org/tsconfig#strict

### JavaScript vs TypeScript

### What is the best part in TypeSCript Language more than other Launguage.

### d.ts vs JSDoc

in d.ts, we can use more JS features, maybe polymorpishm and generics.

We don't have to modify our actual JavaScript code.

@ts-check
JavaScript 파일에서 오류를 활성화하려면 // @ts-check를 .js 파일의 첫 번째 줄에 추가하여 TypeScript가 오류를 발생시키도록 합니다. TypeScript는 여러 오류를 제공할 수 있습니다.
이러한 오류를 무시하고 싶다면 // @ts-ignore 또는 // @ts-expect-error를 추가하여 특정 줄의 오류를 무시할 수 있습니다.
https://www.typescriptlang.org/docs/handbook/intro-to-js-ts.html#ts-check

JSDoc Reference
JSDoc 주석을 사용하여 JavaScript 파일에 type 정보를 제공할 수 있습니다. (자바스크립트 파일에서 타입 정보를 제공할 수 있습니다.)
https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html

@param, @returns

```
/**
* @param {string} p1 - A string param.
* @param {string=} p2 - An optional param (Google Closure syntax)
* @param {string} [p3] - Another optional param (JSDoc syntax).
* @param {string} [p4="test"] - An optional param with a default value
* @returns {string} This is the result
*/
function stringsStringStrings(p1, p2, p3, p4) {
// 코드...
}
```

https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html#param-and-returns

#### ts-node

TypeScript execution and REPL for node.js, with source map and native ESM support.

@ysjkof 'ts-node' 패키지를 설치할 때, crypto.d.ts가 자동으로 node_modules/@types/node 경로에 생성되기 때문인것 같아요. 따라서 ts-node를 설치하지 않고 import crypto from 'crypto'를 작성하게 되면 이때는 타입정의파일이 없기 때문에 영상에서 니코가 보여준 것과 같은 에러가 발생합니다.

ts-node는 Node.js용 TypeScript 실행 엔진 및 REPL입니다. JIT는 TypeScript를 JavaScript로 변환하므로 사전 컴파일 없이 Node.js에서 TypeScript를 직접 실행할 수 있습니다.

[npm i ts-node -D](https://www.npmjs.com/package/ts-node)
Run TypeScript without having to build all the time.

[npm i nodemon -D](https://www.npmjs.com/package/nodemon)

[esModuleInterop](https://www.typescriptlang.org/tsconfig/#esModuleInterop)
CommonJS 모듈을 ES6 모듈 코드베이스로 가져오려고 할 때 발생하는 문제를 해결합니다. ES6 모듈 사양을 준수하여 CommonJS 모듈을 정상적으로 가져올 수 있게 해줍니다.

블록체인 시리즈
https://www.youtube.com/playlist?list=PL7jH19IHhOLOJfXeVqjtiawzNQLxOgTdq
