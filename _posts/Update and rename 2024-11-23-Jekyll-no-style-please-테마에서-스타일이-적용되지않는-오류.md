---
layout: post
title: jekyll no style please 테마에서 스타일이 적용되지않는 오류
---



뭔가 연달아서 작성하게될줄은 몰랐지만. 다행이 테마의 스타일이 블로그에 적용되지않는 원인을 찾았다.

블로그에 접속한 다음 네트워크 탭을 확인했을 때 main.css가 404로 표시되고있는 문제가 계속있었다.

분명 actions 로그를 볼 때는 해당 main.scss를 빌드하는걸 본것같은데.

그리고 실제 요청하는 url주소를 확인해보았다.

```
https://earningquest.github.io/no-style-please/assets/css/main.css
```

뭔가 이상한데.. 패스에 왜 no-style-please 가 들어가있는걸까?
실제로도 접속해보니 404가 되었었는데 중간에 이상한 path가 있어서 해당부분을 삭제해보니 정상적으로 표시가되었다.
```
https://earningquest.github.io/assets/css/main.css
```

놓친게 있을까 싶어서 _config.yml을 보던 중 눈에 익은 단어가 보였다

```
...
url: https://earningquest.github.io # root address of the site
#baseurl: "/no-style-please" # subpath of the site, e.g. "/blog" (leave it blank "" if you're site shouldn't use a subpath)
...
```

내가 찾던 옵션이 맞는것같았다. 그리고 수정하고 커밋을 하고나니 스타일이 정상적으로 표시된다.
우연찮게 다크모드와 함께 내가원하던 스타일로 적용되었다. 없었어도 흰색이 기본 html로 잘 표시가되어서 약간 불만족스러운상태였지만 이제 잘 표시가되니 불만이 사라진것같다.
여기까지가 마지막 글이 되지 않길바라며 글을 작성한다.

그리고 작성일은 2024-11-24이나 일단 23일로 수정해야지. 보고싶으니까

---

세상에... 한글로 파일이름을 작성하면 빌드에서 제외된다..

---

바보같이 끝에 md를 붙이지않았다. 바보

2024-11-23-Jekyll-no-style-please-the-thema-style-not-effect-on-page

