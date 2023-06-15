# 🧷WebCafe Favorite Site
## 🧷 마크업 순서
```
body
 └── section.favoriteSite
    ├── h2.site-title
    │	└── span.accent-site-title
    ├── section.favorite-rank-wrapper
    |   └── ol.favorite-rank-list
    │    	 ├── li.favorite-rank-item sprite sprite1
    │   	 │    └── a 
    │   	 ├── li.favorite-rank-item sprite sprite1
    │   	 │    └── a 
    │   	 ├── li.favorite-rank-item sprite sprite1
    │   	 │    └── a 
    │   	 └── li.favorite-rank-item sprite sprite1
    |       	  └── a      
    |
    └── a.site-more
```
## 🧷 코드 설명
>`site-title` 클래스를 가진 제목 (h2 요소) : "인기" 텍스트와 강조 효과를 주기 위한 "사이트" 텍스트를 포함한다 .
`favorite-rank-wrapper` 클래스를 가진 섹션 요소
`favorite-rank-list` 클래스를 가진 순서 없는 목록 (ol 요소)
`favorite-rank-item` 클래스와 sprite 클래스를 가진 각 항목 (li 요소)
`link (a 요소)` 각 항목의 사이트 이름을 표시하고, 타겟과 관련 속성을 설정하여 링크를 열 수 있도록 한다.
`site-more` 클래스를 가진 링크 (a 요소) : "더보기" 텍스트를 표시하고, 타겟과 관련 속성을 설정하여 링크를 열 수 있도록 한다.
```css
.favorite-rank-list {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
  padding-left: 0;
  list-style: none;
  position: relative;
  gap: 8px;
  top: -8px;
}
```
`display: flex;`: .favorite-rank-list 요소를 유연한 박스 모델로 설정하여 내부 항목을 정렬할 수 있게 한다.
`flex-direction: column;`: 내부 항목을 수직으로 배치한다.
`justify-content: space-between;`: 내부 항목을 수직 방향으로 공간을 동일하게 분배하여 정렬합니다. 각 항목 사이에 동일한 간격을 생성한다.
`padding-left: 0;`: 좌측 여백을 0으로 설정하여 목록의 왼쪽 간격을 제거한다.
`list-style: none;`: 목록 항목 앞에 기본 목록 마커를 제거한다.
`position: relative;`: 상대적인 위치 지정을 설정한다.
`gap: 8px;`: 내부 항목 사이의 간격을 8픽셀로 설정한다.
`top: -8px;`: .favorite-rank-list 요소를 수직 방향으로 8픽셀 위로 이동시킨다.
```css
.favorite-rank-list li::before {
  color: white;
  background: #a3a3a3;
  border-radius: 5px;
  box-sizing: border-box;
  width: 16px;
  height: 16px;
  display: inline-block;
  position: absolute;
  text-align: center;
  line-height: 16px;
}
.favorite-rank-list li:nth-child(1)::before {
  content: "1";
}
.favorite-rank-list li:nth-child(2)::before {
  content: "2";
}
.favorite-rank-list li:nth-child(3)::before {
  content: "3";
}
.favorite-rank-list li:nth-child(4)::before {
  content: "4";
}
```
 `.favorite-rank-list` 클래스 내부의 `li` 요소의 가상 요소인 `::before`에 스타일을 적용하여 원형 모양의 텍스트 배경을 만들고, 텍스트를 가운데 정렬하여 아이콘과 같은 시각적인 효과를 구현했다.
```css
.favorite-rank-item {
  font-size: 0.6875rem;
  line-height: 1.0313rem;
  counter-increment: number;
}
.favorite-rank-item a {
  text-decoration: none;
  color: inherit;
  padding-left: 20px;
}
.favorite-rank-item::before {
  content: counter(number);
  color: white;
  background: #a3a3a3;
  border-radius: 5px;
  box-sizing: border-box;
  width: 16px;
  height: 16px;
  display: inline-block;
  position: absolute;
  text-align: center;
  line-height: 16px;
}
```
`counter-increment: number;`와 `content: counter(number);`css를 더 간단하게 수정해보았다.
`counter-increment: number;`는 list의 차례를 기억하고 `counter(number);`는 기억한 숫자를 불러오는 역할을 한다.
```css
.sprite {
  background: url(../assets/rank.png) no-repeat top right;
}
.sprite1 {
  background-position: 155px 3px;
}
.sprite2 {
  background-position: 155px -42px;
}
.sprite3 {
  background-position: 155px -19px;
}
.sprite4 {
  background-position: 155px 3px;
}
```
`.sprite` 클래스는 스프라이트 이미지를 배경으로 설정한다. 
`url(../assets/rank.png)`은 스프라이트 이미지의 경로를 지정하고, `no-repeat`은 이미지를 반복하지 않도록 설정하며, `top right`는 이미지를 오른쪽 상단에 배치한다.<br>
`.sprite1`, `.sprite2`, `.sprite3`, `.sprite4` 클래스는 각각 다른 스프라이트 위치를 지정한다. `background-position` 속성을 사용하여 X축과 Y축의 값을 지정하는데, 첫 번째 값은 X축 위치, 두 번째 값은 Y축 위치를 나타낸다. 이를 조정하여 각각의 스프라이트 이미지를 정확한 위치에 배치한다.


## 📌결과물
![](https://velog.velcdn.com/images/pearlx_x/post/b83255f6-292a-49ec-84b2-ac53daf2ba20/image.png)
