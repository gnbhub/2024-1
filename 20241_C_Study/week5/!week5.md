# ✏ Week 5
- Topics : 포인터
- context : 강의자료 10
- Homework : 아래 과제를 수행하고 풀이 코드를 출력 화면 캡쳐와 함께 **2024-1/20241_C_Study/week5/(자기이름).md** 파일로 업로드

  
## Homeworks
### 1️⃣ 포인터 연산과 역참조

* 다음 소스 코드를 완성하여 55와 22가 각 줄에 출력되게 만드세요.

```c
#include <stdio.h>

int main()
{
    int numArr[5] = { 11, 22, 33, 44, 55 };
    int *numPtrA;
    void *ptr;

    numPtrA = &numArr[2];
    ptr = numArr;

    printf("%d\n", ①        numPtrA           );
    printf("%d\n", ②           ptr             );

    return 0;
}
```


### 2️⃣ 예제 10-8 포인터를 이용하여 배열을 함수 인자로 전달하기

* 강의자료 ppt 예제 10-8을 실습하여 포인터를 이용해 배열을 함수 인자로 사용하는 방법을 알아봅니다.

