# Flexbox

## Flexbox Intro

Flexbox는 웹 사이트 정렬에 사용되는 1차원 레이아웃 모델입니다. 1차원이라 칭하는 것은, 레이아웃을 다룰 때 한 번에 하나의 차원(행 or 열)만을 다룬다는 뜻입니다.

이해를 돕고자 큰 상자안에 10개의 작은 상자가 있다고 생각해보겠습니다.
큰 상자 내의 작은 상자를 정리하는 방식에는 크게 두 종류가 존재합니다.

1. 가로 방식으로 정렬하기
2. 세로 방식으로 정렬하기

정렬 이후에는 공간 활용도를 위해 작은 상자 사이에 균등한 간격 배치 위치 등을 결정해야 합니다. 정렬 방식은 크게 네 종류가 존재합니다.

1. 왼쪽 끝
2. 가운데
3. 오른쪽 끝
4. 통일된 간격

Flexbox를 요약하자면

1. 큰 상자가 가로 or 세로 중 어떤 방식으로 정렬할 것인지,
2. 정렬 방향을 정했다면, 어떤 방식으로 정렬할 것인지

정의하는 데 유용하게 사용할 수 있는 CSS 속성입니다.

## Flexbox Part1

- **flex**
- **flex-direction**
- **flex-wrap**
- **flex-flow**

`Flexbox`는 부모 자식 관계가 형성된 태그 사이에 적용할 수 있는 속성입니다.

부모는 `Flexbox` 용어로 `Container (큰 상자)`이라고 부르고, <br />
자식은 `Flexbox` 용어로 `Items (작은 상자)`이라고 부릅니다.

<img src="https://cdn-images-1.medium.com/max/800/1*rv8QSFqfnXEZ4WFoqCdsrw.png" />
<img src="https://camo.githubusercontent.com/f528ce220a93abb70d379c5753f99ac872596584fc38c7c57add380d13163681/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a724547667536695641676c54624a30523269626942512e706e67" />

코드를 보면, `ul` 태그와 `li` 태그는 부모 자식 관계가 형성됐습니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        padding: 10px;
        margin: 20px;
        width: 100px;
      }
    </style>
  </head>
  <body>
    <!-- Parent Element-->
    <ul>
      <!-- Child Element-->
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>5</li>
    </ul>
  </body>
</html>
```

`Flexbox` 속성은 부모 역할인 `Container`에게 부여할 수 있습니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;

        /* flexbox 속성 부여*/
        display: flex;
        /* row | row-reverse | column | column-reverse */
        flex-direction: row;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        padding: 10px;
        margin: 20px;
        width: 100px;
      }
    </style>
  </head>
  <body>
    <!-- Parent Element-->
    <ul>
      <!-- Child Element-->
      <li>1</li>
      <li>2</li>
      <li>3</li>
      <li>4</li>
      <li>5</li>
    </ul>
  </body>
</html>
```

`Flexbox` 속성을 부여하면 `Container (큰 상자)` 자식인 `Items(작은 상자)`가 가로, 세로 (행) 균일한 간격으로 나타난 것을 확인할 수 있습니다.
<img src="https://cdn-images-1.medium.com/max/800/1*4tWzNDXs5cckcCxaby7Zug.png" />

정렬 방식은 네 종류가 있습니다.

- `Keyword`: 주축(main-axis), 교차축(cross-axis)

1. **flex-direction: row;** (왼쪽 ==> 오른쪽 (열 - 가로 정렬)): 기본값

- 주축(main-axis): 가로, 교차축(cross-axis): 세로

2. **flex-direction: row-reverse;** (오른쪽 ==> 왼쪽 (열 - 가로 정렬))

- 주축(main-axis): 가로, 교차축(cross-axis): 세로

3. **flex-direction: column;** (위 ==> 아래 (행 - 세로 정렬))

- 주축(main-axis): 세로, 교차축(cross-axis): 가로

4. **flex-direction: column-reverse;** (아래 ==> 위 (행 - 세로 정렬))

- 주축(main-axis): 세로, 교차축(cross-axis): 가로

<img src="https://camo.githubusercontent.com/9362d9d59b6e4695014b7baf1814e68f97758cd0c5857f3af42cd38ef195e8a8/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a37495876584e586c4b45745f663050767246774863412e706e67" />
<img src="https://camo.githubusercontent.com/fa9e20e1d96c979cdb8fa028a113e629d8cac4fd748dbc8fd33975ec12ad526b/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a6272695838586d4767796d2d342d61485842713341672e706e67" />
<img src="https://camo.githubusercontent.com/b633d45d81374701e7e597b0bf85df5e08053f888519dc225fc1cfe25cff8255/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a59364e4e615a31737a4d616a794f33326879515a49672e706e67" />
<img src="https://camo.githubusercontent.com/240913c0761994b6329acd5dd90ac3e68cd9c6a16d1ca5e20559322eb7819002/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a4d7041334748395745384d4270706e6f6647647461772e706e67" />

### flex-wrap

- **flex-wrap: nowrap;**
- **flex-wrap: wrap;**
- **flex-wrap: wrap-reverse;**

다음과 같이 값이 정의된 상황을 생각해보겠습니다. (`Item`: 12개)

- `Container` 가로 길이: 1000px;
- `Item` 가로 길이: 100px;

`Item`이 총 12개 이기 때문에 가로 길이의 총합이 `1200px;`로 계산됩니다. 이 경우 부모 `Container`의 가로 길이를 초과하기 때문에 다음 사진과 같이 부모 요소를 벗어나게 됩니다. 이 경우를 `nowrap`이라 칭합니다. `flexbox`에 `wrap`과 관련된 코드를 별도로 정의하지 않는 경우 `nowrap` 방식으로 동작합니다.

- `flex-wrap: nowrap;`

<img src="https://camo.githubusercontent.com/65fd4a188215f210653e4fea98b12d0d40fcecfa3ef2accdfe8673c7b50ef645/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a33714b4a3777705576694a553543526c4e7973564e772e706e67" />

`Container`를 초과한 요소가 줄 바꿈 되었을 때, 정의된 가로 길이를 유지할 공간이 있다면 자동으로 줄 바꿈 되도록 설정할 수 있습니다. 이렇게 동작방식을 `wrap` 이라고 합니다.

- `flex-wrap: wrap;`

<img src="https://camo.githubusercontent.com/775e5a8ac96084ca41b5fc4bb02910a75797179563545dcd77370ea4706c897f/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a416b45302d33303471643066435a575a7a6f487970772e706e67" />

`wrap`과 같이 동작하면서, 그 순번을 반대로 하고 싶은 경우 `wrap-reverse` 속성을 사용할 수 있습니다.

<img src="https://camo.githubusercontent.com/34a683218e7ef712ab2fb43f2ff90da88e5743cd01775a7d0a6c2a2c42d568b4/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a594c585571324f3033703475716772334666353175672e706e67" />

- `flex-wrap: wrap-reverse;`

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;

        /* nowrap | wrap | wrap-reverse */
        display: flex;
        flex-wrap: nowrap;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        margin: 20px;
        padding: 10px;
        width: 100px;
        font-size: 20px;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
      <li>5th Child</li>
      <li>6th Child</li>
      <li>7th Child</li>
      <li>8th Child</li>
      <li>9th Child</li>
      <li>10th Child</li>
      <li>11th Child</li>
      <li>12th Child</li>
    </ul>
  </body>
</html>
```

### flex-flow

- `flex-flow = flex-direction + flex-wrap;`

`flex-direction`과 `flex-wrap`을 한 번에 정의할 때 `flex-flow` 속성을 사용할 수 있습니다.

Ex)

- flex-direction: row;
- flex-wrap: wrap;

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;
        height: 300px;
        display: flex;
        flex-flow: row wrap;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        margin: 20px;
        padding: 10px;
        width: 100px;
        font-size: 20px;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
      <li>5th Child</li>
      <li>6th Child</li>
      <li>7th Child</li>
      <li>8th Child</li>
      <li>9th Child</li>
      <li>10th Child</li>
      <li>11th Child</li>
      <li>12th Child</li>
    </ul>
  </body>
</html>
```

<img src="https://camo.githubusercontent.com/eb2af57b7e53bc03d8062c5f626c30007a77fee74c28141ef72f65ad1e373dfe/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a594a4e463058646870577a6673477551446b386f33512e706e67" />

Ex)

- flex-direction: column;
- flex-wrap: wrap;

```html
ul { background-color: lightslategray; padding: 20px; height: 300px; display:
flex; flex-flow: column wrap; }
```

<img src="https://camo.githubusercontent.com/edb6a03141c33bb3b2fe839dd508c6870ec10617266824ad1624c7d3a5633655/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a776971776a464b65352d322d5f314e303056373567772e706e67" />

Ex)

- flex-direction: row-reverse;
- flex-wrap: wrap;

```html
ul { background-color: lightslategray; padding: 20px; height: 300px; display:
flex; flex-flow: row-reverse wrap; }
```

<img src="https://camo.githubusercontent.com/2dbc543c421c6567304d0d727770550fb79497c4106c877c0c7d4bec63e22978/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a495456354162586a35515466453155676b43797547672e706e67" />

## Flexbox Part2

- **justify-content**
- **align-items**
- **align-content**

`display: flex;`를 정의하는 순간 **주축(main-axis)**과 **교차축(cross-axis)**의 개념이 발생합니다.

정렬 방식은 네 종류가 있습니다.

- `Keywords`: **주축(main-axis), 교차축(cross-axis)**

1. **flex-direction: row;** (왼쪽 ==> 오른쪽 (열 - 가로 정렬)): 기본값

- 주축(main-axis): 가로, 교차축(cross-axis): 세로

2. **flex-direction: row-reverse;** (오른쪽 ==> 왼쪽 (열 - 가로 정렬))

- 주축(main-axis): 가로, 교차축(cross-axis): 세로

3. **flex-direction: column;** (위 ==> 아래 (행 - 세로 정렬))

- 주축(main-axis): 세로, 교차축(cross-axis): 가로

4. **flex-direction: column-reverse;** (아래 ==> 위 (행 - 세로 정렬))

- 주축(main-axis): 세로, 교차축(cross-axis): 가로

### justify-content

이 속성은 **주축(main-axis)** 기준으로 요소를 정렬할 때 사용하는 속성입니다.

`justify-content` 설명에 사용한 예시는 `flex-direction: row;`를 기준으로 작성했습니다.

- **justify-content: flex-start;**
- **justify-content: center;**
- **justify-content: flex-end;**
- **justify-content: space-between;**
- **justify-content: space-evenly;**
- **justify-content: space-around;**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;
        display: flex;
        justify-content: flex-start;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        margin: 20px;
        padding: 10px;
        width: 100px;
        font-size: 20px;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
      <li>5th Child</li>
    </ul>
  </body>
</html>
```

주축(main-axis) 시작점 위치에 요소를 정렬하고 싶은 경우

- **justify-content: flex-start**;

```html
ul { display: flex; flex-direction: row; justify-content: flex-start; }
```

<img src="https://camo.githubusercontent.com/e0f13f9c65c154595ddc1729cd98fb84bf55817fef0c9fb2fdfd31acfa1f2836/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a614268676d49794576666c36766462314458683264772e706e67" />

주축(main-axis) 끝 위치에 요소를 정렬하고 싶은 경우

- **justify-content: flex-end;**

```html
ul { display: flex; flex-direction: row; justify-content: flex-end; }
```

<img src="https://camo.githubusercontent.com/40e6700371119ab92d7ce315b417e9d019ad287fa8fde52646270ae8c0957452/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a61536e6533666753685053745f416b707a70354b44412e706e67" />

주축(main-axis) 가운데 요소를 정렬하고 싶은 경우

- **justify-content: center;**

```html
ul { display: flex; flex-direction: row; justify-content: center; }
```

<img src="https://camo.githubusercontent.com/0ad5d98f6fd3d9d5fbc7aa8fd283c0678cd24d2b9aac5170de4ccdf6859c8a73/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a6264374d66724e5a72474b3435693835645a427438412e706e67" />

주축(main-axis) 양쪽 끝 지점에 위치한 요소를 제외한, 나머지 요소를 균등한 간격을 배치하고 싶은 경우

- **justify-content: space-between;**

```html
ul { display: flex; flex-direction: row; justify-content: space-between; }
```

<img src="https://camo.githubusercontent.com/faac0593db29288560ae91256dbafc4687a48d9ed1cf027c8b6588152dcbf00c/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a626142746f51546731655f3031395331484e68674b512e706e67" />

주축(main-axis) 양쪽 끝 지점에 있는 요소를 포함해, 모든 요소의 왼쪽, 오른쪽에 균등한 간격을 배치하고 싶은 경우 (이 경우 양쪽 끝 지점에 있는 요소는 왼쪽 혹은 오른쪽 한 칸의 간격밖에 없으므로 균등한 간격이 아닌 것처럼 보일 수 있습니다.)

- **justify-content: space-around;**

```html
ul { display: flex; flex-direction: row; justify-content: space-around; }
```

<img src="https://camo.githubusercontent.com/590b8a8a6e98e66ba02a73b315e48f4bdfe2e02908e2fb625b31de8563755b2f/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a45585f4a6f6e47476a75656f6174416e7159677676512e706e67" />

주축(main-axis) 양쪽 끝 지점을 포함한 모든 요소를 균등한 간격으로 배치하고 싶은 경우

- **justify-content: space-evenly;**

```html
ul { display: flex; flex-direction: row; justify-content: space-evenly; }
```

<img src="https://camo.githubusercontent.com/4a194cc42e8b4b76aa21ba01e71d9ce37342dca5d11b534d1c2e02e1f68939d4/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a545636733030575a4e35694f55775169477533694e412e706e67" />

### align-items

이 속성은 **교차축(cross-axis)** 기준으로 요소를 정렬할 때 사용하는 속성입니다.

`align-items` 설명에 사용한 예시는 `flex-direction: row;`를 기준으로 작성했습니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;
        height: 300px;
        display: flex;
        align-items: stretch;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        margin: 20px;
        padding: 10px;
        width: 100px;
        font-size: 20px;
        text-align: center;
        padding-top: 20px;
        padding-bottom: 20px;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
      <li>5th Child</li>
    </ul>
  </body>
</html>
```

교차축(cross-axis) 정렬을 별도로 정의하지 않으면, `align-items: stretch;` 속성이 적용됩니다.

- align-items: stretch;

```html
ul { display: flex; flex-direction: row; align-items: stretch; }
```

<img src="https://camo.githubusercontent.com/b80b3c2468121f081ec4b2393916e2a97abada154defaac802773ffce0662d1e/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a694872764c4445327558545f46534e636e414d6b41672e706e67" />

교차축(cross-axis) 시작점 위치에 요소를 정렬하고 싶은 경우

- **align-items: flex-start;**

```html
ul { display: flex; flex-direction: row; align-items: flex-start; }
```

<img src="https://camo.githubusercontent.com/fec103d4352c16e0cef5633eeaaf2eb1b15a0a9c6c7b09a2a4892ad3c7eb0b30/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a58777032366c692d6439565f6f747670644b683841672e706e67" />

교차축(cross-axis) 끝 위치에 요소를 정렬하고 싶은 경우

- **align-items: flex-end;**

```html
ul { display: flex; flex-direction: row; align-items: flex-end; }
```

<img src="https://camo.githubusercontent.com/3b1851df4f2827150ad25dbb7d1a868b0e1716d85d58b2cb8990d6f3365cd539/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a577536724b7a336f6b78354d6c396b315f54637133672e706e67" />

교차축(cross-axis) 가운데 요소를 정렬하고 싶은 경우

- **align-items: center;**

```html
ul { display: flex; flex-direction: row; align-items: center; }
```

<img src="https://camo.githubusercontent.com/b166b008e388352d9dffb6dd5e0b01af2ae175c30431fc9dfc3ccbdd7e9a0088/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a6c567a64466b44567449785f495773654764474479412e706e67" />

교차축(cross-axis) 정렬 과정에 `패딩(padding)` 등의 영향으로 글자 높이가 다른 경우, 모든 글자를 같은 높이에 정렬하고 싶은 경우

- **align-items: baseline;**

```html
li:first-child { padding: 5px; } ul { display: flex; flex-direction: row;
align-items: baseline; }
```

<img src="https://camo.githubusercontent.com/b8d0014fe8b43500ebcdf9b73b93e3770923ef6ea1b6942664091983067647a8/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a7942733455473178616a334e565572596b774c6b39772e706e67" />

<img src="https://camo.githubusercontent.com/f29afbe2df5d966273a4f52b42bdeb1fcddac6b6f35c19a1963232cda946b645/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a746155425471526b68624a76543256546359626970412e706e67" />

`align-items: flex-start`로 변경하면 `baseline` 정렬이 깨지는 것을 확인할 수 있습니다.

### align-content

`Container`내의 `Items`가 `wrap` 등에 의해 줄 바꿈이 발생해 두 줄 이상이 된 경우, `align-content` 속성을 활용해 주축(main-axis)과 같이 더욱 동적인 정렬을 구현할 수 있게 해줍니다.

전제: 두 줄 이상의 요소

`align-content` 설명에 사용한 예시는 `flex-direction: row;`를 기준으로 작성했습니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;
        height: 600px;
        display: flex;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        margin: 10px;
        padding: 10px;
        width: 100px;
        font-size: 20px;
        text-align: center;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
      <li>5th Child</li>
      <li>6</li>
      <li>7</li>
      <li>8</li>
      <li>9</li>
      <li>10</li>
      <li>11</li>
      <li>12</li>
      <li>13</li>
      <li>14</li>
      <li>15</li>
    </ul>
  </body>
</html>
```

<img src="https://camo.githubusercontent.com/b8d0014fe8b43500ebcdf9b73b93e3770923ef6ea1b6942664091983067647a8/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a7942733455473178616a334e565572596b774c6b39772e706e67" />

모든 요소(두 줄 이상)가 차지할 수 있는 모든 교차축(cross-axis) 공간을 차지하고 싶은 경우

- **align-content: stretch;**

```html
ul { align-content: stretch; }
```

<img src="https://camo.githubusercontent.com/efce54ec9c9792d94d16401c8a30759b8d2eb39e67eb3a01b105ecf5ce51c1da/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a4c5f4645726c506f514933515f5f37775647316430412e706e67" />

교차축(cross-axis) 시작점 위치에 요소(두 줄 이상)를 정렬하고 싶은 경우

- **align-content: flex-start;**

```html
ul { align-content: flex-start; }
```

<img src="https://camo.githubusercontent.com/4227fbaf1c5527ec2d49b8c540a3e18aac1cf518d42f4beb4f221eaebbb1a3d2/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a686f5f4a746d5244667233696231684e526f354830772e706e67" />

한 줄 교차축 속성인 `align-items: flex-start;`만 정의하고, `align-content`를 별도로 정의하지 않는 경우, 요소가 두 줄 이상일 때 다음 사진과 같은 예상치 못한 오류가 발생한다. 그러므로, 두 줄 이상의 요소를 정렬하는 경우 `align-content` 속성을 사용해 내용을 일관성 있게 정렬해야 한다.

<img src="https://camo.githubusercontent.com/e274d751b8c78b74c3aa960b051e4716dd0c47a84dd557e0b7e8712c351c0bbd/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a567a66314b47776e4544426833706c566e52737932672e706e67" />

교차축(cross-axis) 끝 위치에 요소(두 줄 이상)를 정렬하고 싶은 경우

- **align-content: flex-end;**

```html
ul { align-content: flex-end; }
```

<img src="https://camo.githubusercontent.com/dcee6b05f065056456f6f55e2367d8f9deaf9871cf7fb810bcf88d5b8fe4f1dc/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a546a6275665966306a41464d564f34516e6841316b412e706e67" />

교차축(cross-axis) 양쪽 끝 지점에 위치한 요소를 제외한, 나머지 요소를 균등한 가격으로 배치하고 싶은 경우

- **align-content: space-between;**

```html
ul { align-content: space-between; }
```

<img src="https://camo.githubusercontent.com/3198479ec9fbf10d8549279f4f0b6093c8fb82f8ca6612548630825f6751e47a/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a58565f55573554466b37485866412d68412d4d7943412e706e67" />

교차축(cross-axis) 양쪽 끝 지점에 있는 요소를 포함해 모든 요소를 균등한 간격으로 배치하고 싶은 경우 (이 경우 양쪽 끝 지점에 있는 요소는 왼/오 혹은 위/아래 한 칸의 간격밖에 없으므로 균등한 간격이 아닌 것처럼 보일 수 있습니다.)

- **align-content: space-around;**

```html
ul { align-content: space-around; }
```

<img src="https://camo.githubusercontent.com/77ae9c6fce88019c0235d632b4e7e0deb066b3344e371f029901f0726b87bbad/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a307a35437a6a7732704a77457071646a4d5a4a6563412e706e67" />

교차축(cross-axis) 양쪽 끝 지점을 포함한 모든 요소를 균등한 간격으로 배치하고 싶은 경우

- **align-content: space-evenly;**

```html
ul { align-content: space-evenly; }
```

<img src="https://camo.githubusercontent.com/77ae9c6fce88019c0235d632b4e7e0deb066b3344e371f029901f0726b87bbad/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a307a35437a6a7732704a77457071646a4d5a4a6563412e706e67" />

<img src="https://camo.githubusercontent.com/27a8a356e712b170aa50ece5962fdc5b60f9db3c8c8aa829d344fe4be43b520d/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a4f61374a64515743486c35564b5f74693552386434412e706e67" />

## Exercise

주축(main-axis)을 `column` 방식으로 변경해 다음 속성 연습해보기.

- justify-content
- align-items
- align-content

## Flexbox Part3

- **flex-grow**
- **flex-shrink**
- **flex-basis**
- **flex**

### flex-grow

`flex-grow`는 요소 증가비를 명시할 때 사용하는 속성입니다.

- 기본값: 0

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;
        display: flex;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        margin: 10px;
        padding: 10px;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
    </ul>
  </body>
</html>
```

<img src="https://camo.githubusercontent.com/2c80946fbc103b20c5decdf2f7c6e765653feee6d3a2790e00a95e3634f8d9ad/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a52336768437469325f477750336d6b6e7338717333512e706e67" />

`flex-grow`를 사용하지 않으면 본래 요소에 정의된 `width, padding, border`를 기준으로 기반해 크기가 설정됩니다.

```html
li:first-child { flex-grow: 1; }
```

첫번째 `li` 태그에 `flex-grow: 1;`값을 설정하면, 2 ~ 4번째 `li` 태그의 경우 기존에 정의된 가로 크기를 유지하고 있지만, 첫번째 `li` 태그는 `부모(Container)` 요소에 남은 공간 전체를 채우고 있는 것을 확인할 수 있습니다.

<img src="https://camo.githubusercontent.com/7ef713af631f74271997837068a209bc51e073e990b024b6f886acfcbf10b0c8/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a6173467849575672546c53515f5a4c47444c433262512e706e67" />

세번째 `li` 태그에 `flex-grow: 2`을 설정하면, `flex-grow: 0`으로 설정된 2번째, 세번째 요소를 제외하고, `flex-grow` 값이 1 이상 정의된 첫 번째 `li` 태그와 `1:2` 비율로 `부모(Container)` 요소에 남은 공간을 채우고 있는 것을 확인할 수 있습니다.

```html
li:nth-child(3) { flex-grow: 2 }
```

<img src="https://camo.githubusercontent.com/b7403f52d7bea683d2f1e13a2ffd9156bf9c968ef6cfad2edfdf91254d57f50a/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a6b6f436b5739475a4955424b7178595f5a646f3751772e706e67" />

`flex-grow` 속성은 `flex-grow` 값이 1 이상인 요소에 대해서만 동작하기 때문에 `flex-grow: 0`이 적용된 요소와는 큰 연관성이 없음을 주의해야 합니다.

### flex-shrink

`flex-shrink`는 요소 감소비를 명시할 때 사용하는 속성입니다. <br />
`flex-grow`는 기본값이 0인 반면에, `flex-shrink`는 기본값이 1입니다.

- 기본값: 1 (값이 0일 경우 아무런 감소가 발생하지 않습니다)
- `flex-shrink` 값에 비례해 감소폭이 늘어나는 방식으로 동작합니다.

Ex)

- **flex-shrink: 0;**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;
        display: flex;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        margin: 10px;
        padding: 10px;
        width: 300px;
      }

      li:first-child {
        flex-shrink: 0;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
    </ul>
  </body>
</html>
```

<img src="https://cdn-images-1.medium.com/max/800/1*lKwit9iagMWHF_JmglNUrw.png" />

컨테이너 폭이 줄어들었지만, 첫 번째 요소(flex-shrink: 0)의 크기는 감소비에 영향을 받지 않는 것을 확인할 수 있습니다.

### flex-basis

`Item`이 `Container` 내부에서 얼마의 공간을 차지할지를 보다 명시적으로 정의할 때 `flex-basis` 속성을 사용할 수 있습니다.

기본값: **flex-basis: auto;**

- `auto`로 설정된 경우 `flex-grow` and `flex-shrink` 값에 맞춰 크기가 결정됩니다.

어떠한 값도 정의하지 않는 경우 `flex-basis: auto;` 동작하는 데, 이는 `flex-grow` or `flex-shrink` 값에 맞춰 유연하게 주축의 길이가 설정됩니다.

`flex-basis`는 적어도 이 정도의 크기는 차지하되 고정됨을 의미하지는 않습니다. `flex-grow` 속성이 정의 되면 이에 맞춰 `flex-basis`에 정의한 크기보다 더 커지는 발생합니다.

`width` 속성과 차이점은, `flex-basis` 속성은 `Item`의 주축의 크기를 명시함으로, 주축에 따라 가로 혹은 세로가 될 수 있습니다.

`flex-grow` and `flex-shrink` 속성을 별도로 명시하지 않고 `flex-basis` 속성을 정의한 경우를 살펴보겠습니다.

Ex)

- Item #1 => 60%
- Item #2 => 30%
- Item #3 => 10%

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      .container {
        background-color: lightslategray;
        height: 100vh;
        display: flex;
        padding-top: 200px;
      }

      .item {
        width: 40px;
        height: 40px;
        border: 1px solid black;
        padding: 10px;
        background-color: #20b2aa;
        color: white;
      }

      .item1 {
        flex-basis: 60%;
      }

      .item2 {
        flex-basis: 30%;
      }

      .item3 {
        flex-basis: 10%;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="item item1">1</div>
      <div class="item item2">2</div>
      <div class="item item3">3</div>
    </div>
  </body>
</html>
```

결과를 확인해보면 비율에 맞게 `flex-grow` and `flex-shrink` 속성을 준 것처럼 동작하는 것을 확인할 수 있습니다.

<img src="https://cdn-images-1.medium.com/max/800/1*StfHOnuPm9zotgl-pjsI2A.png" />

`flex-basis` 속성을 요약하자면 `flex-grow` and `flex-shrink` 속성이 있는 경우 정의된 값보다 주축 크기가 커질 수 있지만, 두 속성을 명시하지 않은 상태에서는 작성된 크기에 맞춰 두 속성이 있는 것처럼 동작합니다. 또한 이 크기에 맞춰 `flex-wrap`이 발생합니다.

### flex

flex = **flex-grow flex-shrink flex-basis**

`flex` 속성은 `flex-grow`, `flex-shrink` and `flex-basis` 세 속성을 한 번에 작성할 수 있는 축약형입니다. 사용할 때 주의 사항은 `flex: 1;` 값으로 정의한 경우 `flex-basis` 속성은 `0px or 0%`로 간주하여 `flex-container` 내부 공간에 맞춰 크기가 설정됩니다. 이러한 상태를 `Absolute Flex Item` 칭합니다.

<img src="https://cdn-images-1.medium.com/max/800/1*t_8BQk0oZ2-bc31vwGsASw.png" />

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Document</title>
    <style>
      .container {
        background-color: lightslategray;
        height: 100vh;
        display: flex;
        padding-top: 200px;
      }

      .item {
        width: 40px;
        height: 40px;
        border: 1px solid black;
        padding: 10px;
        background-color: #20b2aa;
        color: white;
      }

      .item1 {
        flex: 1 1 auto;
      }

      .item2 {
        flex: 2 1 auto;
      }

      .item3 {
        flex: 1 1 auto;
      }
    </style>
  </head>
  <body>
    <div class="container">
      <div class="item item1">1</div>
      <div class="item item2">2</div>
      <div class="item item3">3</div>
    </div>
  </body>
</html>
```

## Flexbox Part4

- **order**
- **align-self**
- **gap**

### order

`Flexbox`로 정의된 `Container` 요소의 자식(Item)은 본래 정의된 순서대로 배치되게 됩니다. 저도 실제로 사용한 적은 거의 없지만, 어떠한 경우에 정의된 배치를 따르지 않고 임의로 그 순서를 바꾸고 싶은 경우 `order` 속성을 사용할 수 있습니다.

기본값: 0

`Item` 요소들은 모두 0의 기본값을 가지고 있기 때문에, `order` 값이 0보다 큰 경우, 요소에 부여된 `order` 보다 낮은 값을 가진 모든 요소 앞에 배치되게 됩니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      /* Flex Continer => Parent */
      ul {
        background-color: lightslategray;
        padding: 20px;
        display: flex;
        align-items: flex-start;
        flex-direction: column;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        margin: 10px;
        padding: 10px;
      }

      li:nth-child(3) {
        order: 1;
      }

      li:nth-child(1) {
        order: 3;
      }

      li:nth-child(6) {
        order: 2;
      }

      li:nth-child(5) {
        order: 5;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
      <li>5th Child</li>
      <li>6th Child</li>
      <li>7th Child</li>
      <li>8th Child</li>
    </ul>
  </body>
</html>
```

<img src="https://cdn-images-1.medium.com/max/800/1*meh8BOfdQGS7op3uhv7OVg.png" />

### align-self

교차축(cross-axis) 정렬할 때 자식 요소들 전체에 공통된 정렬 방식이 적용됩니다. 이러한 방식 대신 하나의 요소에만 특정 정렬 방식을 적용하고 싶은 경우 `align-self` 속성을 사용할 수 있습니다.

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      /* Flex Continer => Parent */
      ul {
        background-color: lightslategray;
        padding: 20px;
        height: 300px;
        display: flex;
        align-items: flex-end;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        margin: 10px;
        padding: 10px;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
      <li>5th Child</li>
      <li>6th Child</li>
      <li>7th Child</li>
      <li>8th Child</li>
    </ul>
  </body>
</html>
```

- **align-self: flex-end;**

```html
li:first-child { align-self: flex-end; }
```

<img src="https://camo.githubusercontent.com/70e3212f8942a582750ec9fe88d52f844f738fe2d79eed5dc1360d0e373aa91f/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a4e3249534c6f5951634151786f3169704e6c354345512e706e67" />

- **align-self: center;**

```html
li:first-child { align-self: center; }
```

<img src="https://camo.githubusercontent.com/61a6c56fd0ab64d062a340d7eb4b050d88303f521721229fb9ae8f5ef6553248/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a69447964684f68494934794d4572507045636e496f672e706e67" />

- **align-self: stretch;**

```html
li:first-child { align-self: stretch; }
```

<img src="https://camo.githubusercontent.com/66a1b2bf8c340c27f12034315da0654b69ab3f678761cf20bfeb83333e63dd0f/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a30797964397748674e6e3235726f6f587936796230672e706e67" />

- **align-self: baseline;**

```html
li:first-child { align-self: baseline; padding: 5px }
```

<img src="https://camo.githubusercontent.com/1a314642155fe98d90fc7a415d2a6bec8dafefb6332ada26639242bdc3c7ba88/68747470733a2f2f63646e2d696d616765732d312e6d656469756d2e636f6d2f6d61782f313030302f312a4e76713444545a414f716437514151557231756a68672e706e67" />

### gap

`Flexbox Container` 내부의 자식 요소(Items)가 일정한 간격으로 떨어져 위치하게 하고 싶을 때 `gap` 속성을 사용할 수 있습니다.

보통 요소 간의 간격을 구현하기 위해 `margin` 속성을 사용합니다. `gap` 속성은 `margin` 속성과 유사하게 동작하지만, 한 가지 차이점이 존재합니다.

`margin` 속성은 인접한 요소에 어떤 `display` 속성이 있는지 혹은 다른 요소가 존재하는지에 상관없이 공간을 만듭니다. 하지만 `gap`의 경우 인접한 요소가 없는 경우 불필요한 공간을 만들지 않습니다. 즉, 불필요한 공간을 만들지 않기 때문에 더욱 정렬된 상태의 레이아웃을 구현할 수 있도록 해줍니다.

- **gap: 값 (하나의 값만 적는 경우 요소의 상하 좌우에 해당 값이 적용됩니다)**
- **gap: 값 값 (두 개의 값을 적는 경우 첫 번째 값은 상하, 두 번째 값은 좌우에 적용됩니다)**

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <style>
      ul {
        background-color: lightslategray;
        padding: 20px;
        display: flex;
        width: 700px;
        align-items: flex-end;
        flex-wrap: wrap;
      }

      li {
        list-style: none;
        color: white;
        background-color: #20b2aa;
        padding: 10px;
        width: 180px;
        height: 180px;
      }
    </style>
  </head>
  <body>
    <ul>
      <li>1st Child</li>
      <li>2nd Child</li>
      <li>3rd Child</li>
      <li>4th Child</li>
      <li>5th Child</li>
      <li>6th Child</li>
      <li>7th Child</li>
      <li>8th Child</li>
      <li>9th Child</li>
    </ul>
  </body>
</html>
```

<img src="https://cdn-images-1.medium.com/max/800/1*a7L83RrN9z-E6Nb9Sb87LA.png" />

- **gap: 10px;** (상하좌우 10px 적용)

```html
ul { gap: 10px; }
```

<img src="https://cdn-images-1.medium.com/max/800/1*0jEsygQWj_Tb2ABuD7PpNQ.png" />

- gap: 20px 40px; (상하 20px, 좌우: 40px 적용)

```html
ul { gap: 20px 40px;}
```

<img src="https://cdn-images-1.medium.com/max/800/1*sxUDrWluEnbov5nOLDuvjA.png" />

## Flexbox Summary

```css
display: flex;
flex-direction: row | row-reverse | column | column-reverse;
justify-content: flex-start | center | flex-end | space-around | space-between | space-evenly;
align-items: flex-start | center | flex-end | stretch | baseline;
align-content: flex-start | center | flex-end | stretch | space-around | space-between | space-evenly;
flex-wrap: wrap | nowrap | wrap-reverse;
flex-flow: row wrap;
flex-grow: 1;
flex-shrink: 1;
flex-basis: 10%;
flex: 1 1 auto;
order: 1;
align-self: flex-start | center | flex-end | stretch | baseline
gap: 10px;
gap: 10px 20px;
```
