<p align="center">
    <img width="200px;" src="https://raw.githubusercontent.com/woowacourse/atdd-subway-admin-frontend/master/images/main_logo.png"/>
</p>
<p align="center">
  <img alt="npm" src="https://img.shields.io/badge/npm-6.14.15-blue">
  <img alt="node" src="https://img.shields.io/badge/node-14.18.2-blue">
  <a href="https://edu.nextstep.camp/c/R89PYi5H" alt="nextstep atdd">
    <img alt="Website" src="https://img.shields.io/website?url=https%3A%2F%2Fedu.nextstep.camp%2Fc%2FR89PYi5H">
  </a>
</p>

<br>

# 지하철 노선도 미션
## 🚀 1단계 - 토큰 기반 로그인 구현
**TokenAuthenticationInterceptor 구현하기**
- [x] TokenAuthenticationInterceptorTest 단위 테스트를 작성하며 TDD로 기능 구현하기

**내 정보 관리 인수 테스트**
- [x] /members/me 로 멤버 조회/수정/삭제 기능을 요청하는 인수 테스트 작성
- [x] 로그인 후 token을 응답 받은 후 요청 시 포함시키기

**@AuthenticationPrincipal 적용**
- [x] Controller에서 LoginMember 정보를 받아올 때 @AuthenticationPrincipal를 활용하여 받기
- [x] AuthenticationPrincipalArgumentResolver를 참고하여 ArgumentResolver 기능을 사용하기

<br>

## 🚀 2단계 - 인증 로직 리팩터링
**인증 로직 리팩터링 및 기능 추가**
- [x] 1,2단계에서 구현한 인증 로직에 대한 리팩터링을 진행하기
- [x] 내 정보 수정 / 삭제 기능을 처리하는 기능을 구현하기
- [x] Controller에서 @AuthenticationPrincipal 애너테이션을 활용하여 Login 정보에 접근

**리팩터링**
- [x] AuthenticationConverter 추상화
    * Token Auth와 FormLogin으로 나뉘어 있는 AuthenticationConverter를 추상화

- [x] AuthenticationInterceptor 추상화
    * AuthenticationInterceptor의 후처리 로직을 추상화

- [x] SecurityContextInterceptor 추상화

- [x] auth 패키지와 member 패키지에 대한 의존 제거
    * 현재 auth 패키지와 member 패키지는 서로 의존하고 있음
    * UserDetailsService를 추상화 하여 auth -> member 의존을 제거하기

<br>

## 🚀 3단계 - 즐겨찾기 기능 구현
**즐겨찾기 기능 구현**
- [x] 회원 별로 즐겨찾기를 관리할 수 있도록 기능변경
- [x] TDD 사이클을 적용해서 구현
- [x] 기존 로직에 대하여 테스트 작성 연습

**권한이 없는 경우 401 Unauthorized 응답**
- [x] 내 정보 관리 / 즐겨 찾기 기능은 로그인 된 상태에서만 가능
- [x] 비로그인이거나 유효하지 않을 경우 401 Unauthorized 응답
