# 하루프레스란?
하루프레스는 하루라는 순 우리말과 프레스라는 단어의 조합으로 **하루에 이야기**를 작성하여 **발행**하는 매우 간단한 블로그 엔진이라는 의미에서 **하루프레스** 라고 이름을 지었습니다.

그리고 기술적으로는 웹 서버와 데이터베이스가 필요 없는 정적 페이지 기반의 블로깅 엔진입니다. 정적 페이지 기반 블로그란 PHP 로 만들어진 워드 프레스와 같이 서버측에서 프로그램이 동작하는 것이 아닌 블로그를 구성하는 모든 페이지를 HTML 로 생성하는 프로그램을 말합니다. 

하루프레스는 블로그를 위한 모든 콘텐츠를 정적 페이지(HTML)로 생성합니다.  그리고 이렇게 생성된 페이지들을 인터넷이 되지 않는 컴퓨터에서 볼 수도 있고 Github 의 정적 페이지 서비스를 이용해 퍼블리싱도 할 수 있습니다.

그리고 HTML5, CSS3 을 이용한 테마와 플러그인도 존재하여 다양한 편리한 기능을 부가적으로 제공합니다.

그리고 마지막으로 하루프레스의 가장 중요한 목표는 블로그가 필요한 사람들보다 글을 쓰는데 불필요한 서버 구성, 데이터 베이스 설치 등을 잊고 글 쓰는 곳에만 몰입할 수 있도록 하는데에 있습니다. 

>하루프레스 소개 프리젠테이션 : [http://haroopress.com/about/](http://haroopress.com/about/)

## 하루프레스 이북
하루프레스 프로젝트와 병행하여 활용가이드 이북을 온라인으로 작성중에 있습니다. 

* 하루프레스 활용가이드. [http://haroopress.com/book/](http://haroopress.com/book/)

## 하루프레스 개발 다이어리
개발 다이어리는 개발 과정에서 일어났던 모든 이야기들을 풀어 쓰기 위한 페이지입니다.

* 하루프레스 개발 다이어리 [http://haroopress.com/diary/](http://haroopress.com/diary/)


# 설치와 셋업

### source install
```
//내부 서브 모듈까지 모두 초기화한다.
$ git clone https://github.com/rhiokim/haroopress.git /path/to/haroopress

//하루프레스 디렉토리로 이동한다.
$ cd /path/to/haroopress

//모듈 및 라이브러리 초기화, 리소스 설정
$ make init

... 

```

# 사용법(usage)

```
//배포할 github 저장소를 설정한다.
$ make gh-pages

//새로운 기사를 작성한다.
$ make new-post

//정적 페이지를 생성한다.
$ make gen

//생성된 페이지를 배포전 미리본다.
$ make preview

//배포
$ make deploy

//새로운 페이지를 생성한다.
$ make new-page

//새로운 웹 슬라이드를 생성한다
$ make new-slide
```

# 플러그인(plugins)

* **google analysis**
* **disquss**
* github
* twitter timeline
* **social buttons**
    - twitter
    - google plus
    - facebook like

# 데이터 구조(data structure) 
하루프레스에서는 사용자가 생성하는 모든 내용(포스팅, 페이지, 프로필 등)은 모두 `markdown` 으로 작성되고, 하루프레스는 오직 자바스크립트로만 구현이 되어 있어 엔진에서 사용되거나 생성하는 모든 데이터는 `json` 포맷으로 이루어져있습니다. 

그리고 일반적인 GUI 방식의 관리자 도구가 없기 때문에 하루프레스에서 다루는 매우 간단한 데이터 구조는 알아두면 좋습니다.
해당 내용은 아래의 링크에서 좀더 자세히 참고하실 수 있습니다.

[하루프레스 데이터 구조](http://haroopress.com/post/haroopress-default-data-format/)

# 데이터 변환(convertor)
하루프레스는 데이터 변환기를 유틸로 제공하여 다양한 블로그의 데이터를 하루프레스로 손쉽게 이전할 수 있습니다.

현재는 변환 유틸의 구조를 설계하기 위해 [Octopress](http://octopress.org) 만을 제공하고 있으며 향후 Wordpress, Tumblr, Tistory, Blogger 등의 유명한 블로그 엔진의 데이터를 위한 변환 유틸도 구현할 계획에 있습니다.

## 변환도구 사용법(usage)

```
$ make octopress

Please! insert octopress article directory : `[/path/to/octopress/source/_post]`

haroo> create directory at /path/to/haroopress/source/data/articles/[article-title]
haroo> create image directory at /path/to/haroopress/source/data/articles/[article-title]/@img
haroo> copy to [article-title].markdown file
haroo> jekyll convert to haroopress
----------------------------------------------------------------
```

# 의존성 모듈(dependency modules)
하루프레스는 다음과 같은 모듈을 통해서 개발되어졌습니다.

#### 하루프레스 초기화 및 빌드
* express.js: [http://expressjs.com/](http://expressjs.com/)
* locally: [https://github.com/rhiokim/locally](https://github.com/rhiokim/locally)

##### 하루프레스 코어 엔진
* colors: [http://search.npmjs.org/#/colors](http://search.npmjs.org/#/colors)
* ejs: [http://search.npmjs.org/#/ejs](http://search.npmjs.org/#/ejs)
* findit: [http://search.npmjs.org/#/findit](http://search.npmjs.org/#/findit)
* mkdirp: [http://search.npmjs.org/#/mkdirp](http://search.npmjs.org/#/mkdirp)
* moment: [http://search.npmjs.org/#/moment](http://search.npmjs.org/#/moment)
* robotskirt: [http://search.npmjs.org/#/robotskirt](http://search.npmjs.org/#/robotskirt)
* rss: [http://github.com/dylang/node-rss](http://github.com/dylang/node-rss)
* step: [http://search.npmjs.org/#/step](http://search.npmjs.org/#/step)
* string: [http://stringjs.com/](http://stringjs.com/)
* stringex: [http://search.npmjs.org/#/stringex](http://search.npmjs.org/#/stringex)
* watch: [https://github.com/mikeal/watch](https://github.com/mikeal/watch)
* yaml: [http://search.npmjs.org/#/yaml](http://search.npmjs.org/#/yaml)


# 라이센스(license)
Copyright (c) 2012 Rhio Kim

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
