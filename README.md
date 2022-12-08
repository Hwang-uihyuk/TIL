# TIL
공부한 것들을 기록합니다
<code>
### #2 THE BASIC OF REACT

- react의 기초
- 어려운 방식. ( 이렇게 쓰는 일은 다시는 없을 것) - 한 번 이해하고 넘어가기

const span = React.createElement(”span”)

- ReactDOM.render()
    - render는 html코드를 사용자에게 보여준다.
    - 이제 ReactDOM 에게 span을 어디에 둘 것인지 알려줘야 한다.
    - 일반적으로는 body 부분에 <div id=”root”></div>를 생성해서 그곳에 둔다.
        - 그러기 위에서 선언해주고 const root = document.getElementById(”root”);
        - ReactDOM.render(span, root)
            - render는 사용자에게 span 코드를 보여주는건데 어디다가보여주냐(ReactDOM) ⇒ root에
- react의 강점
    - js에서는 html을 먼저 만들고 그걸, js로 가져와서  만든다.
    - react에서는 js로 시작해서 만들고 그 다음이 html이 된다.

render는 html 코드를 사용자에게 보여준다.

- 위에 것들을 대체 할 것이 JSX다.

- arrow function
    - function button(){return()}
    - const button = () ⇒ ()
- Babel
    - javascript compiler 이고 jsx문법을 javascript언어로 변경해주어 보여준다.

### #3 State

- 3.0 Understanding State
    - 숫자 count 해줄 때  counter = counter + 1 을 해주면 숫자가 증가하지 않는데 그 이유는
    - count는 올라가지만, render된 시점에서는 이미 count가 0이고, 다시 ui를 render시켜주지 않았기 때문에 계속 0이다.
    - 변수 사용하려면 {}
    - update ui → render
- 3.1 setState  1
    - const food = [”tomato” , “potato”]
        - const counter = food[0]
        - const potato = food[1]  ⇒ 별로
        - const [firstFood, secFood] = food;
            - firstFood ⇒ tomamto, secFood ⇒ potato
- 3.2 setState 2
    - set함수는 rerendering 해줌
    - 컴포넌트에서 return(  )
        - return () 괄호안이 사용자가 보게될 컴포넌트
            
            [화면 기록 2022-12-09 오전 1.54.39.mov](https://s3-us-west-2.amazonaws.com/secure.notion-static.com/fb653b26-61a2-462d-9c5b-137942aa2399/%E1%84%92%E1%85%AA%E1%84%86%E1%85%A7%E1%86%AB_%E1%84%80%E1%85%B5%E1%84%85%E1%85%A9%E1%86%A8_2022-12-09_%E1%84%8B%E1%85%A9%E1%84%8C%E1%85%A5%E1%86%AB_1.54.39.mov)
            
        - 

### #4 Props


</code>
