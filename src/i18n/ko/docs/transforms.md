# 🐠 변환

대부분의 번들러들이 애셋 변환(transform)을 위한 플러그인 설치와 설정(configuration)을 요구합니다. Parcel 은 많은 수의 일반적인 변환과 트랜스파일러를 내장하여 지원합니다. [Babel](https://babeljs.io)을 사용하는 JavaScript, [PostCSS](http://postcss.org)을 사용하는 CSS, [PostHTML](https://github.com/posthtml/posthtml)을 사용하는 HTML 을 변환할 수 있습니다. Parcel 은 모듈 안에서 설정 파일(예: `.babelrc`, `.postcssrc`)을 발견했을 때 자동으로 이 변환을 실행합니다.

## 써드파티 모듈

Configuration files (such as `.babelrc`) will not be applied to files inside third-party `node_modules` by default. However, if the module's directory is symlinked (as is common in some monorepo conventions) and the module's `package.json` has the `source` field set, then configuration files inside the module's directory will be respected. Here are the types of values supported by the `source` field:

- Treat all files as source code, don't change the resolution

```json
{
  "main": "foo.js",
  "source": true
}
```

- When compiling from source, use bar.js as the entry point

```json
{
  "main": "foo.js",
  "source": "bar.js"
}
```

- When compiling from source, alias specific files

```json
{
  "main": "foo.js",
  "source": {
    "./foo.js": "./bar.js",
    "./baz.js": "./yay.js"
  }
}
```

- When compiling from source, alias using glob patterns

```json
{
  "main": "foo.js",
  "source": {
    "./lib/**": "./src/$1"
  }
}
```

The last example allows you to replace your entire lib directory with src so import 'my-module/lib/test.js' would resolve to 'my-module/src/test.js'. You could also use a top-level catch-all pattern like `"**": "./src/$1"` for packages like lodash that have many files in the root to replace (e.g. lodash/cloneDeep with lodash/src/cloneDeep).
