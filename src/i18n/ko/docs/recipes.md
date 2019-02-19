# 🍰 레시피

## React

먼저 React 를 위해 다음 의존성들을 설치합니다.

[Blog Post](http://blog.jakoblind.no/react-parcel/)

```bash
npm install --save react
npm install --save react-dom
npm install --save-dev parcel-bundler
```

<sub>혹시 yarn 패키지 매니저를 사용하신다면 다음의 명령어로 설치할 수 있습니다.</sub>

```bash
yarn add react
yarn add react-dom
yarn add --dev parcel-bundler
```

그리고 시작 스크립트를 `package.json`에 지정해주세요.

```javascript
// package.json
"scripts": {
  "start": "parcel index.html"
}
```

## Preact

먼저 Preact 를 위해 다음 의존성들을 설치합니다.

```bash
npm install --save preact
npm install --save preact-compat
npm install --save-dev parcel-bundler
npm install --save-dev babel-preset-preact
```

<sub>혹시 yarn 패키지 매니저를 사용하신다면 다음의 명령어로 설치할 수 있습니다.</sub>

```bash
yarn add preact
yarn add preact-compat
yarn add --dev parcel-bundler
yarn add --dev babel-preset-preact
```

그리고 다음과 같이 babel 설정 파일을 만들어주세요.

```javascript
// .babelrc
{
  "presets": ["preact"]
}
```

그리고 시작 스크립트를 `package.json`에 지정해주세요.

```javascript
// package.json
"scripts": {
  "start": "parcel index.html"
}
```

## Vue

먼저, Vue 를 사용하기 위해 의존성을 설치합니다.

```bash
npm install --save vue
npm install --save-dev parcel-bundler
```

<sub>혹시 yarn 패키지 매니저를 사용하신다면 다음의 명령어로 설치할 수 있습니다.</sub>

```bash
yarn add vue
yarn add --dev parcel-bundler
```

`package.json`에 시작 스크립트를 작성해주세요.

```javascript
// package.json
"scripts": {
  "start": "parcel index.html"
}
```

## Typescript

Typescript를 사용하기 위하여 의존성을 설치합니다.

```bash
npm install --save-dev typescript
npm install --save-dev parcel-bundler
```

<sub>Yarn 패키지 매니저를 사용하신다면 다음의 명령어로 설치할 수 있습니다.</sub>

```bash
yarn add typescript --dev
yarn add --dev parcel-bundler
```

### index.html 컴파일

`package.json`에 스크립트를 추가합니다.

```javascript
// package.json
"scripts": {
  "start": "parcel index.html"
}
```

그리고 `index.html`에 `.ts` 파일을 추가해주세요.

```html
<!-- index.html -->
<!DOCTYPE html>
<html lang="en">
  <head> </head>
  <body>
    <!-- Here 👇 -->
    <script src="./myTypescriptFile.ts"></script>
  </body>
</html>
```

이게 끝입니다!

### 직접 컴파일하기

`package.json`에 스크립트를 추가해주세요.

```javascript
// package.json
"scripts": {
  "start": "parcel myTypescriptFile.ts"
}
```

이걸로 끝입니다! 😄 컴파일 된 `.js` 파일은 dist 폴더에서 찾을 수 있습니다.
