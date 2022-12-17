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
            
-3.3 recap 
    
    
![ezgif com-gif-maker](https://user-images.githubusercontent.com/79883776/206655870-f385bc72-0a78-4ee9-baa9-408c4be96547.gif)



- 3.4 State Functions
    - set함수에는 함수를 넣을수도 있다.
    - 이 함수의 첫번째 argument는 ‘현재 값’이다.
    - 이 함수의 return 값이 새로운 state가 된다.
    
    ```jsx
    setCounter(count + 1) 보다
    setCounter(count => count + 1 )이 더 안전한 방법 이 count가 확실히 현재 값이라는 걸 보장하고 있기 때문에
    ```
<aside>
💡 ‘ 제발 숙지할 것 ‘

- javascript 함수 여러가지 방법으로 쓰기
    - arr.map((item) ⇒ <li>{item} </li>
    - arr.map((item) ⇒ {return <li>{item}</li>}
    - arr.map(function(item) ⇒ {return <li>{item}</li>}
    
</aside>

- 3.5 Inputs and State
    - <label> 태그 input에 연결해주기 위해 id를 알아야한다.
    - input value ⇒ uncontrolled value
- 3.6 State Practice 1
    - 코드 쓰기 minute ⇒ hours and reset button
- 3.7 State Practice 2
    
### #4 Props

- 4.0 Props
    - 부모 컴포넌트로부터 자식 컴포넌트에 데이터를 보낼 수 있게 해주는 방법
- 4.1 memo
    - 불필요한 re-renderd은 memo로 관리할 수 있다.
    - 컴포넌트가 memo()로 wrapping 될 때, react는 컴포넌트 렌더링하고 결과 Memoizing
- 4.2 Prop Types
    - 파라미터 오류가 있어도 확인 할 수없는 문제점
    - 이런 문제를 줄이기 위해 PropTypes 모듈 도움
- 4.3 recap

    //코드 영상 
    
### 5.CREATE REACT APP

- 5.0 Introduction

<img width="526" alt="스크린샷 2022-12-09 오후 2 09 38" src="https://user-images.githubusercontent.com/79883776/206628831-a6b4174c-390e-4e4a-b03e-4250f6731c37.png">


- 5.1 Tour of CRA
    - create-react-app의 작업 포인트 ⇒ 분할, 정복
    - crete-react-app은 무작위적인 랜덤 class를 갖는다.
    
### 6.Effects

- 6.0 Introduction
    - state가 변화 할 때 모든 component는 다시 실행
    - but 몇몇 코드는 처음 딱 한번만 실행되고 다시는 실행되지 않도록 하고 싶을 수 있다.
- 6.1 useEffect
    - useEffect(argumnet1, argurment2)
        - 첫번째는 한번만 실행될 함수
        - 두번째는 배열
- 6.2 Deps
    - useEffects의 배열에 [], 아무것도 있지 않는다면, 아무것도 지킬게 없다.
    - useEffects 배열에  [keyword]가 들어가 있으면 keyword가 있을때만 발동시킨다.
        - [keyword] ⇒처음 시작할때와,  keyword가 변화할 때 코드를 실행할거다.
        - [] ⇒  처음 한번만 실행
- 6.3 recap
    - 코드 영상찍어서
- 6.4 Cleanup
    - 컴포넌트를 Hide 할 때 컴포넌트가 스크린에서 지워짐, Show 할 때 다시 생성 되니까 useEffect도 다시 실행됨
    - 컴포넌트 destroy될 때 코드 실행 가능
        
        ```jsx
        function Hello() {
          useEffect(() => {
            console.log("i'm here")
            return function(){     //여기서 함수 불러주면서 
              console.log('Destroyed!')
            }
          }, []) //한 번 호출
          return(
            <h2>Hello</h2>
          )
        }
        ```
        
        
####7 PRACTICE MOVIE APP

        - 7.0 To Do List Part One
            - form 만들 때  page 가 refresh 되지 않도록 event.preventDefault 해준다.
        - 7.1 To Do List Part Two
            - todos를 보여줄 때 map 활용
            - <li> 태그
        - 7.2 Coin Tracker
            - API 가져오기
            - 한번만 보여주고 싶으니까 useEffect
            - 검사 - network에 tickers가 rending 됬나 확인. preview와 response로 확인
            - map 사용하면 react.js는 element에 key를 주도록 함.
![화면-기록-2022-12-11-오후-9 29 58](https://user-images.githubusercontent.com/79883776/206908112-2e00d4c2-8601-428b-a178-ff04f019e6bd.gif)



        - 7.3 Movie App part One
            - 
        - 7.4 Movie App part Two
            - 
        - 7.5 React Router
        
            - in terminal => yarn install react-router-dom
            
            - import {

                  BrowserRouter as Router,
                  Switch,
                  Route,
                  Routes,
                } from "react-router-dom"
                
                
           - <Switch> </Switch>는 ES5 문법
            
            - <Router>
                  <Routes>
                    <Route path = "/" element={<Home/>}/>
                    <Route path ="/movie" element ={<Detail/>}/>
                  </Routes>

                </Router>
                
            - Browser Router에서 URL은 우리가 예상하는 대로 생겼다.
            
            
            - 영화 제목을 클릭하면, 화면 전체가 재실행 되는걸 볼 수 있어
            
             이걸 방지하기 위해 Link라는 개념이 등장함 
            브라우저 새로고침이 없이도 유저를 다른 페이지로 이동시켜주는 컴포넌트다.
            
              <a href=""> 대신 Link를 쓰는이유는 브라우저 새로고침이 없이도 유저를 다른 페이지로 이동시켜주기 때문이다.
              

        - 7.6 Parameters
            - usecallback 사용하기!
        - 7.7 Publishing
            - npm i gh-pages
            - package.json을 가서 development }, 이 다음에 "homepage": https://                         mygithubname / gitgub.io 
        - 7.8 Conclusions
        - 7.9 Style




#### 1. INTRODUCTION
  
#### 2. STYLED COMPONENTS
     const 컴포넌트명 = styled.태그명
     ex) const Center = css`
            display :flex;
            justify-content:center;
            align-items: center;
            `;

          const Flex = div `
            ${flexCenter}
            `;

            - 스타일에 Props 적용
                장점 => 변수에 의해 스타일을 바꿀 수 있다.
                내부적으로 props 받기 가능하다, 그에 따라 스타일 변경가능
            - global Theme
            - Transient props
            
#### 3. TYPESCRIPT
    3.1 DefinitelyTyped
    
        - 내가 쓰고 있는 타입 바꾸기!
        
    3.2 Typing the Props
    
        - object 에게 type을 설명해주는 시간 필요
        - interface 안에다가 설명
            - interface 활용해서 Object 보호
    3.3 Option Props
    3.4 State
        - component를 업데이트 하고 싶다면 state도 바꿔야함
        - state를 바꾸면 React가 새로고침 하는 것도 알고 있다.
        - 기본적으로 default 값 생서하면 TypeScript => value 타입 설정
    3.5 Forms
    3.6 Themes
        - typescript + styled components 테마 연결하기
        - Create declare file
#### 4. REACT ROUTER

      4.1 BrowserRouter
          - react-router-dom
          - npm install react-router-dom
      4.2 createBrowserRouter
          - return (
      <BrowserRouter>
        <Switch>
          <Route path="/Name/*">
            <Name />
          </Route>
          <Route path="/">
          <Main />
          </Route>
        </Switch>
      </BrowserRouter>
    );
    
      4.3 errorElement
            const router = createBrowserRouter([
        {
          path: "/",
          element: <Root />,
          children: [
            {
              path: "",
              element: <Home />,
            },
            {
              path: "about",
              element: <About />,
            },
          ],
        },
      ]);
  
      4.4 useNavigate
      
        - navigate("../success",  { replace: true});
            첫번째 인자로 주소, 두번째 인자로 {reaplce,state}
        - useHistory의 기능도 포함
        
      4.5 useParams
      
          - import * as React from 'react';
  import { Routes, Route, useParams } from 'react-router-dom';

  function ProfilePage() {
    // Get the userId param from the URL.
    let { userId } = useParams();
    // ...
  }

  function App() {
    return (
      <Routes>
        <Route path="users">
          <Route path=":userId" element={<ProfilePage />} />
          <Route path="me" element={...} />
        </Route>
      </Routes>
    );
  }
    4.6 Outlet
    
        레이아웃 설정이 매우 간단
        {Outlet/}을 사용하면 {children}을 사용하는 것과 같은 효과
        
    4.7 useOutletContext
     
</code>

