# [Redux Motivation](https://redux.js.org/understanding/thinking-in-redux/motivation)

  As the requirements for JavaScript single-page applications have become increasingly complicated, **our code must manage more state than ever before**. This state can include server responses and cached data, as well as locally created data that has not yet been persisted to the server. UI state is also increasing in complexity, as we need to manage active routes, selected tabs, spinners, pagination controls, and so on.

 자바스크립트 SPA에 대한 요구사항들이 점점 복잡해짐에 따라 **우리의 코드는 전 보다 많은 state(상태)를 관리해야만 합니다.** 이 state는 서버 응답들과 캐시된 데이터, 그리고 local에서 생성되어 아직 서버에 연결되지 않은 데이터들도 포함할 수 있습니다. UI state도 마찬가지로 점점 복잡해지기 때문에 active routes, selected tabs, spinners, pagination controls 등등도 관리해야 합니다.
 
 </br>
 
  Managing this ever-changing state is hard. If a model can update another model, then a view can update a model, which updates another model, and this, in turn, might cause another view to update. At some point, you no longer understand what happens in your app as you have **lost control over the when, why, and how of its state.** When a system is opaque and non-deterministic, it's hard to reproduce bugs or add new features.

  변화무쌍한 state를 관리하는 것은 어렵습니다. 만약 하나의 모델이 다른 모델을 update할 수 있다면, 어떤 view는 다른 모델을 update한 그 모델을 update할 수 있고, 그러면 이 view는 결국 다른 view의 update를 불러일으킬지도 모릅니다. 어느 순간 당신은 더 이상 당신의 app에서 어떤 일이 일어나고 있는지 이해할 수 없을 겁니다. **app 내의 state의 어떻게, 언제, 왜에 대한 컨트롤을 놓쳤기 때문입니다.** 시스템이 불투명해지고, 비결정적이게 되면, 버그를 고치거나 새로운 기능들을 추가하기에는 어려워집니다.
 
 </br>
 
 As if this weren't bad enough, consider the **new requirements becoming common in front-end product development**. As developers, we are expected to handle optimistic updates, server-side rendering, fetching data before performing route transitions, and so on. We find ourselves trying to manage a complexity that we have never had to deal with before, and we inevitably ask the question: [is it time to give up?](https://www.quirksmode.org/blog/archives/2015/07/stop_pushing_th.html) The answer is *no*.

 이것이 최악이 아닌 것처럼, **프론트엔드 개발에서 새로운 요구사항들이 점점 당연해진다고 고려해보십시오.** 개발자로서 우리는 낙관적인 update들, 서버 사이드 렌더링, 루트 이행하기 전에 데이터를 fetch하는 것등을 다루도록 기대받습니다. 우리는 전에는 한번도 다뤄본 적 없는 complexity를 처리하려고 노력하는 우리 자신을 발견하고, 예상한대로 '포기해야할 시간일까'라는 질문을 던집니다. 이 질문에 대답은 *no*입니다.
 
 </br>
 
 This complexity is difficult to handle as **we're mixing two concepts** that are very hard for the human mind to reason about: **mutation and asynchronicity.** I call them [Mentos and Coke](https://en.wikipedia.org/wiki/Diet_Coke_and_Mentos_eruption). Both can be great in separation, but together they create a mess. Libraries like [React](https://facebook.github.io/react) attempt to solve this problem in the view layer by removing both asynchrony and direct DOM manipulation. However, managing the state of your data is left up to you. This is where Redux enters.

 이 complexity는 사람이 추론하기에는 너무 어려운 **mutation과 asynchronicity**이라는 **두 가지의 개념이 섞인 것**이라서 다루기 어렵습니다. 나는 이것들을 Mentos와 Coke라고 부릅니다. 둘 다 분리되어 있을 땐 좋을 수 있지만, 함께 사용하면 난장판을 만듭니다. React와 같은 라이브러리들은 asynchrony(비동시성)와 직접 DOM을 조작하는것을 없애서 이 문제를 view layer에서 해결하려고 시도했습니다. 하지만 당신의 데이터의 state를 다루는 것은 당신에게 달려있습니다. 이 부분에서 바로 Redux가 등장합니다.
 
 </br>
 
 Following in the steps of [Flux](https://facebook.github.io/flux), [CQRS](https://martinfowler.com/bliki/CQRS.html), and [Event Sourcing](https://martinfowler.com/eaaDev/EventSourcing.html), **Redux attempts to make state mutations predictable** by imposing certain restrictions on how and when updates can happen. These restrictions are reflected in the [three principles](https://redux.js.org/understanding/thinking-in-redux/three-principles) of Redux.

Flux, CQRS 그리고 Event Sourcing의 단계를 따라서 Redux는 언제 그리고 어떻게 update들이 발생할 수 있는 지에 대한 특정 규제들을 도입함으로써 state 변화들을 예측가능하도록 만들려고 시도하였습니다. 이러한 규제들은 'Redux의 세가지 규칙'에서 확인하실 수 있습니다.

</br>

### 자잘자잘 용어사전

- non-deterministic(비결정적): 같은 입력을 넣어도 경우에 따라 다른 결과가 나오는 기계나 프로그램의 성질.
