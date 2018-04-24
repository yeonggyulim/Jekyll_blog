---
layout: post
title: "GitHub Pages로 Website 만들기"
description: "GitHub Pages를 이용하여 Website를 만드는 방법 설명입니다."
tags: [github pages, website, jekyll]
published: true
comments: true
image:
  feature: github-pages-jekyll.jpg
---
---
### GitHub Pages란?
  - GitHub에서 무료로 호스팅하는 공개 웹페이지

### Jekyll이란?
  - GitHub에서 제공하는 ruby기반 static 웹 페이지 서비스
  - 사용시에 유저는 markdown이나 text기반의 내용을 업로드하여 블로그 운영 가능

### Markdown이란?
  - 일종의 마크업 언어로 텍스트에 태그 이용하여 글자를 꾸미거나 이미지 삽입 가능

---
### 2가지 방법
  1. **User or Organizational site**
      - Repository name : {username}.github.io
      - 주소 : {username}.github.io
      - 한 계정에 한 site 생성 가능
      - Jekyll 사용 제약 적음
  2. **Project site**
      - Repository name : project name
      - 주소 : {username}.github.io/{repositoryname}
      - 여러 site 생성 가능
      - Jekyll 사용 제약 있음
      - gh-pages 혹은 master branch로 사용해야 함

여기서는 제약이 적은 website를 만들기 위해 (1)번 User or organizational site 사용

---
## 1. 프로젝트 시작/저장소 만들기
<img src="/images/github-pages/github-pages-1.jpg" alt="" />
<img src="/images/github-pages/github-pages-2.jpg" alt="" />
<img src="/images/github-pages/github-pages-3.jpg" alt="" />
Start a Project -> 저장소 이름 입력 -> Create repository 클릭 시 저장소가 만들어지면서 {username}.github.io로 publish 되고 간단하게 웹사이트가 만들어진다.

## 2-1. GitHub Pages Theme 이용하기 (Jekyll 기본 Pages Theme) (더 다양한 테마를 보고 사용하고 싶다면 Skip)
The repository -> Settings -> Github Pages -> Coose a Theme -> Select Theme 클릭
<img src="/images/github-pages/github-pages-4.jpg" alt="" />
<img src="/images/github-pages/github-pages-5.jpg" alt="" />
<img src="/images/github-pages/github-pages-6.jpg" alt="" />
<img src="/images/github-pages/github-pages-7.jpg" alt="" />
그러면 웹사이트가 해당 테마로 바뀌게 된다.
<img src="/images/github-pages/github-pages-8.jpg" alt="" />

## 2-2. Jekyll Theme 이용하기 (Jekyll에서 마음에 드는 Theme 골라 적용하기)
<figure>
<img src="/images/github-pages/github-pages-9.jpg" alt="" />
<figcaption>
<a href="http://jekyllthemes.org/" title="Jekyll Theme">지킬 테마</a>
</figcaption>
</figure>
위의 웹사이트에서 원하는 형식의 테마를 선택하여 데모 버전을 볼 수도 있고, 다운로드 받을 수도 있다. 형식은 블로그, 온라인 레쥬메, 프로파일 등이 있다.

<figure>
<img src="/images/github-pages/github-pages-10.jpg" alt="" />
<figcaption>
<a href="http://jekyllthemes.org/themes/landing-page/" title="Jekyll Landing Page Theme">지킬 Landing Page 테마</a>
</figcaption>
</figure>
블로그가 아닌 내 basic 정보를 적기 위한 웹사이트를 만들기 Landing Page라는 테마를 골랐다. 위의 caption에서 다운로드 혹은 데모버전을 볼 수 있다.

## 3. 원격저장소(서버)의 Repository를 지역저장소로 가져오기 (git clone 이용)
<img src="/images/github-pages/github-pages-11.jpg" alt="" />
HTTPS를 Copy해서 Terminal 실행 후 git clone을 이용해 다운로드 한다. (git 설치되었다고 가정)
<img src="/images/github-pages/github-pages-12.jpg" alt="" />

## 4. 지역저장소에 다운로드 받은 Jekyll 테마를 저장하기
git clone으로 다운 받은 지역 저장소 디렉토리에 파일들(2-1에서 받은 파일들)을 삭제하고, 2-2로 받은 테마 폴더 안의 파일들을 복사하여 붙여넣는다.
<img src="/images/github-pages/github-pages-13.jpg" alt="" />
<img src="/images/github-pages/github-pages-14.jpg" alt="" />

## 5. 지역저장소의 파일들을 원격저장소(서버)로 동기화 시키기 (git status, add, commit, push 사용)
git status를 통해 지역저장소의 파일 변화를 볼 수 있고, git add와 commit 그리고 push를 통해 원격 저장소에 동기화 시킨다.
<img src="/images/github-pages/github-pages-15.jpg" alt="" />
<img src="/images/github-pages/github-pages-16.jpg" alt="" />
<img src="/images/github-pages/github-pages-17.jpg" alt="" />
그럼 이렇게 변한 테마의 웹사이트를 확인할 수 있다.
<img src="/images/github-pages/github-pages-18.jpg" alt="" />

## 6. (반복) 지역저장소에 있는 코드들을 수정하여 원격저장소(서버)로 git add, commit, push하여 지속 수정하면 된다.
  - [yeonggyulim.github.io/profile](https://yeonggyulim.github.io/profile)
  - 사정상 User site를 블로그로 이용하기 위해 위의 예제를 후에 project site로 변경하였습니다.

---
### 참조
  - [github pages](https://pages.github.com/)
  - [github page로 블로그 만들기](http://gjchoi.github.io/env/Github-page%EB%A1%9C-%EB%B8%94%EB%A1%9C%EA%B7%B8-%EB%A7%8C%EB%93%A4%EA%B8%B0/)


### 참고 사항
  - [GitHub Help](https://help.github.com/articles/should-i-rename-lt-username-github-com-gt-repositories-to-lt-username-github-io-gt/)
  - 검색하다 보니, 예전에는 {username.github.com}이름의 repositories가 GitHub Pages로 되었는데, 이제는 User and Organizational Page repository 이름으로 {username.github.io}를 쓰고 있다고 한다.
  - .com 으로 만든 Pages를 .io로 바꿀 필요는 없지만, 새로운 repositories들은 .io를 사용하길 강력 추천하고, .io와 .com 파일이 둘 다 있다면 .io 버전이 사용될거라고 한다.
