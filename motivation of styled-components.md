## **Motivation**
[공식문서 바로가기](https://styled-components.com/docs/basics)



**styled-components is the result of wondering how we could enhance CSS for styling React component systems.** By focusing on a single use case we managed to optimize the experience for developers as well as the output for end users.
<br>**styled-components는 React component system의 스타일링을 위해 어떻게 하면 CSS를 강화할 수 있을까 고민하다 나온 결과물입니다.** 단일의 use case에 초점 맞춤으로써 실사용자를 위한 결과물 뿐만 아니라 개발자들을 위한 경험도 최적화하기 위해 관리했습니다. 

Apart from the improved experience for developers, styled-components provides:<br>
개발자들의 향상된 개발 환경 이외에도 styled-components는 다음과 같은 요소들을 제공합니다:

- **Automatic critical CSS**<br>
    styled-components keeps track of which components are rendered on a page and injects their styles and nothing else, fully automatically. Combined with code splitting, this means your users load the least amount of code necessary.
    <br>styled-components는 component가 render된 페이지를 추적하여 완전히 자동으로 해당 component에서 사용하는 스타일을 적용합니다. 즉, styled-components는 code splitting과 함께 결합하여, 사용자들이 필요로 하는 최소한의 코드만 로드할 수 있도록 합니다.

- **No class name bugs**<br>
      styled-components generates unique class names for your styles. You never have to worry about duplication, overlap or misspellings.<br>
      styled-components는 스타일들을 위한 unique한 class명을 만들어 냅니다. 더 이상 중복, 중첩, 스펠링 틀리는 문제를 걱정하지 않아도 됩니다.

- **Easier deletion of CSS**<br>
      it can be hard to know whether a class name is used somewhere in your codebase. styled-components makes it obvious, as every bit of styling is tied to a specific component. If the component is unused (which tooling can detect) and gets deleted, all its styles get deleted with it.
      <br>class 명이 코드 어디에선가 사용되었는지 아는 것은 힘들 수 있습니다. style-components를 사용하면 각각의 styling들을 특정한 component로 묶기 때문에 이 문제가 해결됩니다. 만약 어떤 component가 사용되지 않았고,(tooling으로 발견 가능) 삭제되었다면, 그 component의 styles는 같이 삭제됩니다.

- **Simple dynamic styling**<br>
        adapting the styling of a component based on its props or a global theme is simple and intuitive without having to manually manage dozens of classes.
        <br>props나 전역 theme을 기반으로 component의 styling을 적용하는 것이 수십 개의 class들을 일일히 관리할 필요 없이 직관적이고 간단해집니다.

- **Painless maintenance**<br>
        you never have to hunt across different files to find the styling affecting your component, so maintenance is a piece of cake no matter how big your codebase is.
        <br>더 이상 하나의 component에 영향을 미치는 styling을 찾기 위해 서로 다른 파일들을 찾아다닐 필요가 없기 때문에 코드가 얼마나 크든 상관 없이 유지보수는 식은 죽 먹기가 됩니다.

- **Automatic vendor prefixing**<br>
        write your CSS to the current standard and let styled-components handle the rest.
        <br>현재 기준에 맞춰 CSS를 쓰면 나머지는 모두 styled-components가 관리합니다.

You get all of these benefits while still writing the CSS you know and love, just bound to individual components.<br>
단지 독립적인 components들을 사용하면 여러분들이 잘 알고 사랑하는 CSS를 작성하면서도 이 모든 장점을 얻을 수 있습니다.
