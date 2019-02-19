# 📦 애셋

Parcel 은 애셋(assets)을 기반으로 합니다. 애셋은 어떤 파일로든 표현될 수 있습니다만, Parcel 은 JavaScript, CSS, 그리고 HTML 파일과 같은 특정 유형의 애셋을 특별 지원 합니다. Pacel 은 이 파일들 안의 참조에서 자동으로 의존성을 분석하고 출력 번들에 포함시킵니다. 비슷한 유형의 애셋들은 같은 출력 번들로 함께 그룹화 합니다. 만약 다른 유형의 애셋을 가져왔다면 (예를 들어 JS에서 CSS를 가져온 경우(CSS in JS)), 자식 번들이 만들어지고 부모 번들에게 참조를 남깁니다. 후속 섹션에서 이에 대해 설명할 것입니다.

문서에서 특정 애셋 유형을 찾을 수 없는 경우 문서 번역본이 오래된 것일 수 있습니다. 지원되는 애셋의 전체 목록은 [parcel/src/Parser.js](https://github.com/parcel-bundler/parcel/blob/master/packages/core/parcel-bundler/src/Parser.js#L10)를 확인해주세요. 에셋을 파싱하는 파서는 [parcel/src/asset/](https://github.com/parcel-bundler/parcel/tree/master/packages/core/parcel-bundler/src/assets)를 확인하여 주세요.

Parcel에서 지원하지 않는 에셋 유형의 경우 플러그인이 존재하는지 확인하여 주세요.

- [Yarn](https://yarnpkg.com/en/packages?q=parcel-plugin-&p=1)
- [npm](https://www.npmjs.com/search?q=parcel-plugin-)
- [awesome-parcel](https://github.com/parcel-bundler/awesome-parcel#plugins)

혹은 [직접 만들 수 도 있습니다](plugins.html).
