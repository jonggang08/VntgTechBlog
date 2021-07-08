---
title: Hexo 설치 및 사용 매뉴얼
date: 2021-06-03 11:05:46
thumbnail: ../../image/hexothumb.jpg
lede: dd

categories: 
- [Static Site Generator,Hexo]
---
## 1.초기설정

- Node.js 다운로드
- 명령프롬프트(Command Line/CLI) 에서 npm install -g hexo-cli 입력
```
npm install -g hexo-cli
```
- Hexo 파일 폴더 생성후 페이지 생성 확인
 ```
hexo init [폴더명]
cd [폴더명]
npm install
hexo server
 ```

## 2. 테마설정(Hueman 테마이용)
 - 해당폴더로 이동후 Hueman 테마를 themes/hueman 폴더로 클론.
 ```
cd [폴더명]
git clone https://github.com/ppoffice/hexo-theme-hueman.git themes/hueman
```
- config.yml 에서 ##Theme 부분을 landscape에서 hueman으로 수정.
```
## Themes: https://hexo.io/themes/
theme: hueman
```
- themes/hueman 폴더에 있는 _config.yml.example를 _config.yml로 바꿈.

## 3.커스터마이징
 - Gatsby 블로그와 유사하게 _config.yml에서 제목 및 저자 수정 가능
 ```
 # Site
title: VNTG 기술블로그 
subtitle: Technical Blog
description: ''
keywords:
author: VNTG
language: en
timezone: ''
```

## 4. Github 저장소에 소스 저장(Push)
 - 새로운 저장소(repo)를 만들고 소스들을 푸쉬해준다.
 ```
git init
git remote add origin 저장소
git add .
git commit -m “커밋 메세지”
git push origin master
```

## 5. Github 페이지에 배포
 - _config.yml으로 이동후 deploy를 아래 코드와 같이 변경
 ``` 
 deploy: 
  type: git
  repo: https://github.com/xxxx/xxxx.github.io.git
  branch: master
  ```

- 배포를 가능케하는 플러그인 (hexo-deployer-git)을 설치
``` 
npm install --save hexo-deployer-git
```
- 정적 리소스를 생성후 배포
```
hexo generate
hexo deploy
```

## <a href=" https://hexo.io/docs/github-pages.html" target="_blank"><span style="color:blue">Reference </span></a> 

