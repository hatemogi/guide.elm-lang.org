<!--
# An Introduction to Elm
-->

# Elm 소개

<!--
**Elm is a functional language that compiles to JavaScript.** It helps you make websites and web apps. It has a strong emphasis on simplicity and quality tooling.
-->

**Elm은 자바스크립트로 컴파일되는 함수형 언어입니다.** Elm은 웹사이트와 웹 앱을 만드는데 유용합니다. Elm은 그 간결함과 강력한 도구에 강점이 있습니다.

<!--
This guide will:

  - Teach you the fundamentals of programming in Elm.
  - Show you how to make interactive apps with **The Elm Architecture**.
  - Emphasize principles and patterns that generalize to programming in any language.
-->

이 가이드는:

  - Elm 프로그래밍의 기초를 알려드립니다.
  - **Elm 아키텍처**로 앱을 만드는 법을 보여드립니다.
  - 어떤 언어로든지 유용할 원칙과 패턴을 강조합니다.

<!--
By the end I hope you will not only be able to create great web apps in Elm, but also understand the core ideas and patterns that make Elm nice to use.
-->

이 가이드를 다 읽고 나면, Elm으로 훌륭한 웹앱을 만들 수 있게 될 뿐만 아니라, Elm이 유용하게끔 해주는 핵심 아이디어와 패턴들을 이해하시게 될 겁니다.


<!--
If you are on the fence, I can safely guarantee that if you give Elm a shot and actually make a project in it, you will end up writing better JavaScript code. The ideas transfer pretty easily!
-->

앞으로 Elm을 쓰지 않으실 분들도, Elm을 한번 써서 실제 프로젝트를 진행해보면 더 나은 자바스크립트 코드를 작성하게 될 거라고 장담합니다. 아이디어 자체는 쉽게 쓸 수 있어요!


<!--
## A Quick Sample
-->
## 예제 먼저

<!--
Here is a little program that lets you increment and decrement a number:
-->
여기에 숫자를 올리거나 내리는 간단한 프로그램이 있습니다.

```elm
import Browser
import Html exposing (Html, button, div, text)
import Html.Events exposing (onClick)

main =
  Browser.sandbox { init = 0, update = update, view = view }

type Msg = Increment | Decrement

update msg model =
  case msg of
    Increment ->
      model + 1

    Decrement ->
      model - 1

view model =
  div []
    [ button [ onClick Decrement ] [ text "-" ]
    , div [] [ text (String.fromInt model) ]
    , button [ onClick Increment ] [ text "+" ]
    ]
```

<!--
Try it out in the online editor [here](https://elm-lang.org/examples/buttons).
-->
[여기](https://elm-lang.org/examples/buttons)에서 온라인 에디터로 직접 해보세요.


<!--
The code can definitely look unfamiliar at first, so we will get into how this example works soon!
-->
이 코드는 당연히 처음에는 낯설겠지만, 어떻게 동작하는 건지 곧 설명해드릴게요!

<!--
## Why a functional *language*?
-->
## 왜 함수형 *언어*인가?

<!--
You can get some benefits from programming in a functional *style*, but there are some things you can only get from a functional *language* like Elm:
-->
함수형 스타일로 프로그래밍하면 약간의 잇점이 있겠지만, Elm같은 함수형 *언어*로만 얻을 수 있는 장점들이 있습니다:

<!--
  - No runtime errors in practice.
  - Friendly error messages.
  - Reliable refactoring.
  - Automatically enforced semantic versioning for all Elm packages.
-->
  - 런타임 에러가 발생하지 않습니다.
  - 에러 메시지가 친절합니다.
  - 리팩토링을 하기에 든든합니다.
  - 모든 Elm 패키지기가 유의미 버전을 씁니다.

<!--
No combination of JS libraries can give you all of these guarantees. They come from the design of the language itself! And thanks to these guarantees, it is quite common for Elm programmers to say they never felt so **confident** while programming. Confident to add features quickly. Confident to refactor thousands of lines. But without the background anxiety that you missed something important!
-->
좋은 JS 라이브러리를 여러개 가져다 쓴다 하더라도 이 모든 걸 누릴 수는 없습니다. 이런 건 언어 자체의 디자인으로부터 얻을 수 있는 강점입니다! 이런 장점들 덕분에, 이제껏 개발하면서 이렇게 *자신감*이 넘쳤던 적은 없다고 말하는 Elm 프로그래머가 꽤 많습니다. 새 기능을 빨리 추가하기에 자신있습니다. 코드 수천 라인을 리팩토링하기에도 자신있습니다. 게다가 무언가 중요한 걸 빠뜨렸을지 모른다는 불안감 없이도 말이죠!

<!--
I have put a huge emphasis on making Elm easy to learn and use, so all I ask is that you give Elm a shot and see what you think. I hope you will be pleasantly surprised!
-->
Elm을 만들 때 배워서 쓰기 쉽도록 공을 들였습니다. Elm을 한번 써보세요. 즐거운 놀라움을 느끼시길 바랍니다.
