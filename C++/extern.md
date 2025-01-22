# extern
다른 cpp 파일에 있는 전역 변수, 전역 함수를 사용할 때 쓰는 키워드이다.

#### 전역 변수 예시
```c++
// fileA.cpp
int i = 42;
```
```c++
// fileB.cpp
extern int i; // 해당 cpp파일에서 i 사용 가능
```
```c++
// fileC.cpp
std::cout << i; // 에러.
```
```c++
// fileD.cpp
int i = 43; // 에러. LNK2005! 'i' already has a definition.
```

#### 전역 함수 예시
```c++
// imgui_impl_win32.cpp
IMGUI_IMPL_API LRESULT ImGui_ImplWin32_WndProcHandler(HWND hwnd, UINT msg, WPARAM wParam, LPARAM lParam)
{
    // Most backends don't have silent checks like this one, but we need it because WndProc are called early in CreateWindow().
    // We silently allow both context or just only backend data to be nullptr.
    if (ImGui::GetCurrentContext() == nullptr)
        return 0;
    return ImGui_ImplWin32_WndProcHandlerEx(hwnd, msg, wParam, lParam, ImGui::GetIO());
}
```
```c++
// main.cpp
extern LRESULT ImGui_ImplWin32_WndProcHandler(HWND hwnd, UINT msg, WPARAM wParam, LPARAM lParam);
```

<br>

---
참고 : https://learn.microsoft.com/ko-kr/cpp/cpp/extern-cpp?view=msvc-170