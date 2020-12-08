# 난수

- 난수란 무작위의 수를 뜻한다. 이 난수 함수를 이용해 무작위의 값을 받아 결과를 출력한다.

1. rand();

- rand() 함수는 <stdlib.h> 에 포함되어 있는 함수로 난수를 만들어 내는 함수이다.

* rand() 함수에 의해 생성되는 난수 : 0 ~ 32767

```
#include <stdio.h>
#include <stdlib.h>

int main()
{
	int randombox = 0;

	srand(time(NULL)); 

	for(i = 0; i <10; i++)
		{
			randombox = rand() % 10; // 1~9 까지의 무작위 숫자
			printf("%d\n", randombox); // 그 무작위 숫자를 출력 
		}
	}

```
위와 같이 1 ~9 까지의 무작위 숫자를 받아 출력 할 수 있다.

그러나 아쉽게도 이 rand() 으로는 완벽한 난수를 만들수 없다 왜냐하면 일정한 패턴이 있고 바뀌지 않는다.

만약 그 패턴을 바꾸고 싶다면 srand() 함수를 rand() 함수와 같이 사용하면 문제가 해결된다.

2. srand();

- 이 함수는 rand() 라는 함수의 무작위 시드값을 주기위한 함수이다 그리고 그 srand(); 의 매개변수로 절대로 일치할수 없는 숫자를 부여하면 난수가 완성된다.

그렇다면 다신 일치 할 수 없는 수란 무엇인가? 바로 시간이다. 지금 그 순간은 한번 지나가면 다시 돌아오지 않는것을 이용해 srand(); 의 매개변수로 time();을 부여 할 것이다.

* time 은 <time.h> 를 추가해주어야 한다.

```
#include <stdio.h>
#include <stdlib.h>
#include <time.h>

int main()
{
	int randombox = 0;

	srand(time(NULL)); 

	for(i = 0; i <10; i++)
		{
			randombox = rand() % 10; // 1~9 까지의 무작위 숫자
			printf("%d\n", randombox); // 그 무작위 숫자를 출력 
		}
	}


```

위 예문을 보면 srand() 에 time(null) 이라는 매개변수를 부여한다. time(null)은 1970년 1월 1일 이후 경과된 시간을 초 단위로 반환한다.

1초전과 지금은 다르기 때문에 계속해서 무작위 값의 난수를 입력해 줄 수 있다.

## 참고 
[열코의 프로그래밍 일기](https://yeolco.tistory.com/)