## 1. 레일즈란 무엇인가?

레일즈란 루비로 쓰여진 웹 애플리케이션 `프레임워크`입니다.
개발자가 웹을 개발하기 시작할 때 필요할 것으로 생각한 작업 및 리소스들을 가정하고 미리 준비하여 **쉽게** 작성할 수 있게 합니다. 
다른 웹 프레임워크와의 장점으로는 상대적으로 적은 코드로 더 많은 기능들을 구현할 수 있습니다.

큰 특징으로는 최선의 개발 방법을 하나로 가정합니다.
특정 작업을 할 때 그 작업을 수행하는 최선의 방법을 한 가지로 가정하고, 그 방법을 전폭적으로 지지합니다. 
다시 말하자면 가정된 개발 방식과 맞지 않는 다른 개발 방법으로는 작업하기 어렵게 되어있습니다. 이렇게 특정한 한 방식으로 개발하는 특징을 `Rails Way`로 부르며  이 방법으로 개발하다면 **생산성이 매우 크게 향상**됩니다. 

> 레일즈 개발에 있어서 다른 언어환경에서 써왔던 종래의 개발방식을 고집하고, 다른 곳에서 배운 패턴을 억지로 적용하려고 한다면, 레일즈 개발이 어렵고 재미없어질 겁니다.



## 2. 레일즈로 개발하기?

앞서 설명했던 것처럼 레일즈는 `Rails Way`대로 레일즈가 정해진 방식대로 개발하는 것이 가장 효과적이고 적합한 방법입니다.
그래서 레일즈를 개발하려면 웹서비스가 작동하는 큰 틀에서  `Rails Way`의 방식을 아는 것이 중요합니다.
레일즈를 공부하는 초반 단계에서는 기존처럼 단순히 웹 페이지를 개발하는 것에서 그쳤다면 중고급 단계에서는  `Rails Way`대로 개발하는 법을 익혀서 더욱 쉽고 빠르게 개발할 수 있어야 합니다. 

그 이후에 실제 서비스 개발 단계에 들어가면 선택을 해야합니다.
어떠한 기능을 만들어야 할 때 
  1. `직접 구현`하는지 
  2. 다른 사람들이 만든 `gem`으로 개발 할지

`gem`을 선택한다면 이미 완성되고 검증된 기능을 붙이고 싶을 때 
`직접 구현`이라면 자신이 그 기능을 오롯이 이해하고 있거나  단순하게 기능을 구현하고 싶을 때 선택하면 됩니다. 

물론 `gem`으로 개발했을때 나한테 필요 없는 추가 기능들이 덕지덕지 붙어있거나, 버전이 맞지 않아서 오류가 나거나,  그 `gem`을 공부하는데 시간이 너무 오래 걸리거나 등의 단점들이 있을 수도 있으니 잘 선택하는 것이 좋습니다. 

## 3. 레일즈 간단 정리(복습)

#### 1. rails 작업 흐름

route => controller => (model) => view

route로 url을 작성해서 url과 컨트롤러와 연결  
컨트롤러에서 로직을 짜고 (모델을 CRUD)
view에다 뿌린다.

#### 2. rails 철학

1. DRY

   1. 같은 것을 반복하지 말 것

2. CoC

   1. 설정보다 규약 
   2. 원하는 기능을 일정한 가정에 따라 미리 해결책을 제시(뷰
      헬퍼) 

3. RESTful 인터페이스

   1. REST의 특징을 가진 라우트를 뜻함 REST는 네트워크의 모든 모든 콘텐츠를 URL로 표현하고 이러한 URL을 HTTP 메소드 그대로 사용하고, 이는 CRUD에 해당하는 메소드를 사용해 통일감 있고 의미가 명확한 URL설계를 가능하게 한다. REST의 요소로는 리소스, 메소드, 메세지로 구성된다.

      | HTTP 메소드 |   역할   |    CRUD    |
      | :------: | :----: | :--------: |
      |   POST   | 데이터 전송 |   CREATE   |
      |   GET    |   검색   | READ(SHOW) |
      |   PUT    |   수정   |   UPDATE   |
      |  DELETE  |   삭제   |   DELETE   |

#### 3. CRUD

**Create,Read,Update,Delete**
가장 기본적인 데이터 처리

#### 4. MVC 패턴

1. 모델

   모델은 어플리케이션의 정보(data)와 데이터를 다루는 규칙들을 의미.
   레일즈의 경우에, 모델은 주로 데이터베이스 테이블과 상호 작용하는 규칙들을 관리한다. 대부분의 비즈니스 로직은 모델에 집중된다.

2. 뷰

   뷰는 어플리케이션의 UI를 의미, 레일즈에서 뷰는 주로 데이터
   표현에 관련된 루비 코드가 삽입되어 있는 HTML 파일이다. 뷰는
   데이터를 웹 브라우저나 다른 기기에게 데이터를 제공하는 일을 담당한다.

3. 컨트롤러

   컨트롤러는 모델과 뷰를 '연결'하는 역할을 합니다. 레일즈에서 컨트롤러는 웹브라우저의 요청 받아서, 모델을 통해서 데이터를
   조회하여, 출력을 위해 뷰에게 데이터를 넘겨줍니다.

4. 작동순서

   사용자 => 브라우저 => router => controller => model => controller => view => controller => 브라우저 => 사용자

   ​

## 4. Scaffold 이해하기 1 (restful?)

#### 1. 스캐폴딩이란?

MVC 패턴을 레일즈의 철학(RESTful)대로 데이터를 CRUD하게 구현하는 기능

#### 2. 실행 명령어

- rails g scaffold post title content:text

  (post라는 테이블을 생성해서 이를 crud 할 수 있는 토대를 만들어라)

- rake db:migrate

  (DB 마이그레이트하기)

- rake routes

  (라우트 경로 확인)

#### 3. resources :post

|  CRUD  |  prefix   |   verb    |   uri pattern   |    컨트롤러#액션    |
| :----: | :-------: | :-------: | :-------------: | :-----------: |
|        |   posts   |    get    |     /posts      |  posts#index  |
| create | new_post  |    get    |   /posts/new    |   posts#new   |
| create |           |   post    |     /posts      | posts#create  |
|  read  |   post    |    get    |   /posts/:id    |  posts#show   |
| update | edit_post |    get    | /posts/:id/edit |  posts#edit   |
| update |           | patch/put |   /posts/:id    | posts#update  |
| delete |           |  delete   |   /posts/:id    | posts#destroy |

1. CRUD에 매칭되는 액션들 생성

2. Create나 Update 때에는 new 액션이나 edit 액션으로 생성이나 변경 폼을 제공(get) 메소드

3. resources 메소드는 뷰 헬퍼(link_to 등)에서 사용할 수 있는 URL 헬퍼도 자동으로 생성합니다. 

4. resources :post로 자동 생성되는 경로

   |    헬퍼 이름(_path)    |    헬퍼 이름(_url)    |      리턴 값      |
   | :----------------: | :---------------: | :------------: |
   |     posts_path     |     posts_url     |     /posts     |
   |   post_path(id)    |   post_url(id)    |   /posts/:id   |
   |   new_post_path    |   post_user_url   |   /posts/new   |
   | edit_post_path(id) | edit_post_url(id) | /post/:id/edit |

-------


## . 레일즈 깔기

[윈도우 railsinstaller 버전](https://uni.likelion.org/posts/26)
[윈도우 bash로 설치 1](http://limdongjin.tistory.com/10) [윈도우 bash로 설치 2](http://limdongjin.tistory.com/11)
[윈도우 bash로 설치 (영어 버전)](https://gorails.com/setup/windows/10) 