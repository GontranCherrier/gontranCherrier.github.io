# https://gontrancherrier.github.io/

[hexo](https://hexo.io/ko/docs/index.html)를 템플릿으로 사용해서 [git page](https://pages.github.com/)로 호스팅 하는 형식

git pages 를 이용하기 위해 master 는 빌드 결과물이 올라가야 하고   
코드 원본과 포스트 내용을 남기기 위해 develop을 사용했습니다.   
때문에 develop랑 master는 파일 구조가 완전히 다르기 때문에    
master는 잊어버리고 develop만 체크아웃 받아 사용하시면 됩니다. 

### 환경 셋팅 

```bash
$ git clone -b develop https://github.com/gontrancherrier/gontrancherrier.github.io.git
$ cd gontrancherrier.github.io.git 
$ npm install
```

(편하게 쓰려면 hexo를 global 설치하는 것을 추천하고요)
```bash
$ npm install -g hexo-cli
```

로컬에서 커밋하다가 정체 탄로나기 전에 이런 거 넣어둬...
```bash
$ git config user.name "빵순이" && git config user.email "빵야빵야@gmail.com"
```

### 사용
기본적인 스텝은 이렇습니다. 

1. 포스트 생성
    * `$ hexo new '포스트 이름'`
1. 포스트 작성
    * `/source/_posts/포스트_이름.md`을 편집
    * 이 때 로컬호스트에서 결과물을 확인해볼 수 있음 (`$ hexo server`)
    * 이미지 추가는 `/source/img/`에 넣구 마크다운 문법으로 사용 가능 (`![test][img/~]`)
1. 포스트 게시
    * develop 에 커밋
    * 배포
        * `$ hexo depoly -g`: master에 푸쉬 -> page 배포
    * 변경사항 푸쉬

### 기타 설정
#### 테마
[maupassant](https://github.com/gontrancherrier/maupassant-hexo)(forked) 를 적용했고  
이 repo의 `themes/maupassant` 으로 submodule 등록되어 있음

* 현재는 폰트랑 메뉴같은것만 수정했고
* 댓글로 [gittalk](https://github.com/gitalk/gitalk) 지원한대서 붙이려고 하다가 왠지 안되서 멈춘 상태 ;
* 템플릿 내의 tags, category <- 이거 변경해서 author, book(name) 같은거로 바꿀 예정

참고로 로긴 계정 여러개 써야해서 자꾸 에러날 때 이것이 도움이 되었음 
```bash
$ git remote set-url origin https://ba9uette@github.com/gontrancherrier/gontrancherrier.github.io.git
```
