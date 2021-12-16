# 유레카프로젝트 기말 프로젝트
#### 20213079 정수현

#### Blog 주소

- https://suhyun7890.github.io/
- 유레카프로젝트 기말 프로젝트를 위해 임시로 생성한 계정인 suhyun7890과 원래 쓰던 계정인 112jshjsh를 둘 다 사용하였습니다.

### 개발 방법

- Jekyll을 이용하였습니다.
- Github Repository를 이용하여 Webpage로 제작하였습니다.


## 1. Repository

### ① Repository 생성

- Github에서 suhyun7890.github.io라는 이름의 repository를 생성하였습니다.

### ②Local-Remote Repository와 연동

- Remote Repo의 주소를 복사하여, 터미널에서 clone하였습니다.
- 이 결과로 'blog'라는 폴더가 생성되었고, 이 폴더 내부에서 작업을 진행하였습니다.

```
git clone https://github.com/suhyun7890/suhyun7890.github.io.git blog
```

### ③HTML 예시 문서 작성 및 commit

- 예시 문서(index.html)를 작성 후, git commit을 남기고 원격 저장소에 반영하였습니다.

```
# 현재 상태 확인
git status

# 변경한 파일(예시 문서) 추가
git add index.html

# commit 남기기
git commit -m "add: index.html"

# 현재 branch의 이름 main으로 변경
git branch -M main

# 원격 저장소에 반영하기 (토큰 생성 필요)
git push origin main
```

### ④Github Page 설정 확인

- Repository Settings > Pages > suhyun7890.github.io로 접속하여, 작성한 HTML 문서가 정상적으로 뜨는지 확인하였습니다.


## 2. Jekyll 설치

- 웹사이트를 생성하기 위해 Jekyll을 설치하는 과정이 필요하였습니다.
- 해당 링크를 참고하였습니다: https://velog.io/@ilcm96/install-jekyll-on-ubuntu

### ① 필요한 package 설치하기

```
sudo apt install ruby-full build-essential zlib1g-dev
```

### ② Jekyll 및 Bundler 설치하기

```
gem install jekyll bunlder
bundle install
```

### ③ Jekyll가 정상적으로 설치되었는지 확인하기

```
jekyll -v
```

### ④ 현재 디렉토리(.)에 Jekyll 설치하기

```
jekyll new . --force
```

### ⑤ jekyll 시작하기

```
(bundle exec) jekyll serve
```


## 3. Theme 변경 및 _config.yml 변경

- 사용한 테마는 'zivong' user의 'Hydure'입니다.
- https://github.com/zivong/jekyll-theme-hydure

### ① 로컬 저장소에 테마 받아오기

- 해당 테마의 HTTPS 코드를 복사 후, 터미널에서 git clone하여 로컬 저장소에 저장하였습니다.

```
git clone https://github.com/zivong/jekyll-theme-hydure.git
```

### ② 테마 파일을 로컬/원격 저장소에 반영

- 저장한 테마 파일들을 blog 에 덮어쓰기하여 반영하였습니다.
- Hydure 테마의 경우, _posts 폴더가 포함되지 않았기 때문에 모두 덮어쓰기하였습니다.
- git add를 통하여 변경된 파일들을 git에 반영하였고, commit과 push를 거쳐 원격 저장소에 또한 반영하였습니다.

### ③ _config.yml 변경 및 테마 레이아웃 보충

- 설치한 테마 'Hydure'의 특성을 반영하여, blog 폴더에 Jekyll을 설치함으로써 생성된 _config.yml의 내용을 변경하였습니다.
- title을 적절하게 변경하고, tagline을 추가하여 title의 밑에 간단한 소개글을 배치하였습니다.
- 설치한 테마에는 기본적으로 이메일과 트위터, 깃허브 아이콘이 노출되지 않았습니다. 그렇기 때문에 톄마 제작자의 원격 저장소를 참고하여 _data/social.yml 파일을 새로 생성하고, 내용을 보충하였습니다. 이 결과, tagline 밑에 이메일 작성 및 GitHub 링크가 로드되는 아이콘을 생성할 수 있었습니다. 

```
- title: Email
  url: mailto:112jshjsh@kookmin.ac.kr
  icon: fas fa-envelope
- title: GitHub
  url: https://github.com/suhyun7890
  icon: fab fa-github

```

- 사용하지 않는 twitter_username은 삭제하였습니다. 트위터 링크가 로드되는 아이콘 또한 생성하지 않았습니다.


## 3. Post Upload

- _post에 Makrdown 형식을 사용한 파일을 로컬 저장소에서 작성 후, commit 및 push하여 원격 저장소에 반영하였습니다.
- _post의 내용들은 유레카프로젝트에서 제공한 PPT를 중심으로 작성하였습니다.
- YYYY-MM-DD-TITLE.md와 같은 형식으로 문서를 생성한 후, 다음과 같은 형식으로 문서를 시작하였습니다.

```
---
layout: post
title: "②Jekyll"
date: 2021-12-14 18:09:30 +0900
categories: 유레카프로젝트
comments: true
# comments 항목은 댓글 기능을 활성화한 후 추가하였습니다.
---
```


## 4. Comments

- Disqus를 이용하여 댓글 기능을 추가하였습니다.
- GitHub 사용자 이름, 즉 suhyun7890을 Website Name으로 지정하여 Disqus에 새로운 사이트를 생성하였습니다.
- _config.yml에 다음과 같은 key_value를 추가하였습니다.

```
comment:
  provider:        "discus"
  disqus:
    shortname:     "suhyun7890"
```

- Disqus 홈페이지에서 Universal Code를 복사 후, _layouts/post.html에 수정 및 반영하였습니다.

'''
{% if page.comments %}
<h2>Comments</h2>
<div id="disqus_thread"></div>
<script>
    /**
    *  RECOMMENDED CONFIGURATION VARIABLES: EDIT AND UNCOMMENT THE SECTION BELOW TO INSERT DYNAMIC VALUES FROM YOUR PLATFORM OR CMS.
    *  LEARN WHY DEFINING THESE VARIABLES IS IMPORTANT: https://disqus.com/admin/universalcode/#configuration-variables    */
    let PAGE_URL = "{{site.url}}{{page.url}}"
    let PAGE_IDENTIFIER = "{{page.url}}"
    var disqus_config = function () {
    this.page.url = PAGE_URL;  // Replace PAGE_URL with your page's canonical URL variable
    this.page.identifier = PAGE_IDENTIFIER; // Replace PAGE_IDENTIFIER with your page's unique identifier variable
    };
    (function() { // DON'T EDIT BELOW THIS LINE
    var d = document, s = d.createElement('script');
    s.src = 'https://suhyun7890.disqus.com/embed.js';
    s.setAttribute('data-timestamp', +new Date());
    (d.head || d.body).appendChild(s);
    })();
</script>
<noscript>Please enable JavaScript to view the <a href="https://disqus.com/?ref_noscript">comments powered by Disqus.</a></noscript>
{% endif %}
'''

- _posts의 게시물들 상단에 다음 코드를 추가함으로써, 댓글 기능을 허용하였습니다.

```
comments: true
```
