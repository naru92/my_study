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
