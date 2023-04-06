**_ Default Setting _**

### make a folder on cmd

mkdir typechain

### open vsc's project on cmd

code typechain

### install typescript

npm i -D typescript

### initialize package.json

npm init -y

---

### tsconfig.json

A TSConfig file in a directory indicates that the directory is the root of a TypeScript or JavaScript project.

디렉터리에 tsconfig.json 파일이 있으면 해당 디렉터리가 TypeScript 프로젝트의 루트임을 나타냅니다. tsconfig.json 파일은 프로젝트를 컴파일하는 데 필요한 루트 파일과 컴파일러 옵션을 지정합니다.
https://www.typescriptlang.org/docs/handbook/tsconfig-json.html#handbook-content

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
