# 무엇을 하는 곳인가?

제가 그날 하루하루 배웠던 내용을 정리해서 올리는 곳입니다.  
배웠던 내용은 여기에 먼저 적고, 다른 repo에 옮기거나 복사할 수 있습니다.  

## 다루고 있는 내용

현재 다루고 있는 내용은 다양합니다.
내용은 다음과 같습니다.

* shell(bash, zsh등등)
* algorithm
  * bit manipulation
* data structure
* math
* theory of computation
* jekyll
* computer hardware
* git

## 앞으로 다룰 내용

* 2018/03/18 카카오톡 입사 문제에서 공부할 내용을 찾아보려고합니다. 다음 링크들을 참조해 주세요.
  * http://tech.kakao.com/2017/09/27/kakao-blind-recruitment-round-1/
  * http://tech.kakao.com/2017/10/24/kakao-blind-recruitment-round-2/
  * http://tech.kakao.com/2017/11/14/kakao-blind-recruitment-round-3/
  * [1차 온라인 코딩테스트 풀이](http://jay-ji.tistory.com/category/%ED%94%84%EB%A1%9C%EA%B7%B8%EB%9E%98%EB%B0%8D/%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98)

### 공부할 주제

위에서 언급한 링크로부터 여러가지 주제를 뽑아 보았습니다.

#### 1차 코딩테스트

* bit manipulation
* string manipulation
  * tokenize
  * semantic analysis
* cache replacement algorithm
  * LRU(Least Recently used)
* set(집합)
  * multiset(다중 집합)
  * 자카드 유사도
* 블록 매트릭스(?)
* 윈도우
* 그리디 알고리즘?

#### 2차 코딩테스트

여기서 알 수 있는 것이 바로 C++만 공부했다가는 큰일 나고, 파이썬을 어느 정도 공부하는 것이 중요하다는 사실을 알 수 있습니다.

* Crawler 구현
  * 이미지 특징값을 수집한다.
  * REST API
  * JSON parsing
* 토큰(컴파일러 과목의 token 아님)
  * 제한된 토큰 유효시간
* 다양한 시나리오
  * 정상적으로 추가 혹은 삭제되는 경우
  * 이미 기존에 추가한 이미지를 또 추가하는 경우
  * 방금 추가한 이미지를 바로 삭제하는 경우
  * 추가된 적 없는 이미지를 삭제하라고 오는 경우
  * 추가, 삭제, 추가가 연달아 오는 경우
* 대략적인 득점사항들
  * 예외처리
  * 배치처리
  * 병렬처리
* Issue(이슈)
  * 크로스 도메인 문제
    * 웰컴 서버의 CORS(Cross Origin Resource Sharing)
  * Non-minified Json 파싱 문제
    * Feature Save/Delete API의 request body가 minified JSON 형태가 아닌 경우 일부 채점이 안되는 문제가 있었다고 한다.

#### 3차 코딩테스트

##### PS

* 진법 변환
* 참고: 챔퍼나운 수
* 정보이론: 압축 알고리즘
  * 허프만 코딩
  * LZW 압축
* 정렬의 실용적인 예
  * 정렬 조건(숫자? 사전순?)
  * 안정 정렬? 비안정 정렬?
  * decorate-sort-undecorate 패턴?
* string manipulation
  * 부분 문자열 비교
  * 토큰화
  * 치환(substitution)
  * 트라이(trie)
  * 접두어, 접미어, 진접두어, 진접미어


##### 필기 문제

* 영(Q1 ~ Q11번까지)
* 네트워크 문제(다음 링크를 참조할 것)
  * TCP/IP의 FSM을 외워야 겠다.
  * http://tech.kakao.com/2016/04/21/closewait-timewait/
* MVC, MVP, MVVM
* 다양한 조건에서 시간 복잡도 분석(Q13 ~ Q15)
* 트리와 그래프 다루는 법
