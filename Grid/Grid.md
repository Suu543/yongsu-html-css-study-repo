# Grid

## Grid Intro

`CSS Grid`를 활용하면 주축, 교차축 요소가 공통의 레이아웃을 가지는 것과 달리, 다음 사진과 같이 더욱 다양한 형태와 구조를 구현할 수 있습니다.

<img src="https://cdn-images-1.medium.com/max/800/1*z0Hx7e2rahNFzgQNm4dWkw.png" />
<img src="https://cdn-images-1.medium.com/max/800/1*rDh3u3RTNrj8jNa2OC2yBg.png" />
<img src="https://cdn-images-1.medium.com/max/800/1*xlbqVVOqz8qlata79kk-Cg.png" />

- https://gridbyexample.com/examples/

`CSS Flexbox`는 행(가로) 혹은 열(세로) 방식 중 하나로 배치할 때 사용하는 1차원 레이아웃입니다.
<img src="https://cdn-images-1.medium.com/max/800/1*TJZkKG-rhVP-YRYOFGC_YQ.png" />

`CSS Grid`는 행(가로) 그리고 열(세로) 두 개를 동시에 배치할 때 사용하는 2차원 레이아웃입니다.
<img src="https://cdn-images-1.medium.com/max/800/1*BXyS5KHQMQKQ3d2kDsbcJg.png" />

`CSS Flexbox`에서 또한 `flex-wrap` 속성을 사용하면 한 줄에 모든 요소를 포함하기에 공간이 부족한 경우 다음 줄로 건너뛰게 하는 방식으로 사용할 수 있습니다.
그래서 현재는 `CSS Flexbox` 속성이 레이아웃에 보편적으로 가장 많이 사용됩니다. 하지만 앞서 소개한 것 처럼 요소마다 크기가 다른 갤러리 혹은 레이아웃 형태 자체를 미리 잡고 가고 싶은 경우에는 `CSS Grid` 방식이 레이아웃 구현에 더 많은 효율과 이점을 얻을 수 있습니다. 어느 것이 좋다 말할 수는 없지만, `CSS Flexbox and Grid`를 모두 학습하고, 여러 프로젝트를 진행하면서 필요한 상황을 익히고, 각 상황에 적절한 것을 사용하는 것이 중요합니다.

1. `CSS Grid` 또한 `CSS Flexbox`와 동일하게 `부모(Container)` 역할을 하는 요소에 `grid`를 정의해야합니다.
2. `display: grid;` 레이아웃이 정의되면, 자식 요소는 `자식(grid cell)`로 변환됩니다.

```css
.parent {
  display: grid;
}
```

<img src="https://cdn-images-1.medium.com/max/800/1*Am8w3KEc7jKEHfXxmKI6pQ.png" />

`부모(Container)`에 정의할 수 있는 속성

- grid-template-columns: 가로축에 몇 개의 요소가 배치되고, 각 요소의 크기는 얼마인지 정의할 때 사용합니다.
- grid-template-rows: 세로축에 몇 개의 요소가 배치되고, 각 요소의 크기는 얼마인지 정의할 때
- grid-template-areas: 가로/세로축 영역을 정의하는 동시에 각 영역에 이름을 할당할 때
- grid-gap: 가로/세로축 요소 간 얼마의 간격을 줄 것인지 정의할 때
- grid-column-gap: 세로축 요소 간 얼마의 간격을 줄 것인지 정의할 때
- grid-row-gap: 가로축 요소 간 얼마의 간격을 줄 것인지 정의할 때

`자식(Grid Cell)`에 정의할 수 있는 속성

- grid-column-start: 정의된 `Grid` 탬플릿 내에서 어느 부분에 배치될 것인지 시작점 (가로 몇 번째)
- grid-column-end: 정의된 `Grid` 탬플릿 내에서 어느 부분까지 배치될 것인지 끝점 (가로 몇 번째까지)
- grid-row-start: 정의된 `Grid` 탬플릿 내에서 어느 부분에 배치될 것인지 시작점 (세로 몇 번째)
- grid-row-end: 정의된 `Grid` 탬플릿 내에서 어느 부분에 배치될 것인지 끝점 (세로 몇 번째까지)
- grid-area: `grid-template-areas`에 정의한 이름을 통해 배치될 영역을 정할 때

`CSS Grid`가 `CSS Flexbox`보다 어려운 이유는 `Grid`를 정의하는 방식이 다양하기 때문입니다.

## Grid Boilerplate

`Grid` 학습에 사용 할 `Boilerplate` 코드는 다음과 같습니다.

1. 부모 요소에는 `container` 클래스 정의
2. 자식 요소에는 `item` 클래스 정의
3. `div` 태그는 기본적으로 한 줄을 차지하기 때문에 줄마다 요소가 배치됐습니다.

- `item` 클래스 자식으로 오는 요소를 가운데 정렬하기 위해 `flex`를 정의하고, 행/열 모두 `center`를 적용했습니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="./basic-style.css" />
    <style></style>
  </head>
  <body>
    <div class="container">
      <div class="item color1">Item1</div>
      <div class="item color2">Item2</div>
      <div class="item color3">Item3</div>
      <div class="item color4">Item4</div>
      <div class="item color5">Item5</div>
      <div class="item color1">Item6</div>
      <div class="item color2">Item7</div>
      <div class="item color3">Item8</div>
      <div class="item color4">Item9</div>
      <div class="item color5">Item10</div>
    </div>
  </body>
</html>
```

```css
/* basic-style.css */
* {
  box-sizing: border-box;
}

body {
  width: 100vw;
  height: 100vh;
  margin: 0;
}

.item {
  display: flex;
  justify-content: center;
  align-items: center;
  border: 1px solid #181818;
  font-size: 1.2rem;
  font-weight: bold;
}

.color1 {
  background-color: #173f5f;
}

.color2 {
  background-color: #20639b;
}

.color3 {
  background-color: #3caea3;
}

.color4 {
  background-color: #f6d55c;
}

.color5 {
  background-color: #ed553b;
}
```

### Grid Part1

- `display: grid`

```html
<style>
  .container {
    display: grid;
  }
</style>
```

`display: grid;`만을 정의하면 레이아웃에 아무런 변화가 생기지 않습니다. <br />
레이아웃에 변화를 부여하기 위해 `grid-template-columns | grid-template-rows` 속성을 적용해보겠습니다.

```css
/* grid.css */
.container {
  display: grid;
  grid-template-columns: 100px 100px 100px;
  grid-template-rows: 100px 200px 100px 100px;
}
```

같은 크기를 여러 번 반복하는 경우 `repeat` 함수를 사용해 간편히 구현할 수 있습니다.

```css
.container {
  display: grid;
  grid-template-columns: repeat(5, 100px);
  grid-template-rows: 100px 200px repeat(2, 100px);
}
```

보통 `Grid`를 사용할 때 반응형으로 만드는 것이 중요하므로, `px` 단위 대신 사용 가능한 부모 `Grid` 너비의 총 다섯 개로 나누어 할당한 것인지 `%`를 사용해도 되고, `Grid`에서 구획을 의미하는 `fr` 단위를 사용할 수 있습니다.

사용 가능한 전체 너비의 `20%`씩 다섯 번 나누고 싶은 경우 다음과 같이 코드를 작성할 수 있습니다.

```css
.container {
  display: grid;
  grid-template-columns: repeat(5, 20%);
  grid-template-rows: 100px 200px 100px 100px;
}
```

`fr` 단위를 사용하는 경우 다음과 같이 코드를 작성할 수 있습니다. `fr` 총합으로 화면을 나누고 그 비율만큼 공간이 할당되는 방식으로 동작합니다.

```css
.container {
  display: grid;
  grid-template-columns: 1fr 2fr 1fr;
  grid-template-rows: 100px 200px 100px 100px;
}
```

크기를 보다 유동적으로 변할 수 있도록 `px` 단위보다는 `fr or %` 등의 단위 사용이 권장됩니다.

```css
.container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: 100px 200px 100px 100px;
}
```

`row`가 정확히 몇 줄인지는 모르겠지만, 자동으로 전체적인 크기를 지정하고 싶은 경우 `grid-auto-rows` 속성을 사용할 수 있습니다. 다음 코드는 몇 줄이 될지는 모르겠지만, 각 줄당 `150px`의 높이가 설정된 방식으로 동작합니다.

```css
.container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-auto-rows: 150px;
}
```

만약 `Item` 텍스트가 양이 정의한 `150px`의 길이를 초과하는 경우 잘리는 현상이 발생합니다. 그래서 고정된 `150px`이 아닌, `minmax` 함수를 이용해 최소, 최대 높이를 지정할 수 있습니다.

```css
.container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-auto-rows: minmax(150px, auto);
}
```

`Column` 간의 간격을 주고 싶은 경우 `grid-column-gap` 속성을 사용할 수 있습니다. <br />
`Row` 간의 간격을 주고 싶은 경우 `grid-row-gap` 속성을 사용할 수 있습니다. <br />
만약 `Column and Row` 모두 같은 간격을 가지고 있는 경우 축약형으로 `grid-gap` 속성을 사용할 수 있습니다.

```css
.container {
  display: grid;
  grid-template-columns: repeat(5, 1fr);
  grid-auto-rows: minmax(150px, auto);
  grid-column-gap: 10px;
  grid-row-gap: 10px;

  /* grid-gap: 10px */
}
```

`grid-gap`은 `grid-cell` 사이에 간격을 주는 속성이기 때문에, `grid container` 자체에 간격을 주고 싶은 경우 `padding`을 활용할 수 있습니다.

```css
.container {
  display: grid;
  padding: 10px;
  grid-template-columns: repeat(5, 1fr);
  grid-auto-rows: minmax(150px, auto);
  grid-gap: 10px;
}
```

`Grid Part1` 에서는 `Grid Container`를 정의하고, `grid-template-columns and grid-template-rows` 속성을 지정하는 것까지 알아봤습니다. 지금부터는 각각의 `Item`이 `Grid Cell`을 몇 개 차지할 것인지에 대해 정의 방식을 알아보겠습니다.

## Grid Part2

`Item2` 요소가 `Item2 ~ Item3` 공간까지 차지할 수 있도록 구현해보겠습니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <link rel="stylesheet" href="./basic-style.css" />
    <link rel="stylesheet" href="./grid.css" />
  </head>
  <body>
    <div class="container">
      <div class="item color1">Item1</div>
      <div class="item item2 color2">Item2</div>
      <div class="item color3">Item3</div>
      <div class="item color4">Item4</div>
      <div class="item color5">Item5</div>
      <div class="item color1">Item6</div>
      <div class="item color2">Item7</div>
      <div class="item color3">Item8</div>
      <div class="item color4">Item9</div>
      <div class="item color5">Item10</div>
    </div>
  </body>
</html>
```

```css
/* grid.css */
.container {
  display: grid;
  padding: 10px;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: minmax(150px, auto);
  grid-gap: 10px;
}
```

<img src="https://cdn-images-1.medium.com/max/800/1*BolebCxK3xXHZpUeQe8qIA.png" />
<img src="https://cdn-images-1.medium.com/max/800/1*R8cTrHCpPeIkSbwLGxMyWA.png" />

별도로 `Item`에 별도의 속성을 지정하지 않으면, 각각 하나의 `Cell`을 차지합니다. 하지만 `grid-column-start and grid-column-end` 속성을 통해 더 많은 `Cell`을 차지할 수 있게 지정할 수 있습니다.

`column`에서 2 ~ 4번째 까지 자리를 차지하도록 지정해보겠습니다.

```css
/* grid.css */
.container {
  display: grid;
  padding: 10px;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: minmax(150px, auto);
  grid-gap: 10px;
}

.item2 {
  grid-column-start: 2;
  grid-column-end: 4;
}
```

이 상태에서 `Item6 ~ Item7`까지 자리를 확장하고 싶은 경우 `grid-row-start and grid-row-end` 속성을 사용할 수 있습니다.

```css
/* grid.css */
.container {
  display: grid;
  padding: 10px;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: minmax(150px, auto);
  grid-gap: 10px;
}

.item2 {
  grid-column-start: 2;
  grid-column-end: 4;
  grid-row-start: 1;
  grid-row-end: 3;
}
```

매번 시작과 끝 지점을 일일이 명시하는 것이 번거로워서 `grid-column and grid-row` 축약형을 사용할 수 있습니다.

```css
/* grid.css */
.container {
  display: grid;
  padding: 10px;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: minmax(150px, auto);
  grid-gap: 10px;
}

.item2 {
  grid-column: 2 / 4;
  grid-row: 1 / 3;
}
```

또는 일일이 줄 번호를 정의하기 귀찮다면, `span` 기능을 이용할 수 있습니다.

- `2 / 4` == `2 / span 2`

```css
/* grid.css */
.container {
  display: grid;
  padding: 10px;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: minmax(150px, auto);
  grid-gap: 10px;
}

.item2 {
  grid-column: 2 / span 2;
  grid-row: 1 / span 2;
}
```

만약 2번째부터 끝까지 차지하고 싶은 경우 `-1` 값을 이용할 수 있습니다.

```css
/* grid.css */
.container {
  display: grid;
  padding: 10px;
  grid-template-columns: repeat(5, 1fr);
  grid-template-rows: minmax(150px, auto);
  grid-gap: 10px;
}

.item2 {
  grid-column: 2 / -1;
  grid-row: 1 / span 2;
}
```

## Grid Part3

`grid-area` 속성을 통해 `grid layout` 배치를 조금 더 편리하게 구현할 수 있습니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="basic-style.css" />
    <link rel="stylesheet" href="image.css" />
    <title>Document</title>
  </head>
  <body>
    <section class="container">
      <img
        src="https://images.unsplash.com/photo-1661933021480-75b708d5648f?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwzfHx8ZW58MHx8fHw%3D&auto=format&fit=crop&w=500&q=60"
        alt="img"
        class="image image1"
      />
      <img
        src="https://images.unsplash.com/photo-1661912267451-712c028d74a7?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwyfHx8ZW58MHx8fHw%3D&auto=format&fit=crop&w=500&q=60"
        alt="img"
        class="image image2"
      />
      <img
        src="https://images.unsplash.com/photo-1661895581832-51c8e3538b4d?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80"
        alt="img"
        class="image image3"
      />
      <img
        src="https://images.unsplash.com/photo-1661836890977-1cc392056094?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxlZGl0b3JpYWwtZmVlZHwxN3x8fGVufDB8fHx8&auto=format&fit=crop&w=500&q=60"
        alt="img"
        class="image image4"
      />
      <img
        src="https://images.unsplash.com/photo-1661900980235-db5affe17d8c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1567&q=80"
        alt="img"
        class="image image5"
      />
      <img
        src="https://images.unsplash.com/photo-1661901060088-32dbfeb040df?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=774&q=80"
        alt="img"
        class="image image6"
      />
      <img
        src="https://images.unsplash.com/photo-1661890090656-6bf16bbdee4c?ixlib=rb-1.2.1&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=874&q=80"
        alt="img"
        class="image image7"
      />
    </section>
  </body>
</html>
```

```css
/* image.css */
body {
  padding: 5rem;
  background-color: black;
}

.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 150px;
  grid-gap: 1rem;
}

.image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

`grid-area` 속성은 앞서 봤던 `grid-column and grid-row` 번호 대신에 해당 위치에 변수명을 짓는 것처럼 이름을 정의할 수 있습니다.

```css
/* image.css */
body {
  padding: 5rem;
  background-color: black;
}

.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 150px;
  grid-gap: 1rem;
  grid-template-areas:
    "a a a"
    "b c c"
    "b d g"
    "e f g";
}

.image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}
```

위와 같이 `grid-template-areas`를 정의하면, `Item Cell A`는 `a` 위치에, `Item Cell B`는 `b` 위치에, `Item Cell C`는 `c` 위치에 배치하고 더욱 손쉽게 레이아웃을 구성할 수 있습니다.

<img src="https://cdn-images-1.medium.com/max/800/1*90DoEbFctDujIVdPoGVXHA.png" />

`Item Cell` 요소에 `grid-area` 속성을 이용해 정의한 공간의 이름을 할당하면, 정의한 형태에 맞춰 레이아웃이 형성됩니다.

```css
/* image.css */
body {
  padding: 5rem;
  background-color: black;
}

.container {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  grid-auto-rows: 150px;
  grid-gap: 1rem;
}

.image {
  width: 100%;
  height: 100%;
  object-fit: cover;
}

.image1 {
  grid-area: a;
}

.image2 {
  grid-area: b;
}

.image3 {
  grid-area: c;
}

.image4 {
  grid-area: d;
}

.image5 {
  grid-area: e;
}

.image6 {
  grid-area: f;
}

.image7 {
  grid-area: g;
}
```

어떤 영역에 포함될 것인지 정의함으로써 원하는 레이아웃을 구현할 수 있습니다.

## Grid Part4

<img src="https://cdn-images-1.medium.com/max/800/1*6xlly22qNI9F4p9Tq3-j7A.png" />

앞서 학습한 내용만 잘 파악해도 전체적인 웹사이트 구조를 `CSS Grid` 만으로 지정해 볼 수 있습니다.
위 사진과 같이 레이아웃을 구성해보겠습니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link rel="stylesheet" href="./index.css" />
    <title>Document</title>
  </head>
  <body>
    <header class="header">Header</header>
    <main class="main">Main :)</main>
    <aside class="aside">Side</aside>
    <footer class="footer">Footer</footer>
  </body>
</html>
```

```css
body {
  font-size: 2rem;
  font-weight: bold;
  background-color: white;
}

header,
main,
aside,
footer {
  display: flex;
  justify-content: center;
  align-items: center;
}

header {
  background-color: black;
  color: white;
}

aside {
  background-color: #ff9d00;
}

footer {
  background-color: black;
  color: white;
}

body {
  width: 100vw;
  height: 100vh;
  margin: 0;
  display: grid;
  grid-template-columns: 3fr 1fr;
  grid-template-rows: 100px auto 50px;
  grid-template-areas:
    "header header"
    "main side"
    "footer footer";
}

.header {
  grid-area: header;
}

.main {
  grid-area: main;
}

.aside {
  grid-area: side;
}

.footer {
  grid-area: footer;
}
```
