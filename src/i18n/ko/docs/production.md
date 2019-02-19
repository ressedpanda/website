# ✨ 프로덕션

제품화를 위해 애플리케이션을 번들할 때가 왔다면, Parcel 의 프로덕션(production) 모드를 사용하세요.

```bash
parcel build entry.js
```

## 최적화

감시(watch) 모드와 빠른 모듈 교체가 비활성화 되기 때문에 한 번 만 빌드 됩니다. 또한 모든 번들의 파일 크기를 줄이기 위하여 Parcel에서는 [terser](https://github.com/fabiosantoscode/terser)(자바스크립트), [cssnano](http://cssnano.co)(CSS), [htmlnano](https://github.com/posthtml/htmlnano)(HTML) 같은 미니파이어(minifier)를 사용합니다.

프로덕션 모드 활성화는 또한 환경 변수를 NODE_ENV=production로 설정합니다. React 와 같은 큰 라이브러리는 이 환경 변수를 설정함으로써 비활성화 되는 개발 전용 디버깅 요소가 있어 보다 작게 보다 빠르게 제품 빌드를 할 수 있습니다.

이러한 개발 전용 디버깅 기능을 이용하고 싶다면 [terser의 `dead_code` 옵션](https://github.com/terser-js/terser#compress-options)을 `true`로 설정하고(기본값) 아래와 같이 래핑할 수 있습니다.

```js
if (process.env.NODE_ENV === 'development') {
  // 또는, `process.env.NODE_ENV !== 'production'`
  // 개발 모드에서 작동, 운영 모드에서는 제거
}
```

## 파일 명명 규칙

Parcel은 최적의 성능과 효율을 위해 CDN에 까다로운 캐싱 규칙(SEO를 위한 번들을 읽을 수 있고 기억할 수 있는 이름을 가지고 있는지 등)을 설정 할 수 있도록 해시합니다.

번들의 이름을 지정할 때 Parcel은 아래의 표를 따릅니다. (진입점은 해시되지 않습니다.)

|                   Bundle Type | Type               | Content hashed |
| ----------------------------: | ------------------ | :------------: |
|                           Any | Entrypoint         |       ❌       |
|                    JavaScript | `<script>`         |       ✅       |
|                    JavaScript | Dynamic import     |       ❌       |
|                    JavaScript | Service worker     |       ❌       |
|                          HTML | iframe             |       ❌       |
|                          HTML | anchor link        |       ❌       |
| Raw (Images, text files, ...) | Import/Require/... |       ✅       |

파일 해시는 `<directory name>-<hash>.<extension>` 형식으로 명명됩니다.

## 크로스 플랫폼

프로덕션 빌드 성능을 최적화 하기 위해 Parcel은 [physical-cpu-count](https://www.npmjs.com/package/physical-cpu-count) 라이브러리를 사용해 시스템에서 사용 가능한 CPU 수를 판별하여 작업을 분배합니다.

이 모듈은 사용자 시스템에서 [`lscpu`](http://manpages.courier-mta.org/htmlman1/lscpu.1.html)를 사용할 수 있어야 작동합니다.

## CI 사용하기

Travis CI나 Circle CI 같은 지속적 통합(Continuous Integration) 도구와 통합하려는 경우 Parcel을 로컬 종속성으로 설치해야 합니다.

자세한 사항은 [이곳](getting_started.html#adding-parcel-to-your-project)을 참고해주세요.
