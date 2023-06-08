# 🧷WebCafe login 레이아웃 구현
## 🧷마크업 순서
`로그인(제목)` ➡️ `아이디 레이블과 입력서식` 
➡️ `비밀번호 레이블과 입력서식` ➡️ `로그인 버튼` ➡️ `회원가입 및 아이디/비밀번호 찾기 링크`
### 🧷class 구성
![](https://velog.velcdn.com/images/pearlx_x/post/5a080f68-5bdd-4fde-9803-636519f62794/image.png)

---
### 🧷 코드 설명
#### 제목영역
>
```css
h1 {
  margin: 0;
  color: #FFFF00;
  font-weight: 700;
  font-size: 0.9375rem;
  margin-bottom: 8px;
}
```
- 대제목인 '로그인'을 **h1 태그**로 표현하여 스크린리더로 읽더라도 로그인이라는 것을 알게 하였다.
- h1의 에이전트 스타일을 초기화 시켜 로그인의 위치를 배치시켰다.

#### 로그인 폼 영역
>
```
<!-- 로그인 폼 영역 -->
<form class="login-form">
  <fieldset>
    <legend>로그인</legend>
    <div class="login-group">
        <label for="loginId">아이디</label>
        <input type="text" id="loginId" placeholder="euid@euid.dev" />
        <label for="password">비밀번호</label>
        <input type="password" id="password" placeholder="8자리 이상" />
    </div>
    <button type="submit" class="button">로그인</button>
  </fieldset>
</form>
```
- ** &lt;div class="login-group"&gt;** 에는 CSS부분에서 둘을 묶어서 배치 시키는게 편할거 같아아이디 부분과 비밀번호 부분을 한 태그로 묶었다. 
**&lt;form class="login-form"&gt;** 에는 아이디 부분과 비밀번호 부분 로그인 버튼을 포함시켜 버티컬 바를 기준으로 위쪽 흰색 부분의 전체 레이아웃을 구성했다. 
```css
/* margin-bottom,,margin-left을 사용하여 레이블과 input 간에 거리 조정*/
.login-form input {
  box-sizing: border-box;
  width: 90px;
  height: 21px;
  border: 1px solid #CCCCCC;
  border-radius: 5px;
  margin-bottom: 4px;
  margin-left: 4px;
  padding-left: 8px;
}
#loginId {
  margin-left: 16px;
}
```
- 아이디 / 비밀번호의 크기가 맞지 않아 margin-bottom, margin-left을 사용하여 아이디 오른쪽 공간을 넓혀주고 input 창과의 여백을 조정하였다.

#### 로그인 버튼
>
```css
/* position: absolute을 활용하여 input창 옆에 배치 */
.login-form button {
  position: absolute;
  font-size: 0.8125rem;
  border: 0;
  border-radius: 5px;
  width: 50px;
  height: 53px;
  padding: 4px;
  background-color: #ED552F;
  color: white;
  left: 170px;
  top: 8px;
}
```
- `position: absolute`을 활용하여 button 속성을 input창 옆에 배치시켰다.

----
#### 로그인 옵션 영역
>
```
 <!-- 로그인 옵션 영역 -->
 <!-- link 태그를 li 태그로 표현 -->
<section class="login-option">
  <ul>
    <li><a href="#">회원가입</a></li>
    <li><a href="#">아이디 비밀번호 찾기</a></li>
  </ul>
</section>
```
- 회원가입과 아이디 비밀번호 찾기는 순서 없는 리스트라고 생각할 수 있기 때문에
`ul>li>a` 로 구성했다. float를 사용하여 배치할 것이기 때문에 `first-child/last-child`
를 사용하여 각각 배치 시킬 것이다.
```css
.login-option ul {
  list-style: none;
  padding-left: 0;
  margin: 0;
}
.login-option a { 
  text-decoration: none;
  color: black;
  font-size: 0.8125rem;
  font-weight: 400;
}
/* margin 속성을 이용하여 공백을 없애고 첫 번째 요소는 왼쪽에 두 번째 요소는 오른쪽에 배치 */
.login-option li:first-child {
  margin-left: 13px;
  margin-top: 4px;
  float: left;
}
.login-option li:last-child {
  margin-top: 4px;
  float: right;
}
```
- ul 태그에 `list-style: none;` , `padding-left: 0;` 선언하여 ul이 가지는 에이전트 스타일을 초기화 해주었다.
- a 태그에서는 `text-decoration: none;`를 사용하여 링크에 달리는 밑줄을 제거 해주었다.
- margin 속성을 이용하여 공백을 없애고 첫 번째 요소는 왼쪽에 두 번째 요소는 오른쪽에 배치했다.

#### 그림자 영역
>
```css
.container {
  width: 260px;
  border-radius: 5px;
  background: #A3A3A3;
}
.login {
  position: relative;
  background: linear-gradient(90deg,  #ED552F, #E8852E);
  box-sizing: border-box;
  padding: 12px;
  width: 260px;
  height: 161px;
  border-radius: 5px;
  top: -5px;
  left: -5px;
}
```
- 로그인창 아래 보이는 회색 박스는 로그인과 같은 크기로 만들어준 후 background에 컬러를 설정했다.
- `position: relative;` 를 활용하여 로그인 창 위치를 위와 왼쪽으로 -5px씩 움직여 완성했다.

### 📌결과물
![](https://velog.velcdn.com/images/pearlx_x/post/51df0e88-f7fa-45ca-bdb3-b1d6a4783e6e/image.png)