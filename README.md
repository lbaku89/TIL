# Description
학습한 내용이나, 메모용을 위한 repository

## 2024.02
#### Design System Component 만들 때 styling은 어떻게 하는 것이 좋을까?
일단 Nexts js 공홈을 살펴보니 4가지 선택권이 있었다. (https://nextjs.org/docs/app/building-your-application/styling/css-modules)
1. css module
2. Tailwind.css
3. css in js
4. Sass  

https://nextjs.org/docs/app/building-your-application/styling/css-modules 홈페이지에서 각각 내용을 살펴보니
css in js는 현재 서버컴포넌트에서 지원이 안된다고 하니 일단 제외 시키고 나머지 3가지 옵션중에서는 1 -> 4 -> 2 순서대로 마음에 든다. 원래는 scss가 좋아보였는데 요즘 css기능들이 많이 좋아져서 scss를 굳이 안써도 될 것 같다는 의견이 있었고 이는 타당해 보였다. 실제로 확인해보니 nesting도 되고, 변수선언도 되고, @mixin도 되고, calc를 이용한 산술 연산도 되고, import도 되는 듯 보인다. (직접 확인 필요)


#### 디자인 컴포넌트 관련 세미나 영상
```
FECONF 2022 [B1] 디자인 시스템, 형태를 넘어서
https://www.youtube.com/watch?v=21eiJc90ggo

FEConf 2023 [B5] 크로스 플랫폼 디자인 시스템, 1.5년의 기록
https://www.youtube.com/watch?v=obQvttzgSzY
```

