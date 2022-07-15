## Network
# Part 01. Network
Made by. 

## 1. Core of Network Overview

## HTTP & HTTPS(#HTTP & HTTPS 답변)
#### 💡 GET 방식과 POST 방식의 차이는 무엇인가요?

<br/><br/>

# 1. Core of Network

## HTTP & HTTPS 답변

#### 💡 GET 방식과 POST 방식의 차이는 무엇인가요?

먼저, HTTP 패킷의 구조는 크게 헤더와 바디로 나뉩니다.
그 중 헤더에는 HTTP 메서드 방식인 GET과 POST 중 무엇을 썼는지의 정보가 담겨 있습니다.
두 방식 모두 서버에 요청을 하는 request 메서드이지만, 
GET은 데이터를 조회하기 위해서 사용하는 방식으로 데이터를 헤더에 추가하여 전송하며, URL에 데이터가 노출되기 때문에 패스워드 같은 중요한 데이터를 포함하면 안되는 방식이며,
POST는 데이터를 추가 또는 수정하기 위해서 사용하는 방식으로 데이터를 바디에 추가하여 전송하는 방식이며, URL에 데이터가 직접적으로 노출되지 않기 때문에 GET 방식보다는 비교적 안전하다고 할 수 있습니다.

</br>

</br>
