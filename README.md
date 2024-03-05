# Description
학습한 내용이나, 메모용을 위한 repository

## 2024.03 

#### Nextjs 실험: 서버컴포넌트 loading 시 fallback UI 처리 해보자
아래와 같이 실험 시 serverComponent1 는 promise가 도는 10초동안 fallback UI가 대체 되고 그 후 나타났다.
나머지 컴포넌트1,2,3는 serverComponent1과 독립적으로 화면에 렌더링 되어 있었다. 

```tsx
// page.tsx 
import { lazy, Suspense } from "react";
const ServerComponent1 = lazy(() => import("./_component/ServerComponent1")); 

return (
  <다른컴포넌트1 />
  <Suspense
    fallback={<div>suspense loading ui</div>}>
  >
    <serverComponent1 />
  </Suspense>
  <다른컴포넌트2 />
  <다른컴포넌트3 />
)

// serverComponent1.tsx
export default function ServerComponent1() {
    const promise:Promise<string> = new Promise((resolve, reject) => {
        setTimeout(() => {
            resolve('안녕하세요')
        }, 10000)
    })

    return (
        <div>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            <h3>test</h3>
            {promise}
        </div>
    )
}
```

lazy 없이 사용하게 된다면 아래와 같은 에러가 뜬다 
( 대충 서버에서 렌더링된 모습과 클라이언트에서 하이드레이션 된 모습이 다르다는 식의 내용이다 ) 

![image](https://github.com/lbaku89/TIL/assets/96039047/7a9ca761-ebb1-482b-bf64-70e309670d47)





#### call, apply, bind
- call
```js
const hyunwoo = { name:"hyunwoo"}

function showName(){
  console.log(this.name)
}

const showName2(){
  console.log(this.name)
}

showName.call(hyunwoo) // hyunwoo <- 실행 컨텍스트에서 this를 해석
showName2.call(hyunwoo) // undefined <- arrow function은 정의 될 때
// this를 판단하기 때문에 여기서 this는 window나 node 같은 요소로 판단 하기 때문에 undefined가 출력

``` 


#### debounce 
- 구현 경험기 
  - https://eun-jee.com/post/front-end/debounce_in_React/
- 기본 원리
 ```html
//index.html

...
<button onclick="debounce(log,1000)">버튼</button>
...

<script>
  let timerObj = null // timer 라는 변수는 비어있음
   
  const log =()=>{
      console.log('hello')
  }

  // 호출 시 timerObj에 setTimeout 존재 시 해당 timer를 clear 하고 새로운 setTimeout 실행 
  const debounce = (fn,delay) =>{
    if(timerObj){    
      clearTimeout(timerObj)
    }
    timerObj = setTimeout(()=>{
      fn()
    },delay) 
  }

</script>
``` 

#### 앞으로의 공부 방향
- React, Ts, Yarn, Prettier, emotion, interaction, Jest Test, 

#### 프로그래머스 모의 과제 테스트  
https://school.programmers.co.kr/skill_check_assignments?page=1

#### Nextjs Lint 설정에 관해 ... 
https://nextjs.org/docs/app/building-your-application/configuring/eslint (공홈) 을 확인해본 결과 
- Nextjs 설치 시 typescript option을 설정하면 깔리는 eslint-config-next 는 recommended configuration 이라고 한다.
- Nextjs 를 사용하면서 생길 수 있는 common issue 들을 catch 할 수 있는 lint config 이므로 기본으로 깔리는 설정으로 사용하기를 권장한다.
- 다른 config 사용할 시 guide 문서도 제공된다. 

## 2024.02

#### 새로운 프로젝트 진행시 ... 
  - 기상청 open api 이용 하자
  - Nextjs
  - react-query
  - redux-toolkit or zustand
  - 노드 서버 구축
#### semantic versions in published packages  

![image](https://github.com/lbaku89/TIL/assets/96039047/e71d1d39-e92b-4616-91e1-bc4766ca242a)

#### pre-onboarding 3월 프론트엔드 챌린지 커리큘럼    

![image](https://github.com/lbaku89/TIL/assets/96039047/78de917c-5db7-467d-9d00-5e19af9b245c)


#### 다음으로 진행할 사이드 프로젝트 진행시 관심있는 기술 및 프로젝트 주제 
- 무한 스티커 게시판 프로젝트
- 메이플랜드 오픈 api를 이용한 프로젝트
- ui kit library npm에 배포
- 스토리북
- next server component
- react portal
- zustand, theme, dark mode    
- aws, mysql 배포
- Next auth, Oauth2.0, jwt 이용
- React query, zustand, react portal
- Next app route, server component, fetch caching 기능 이용 
- 웹소켓, 웹RTC
- 크롤링
- 카카오 오픈 api 이용
- 베스트 댓글 모음집 
- 스토리북 배포
```
사이드 프로젝트 주제 선정
https://www.youtube.com/watch?v=L0jjicJ85NI
```

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

