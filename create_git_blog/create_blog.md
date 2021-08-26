# Visual Studio Code, Ruby를 통한 git Blog 생성


## Hyjack 템플릿사용

* 커스텀 할 목록
1. _data
2. _featured_tags
3. _includes
4. _posts
5. .assets
6. _config.yml
7. about.md

---
### 1. _data

resume.yml - hyjack primium시 해당

authors.yml - 저자 커스텀
```
## authors.yml ##

vvs:
  name:              <닉네임>
  email:             <메일주소>
  
  about:             |
    <간단한 자기소개 기입>
    
  picture:
    src:             /assets/img/me.png <저자 사진>
   
    #사진 배율 지정도 가능
    srcset:
      1x:            /assets/img/me.png 
      2x:            /assets/img/me.png
      
    #소셜 섹션(있을경우 커스텀)  
    social:
    facebook:         khw11044
    # twitter:         <username>
    # google:          <number>
    # vk:              <username>
    # youtube:         <string_string_string>
    # vimeo:           <username>
    # vine:            <username>
    # spotify:         <user>/<number>
    # soundcloud:      <username>
    # lastfm:          <username>
    # instagram:        <username>
    # flickr:          <string@string>
    # 500px:           <username>
    # dribbble:        <username>
    # behance:         <username>
    # deviantart:      <username>
    # ello:            <username>
    # twitch:          <username>
    # steam:           <number>
    # reddit:          <username>
    # tumblr:          <username>
    # pinterest:       <username>
    # foursquare:      <number>
    # yelp:            <string>
    github:          <자신의 깃허브 아이디>
    # stackoverflow:   <number/username>
    # npm:             <username>
    # hackernews:      <username>
    # trello:          <firstnamelastname>
    # linkedin:        <firstname-lastname-string>
    # xing:            <firstname_lastname_counter>
    # blogger:         <number>
    # delicious:       <username>
    # stumbleupon:     <username>
    # paypal:          <username>
    email:           dleo_vvs@kakao.com
    rss:             https://khw11044.github.io/feed.xml
    
```
countires.yml - 커스텀 사항없음 <br>
resume.json - 커스텀 사항없음<br>

### 2. featured.category (왼 사이드바 메뉴)

 
##### - featured.category 커스텀 메뉴
  
  ```
  layout: list  → 레이아웃 설정
  title: Blog  → 섹션 제목
  slug: blog  → 섹션 제목과 맞춤
  menu: true  → 큰 메뉴 활성화
  submenu: true → 서브메뉴 활성화
  order: 4    → 카테고리에 보여질 순서
  description: >
  <메뉴에 대한 간단한 설명란>  
  ```
##### - featured.tags 커스텀 메뉴(큰메뉴 밑에 사이드 메뉴)
```
layout: tag-blog
title: NLP
slug: nlp
category: blog → 어디 그룹의 하위 메뉴인지
menu: false
order: 1
```

### 3. _include

##### - footer.html
```
<footer>
  <hr/>
  {% if site.copyright.size > 0 %}
    {{ site.copyright | markdownify }}
  {% endif %}
  <p>
    <code>Powered by <a href="https://khw11044.github.io/">블로그 이름</a></code>
  </p>
</footer>

```
##### - sidebar.html -

```
//image div 생성

   <div class="sidebar-box">
        {% if author.picture %}
          {% include srcset-img.html class="me" img=author.picture alt=author.name %}
        {% endif %}
   </div>

```

**검색창 추가 (예정)** <br>
**조회수 추가 (예정)** <br>

```
```
### 4. _posts -게시글관리
##### 확장자 .md 기본 형식은 아래와 같다.
```
---
layout: post
title:  "[GithubPages] 01.하루만에 깃허브 블로그 만들기" //제목
subtitle:   "개요" //부제목
date: 2020-12-26 11:45:51 +0900 //작성날짜
categories: study //카테고리(메뉴)
tags: githubpage //글의 태그관련
comments: true //댓글 가능여부
related_posts:
    - category/_posts/study/2020-12-26-making-blog-02.md //관련 게시글을 다음과 같이 명시
---

이 공간은 내용을 명시한다.

# 이미지


![그림2](../../../../assets/img/study/githubpages/1.png){: width="400" height="400} // 이미지넣을때 다음과 같은 형식


```
### 5. assets -블로그 스타일, 포스팅 이미지보관

#### 파비콘 설정
##### https://www.favicon-generator.org/ ← 파비콘 만들기

### 6. _config //페이지 구성정보, 환경변수 설정
```
# -----------------------------------------------------------------------------
#  User configuration
# -----------------------------------------------------------------------------

title:               Developer Kang //블로그이름

# The unique resource location of your page.
# Set to `https://<username>.github.io` when hosting on GitHub Pages
url:                 https://naru92.github.io

# Set to '' when hosting a blog on GitHub Pages, ie on `//<username>.github.io`
# Set to '/<reponame>' when using the `gh-pages` branch of a repository
baseurl:             ""

# A very short description of your page
tagline:             "Backend A TO Z !" //블로그에 대한 간단한 소개문구

# A short description of the page, used in the sidebar and as fallback for the meta description tag.
# Markdown enabled, but don't use more than one paragraph (enforced by `>`)
description:         >
  이번생은 개발자로 살아보기! //블로그에 대한 간단한 소개

# This should be the same author as first entry in `_data/authors.yml`
author:
  name:              xxxx
  email:             xxxx@xxxx.com

# Fallback image and color
image:               /assets/img/main_left.JPG
color:               '#4f86aa'

# The font used for headings. Expects a string that is a valid CSS font-family value.
font_heading:        "'Merriweather-Light','Lato','-apple-system','Verdana','PingFang SC','Helvetica Neue','Arial','Hiragino Sans GB','Microsoft YaHei','WenQuanYi Micro Hei','sans-serif'"

# The text font. Expects a string that is a valid CSS font-family value.
font:                "'Merriweather-Light','Lato','-apple-system','Verdana','PingFang SC','Helvetica Neue','Arial','Hiragino Sans GB','Microsoft YaHei','WenQuanYi Micro Hei','sans-serif'"

# The string encoding what fonts to fetch from Google Fonts.
# See: https://qwtel.com/hydejack/docs/configuration/
google_fonts:        Lato

# If you do not use a Google Fonts, uncomment the line below
# no_google_fonts:     true

# Set your Google Analytics id to receive `pageview` events.
# To remove Google Anaylics from your page, remove the line below.
google_analytics:    G-xxxx

# 댓글기능
disqus: True
disqus_shortname:    xxxx

# This text will appear in the footer of every page. Markdown enabled.
copyright:           '&copy; 2021.08.26 by Kang Naru '

# Format of the permalinks
permalink:           

# Pagination configuration (used by the `blog` layout)
paginate:            3
paginate_path:       '/page-:num/'

# If you are upgrading form a v5 verison of Hydejack, uncomment the two lines below,
# so that the location of the feed XML stays the same.
# feed:
#   path:              atom.xml

# Set to true when building with the `--lsi` option
# See: https://jekyllrb.com/docs/variables/#site-variables
# use_lsi:             true

# Set to `true` if you don't want to show an icon after each link that opens to an external site
# no_mark_external:    true

# Uncomment this line if third party plugins fail to work with dynimically loaded pages
# disable_push_state:  true

# Uncomment this line if want to disable the touch drawer on mobile
# disable_drawer: true

# -----------------------------------------------------------------------------
#  Collections
# -----------------------------------------------------------------------------

collections:
  featured_categories:
    permalink:       /category/:name/
    output:          true
  featured_tags:
    permalink:       /tag/:name/
    output:          true
  projects:
    permalink:       /projects/:path/
    output:          true

# -----------------------------------------------------------------------------
#  Advanced configuration
# -----------------------------------------------------------------------------

plugins:
  - jekyll-feed
  - jekyll-sitemap
  - jekyll-paginate
  - jekyll-redirect-from

exclude:
  - README.md
  - LICENSE.md
  - node_modules
  - package.json
  - package-lock.json
  - Gemfile
  - Gemfile.lock
  - _posts/study/2020-12-26-making-blog04.md


kramdown:
  footnote_backlink: '&#x21a9;&#xfe0e;'
  math_engine:       mathjax
  math_engine_opts:
    preview:         true
    preview_as_code: true

compress_html:
  comments:          ["<!-- ", " -->"]
  clippings:         all
  endings:           all
  ignore:
    envs:            [development]

sass:
  style:             compressed



```

### 7. about( post폴더 밖에 portfolio.md 이름으로 따로 생성 )

```
---
layout: about //about 형식
title: Portfolio //포트폴리오
menu: true //메뉴에 나타날지
order: 1 //메뉴 맨위
---
```

