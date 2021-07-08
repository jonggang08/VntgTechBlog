---
title: Gatsby 설치 및 사용 매뉴얼
date: 2021-06-03 10:05:46
thumbnail: ../../image/gatsbymanual.jpg
categories: 
- [Static Site Generator,Gatsby]
---
###### 배종강@기술지원실
# Gatsby 

## 1.초기설정

- Node.js 다운로드
- 명령프롬프트(Command Line/CLI) 에서 npm install -g gatsby-cli 입력
```
npm install -g gatsby-cli
```
- 템플릿 클론
    - 해당 홈페이지에 많은 템플릿들을 확인후 선택.
    - 템플릿 고르고 github repository 링크를 clone
    - CLI에서 클론한 링크 입력후 페이지 생성 확인 
 ```
 gatsby new my-project https://xxxxxxx
 cd my-project
 gatsby develop
 ```

 ## 2.커스터마이징

 - gatsby-config.js으로 접속후 제목/저자/테마배경컬러등을 바꿀수 있음

```
      options: {
        name: `VNTG`,
        short_name: `VNTG`,
        start_url: `/`,
        background_color: `#f7f0eb`,
        theme_color: `#a2466c`,
        display: `standalone`,
        icon: "static" + settings.meta.iconimage,
      },
 ```

 ## 3.포스트 추가하기

 - 포스트는 우리가 gatsby-config.js 파일에서 별다른 설정을 하지 않았기 때문에 디폴트로 content/posts 디렉터리 내에 만들면 자동으로 블로그 포스트 목록에 표시됨.
 - 템플릿은 똑같이 입력하고 제목이나 slug 추가후 내용삽입하면 완성
```
---
template: blog-post
title: 예시
slug: /newblogpage
date: 2021-06-03 10:46
description: 예시포스트
---

```

 ## 4. Github 배포

 - GitHub Pages 는 GitHub에서 무료로 호스팅하는 공개 웹페이지.
GitHub의 저장소에서 개인이나 조직 또는 프로젝트 페이지를 호스팅하도록 설계됨.
- GitHub Pages 의 종류는 크게 두가지
    - 개인 사이트 GitHub Pages
    - 프로젝트 사이트 GitHub Pages
- <b>개인 사이트</b>는 (username).github.io라는 저장소를 만들게되면 자동으로 개인 사이트를 위한 GitHub Pages를 만들 수 있음. 이 사이트의 저장소 브랜치는 master에서 만들어져야함.
- <b>프로젝트 사이트</b> GitHub에 등록한 프로젝트별로 사이트를 자동으로 만들 수 있음. 프로젝트 사이트는 (username).github.io/[프로젝트 저장소 이름]으로 만들어짐. 사이트의 저장소를 위한 브랜치가 gh-pages라는 브랜치이여야함.

### 배포방법
- github에서 ‘owner이름/owner이름github.io’ repository 생성 
e.g) https://github.com/배종강/배종강.github.io.git
- CLI에서 gh-pages 설치 
```
npm install gh-pages --save-dev
```
- package.json에서 gh-pages 코드 추가 
```
 {
  "scripts": {
    "deploy": "gatsby build --prefix-paths && gh-pages -d public"
  }
} 
```
- CLI에서 코드를 Github 해당 repo로 push후 배포
``` 
git init
git remote add origin (github repo 주소)
git add .
git commit -m "커밋내용"
git push -u origin gh-pages
npm run deploy

```
## <a href=" https://www.gatsbyjs.com/docs/how-to/previews-deploys-hosting/how-gatsby-works-with-github-pages/" target="_blank"><span style="color:blue">Reference </span></a> 