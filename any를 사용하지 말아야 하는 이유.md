
# ❌```any```를 사용하지 말아야 하는 이유

## any
❌ **Don’t** use `any` as a type unless you are in the process of migrating a JavaScript project to TypeScript. The compiler *effectively* treats `any` as “please turn off type checking for this thing”. It is similar to putting an `@ts-ignore` comment around every usage of the variable. This can be very helpful when you are first migrating a JavaScript project to TypeScript as you can set the type for stuff you haven’t migrated yet as `any`, but in a full TypeScript project you are disabling type checking for any parts of your program that use it.

In cases where you don’t know what type you want to accept, or when you want to accept anything because you will be blindly passing it through without interacting with it, you can use [unknown](https://www.typescriptlang.org/play/#example/unknown-and-never).

## any
자바스크립트 프로젝트를 타입스크립트으로 옮기고 있지 않는 한 ```any```를 하나의 데이터 타입으로 사용하지 마세요. 
컴파일러는 ```any```를 **"이 변수에 대해서는 타입을 확인하지 말아주세요"** 와 같이 효율적으로 처리하기 때문입니다. 
```any```를 사용하는 것은 해당 변수의 모든 용법에 ```@ts-ignore```를 붙이는 것과 유사합니다. 
처음 자바스크립트 프로젝트를 타입스크립트로 옮길 때는, 아직 이동하지 않은 부분들(변수 등)의 타입을 ```any```로 설정할 수 있기 때문에 매우 도움이 되지만, 
타입스크립트로 시작하는 프로젝트에서 ```any```를 사용하면 프로그램 내부의 ```any```를 사용하는 부분들에 대해 type checking을 막아버리게 됩니다.

만약 당신이 어떤 타입을 받아들일지 모르겠는 경우이거나 아무거나 그것과의 상호작용 없이 무작정 전달받고 싶은 것이라면 당신은 ```unknown```을 사용할 수 있습니다.

<br></br>
[타입스크립트 공식문서 바로가기](https://www.typescriptlang.org/docs/handbook/declaration-files/do-s-and-don-ts.html#any)
