# 순열 구하기
* nPr
* #include \<algorithm>
* next_permutation 사용

## next_permutation
* 오름차순 -> 내림차순으로 정렬하는 함수
* 그러므로 수열은 사전에 오름차순으로 정렬되어있어야 한다

```c++
// 3개의 수 중 2개를 뽑아 순열 구하기
#include <iostream>
#include <vector>
#include <algorithm>

int main()
{
    std::vector<int> vec{ 1,2,3 };

    do
    {
        for (int i = 0; i < 2; i++)
        {
            std::cout << vec[i] << ' ';
        }
        std::cout << '\n';
    } while (std::next_permutation(vec.begin(), vec.end()));
}
```

# 조합 구하기
* nCr
* #include <algorithm>
* prev_permutation 사용

## prev_permutation
* 내림차순 -> 오름차순으로 정렬하는 함수
* 전체 0으로 된 n개 배열에서 앞의 r개를 1로 채운다
* ex) 3C2라면 {1,1,0}

```c++
// 3개 중 2개를 뽑아 조합 구하기
#include <iostream>
#include <vector>
#include <algorithm>

int main()
{
	std::vector<int> vec{ 1,2,3 };

	std::vector<int> sortVec(vec.size(), 0);
	std::fill(sortVec.begin(), sortVec.begin() + 2, 1);

	do
	{
		for (int i = 0; i < 3; i++)
		{
			if (sortVec[i] == 1)
				std::cout << vec[i] << ' ';
		}
		std::cout << '\n';
	} while (std::prev_permutation(sortVec.begin(), sortVec.end()));
}
```
<br>

---
참고
* https://mjmjmj98.tistory.com/38 - 사용법 정리 글
* https://charles098.tistory.com/8 - 함수 원리 설명 글