# #define
#: 전처리 지시자 -> 컴파일 이전에 수행   
(c++ 컴파일 과정 : 전처리 -> 컴파일 -> 어셈블 -> 링크)   
매크로를 정의할 때 사용한다.

## 1. 매크로 상수
```c++
#define PI 3.14f
```
;을 작성할 경우 ;도 같이 치환된다.

## 2. 매크로 함수
```c++
// WinUser.h
#define PostMessage  PostMessageW

WINUSERAPI
BOOL
WINAPI
PostMessageW(
    _In_opt_ HWND hWnd,
    _In_ UINT Msg,
    _In_ WPARAM wParam,
    _In_ LPARAM lParam);
```
```c++
// main.cpp
#include <windows.h> // windows.h 안에는 #include <winuser.h>가 포함되어있음

if (ImGui::Button("Quit this app"))
{
    PostMessage(hWnd, WM_QUIT, 0, 0);
}
```

#### 일반 함수 호출
-> 함수가 위치한 호출 번지로 이동 -> Stack 영역 할당 및 매개 변수 복사   
-> 연산 -> 값 반환 및 Stack 영역 정리 -> 호출했던 위치로 복귀

#### 매크로 함수 호출
-> Stack 영역 할당 및 복사가 없다.   
-> 속도가 빠르다.   
-> 함수 호출을 위하 연산들이 필요 없어진다.

<br>

---
참고
* https://gyong0.tistory.com/127
* https://wikidocs.net/86263