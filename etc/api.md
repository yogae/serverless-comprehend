# API(Application Programming Interface)

응용 프로그램에서 사용할 수 있도록, 운영체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스를 뜻합니다.

google map에서 내 위치를 받아오려면 google map 서버에 내 위치를 요청 해야합니다. 요청을 할 때 서버와 사용자간에 약속이 필요합니다. 이러한 약속을 정해놓은 것을 api라고 생각하시면 쉬울 것 같습니다.

tensorflow에도 api를 구성하여 개발자들이 tensorflow를 사용할 수 있도록 구성되어 있습니다. tensorflow를 사용하기 위해서는 python이나 다른 언어에 library를 import하여 사용합니다. tensorflow api를 확인해보시면 언어별로 tensorflow library를 어떻게 사용해야하는지 설명하고 있습니다.[[참고 - tensorflow api](https://www.tensorflow.org/api_docs)]

twitter api와 tensorflow api가 다른 것은 tensorflow는 python에서 사용하는 library이고 twitter api는 http request로 호출할 수 있는 api 서버입니다.[[참고 - twitter api](https://developer.twitter.com/en/docs/tweets/post-and-engage/overview)]

google map api는 javascript로 구현된 library로 구현되어 있습니다.[[참고 - google map api](https://developers.google.com/maps/documentation/javascript/tutorial?hl=ko)] javascript library 내부에 google map api server 호출 하도록 구성되어 있어서 endpoint를 확인할 수 없는 것 같습니다.

## REST API

REST API는 http 프로토콜을 효율적으로 사용할 수 있는 방법이라고 생각하시면 됩니다.

tensorflow api는 http 호출을 위한 api가 아니라 tensorflow library를 사용하기 위한 api이므로 rest api라고 말하지 않습니다. twitter api는 rest api를 구성하고 있어서 사용자가 http 프로토콜을 사용하여 twitter 서버로 요청을 보낼 수 있습니다.

### REST API 구성

* resouce(URI)

  `example.com/users/1` uri는 1번 사용자를 나타냅니다. 이 처럼 uri는 정보의 자원을 표현해야 합니다.

* method

  `POST example.com/users/1` post method는 자원의 생성을 나타냅니다. http method에는 자원의 CRUD(create, read, upadte, delete) 행위를 나타냅니다.

* message
  
  `POST`, `PUT` method에서는 body data에 추가적인 정보를 추가하여 http 요청을 합니다.

### endpoint

URI 별 HTTP 메소드로 구현된 항목을 Endpoint라고 합니다.

ex)

| URI                                     | 의미            |
| --------------------------------------- | ------------- |
| `POST http://api.example.com/users`     | user 생성       |
| `GET http://api.example.com/users`      | user list 정보  |
| `GET http://api.example.com/users/1`    | 1번 user 정보    |
| `PUT http://api.example.com/users/1`    | 1번 user 정보 수정 |
| `DELETE http://api.example.com/users/1` | 1번 user 삭제    |

## URI vs URL

URI: 인터넷 상의 자원을 식별하기 위한 문자열

URL: URI의 한 형태이며, 인터넷 상의 자원 위치

URL은 주로 file이 인터넷 상에 있는 위치를 나타냅니다. `image.example.com/file.txt`

## Reference

* [API vs. SDK vs. Framework vs. Library](https://you9010.tistory.com/147)
