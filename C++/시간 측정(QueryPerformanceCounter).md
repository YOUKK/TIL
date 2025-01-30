# 시간 측정 방법

## QueryPerformanceCounter 란?
Windows API에서 제공하는 고해상도 타이머 함수로, 매우 정밀한 시간 측정이 가능하다. 일반적으로 GetTickCount나 timeGetTime보다 더 높은 해상도를 제공한다.

## 사용 방법
```c++
#include <windows.h>
#include <iostream>

int main() {
    LARGE_INTEGER frequency;  // 주파수 (초당 카운트 횟수)
    LARGE_INTEGER start, end; // 시작 및 종료 카운트 값
    double elapsedTime;       // 경과 시간(초)

    QueryPerformanceFrequency(&frequency); // 타이머 주파수 가져오기

    QueryPerformanceCounter(&start); // 시작 시간 측정

    // 측정할 코드 (예: 1초 대기)
    Sleep(1000); // 1000ms = 1초

    QueryPerformanceCounter(&end); // 종료 시간 측정

    // 경과 시간 계산 (초 단위)
    elapsedTime = static_cast<double>(end.QuadPart - start.QuadPart) / frequency.QuadPart;

    std::cout << "Elapsed time: " << elapsedTime << " seconds" << std::endl;

    return 0;
}

```