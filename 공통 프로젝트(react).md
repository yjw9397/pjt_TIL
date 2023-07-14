# 공통 프로젝트

## React

- Git
    - 브랜치 생성
        
        `git branch [브랜치명]`
        
    - 생성한 브랜치로 이동
        
        `git switch [브랜치명]`
        
    - 브랜치 생성 후 이동
        
        `git switch -c [브랜치명]`
        
    - 원격 브랜치와 같은 이름으로 로컬 브랜치를 생성 후 스위치
        
        `git switch -t orogin/[원격브랜치명]`
        
    - 브랜치 삭제
        
        `git branch -d [브랜치명]`
        
        - 브랜치 강제 삭제
            
            `git branch -D [브랜치명]`
            
        - 원격 브랜치 삭제
            
            `git push origin --delete [브랜치명]`
            
    - push
        - 처음 push 할 때
            
            `git push --set-upstream origin [브랜치명]` 
            
    - 원격 브랜치 가져올 때
        
        `git remote update`
        
- password field 사용하기
    - `$ npm install password-field --save`
    - `import PasswordField from 'password-field'`
- axios
    - `npm install axios` or `yarn **add** axios`
    - **`import** axios **from** 'axios'`
    
    ![Untitled](%E1%84%80%E1%85%A9%E1%86%BC%E1%84%90%E1%85%A9%E1%86%BC%20%E1%84%91%E1%85%B3%E1%84%85%E1%85%A9%E1%84%8C%E1%85%A6%E1%86%A8%E1%84%90%E1%85%B3%20cc1115aae78c4d1bbd5d3a713914d270/Untitled.png)
    
- useCallback
    - `useCallback(function, deps)`
    - 첫 번째 인자로 넘어온 함수를 두 번째 인자로 넘어온 배열 형태의 함수 실행 조건의 값이 변경될 때까지 저장해놓고 재사용할 수 있게 해줌
    - 리액트 컴포넌트 안에 함수가 선언되어있을 때 이 함수는 해당 컴포넌트가 렌더링 될 때마다 새로운 함수가 생성되는데, useCallback을 사용하면 해당 컴포넌트가 렌더링 되더라도 그 함수가 의존하는 값(deps)들이 바뀌지 않는 한 기존 함수를 재사용할 수 있음
    - `const ****add = () => x + y;`
        
        → `const ****add = useCallback(() => x + y, [x, y]);`
        
    
    ```jsx
    
    ```
    
- useInput
    - input을 업데이트
    - args로 initialValue를 받고, initialValue를 초기값으로 갖는 useState를 작서
- useNavigate
    
    ```jsx
    const navigate = useNavigate()
    
    navigate("/login")
    
    // 함수 내에는 사용X
    // return에 넣으면 
    ```
    
    - 함수 내에서 사용X (따로 정의하여 사용해야 함)
        
        ```jsx
        function goNotice() {
        	usenavigate("/notice")
        }
        // -> 오류
        ```
        
    - return 안에 넣으면 함수 실행 조건이 발생 안 하더라도 실행됨
        
        `onClick={navigate(”/notice”)}` → 화면 랜더링 되자마자 실행됨
        
        ```jsx
        function goNotice() {
        	navigate(”/notice”)
        }
        
        //////
        return (
        <button onClick={goNotice}></button>
        )
        ```
        
- useEffect
    - `useEffect(함수, [의존값](deps))`
    - 컴포넌트가 처음 마운트 될 때 **&** deps에 있는 값들이 바뀔 때 호출
    - deps가 비어있는 경우
        - 컴포넌트가 처음 나타날 때만 useEffect에 등록한 함수가 호출됨
        - 컴포넌트가 사라질 때 cleanup함수 호출
            - cleanup 함수 → useEffect에 대한 뒷정리를 해주는 함수
    - deps를 생략한 경우
        - 컴포넌트가 리랜더링 될 때마다 호출
- filter
    
    배열.filter(data ⇒ 조건)
    
    `const privateRoom = list.((room) ⇒ room.private === true)` → private이 true인 방만
    
- 시간 표현법
    
    ```jsx
    // 보통 - "2023-02-02T10:00:37Z" 이런 형태
    const orgin = "2023-02-02T10:00:37Z"
    const cut = origin.substr(0, 10) // 0~10번째 문자열만 cut
    const result = moment(cut, "YYYY-MM-DD").format("YYYY.MM.DD")
    // -> 2023.02.02
    
    const result = moment(cut, "YYYY-MM-DD").add(5, days').format("YYYY.MM.DD")
    // -> 2023.02.07
    ```
    
- display
    - `display: flex` → div 안에 있는 요소들이 옆으로 배치됨
        
        → `flex-flow: wrap`으로 하니 줄 바꿈됨
        
        - 초기값: nowrap, wrap-reverse하면 순서가 역방향
        - flex-flow는 flex-direction과 flex-wrap를 합쳐 지정하는 단축 속성
            
            `flex-direction: row;` + `flex-wrap: wrap;`
            
            `→ flex-flow: row wrap;` 
            
    - 다시 해보니 wrap으로해도 줄 바꿈이 안됨
        - `width:100%`로 하여 해결함
- pagination
    - [https://mui.com/material-ui/api/pagination/](https://mui.com/material-ui/api/pagination/)
    - mui 설치 후 `import { Pagination } from "@mui/material";`  `<Pagination />`
    - props → count={총 페이지 수} onChange={페이지내이션안의 버튼을 클릭했을 때 실행되는 함수}
- array.slice()
    
    ```jsx
    배열.slice(a, b) // 배열 index a부터 b-1까지의 값을 복사하여 반환
    
    A = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    
    A.slice(5, 10)  //배열 index 5~9
    -> [6, 7, 8, 9, 10]
    
    A.slice(3) // 배열 index 3부터 끝까지
    -> [4, 5, 6, 7, 8, 9, 10]
    ```
    
- array.splice()
    
    ```jsx
    배열.splice(a, b, *c) // 배열 index a부터 b개의 값을 삭제, c값을 추가 후 삭제한 값들을 반환
    
    A = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
    
    A.splice(5, 3)  //배열 index 5부터 3개의 값을 삭제
    -> [6, 7, 8]
    A               // 원 배열에서 삭제 됨
    -> [1, 2, 3, 4, 5, 9, 10]
    
    A.splice(3, 1, -1, -2) // 배열 index 3부터 1개의 값을 삭제 후 -1, -2 추가
    -> [4]
    A
    -> [1, 2, 3, -1, -2, 5, 9, 10]
    ```
    
- textarea → pre 태그
    - input태그 수직 정렬 안됨(가운데정렬으로 되어있음) → textare태그를 쓰면 해결됨
    - textarea 사용 후 출력하면 줄 바꿈이 반영 안됨
        - 출력 부분 태그를 pre 태그로 바꿔주면 해결됨
        - 출력할 때도 textarea로 출력
        - `content = content.replaceAll("\n", "<br/>")`
            - 시도해봤으나 줄바꿈 부분에 <br/>이라는 문자 그대로 출력됨
        - `style={{white-space: ”pre”}}`
            - **normal** : HTML의 기본 값입니다. 여러개의 공백은 하나로 표시되고, \n은 무시되며 긴 행은 필요시에 Wrap 됩니다.
            - **nowrap** : normal과 같은데 긴행이 wrap 되지 않습니다. 글을 포함한 컨테이너를 넘어서 표시됩니다.
            - **pre** : 여러개의 공백과 개행문자가 모두 표현됩니다. <pre> 태그와 같이 동작합니다. 긴 행은 개행문자에서만 개행이 되고, wrap 되지 않습니다.
            - **pre-line** : 여러개의 공백은 하나로 표시되고, 긴 행은 필요시 wrap 됩니다. 개행문자를 만나도 개행됩니다.
            - **pre-wrap** : 여러개의 공백과 개행문자가 모두 보존됩니다. 개행문자외 에서도 필요시 wrap 됩니다.
- margin-inline → x축, margin-block → y축
- align-content, align-items
    - flex-wrap 속성을 통해 items가 여러 줄이고 여백이 있을 경우만 사용
    - items가 한 줄인 경우 align-items 속성을 사용
- 정렬
    
    ```jsx
    const array = [50, 4, 130]
    array.sort()
    -> [130, 4, 50] // 첫번째 자리수를 기준으로 정렬됨
    
    array.sort((a, b) ⇒ a - b)
    -> [4, 50, 130] // 내림차순은 ((a, b) ⇒ b - a)
    ```
    
- ?, &&
    - `조건 ? A : B` → 조건이 true일 때 A, false일 때 B
    - `조건 && A` → 조건이 true일 때 A, false 일 때는 무시(반환하는 경우 0 반환)
- 라디오버튼
    - input name을 동일하게 주어야 하나만 선택되게 할 수 있음
- 콤보박스(select)
    
    ```jsx
    <select>  // select 태그에 disabled를 쓰면 콤보박스 비활성화(사용자가 값을 변경X), option에도 줄 수 있음
    	<option value="none">선택</option>  // value를 none으로 줌
    	<option value="1" selected>1</option> //selected를 쓰면 기본값으로 지정됨
    	<option value="2" hidden>2</option>  // hidden을 쓰면 안 보임(disabled는 보이긴 함)
    	<option value="3">3</option>
    </select>
    
    // select style에 appearance: "none" 하면 오른쪽 화살표 안 보임
    ```
    
- 조건부 CSS 적용
    - 인라인
        - `<div style={조건 ? {스타일: “1”} : {스타일: “2”}}></div>`
        - `<div style={{스타일: 조건 ? “1” : “2” }}></div>`
    - 클래스 적용
        - `<div className={`클래스이름 ${조건 ? “1” : “2”}`}></div>`
- background 적용할 때 빈틈없이 채우려면 margin 대신 padding을 줘서 조절하면 됨
- include(), some()
    - include()는 primitive type 확인, some()은 그 외의 타입을 확인하는데 적절
        - `array.includes(value)`
        - `array.some(callback(element))`
            - `array.some((element) => element.id === target.id)`
            - `array.some(외부함수)`
    - include()는 값을 비교할 때 ‘===’ 연산자를 사용하는데, object의 값이 같은지가 아니라 같은 객체를 가리키고 있는지를 비교
    
    ```jsx
    const obj1 = {name: 'apple'};
    const obj2 = {name: 'apple'};
    const obj3 = obj1;
    
    obj1 === obj2
    -> false
    obj1 === obj3
    -> true
    ```
    
- useLocation(), QueryString
    - params 말고 url에 있는 값 받아오는 법
    - `https://localhost:3000/user/password?userEmail=ykm9397@naver.com&passwordCodeContent=2950a4`
        
        ```jsx
        import {useLocation} from 'react-router';
        
        const location = useLocation()
        console.log(location)
        -> {hash: ""
        	key: "default"
        	pathname: "/user/password"   // 라우터에 있는 경로
        	search: "?userEmail=ykm9397@naver.com&passwordCodeContent=2950a4"
        	state: null}
        ```
        
    - ? 이후의 string만 가져오기 위해서 qs 라이브러리 사용 → `yarn add qs`
        
        ```jsx
        import {useLocation} from 'react-router';
        import QueryString from 'qs';
        
        const queryData = QueryString.parse(useLocation().search, { ignoreQueryPrefix: true });
        console.log(queryData)
        -> {passwordCodeContent: "2950a4"
        	userEmail: "ykm9397@naver.com"}
        ```
        
- 숫자화 Number()
- github - db.json 파일로 axios test
    - [https://my-json-server.typicode.com/](https://my-json-server.typicode.com/)
- grid
    - display: grid, grid-template-columns: repeat(2, 1fr) → 가로로 2개씩 배치됨(div전체가 가로로 2등분)
- import한 CSS 파일에 있는 스타일만 적용
    - css파일명 → 모둘명.module.css
    
    ```jsx
    import styles from "./Room.module.css";
    
    <div className={styles.클래스명}></div>
    // or
    <div className={styles['클래스명']></div>
    // 클래스명이 변수인 경우 {style[변수]}로 적용 가능
    
    // 클래스명이 2개 이상일 때
    <div className={`${styles.클래스명1} ${styles.클래스명2}`}>
    <div className={`${styles['클래스명1'] ${styles['클래스명2']`}>
    ```
    
- boolean값으로 변경
    - Boolean()
        - () 안의 값이 null, false, 0, ‘’ 등이 아니면 true값 반환
        - Boolean(’true’) → true
        - Boolean(’false’) → true
    - JSON.parse() (’TRUE’, ‘FALSE’는 안됨)
        - JSON.parse(’true’) → true
        - JSON.parse(’false’) → false
- form control
    - [https://swoo1226.tistory.com/230](https://swoo1226.tistory.com/230)
    - checkbox [https://moderncss.dev/pure-css-custom-checkbox-style/](https://moderncss.dev/pure-css-custom-checkbox-style/)
- 키보드 이벤트(keypress 이벤트 지원X)
    - onKeyUp → 키에서 손을 떼면 이벤트 발생
    - onKeyDown → 키를 누르면 이벤트 발생
    - 엔터키 누르면 검색
        - `onKeyDown={(e) => e.key === "Enter" && goSearch()}`
- 스크롤
    
    ```jsx
    body::-webkit-scrollbar {
      width: 15px;  /* 스크롤바의 너비 */
    }
    
    /* 움직이는 바 관련 */
    body::-webkit-scrollbar-thumb { 
    	background-color: #d6ebfc;
      border-radius: 10px;
    }
    
    /*스크롤바 뒷 배경 색상*/
    body::-webkit-scrollbar-track {
        background-color: rgba(214, 235, 252, 0.3);
    		border-radius: 0 10px 10px 0;
    }
    ```
    
- map
    
    [https://devbirdfeet.tistory.com/184](https://devbirdfeet.tistory.com/184)
    
- 새로고침 로그인
    
    [https://backend-intro.vlpt.us/6/06.html](https://backend-intro.vlpt.us/6/06.html)
    
    [https://chuun92.tistory.com/30](https://chuun92.tistory.com/30)
    

[[React] MySQL, redux 를 이용하여 게시판 만들기 - 떽떽대는 개발공부](https://ddeck.tistory.com/31)

[Route와 Context API를 사용해서 로그인, 회원가입, 마이페이지 만들기](https://velog.io/@annie1004619/Route%EC%99%80-Context-API%EB%A5%BC-%EC%82%AC%EC%9A%A9%ED%95%B4%EC%84%9C-%EB%A1%9C%EA%B7%B8%EC%9D%B8-%ED%9A%8C%EC%9B%90%EA%B0%80%EC%9E%85-%EB%A7%88%EC%9D%B4%ED%8E%98%EC%9D%B4%EC%A7%80-%EB%A7%8C%EB%93%A4%EA%B8%B0)

`yarn add redux-persist`