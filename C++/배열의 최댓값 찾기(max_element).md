# 배열의 최댓값 찾기(max_element)
```c++
int arr[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};

int idx = std::max_element(arr, arr+10) - arr; // 최댓값의 인덱스
int num = *std::max_element(arr, arr+10); // 최댓값
```
max_element()는 최댓값의 포인터를 반환한다.