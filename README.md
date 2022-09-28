# react-toast
> React JS로 Toast Message 만들기

## 데모
[데모 보러가기](https://codesandbox.io/s/github/rieulp/react-toast-ui)
<p align="center"><img height="400" src="https://user-images.githubusercontent.com/38723811/192767472-25cb6782-36d0-4876-b2c4-86acbbf7f547.png"></p>

## Toast 기능
- 5가지 타입 : `default`, `info`, `success`, `error`, `warning` 5가지 타입 toast message를 제공함(타입별로 다른 색으로 나타냄)
- duration 기능 : 메세지를 호출할 때 **duration**값을 입력하면 입력된 시간(ms) 후에 메세지가 삭제됨
- link 기능 : 메세지를 호출할 때 **link**값을 입력하면 입력된 link로 이동하는 **learn more** 라는 하이퍼링크가 토스트 박스 하단에 추가됨
- 닫기 기능 : 토스트 박스 상단에 닫기 버튼을 추가해 토스트 박스를 삭제할 수 있게 함

## 사용방법
useToast에서 `{ toasts, register }`을 받아서 `Toaster`컴포넌트에 `toasts`를 props로 전달해 사용합니다.

메세지를 생성할 때 `register`함수를 사용합니다.

```javascript
import Toaster from "./components/Toast";
import useToast from "./components/Toast/core/useToast";

export default function App() {
    const { toasts, register } = useToast();
    
    const makeToast = ()  =>{
      // register(타입, 제목, 내용, 링크주소, 메세지 수명)
      register("default", "제목입니다", "토스트 내용", "https://github.com/rieulp", 3000);
    }
    
    return (
      <div className="App">
        {/* Toaster 컴포넌트에 toasts값 props로 전달 */}
        <Toaster toasts={toasts} />
        <button onClick={makeToast}>default 토스트 만들기</button>
      </div>
    );

```

## 개발 환경
- `Typescript`
- `React JS`

## 추가 라이브러리
- `@emotion/styled`
- `@emotion/react`
- `react-transision-group`

