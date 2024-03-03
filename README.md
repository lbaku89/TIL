# Description
학습한 내용이나, 메모용을 위한 repository

## 2024.03 

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

