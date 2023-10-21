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
