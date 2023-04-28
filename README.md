# pre-onboarding 1-1 정리

개발자가 주로 작성하는 문서는 commit, PR, 그리고 code 입니다. 이러한 문서를 통해 개발자들은 서로 의도를 표현하고, 피드백을 주고 받고, 팀의 능률을 올리기 위해 노력합니다. 따라서 이러한 문서들의 중요성을 인식하고 이를 잘 작성하고자 하는 노력은 굉장히 중요합니다.

따라서 그와 관련된 라이브러리인 eslint, prettier, husky를 정리하겠습니다.

## install
```javasctipt
$ npm install eslint —save—dev
$ npm install prettier —save—dev
$ npm install eslint-config-prettier —save—dev
$ npm install husky —save—dev
```

---

## Prettier

### 설정방법
```javascript
// .prettierrc.js

module.exports = {
  printWidth: 100, // printWidth default 80 => 100 으로 변경
  singleQuote: true, // "" => ''
  arrowParens: 'avoid', // arrow function parameter가 하나일 경우 괄호 생략
};
```

### 명령어

* `npx prettier .`
    *  디렉토리의 모든 파일을 포맷팅한다.
* `npx prettier --watch .`
    *  `npx prettier .` 해당 명령어로는 파일의 내용을 변경할 수 없다.
    * 따라써 `--watch .`옵션을 통해 포맷팅 후 파일을 실제로 저장
* `npx prettier --watch -- cache .`
    *  `npx prettier --watch .` 해당 명령어로는 파일의 내용을 변경하고 저장까지 할 수 있지만, 변경되지 않은 모든 파일에 대해 포맷팅을 한다.
    * 따라서 `--cache`옵션을 추가해 변경된 파일에만 포맷팅을 적용할 수 있다. 

---

## ESLint

### 설정방법

```JSON
// .eslintrc
// 파일명에 확장자가 없을 경우 JSON + comment!

{
    "rules": {
        "no-var" : "error", // var를 사용할 경우 에러
        "eqeqeq" : "error" 
    }
}
```

### 명령어

* `npx eslint .`
    *  디렉토리의 모든 파일을 eslint로 검사
* `npx eslint --cache .`
    *  디렉토리의 모든 파일 중 변경된 파일만 검사
    *  해당 명령어를 사용하면 자동으로 .eslintcache 파일이 생성되는데 이것은 .gitignore에 넣어주는 것이 좋다.







