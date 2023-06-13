# 🧷WebCafe news 레이아웃 구현
## 🧷마크업 순서

```
body
  └── section.news
      ├── h2
      ├── div.news-more
      │   ├── i.fa-sharp.fa-solid.fa-plus
      │   └── span
      └── hr
      └── section.news-container
          ├── figure.news-image
          │   ├── img
          │   └── figcaption
          ├── div.news-title
          │   ├── span.title
          │   └── span.date
          └── div.news-detail
```

---
### 🧷 코드 설명
#### header
>
```
<h2>새소식</h2>
<div class="news-more">
	<i class="fa-sharp fa-solid fa-plus" style="color: #447231;"></i>
       <span>더보기</span>
</div>
```
- 새소식은 이 section의 header이기 때문에 `<h2>`를 사용했다. 
- 아이콘과 텍스트를 묶기 위해 div로** news-more**이라는 이름을 가진 클래스를 만들었다.
```css
.news h2 {
  margin: 0;
  color: #ed552f;
  font-size: 0.875rem;
  font-weight: 700;
}
.news-more {
  font-weight: 400;
  position: absolute;
  top: 0;
  right: 0;
}
```
news-more를 우측 상단에 위치시키기 위해 `position: absolute`를 사용했다.

#### 구분선
>
```css
hr {
  width: 266px;
  border:0;
  margin:12px 0;
  height: 1px;
  background: linear-gradient(to right, #A9A9A9, #FFFFFF);
}
```
- `<hr>`를 사용해여 구분선을 만들었다.
- 시안에 있는 구분선에는 `linear-gradient` 효과가 들어가 있는데 그걸 표현하기 위해 
background를 사용하여 구현하였다.

#### news-container
>
```css
.news-container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-template-rows: auto;
  gap: 12px;
}
.news-image {
  grid-area: 1 / 1 / 4 / 2;
}
.news-title {
  grid-area: 1 / 2 / 3 / 2;
}
.news-detail {
  grid-area: 2 / 2 / 4/ 3;
}
```
- 그리드를 사용하여 레이아웃을 짰다
![](https://velog.velcdn.com/images/pearlx_x/post/a912b188-65f1-4e1b-a57f-2dc5fd883681/image.png)

#### figure
>
```
<figure class="news-image">
      <img src="./images/news1.png" alt="새로 단장한 W3C 홈페이지 사진" />
      <figcaption>W3C 리뉴얼</figcaption>
</figure>
```
- figure / figcaption을 사용하여 이미지에 대한 설명을 달아줬다.


### 📌결과물
![](https://velog.velcdn.com/images/pearlx_x/post/2ea1dd9c-0b6e-44d3-aa0a-db8a3c99c36e/image.png)

