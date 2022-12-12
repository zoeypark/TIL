# SPA (Single Page Application) 
새로운 페이지로 이동할 때마다 리소스가 다운로드 받아져서 전체 페이지가 새로 렌더링되는 MPA와는 달리<br>
SPA는 웹앱에 필요한 모든 리소스를 처음에 한번 다운로드 받아, 처음에 표시된 페이지에서 벗어나지 않고<br>
경로를 다르게 하여 각기 다른 경로에 따라 다른 화면을 보여준다.<br>

# React Router 
## How to use
    1. react-router-dom 설치 명령어
    npm install react-router-dom@^<버전넘버>
    2. Routing을 할 컴포넌트 파일 내부에서 라우팅 컴포넌트 import 해오기
    import { BrowserRouter, Routes, Route, Link } from "react-router-dom";
    3. BrowserRouter 컴포넌트를 가장 상위에 위치 시킨다.
    4. Routes 컴포넌트는 Route 컴포넌트들을 감싸주면 된다.
    5. Route 의 path와 element 속성을 부여하여 라우팅을 해준다.
    path는 경로, element는 경로를 통해 보여줄 페이지 컴포넌트이다.

```
function App () {
        return (
        <BrowserRouter>
            <div>
                <nav>
                <ul>
                    <li>
                    Home
                    </li>
                    <li>
                    MyPage
                    </li>
                    <li>
                    Dashboard
                    </li>
                </ul>
                </nav>

            {/* 주소 경로와 아까 만든 3개의 컴포넌트를 연결해 줍니다. */}
            {/* Routes 컴포넌트는 Route 컴포넌트들을 감싸고 있어야 합니다. */}
                <Routes>
                {/* 경로는 path로 컴포넌트는 element로 연결해 줍니다. */}
                <Route path="/" element={<Home />} /> 
                <Route path="/mypage" element={<MyPage />} /> 
                <Route path="/dashboard" element={<Dashboard />} />
                </Routes>
            </div>
        </BrowserRouter>
        )
    }

    export default App;
```
