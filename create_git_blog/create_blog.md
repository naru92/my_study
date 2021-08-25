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

    
```
