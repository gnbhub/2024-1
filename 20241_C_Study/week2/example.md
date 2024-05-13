아래 코드가 정답은 아닙니다.

각자의 방식대로 오류 나지 않고 출력만 잘 되면 정답!

### 1

- int Overflow 참조 : https://blog.naver.com/sharonichoya/220340284388

```c
#include <stdio.h>

int main(void) {
  int num, res, i;
  while (1){
    // 정수 입력받기
    printf("정수를 입력하세요 : ");
    scanf("%d", &num);

    // 입력받은 정수의 유효성 확인
    if (num <=0){
      printf("유효하지 않은 입력입니다. 1 이상의 정수를 입력해주세요.");
      continue;
    }

    // 팩토리얼 계산
    for (i=2, res=1; i<=num; i++){
      res *= i;
      if (res < 0) break;  // 오버플로우 발생 시 반복문 탈출
    }

    // 오버플로우 발생 시 발생 시점 출력
    if (res < 0){
      printf("오버플로우 발생! %d 이상 입력 시 오버플로우가 발생합니다.\n", i);
      // 아래 else문 사용 대신 여기에서 continue를 사용하여
      // 처음으로 돌아가도 무방
    }

    // 정상 : 팩토리얼 출력
    else{
      printf("%d! = %d\n", num, res);
      break;
    }
  }
  return 0;
}
```
![image](https://github.com/gnbhub/2024-1/assets/51956616/b218bc6b-9fcd-45d4-a78b-0ab85d076898)



### 2
** 저는 double형으로 풀이하였습니다!
```c
#include <stdio.h>

int main() {
  double num1, num2;
  char op;

  printf("연산식을 입력하세요: ");
  scanf("%lf %c %lf", &num1, &op, &num2);

  switch (op) {
  case '+':
    printf("%.2lf + %.2lf = %.2lf\n", num1, num2, num1 + num2);
    break;
  case '-':
    printf("%.2lf - %.2lf = %.2lf\n", num1, num2, num1 - num2);
    break;
  case '*':
    printf("%.2lf * %.2lf = %.2lf\n", num1, num2, num1 * num2);
    break;
  case '/':
    if (num2 != 0)
      printf("%.2lf / %.2lf = %.2lf\n", num1, num2, num1 / num2);
    else
      printf("0으로 나눌 수 없습니다.\n");
    break;
  default:
    printf("잘못된 연산자입니다. +, -, *, / 중 하나를 입력하세요.\n");
    continue;
  }

  return 0;
}
```
![image](https://github.com/gnbhub/2024-1/assets/51956616/491d5b7b-8863-4a87-87f4-37aa5cb535b3)


### 3

```c
#include <stdio.h>

int main() {
  int n;

  while (1) {
    printf("정수를 입력하세요: ");
    scanf("%d", &n);
    if (n < 0) {
      printf("음수는 입력할 수 없습니다.\n");
      continue;
    } else
      break;
  }

  for (int i = 1; i <= n; i++) {
    // 공백 출력
    for (int j = 1; j <= n - i; j++) {
      printf(" ");
    }
    // 별표 출력
    for (int k = 1; k <= i; k++) {
      printf("*");
    }
    printf("\n");
  }

  return 0;
}
```
![image](https://github.com/gnbhub/2024-1/assets/51956616/6c9b3b1b-bfce-489b-a48a-e05359c9e529)


### 4

```c
#include <stdio.h>

int main() {
  int H, M;
  scanf("%d %d", &H, &M);

  // 분을 먼저 처리
  M -= 45;

  // 분이 음수가 되었을 경우 시간에서 1을 빼고 60을 더해줌
  if (M < 0) {
    M += 60;
    H -= 1;
    // 시간이 음수가 되면 24를 더해주어야 함
    if (H < 0)
      H += 24;
  }

  printf("%d %d\n", H, M);

  return 0;
}
```
![image](https://github.com/gnbhub/2024-1/assets/51956616/8b282542-b1c3-4de4-97fc-a1ddfcfea859)
