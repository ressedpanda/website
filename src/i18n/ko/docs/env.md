# 🌳 환경 변수

Parcel은 [dotenv](https://github.com/motdotla/dotenv)을 사용하여 `.env`파일을 통해 환경변수를 불러올 수 있습니다.

`.env` files are to be stored alongside the `package.json` that contains your `parcel-bundler` dependency.

Parcel은 `NODE_ENV`의 값에 따라 `.env`파일을 로드합니다.

| 유효한 `.env` 파일이름   | `NODE_ENV=\*` | `NODE_ENV=test` |
| ------------------------ | ------------- | --------------- |
| `.env`                   | ✔️            | ✔️              |
| `.env.local`             | ✔️            | ✖️              |
| `.env.${NODE_ENV}`       | ✔️            | ✔️              |
| `.env.${NODE_ENV}.local` | ✔️            | ✔️              |

참고:

- `NODE_ENV` 의 기본 값은 `development`입니다.
- [테스트 결과는 모두 동일해야 하므로](https://github.com/parcel-bundler/parcel/blob/28df546a2249b6aac1e529dd629f506ba6b0a4bb/src/utils/env.js#L9)`.env.local`은 `NODE_ENV=test`일 때 로드되지 않습니다.
