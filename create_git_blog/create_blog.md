# Visual Studio Code, Ruby를 통한 git Blog 생성


### Hyjack 템플릿사용

* 커스텀 할 목록
1. _data
2. _featured_tags
3. _includes
4. _posts
5. .assets
6. _config.yml
7. about.md

---
#### 1. _data

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
resume.json - 커스텀 사항없음
