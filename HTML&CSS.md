# CSS

### margin과 padding이란?

-

<br/>

### position이란?

-

<br/>

### Box-model에서 width의 값을 차지하는 크기는?

-

<br/>

### Sass의 장점에 대해 설명해주세요.

- `변수 사용` : 색상, 폰트, 여백 등과 같은 스타일 속성을 변수로 정의하고 여러 곳에서 재사용 할 수 있습니다.

    ```javascript
    $jb-color: #fff;

    h1 {
      color: $jb-color;
    }
    ```

- `중첩된 규칙` : 중첩된 CSS 규칙을 지원하며, 코드의 가독성을 향상시키고 중첩된 요소를 간단하게 스타일링할 수 있도록 도와줍니다.

    ```javascript
    #gnb {
      background-color: #fff;
      width: 200px;
      ul {
        display: flex;
        color: #111;
      }
    }
    ```

- `연산 및 함수` : 수학 연산을 수행하거나 문자열 조작과 같은 다양한 함수를 제공하여 스타일을 동적으로 생성할 수 있습니다.

    - `연산`
    ```javascript
    div {
      $x: 100px;
      width: $x / 2;  /* 변수에 저장된 값을 나누기 */
      height: (100px / 2);  /* 괄호로 묶어서 나누기 */
      font-size: 10px + 12px / 3;  /* 더하기 연산과 같이 사용 */
    }
    ```

    - `함수`
    ```javascript
    /* 내가 정의한 함수 */
    @function extract-red($color) {
      /* 내장 함수 */
      @return rgb(red($color), 0, 0);
    }

    div {
      color: extract-red(#D55A93);
    }
    ```

- `mixin` : 스타일 속성의 그룹을 만들고 재사용할 수 있는 방법을 제공합니다. 

    ```javascript
    @mixin large-text { /* 선언 */
      font: {
        size: 22px;
        weight: bold;
        family: sans-serif;
    }
      color: orange;

      &::after {
        content: "!!";
      }

      span.icon {
        background: url("/images/icon.png");
      }
    }

    h1 {
      @include large-text; /* 사용 */
    }
    ```

- `모듈화` : 모듈화하고 여러 파일로 분할할 수 있게 해줍니다. 이를 통해 큰 프로젝트를 다룰 때 코드의 구성과 유지보수를 간편하게 만들어줍니다.

     ```javascript
    /* box.scss */
    $item-bg: #fff;
    $item-mg: 10px;

    /* style.scss */
    @import "box";
    .item {
      background-color: $item-bg;
      margin: $item-mg;
    }
    ```

<br/>
<details>
  <summary>Sass란 무엇인가요?</summary>

- CSS를 확장한 언어이며, CSS를 효율적으로 사용할 수 있도록 도와주는 도구입니다.

</details>

<br/>
<details>
  <summary>Sass의 단점에 대해 설명해주세요.</summary>

- `컴파일러 필요` : Sass 코드는 브라우저에서 직접 실행할 수 없으며, Sass 코드를 CSS로 변환하기 위한 컴파일러가 필요합니다.

- `복잡성 추가 가능` : 과도한 중첩 및 mixin 사용은 코드를 복잡하게 만들 수 있고, 유지보수를 어렵게 할 수 있습니다. 올바르게 사용하지 않으면 코드의 가독성을 떨어뜨릴 수 있습니다.

</details>

<br/>

### Reflow와 Repaint가 실행되는 시점

- Reflow, Repaint는 모두 웹페이지 랜더링 과정에서 랜더트리가 구축된 다음 발생하는 것으로 알고 있습니다.
이 두 프로세스는 웹 페이지의 구성 요소와 스타일 변경에 따라 발생하며 많은 비용을 발생시키기도 합니다.
리플로우와 리페인트를 발생시키는 요소는 여러 개가 있지만
주로 리플로우는 웹페이지의 레이아웃과 관련된 것들을 다시 계산하고 업데이트 하는 경우로  요소의 위치, 패딩, 마진 등이 변경되거나, 동적으로 레이아웃이 변경될 때, 뷰포트가 변경될 때 발생합니다.
리페인트는 웹 페이지의 레이아웃은 변경하지 않고 새로운 픽셀을 그려야 할 때 발생하며
요소의 배경색, 텍스트 색상, 테두리 등 그래픽 스타일 속성이 변경될 때. 요소가 가려져서 나타나거나 다시 그려질 때. 실행됩니다.
빈번한 리플로우와 리페인트는 브라우저 성능에 영향을 끼칠 수 있으므로 최적화가 필요합니다.
인라인 스타일을 자제하거나, 스트라이프 이미지를 사용하는 것, 자주 사용하는 속성은 캐싱처리하는 형태로 최적화를 하는 것으로 알고 있습니다.
- [Reflow, Repaint을 알아보자!](https://velog.io/@young_pallete/Reflow-Repaint%EC%9D%84-%EC%95%8C%EC%95%84%EB%B3%B4%EC%9E%90#%EC%B0%B8%EA%B3%A0%EC%9E%90%EB%A3%8C)

