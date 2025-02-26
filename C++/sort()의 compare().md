# sort()의 compare()
## 주의사항
1. compare()의 인자 두 값이 같을 때(혹은 우선순위가 같을 때) false를 반환해야한다! 두 인자가 같을 때 true를 반환하면 런타임 에러가 발생할 수 있음
2. compare()의 인자로 STL 혹은 클래스 객체를 전달시 reference를 사용한다! 값복사는 시간이 들기 때문에 reference를 전달해 빠르게 계산

<br>

---
참고   
https://blog.encrypted.gg/966