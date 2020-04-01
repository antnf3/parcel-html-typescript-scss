# parcel-html-typescript-scss

html-typescript-scss with parcel

## 기본 web 개발환경 설정

1.pacel
2.typescript
3.scss

## package.json 파일 생성

```shell
> yarn init -y
```

## parcel 설치

parcel이 설치되어있지 않으면 아래 명령어를 사용하여 전역으로 설치한다.

```shell
> yarn global add parcel-bundler
```

## yarn global add 오류 수정

windows 에서 yarn global add 를 실행하면 설치한 해당패키지를 찾을 수 없다고 나옵니다.

- 문제해결방법

1. 아래 명령어를 사용하여 bin 폴더의 위치를 알아냅니다.

```shell
$ yarn global bin
C:\Users\antnf\AppData\Local\Yarn\bin
```

2. windows환경변수 path에 위의 bin 경로를 등록해줍니다.
3. 터미널을 재실행하면 정상적으로 패키지가 실행됩니다.

## typescript 설정

```shell
> touch tsconfig.json
```

```json
{
  "compilerOptions": {
    "module": "commonjs",
    "noImplicitAny": true,
    "removeComments": true,
    "esModuleInterop": true,
    "sourceMap": true,
    "target": "es5",
    "jsx": "react",
    "baseUrl": "./src",
    "paths": {
      "~*": ["./*"]
    }
  },
  "include": ["src/**/*"],
  "exclude": ["node_modules"]
}
```

## package.json파일의 scripts 등록

```json
"scripts": {
    "start": "parcel src/index.html --target browser --port 3000 --open",
    "build": "parcel build src/index.html -d build --public-url ./"
  }
```

## SCSS 사용설정

> > SCSS 컴파일은 sass (dart-sass의 JS 버전) 모듈을 필요로 합니다.

```shell
> yarn add -D sass
```
