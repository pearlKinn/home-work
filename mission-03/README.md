# 📌 관련 사이트 구현
## 🧷 트리구조
```
body
└── section.siteWrapper
    ├── h2[hidden] 
    ├── div.related-site
    │   └── span.emphasis 
    └── div.listWrapper
        └── ul.site__list
           ├── li.site__item
           │   └── a 
           ├── li.site__item
           │   └── a 
           ├── li.site__item
           │   └── a
           ├── li.site__item
           │   └── a 
           └── li.site__item
               └── a
```
## 🧷 코드 리뷰

>**과제 조건**
> 1. 관련 사이트는 제목으로 각각 항목은 링크로 구현한다.
> 2. 링크 목록은 5개이며 CSS를 사용하여 화면에 1개의 목록만 보이도록 구현한다.
> 3. 목록에 마우스를 올리면 5개의 목록이 펼쳐지도록 구현한다.
> 4. transition 속성을 활용하여 애니메이션 효과를 적용한다.


- 헤더 부분에서는 구조적으로 제목을 사용하기 위해 `<h2>` 를 사용했고 아래 있는 '관련 사이트'와 스크린리더에서 내용이 겹치지 않도록 `hidden` 처리를 해주었다.
- `.related-site`에는 '관련 사이트'라는 텍스트를 넣어줬는데 뒤에 있는 '사이트'에 <span style="color:orange">주황색</span>으로 글자를 처리하고싶어 `<span>`을 사용하여 '사이트' 텍스트만  따로 뮦어줬다.
- 슬라이딩 부분
	- 2번, 3번의 조건을 모두 맞추기 위해 `.listWrapper` css에 
    `width`는 166px,`height`는 21px로 선언하고 
    한 개의 값만 보여줄 수 있도록 `overflow: hidden`을 선언하여 
    상자 밖으로 넘치는 텍스트들은 숨겨줬다.
	- 시안을 보면 시간차를 두고 리스트가 펼쳐지고 텍스트가 다시 정렬되는데 그런 애니메이션은 `transition: height 500ms, padding-top 500ms 500ms;`으로 시간차를 두고 작동할 수 있게 해주었다.

### 🏷️ CSS
```css
.listWrapper {
  box-sizing: border-box;
  border: 1px solid #A3A3A3;
  border-radius: 3px;
  background: white;
  width: 166px;
  height: 21px;
  overflow: hidden;
  transition: height 500ms, padding-top 500ms 500ms;
}

.listWrapper:hover {
/* hover시 글자를 아래로 정렬 */
  padding-top: 5px;
  width: 166px;
  height: 145px;
}

.site__list {
  position: relative;
  top: -5px;
  display: flex;
  flex-direction: column;
  justify-content: space-around;
  position: relative;
  box-sizing: border-box;
  list-style: none;
  padding-left: 24px;
  margin: 0;
  line-height: 27px;
}

.site__item {
  height: 29px;
}

.site__item a {
  color: #000;
  text-decoration: none;
  font-size: 0.875rem;
}

```

### 📌 결과물
![](https://velog.velcdn.com/images/pearlx_x/post/649d19ff-73e1-4e1c-a85c-53d93a4dfe11/image.gif)
