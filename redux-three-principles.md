# [Three Principles 세 가지 규칙](https://redux.js.org/understanding/thinking-in-redux/three-principles)

Redux can be described in three fundamental principles: </br>
리덕스는 세 가지의 핵심적인 규칙으로 설명할 수 있습니다: 

</br>

### Single source of truth[#](https://redux.js.org/understanding/thinking-in-redux/three-principles#single-source-of-truth)

**The [global state](https://redux.js.org/understanding/thinking-in-redux/glossary#state) of your application is stored in an object tree within a single [store](https://redux.js.org/understanding/thinking-in-redux/glossary#store).**

This makes it easy to create universal apps, as the state from your server can be serialized and hydrated into the client with no extra coding effort. A single state tree also makes it easier to debug or inspect an application; it also enables you to persist your app's state in development, for a faster development cycle. Some functionality which has been traditionally difficult to implement - Undo/Redo, for example - can suddenly become trivial to implement, if all of your state is stored in a single tree.


### Single source of truth[#](https://redux.js.org/understanding/thinking-in-redux/three-principles#single-source-of-truth)

**당신 앱의 global state는 object tree 내의 단일 store에 저장됩니다.**

이 규칙은 당신의 서버로부터 받은 state가 _직렬화_ 되고, 추가적으로 코드를 작성하는 노력 없이 client로 흡수될 수 있게 함으로써 _universal app_ 을 쉽게 생성할 수 있도록 만듭니다. 또한 하나의 state tree는 앱을 디버깅하거나 점검하기에 쉽게 만들어줍니다. 더불어 더 빠른 개발 주기를 위해 당신이 계속해서 당신의 앱의 state를 개발하는 것을 가능하도록 합니다.  만약 모든 state가 단일 tree안에 저장되어 있으면, Undo/Redo와 같이 전통적으로 구현하기에 어려웠던 몇몇의 기능들은 더 이상 구현하는데 어렵지 않은 사소한 문제가 될 수 있습니다.

</br>

### State is read-only[#](https://redux.js.org/understanding/thinking-in-redux/three-principles#state-is-read-only)

**The only way to change the state is to emit an [action](https://redux.js.org/understanding/thinking-in-redux/glossary), an object describing what happened.**

This ensures that neither the views nor the network callbacks will ever write directly to the state. Instead, they express an intent to transform the state. Because all changes are centralized and happen one by one in a strict order, there are no subtle race conditions to watch out for. As actions are just plain objects, they can be logged, serialized, stored, and later replayed for debugging or testing purposes.


### State는 읽기 전용입니다.

**state를 바꿀 수 있는 유일한 방법은 어떤 일이 일어나는 지 묘사해주는 객체인 action을 만들어 내는 것입니다.**

이 규칙으로 인해 view도 network callback도 절대 state에 직접적으로 작성할 수 없습니다. 대신에 view나 network callback은 state를 변형시키겠다는 목적을 표현합니다. 모든 변경들은 중앙으로 모여있고, 엄격한 순서 아래 하나씩 실행되기 때문에 더 이상 조심해야 하는 감지하기 힘든 _경쟁 상태_ (race conditions)는 없습니다. action은 단지 순수한 객체이기 때문에 기록될 수 있고, 직렬화될 수 있고, 저장될 수 있으며 나중에 디버깅이나 테스팅 목적으로 다시 실행될 수 도 있습니다.

</br>

### Changes are made with pure functions[#](https://redux.js.org/understanding/thinking-in-redux/three-principles#changes-are-made-with-pure-functions)

**To specify how the state tree is transformed by actions, you write pure [reducers](https://redux.js.org/understanding/thinking-in-redux/glossary#reducer).**

Reducers are just pure functions that take the previous state and an action, and return the next state. Remember to return new state objects, instead of mutating the previous state. You can start with a single reducer, and as your app grows, split it off into smaller reducers that manage specific parts of the state tree. Because reducers are just functions, you can control the order in which they are called, pass additional data, or even make reusable reducers for common tasks such as pagination.

That's it! Now you know what Redux is all about.


### Change들은 _순수함수_ 로 만들어집니다.[#](https://redux.js.org/understanding/thinking-in-redux/three-principles#changes-are-made-with-pure-functions)

**state tree가 action들로 어떻게 변경되는지 구체화하기 위해서는 순수한 reducer들을 작성해야 합니다.**

Reducer들은 단지 지난 state와 action을 가지고 다음 state를 반환하는 순수 함수들입니다. 지난 state를 변형시키는 대신에 새로운 state 객체들을 반환한다는 점을 기억해주세요. 당신은 단일 reducer로 시작하여 어플리케이션이 성장하면 그 reducer를 state tree의 세부적인 부분들을 관리하는 더 작은 reducer들로 분리할 수 있습니다. reducer들은 단순 함수들이기 때문에 언제 함수가 호출되고, 부가적인 데이터를 넘기고, 페이지네이션과 같이 공통적인 task를 위해 재사용가능한 reducer를 만들어 낼지 명령을 제어할 수 있습니다. 

이게 다입니다! 이제 당신은 Redux에 대한 모든 것을 알게 되었습니다.

</br>

## 깨알 용어 사전

- Universal app : 하나의 프로젝트에서 개발한, 데스크톱, 모바일, 태블릿 등 모든 기기와 운영체제를 아우르는 서비스 또는 앱을 의미합니다. 한 번 개발하면 화면 크기에 따라 UI가 자동으로 변하고, 디스플레이 크기와 기기에 따른 파편화된 사용자 경험을 합칠 수 있다는 장점이 있습니다. [출처](https://www.itworld.co.kr/news/95019)
- 직렬화: 직렬화란 객체를 바이트 스트림으로 바꾸는 것, 즉 객체에 저장된 데이터를 스트림에 쓰기write 위해 연속적인serial 데이터로 변환하는 것입니다. 직렬화의 주된 목적은 객체를 상태 그대로 저장하고 필요할 때 다시 생성하여 사용하는 것입니다. [출처](https://medium.com/@lunay0ung/basics-%EC%A7%81%EB%A0%AC%ED%99%94-serialization-%EB%9E%80-feat-java-2f3eb11e9a8)
- 경쟁 상태(Race Condition): 둘 이상의 입력 또는 조작의 타이밍이나 순서 등이 결과값에 영향을 줄 수 있는 상태. 전산학에서 경쟁 상태란 공유 자원에 대해 여러 개의 프로세스가 동시에 접근을 시도할 때 접근의 타이밍이나 순서 등이 결과값에 영향을 줄 수 있는 상태를 말하기도 한다. [출처](https://ko.wikipedia.org/wiki/%EA%B2%BD%EC%9F%81_%EC%83%81%ED%83%9C)
- 순수함수(Pure Function) : 부수효과가 없는 함수로, 어떤 함수에 동일한 인자가 주어졌을 때, 외부의 상태를 변경시키지 않고 항상 같은 값을 반환(return)하는 함수 [출처](https://jeong-pro.tistory.com/23)
