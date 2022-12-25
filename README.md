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

    # CRYPTO TRACKER

### 5.0set up

복습

- router 사용
    - yarn install react-router-dom
    - 
    
    ```jsx
    <BrowserRouter>
    	<Routes>
    		<Route path="/" element =''/></Routes>
    	</Routes>
    </BrowserRouter>
    ```
    
    - useParams
        
        ```jsx
        1번 : const {coinId} = useParams<coinId : string>
        
        2번 : interface 사용하기
        
        interface parmas
        {
        	coinId : string
        }
        
        const {coinId} = useParamas<params>
        ```
        

### 5.1 styles

- Source Sans Pro 폰트
    
    @import
    
    url('https://fonts.googleapis.com/css2?family=Source+Sans+Pro:wght
    
    @300
    
    ;400&display=swap');
    
    font-family: 'Source Sans Pro', sans-serif;
    
- createGlobalStyle
    - 전역 스타일을 처리하는 특수 Styled Component

### 5.2 Home Part One

- JSON Viewer (JSON 데이터 가독성 좋게 보기)
    
    https://chrome.google.com/webstore/detail/json-viewer/gbmdgpbipfallnflgajpaliibnhdgobh?hl=ko
    

### 5.3 Home Part Two

- https://api.coinpaprika.com/v1/coins

### 5.4 Route States

- Es6
    - < Link to="/home" state={state} / >
- Es5
    - < Link to={{ pathname: "/home", state: state }} / >

### 5.5 Coin Data

### 5.6 Data Types

VSCode 단축키

Ctrl(Command)+D: 같은 문자열 선택

Shift+Alt(Option)+i: 선택한 모든 문자열에 가장 우측 끝으로 포커싱

Ctrl(Command)+Shift+오른쪽 화살표: 현재 선택한 문자열을 기준으로 우측 끝까지 문자열 선택

### 5.7. Nested Routes Part One

- outlet (중첩 라우트 사용하기)
    - 자식 라우트 사용하기

### 5.8. Nested Routes Part Two

- useRouteMatch() ⇒ useMatch()
    - 현재 위치를 기준 지정된 경로에 대한 일치 데이터를 반환한다.

### 5.9 React Query Part One

- 

간단한 axios 로 사용법 데이터 가져오기

export const fetchCoins = async() =>{

// 데이터 얻는법

// axios.get(url).then(res => console.log(res.data))

return await axios.get("https://api.coinpaprika.com/v1/coins").then(res => res.data);

}

기존 axios 인스톨 해줘야함

### 5.10 React Query Part Two

- React Query Devtools
    - import { ReactQueryDevtools } from 'react-query/devtools';
    - < ReactQueryDevtools initialIsOpen={false} / >

  

### 5.11 Recap

- recap!

### 5.12 Price Chart part One

- context ⇒ prop전달
    - 상위 컴포넌트에서 Outlet 컴포넌트에 context에 prop를 전달한다.
    
    useOutletContext() 훅이용 props를 받아온다.
    

### 5.13 Price Chart part Two

- 오류
    
    data: data?.map((price) => Number(price.close)) as number[],
    
     ⇒ Number() 감싸기
    

### 5.14 Three

- Apex Charts Fill
    - https://apexcharts.com/docs/options/fill/
- Flat UI Color
    - https://flatuicolors.com
- UTC형태의 값
    - 
    
    ```jsx
    categories: chartData?.map((price) =>
    new Date(price.time_close * 1000).toISOString()
    ),
    ```
    

### 5.15 Final Touch

- react helmet = > react-helmet-async

### 6.0 Dark Mode part one

- Recoil
    - state management library

### 6.1 Dark Mode part two

- useState
    - 컴포넌트 local State

### 6.2 Introduction to Recoil

- RecoilRoot

```jsx
atom({
key: "저장할 state",
default:"state의 기본 상태"
});
```

### 6.3 Introduction to Recoil part two

- useRecoilValue(state)
    - Recoil state return
- useSetRecoilState(state)
    - value → update → setter return
    - 비동기로 사용 → setter return

### 6.4 Recap

### 6.5 To Do Setup

```jsx
npx create-react-app react-todo-app --template typescript
```

### 6.6 Forms

- useForm
    - register
        - name, onBlur, onChange, onClick, ref를 return
    - watch
        - form의 입력값들의 변화를 관찰할 수 있게 해주는 함수

### 6.7 Form Validation

```jsx
handleSubmit: ((data: Object, e?: Event) => void, (errors: Object, e?: Event) => void) => Function
```

### 6.8 Forms Errors

```jsx
/^[A-Za-z0-9._%+-]+@naver.com$/

^ :문장의 시작
[] : 문자셋 안의 아무문자
+ : 하나 또는 많이
```

### 6.9 Custom Validation

```jsx
validate : { (value) => !value.includes("nico") || "error message"}
```

### 6.10 Recap

### 6.11 Add To Do

- useRecoilValue(state)
    - Recoil state return
- useSetRecoilState(state)
    - value → update → setter return
    - 비동기로 사용 → setter return

### 6.12 Refactoring

- Divide!
- Conquer!

### 6.13 Categories

- 단축평가
    - 논리 연산의 결과를 결정하는 피 연산자를 타입 변환하지 않고 그대로 반환

### 6.14 Immutability part One

- Array.prototype.findIndex()
    - array 첫 번째 요소에 대한 인덱스 반환
    - 없을시 -1 반환
    - 인덱스 대신 반환 find()

### 6.15 Immutability part Two

- 다시 듣기 잘 안됨….
- another way 참고 할것 댓글

```jsx
Another way.
setTodos((prevTodos) => {
const targetIndex = prevTodos.findIndex((todo) => todo.id === id);
const newTodo: ITodo = {
id,
text,
category: categoryState as ITodo["category"],
};
const newTodos = [...prevTodos]; // create new array
newTodos.splice(targetIndex, 1, newTodo);
return newTodos;
});
```

### 6.16 Selectors part One

- Selectors
    - 파생된 state 일부를 나타냄
    
    ```jsx
    const filteredTodoListState = selector({
    key: 'filteredTodoListState',
    get: ({get}) => {
    const filter = get(todoListFilterState);
    const list = get(todoListState);
    
    switch (filter) {
    case 'Show Completed':
    return list.filter((item) => item.isComplete);
    case 'Show Uncompleted':
    return list.filter((item) => !item.isComplete);
    default:
    return list;
    }
    },
    });
    ```
    

### 6.17 Selectors part Two

- onInput
    - 클릭하자마자 동작
- onChange
    - 포커스를 잃었을때 동작

### 6.18 Enums

- Enums

```jsx
숫자 열거형 (Numeric enums)
enum Direction {
Up = 1,
Down,
Left,
Right,
}

문자열 열거형 (String enums)
enum Direction {
Up = "UP",
Down = "DOWN",
Left = "LEFT",
Right = "RIGHT",
}
```

### 6.19 Recap

### 7.0 Get Selectors

- selecotrs

```jsx
const proxySelector = selector({
key: 'ProxySelector',
get: ({get}) => ({...get(myAtom), extraField: 'hi'}),
set: ({set}, newValue) => set(myAtom, newValue),
});
```

### 7.1 Set Selectors

- get
    - 다른 atom selector로부터 값을 찾는데 사용되는 함수
- set
    - 업스트림 Recoil 상태의 값을 설정할 때 사용되는 함수

### 7.2 Drag and Drop part One

```jsx
react-beautiful-dnd
React로 list를 만들기 위한 아름답고 접근 가능한 드래그 앤 드롭
npm i react-beautiful-dnd
npm i --save-dev @types/react-beautiful-dnd

https://www.npmjs.com/package/react-beautiful-dnd
https://github.com/atlassian/react-beautiful-dnd/blob/master/docs/about/installation.md

react-beautiful-dnd 테스트해 보기
https://react-beautiful-dnd.netlify.app/iframe.html?id=board--simple

react-beautiful-dnd 예시 코드
https://codesandbox.io/s/k260nyxq9v

DragDropContext
https://github.com/LeeHyungGeun/react-beautiful-dnd-kr
```

### 7.3 Drag and Drop part Two

- dragHandleProps
    - 특정 영역을 통해서만 드래그를 가능하게 할 때

### 7.4 Styles and Placeholders

- provided.placeholder (?ReactElement)

### 7.5 Reordering

- result
- result.draggableId
- result.type
- result.source
- result.destination

### 7.6 Reordering part Two

- key
    - list내에서 키값안주면 오류
    - list 내에서 고유해야한다.
    - draggabledId를 key사용하면 된다.

### 7.7 performance

- React.memo
    - 결과를 메모이징하도록 래핑한다.
        - 즉 성능향상

### 7.8 MultiBoards

- Object.keys()
    - 객체의 속성 이름들을 일반적인 반복문과 동일한 순서로 순회되는 열거할 수 있는 배열로 반환

### 7.9 Same Board Movement

- DropResult
    
    ```jsx
    DropResult
    draggableId: 드래그 되었던 Draggable의 id
    type: 드래그 되었던 Draggable의 type
    source: Draggable이 시작된 위치
    destination: Draggable이 끝난 위치
    ```
    

### 7.10 Cross Board Movement

오류..

### 7.11 Droppable Snapshot

- snapshot
    
    ```jsx
    isDraggingOver: boolean
    현재 선택한 Draggable이 특정 Droppable위에 드래깅 되고 있는지 여부 확인
    
    draggingOverWith: ?DraggableId
    Droppable 위로 드래그하는 Draggable ID
    
    draggingFromThisWith: ?DraggableId
    현재 Droppable에서 벗어난 드래깅되고 있는 Draggable ID
    
    isUsingPlaceholder: boolean
    placeholder가 사용되고 있는지 여부
    ```
    

### 7.12 Final Styles

- Flatuicolors
    - https://flatuicolors.com/palette/us

### 7.13 Refs

- useRef()
    - current 프로퍼티로 전달된 인자로 초기화된 변경 가능한 ref 객체 반환
    - ref 속성 < useRef() 쓰자

### 7.14 Task Objects

- React Hook Form

### 7.15 Creating Tasks

- todo 객체 한번에 뽑아낼려고 하면 안된다.
- 따로 값들을 꺼내야함

### 7.16 Code Challenge

오류
