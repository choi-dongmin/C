# 제어문

## 반복문 

- 포함된 코드를 조건만큼 반복할 수 있도록 하는 제어문

- loop 의 종류
	1. for
	2. while 
	3. do while 

## for

- 특정 횟수만큼 반복해서 처리 할 때 유용

```
* for 반복문의 형식 

for (초기식; 조건식; 증감식)
	반복할 코드 ;

for(i=1; i<=100; i++)
	printf("%d", i);	
``` 
- for 문은 초기에 초기식을 설정을 받고(i=1) 조건식에 만족하는 동안 반복하고(i>=100) 소속된 코드가 한번 실행이 되면 증감식에 따라 값을 변경한다(i++) 그리고 다시 조건식에 부합하는지 확인하고 부합할때 계속 반복한다.

알고리즘 형식으로 표현한다면
```
-> 1. |초기식| -> 2. <조건식> -> 3. 참 : |반복할 문장| -> 4. |증감식| -> 2. <조건식> 
					 	    ->  5. 거짓 : |for의 다음 문장|
```

```
# include <stdio.h>

main()
{
	int x;
	int sum = 0 ;

	for(x=1; x <= 100; x++)
	{
		sum += x;
	}
	printf("1 부터 100 의 합은 %d 입니다.", sum);
}
```

반복해서 나타내 줄 수 있는 계산하여 1~10 까지의 합과 곱을 구하는 코드를 만들어 보자
```
# include <stdio.h>

main()
{
	int x;
	int sum = 0, factorial = 1 ;

	for(x = 1; x <= 10; x++)
	{

		sum += i;
		factorial *= i;
		printf("1 부터 10 의 합은 %d 입니다.", sum);
		printf("1 부터 10 의 곱은 %d 입니다.", factorial);

	}

```

### 중첩 for 

우리는 for 문을 사용하는 법을 배웠다 그러나 만약 for 안쪽에 다시 한번 for 를 넣는다면 더 효율적일 것이다.

이때 사용하는 방법이 바로 for의 중첩이다.

```
 1 	2  3  4  5
 6 	7  8  9 10
11 12 13 14 15

```

위와 같은 결과값을 원할때 어떻게 할 수 있을까? 위의 숫자는 3행 5열의 구성을 가지고 있고 5의 배수 마다 칸을 넘기고 있다.

우리는 위와 같은 결과값을 이루기 위해 다음과 같이 할 수 있다.

```
# include <stdio.h>

main()
{
	int x,y,z;
	z = 1; 
	
	for(x = 1; x <= 3; x++)
	{
		for(y = 1; y <= 5; y++)
		{
			printf(%4d,z++)
		}
		printf("\n");
	}
}
}	
``` 

위를 보면 x 는 행을 구성하며 y 는 열을 의미하고 그 안쪽에서 z 를 통해 값을 입력하고 5의 배수가 되면 가장 안쪽의 for 문을 나오고 칸을 넘기고 다시 x 가 2 되면서 for 문이 다시 시작한다. 

## while 

- 조건식이 '참' 일 경우에만 진행
```
int i = 0;
while (i <= 10);
{
	printf("%3d", i);
	i++
}
```

*for 문과 While 이 다른점은 증감자를 따로 지정해주어야 하고 사용할 변수를 외부에서 초기화를 해줘야한다는 점이다.


- while 이용한 무한 루프

```
int num = 0, i;
while (1)
{
	printf("정수를 입력하세요");
	scanf("%d", &num);
	for(i = 0; i <10; i++)
	{
		printf("%d * %d = %2d\n",num,i,num* i )
	}
	printf("\n")
}

C언어에서 참은 1 거짓은 2 이다.
```

만약 탈출(break)를 하고 싶으면 보통 지정받은 입력값에 조건문을 주어 사용한다.

```
int num = 0, i;
while (1)
{
	printf("정수를 입력하세요");
	scanf("%d", &num);
	if(num == 0)
	{
		break;
	}eles
		{
		for(i = 0; i <10; i++)
		{
			printf("%d * %d = %2d\n",num,i,num* i )
		}
		printf("\n")
	}
}
C언어에서 참은 1 거짓은 2 이다.
```

위처럼 만약 입력받은 num 의 값이 0 이라면 while 을 넘어간다.

## do while

do while 문을 설명하기 전에 앞서 형식을 보자.
```
int i = 0;
do 
{
	printf("%d", ++i);
}while(i <= 10);
```

do while 문은 보이는 바와 같이 절차지향에 따라 우선 do 안쪽의 문장을 실행을 하고 그다음 while 의 조건식이 참,거짓인가 판단하고 반복한다.

정리를 하자면 for 와 while 은 조건식을 검사한 후 참인 경우 반복을 하고 do while 문은 문장을 실핸한 후 조건식을 확인하여 반복할지 결정한다.

## 분기문

- 문장의 실행 순서를 바꾸는 제어문

break, continue, goto,return

1. break

문장이 실행되다 break 를 만나게 되면 해당 문장을 빠져나가게 된다.

2. continue

반복문이 실행되다 continue 를 만나면 반복의 시작점으로 되돌아 간다.

```
for (i = 0; i < 10; i++)
{
	if(i % 2 == 0)
	{
		continue ;
	}
	else
	{
		printf("%3d", i);

	}
}

결과값 : 1 3 5 6 7 9
```
*do while 일때는 반복문의 시작 while 로 간다.


3. goto

- 프로그램이 실행되는 도중 특정 위치로 이동하게 하려면 goto 를 사용하면 된다.
- 레이블을 정의할때는 구별하기 위한 콜론(:)이 필요하다
```
for(i = 1; i <= 10; i++)
{
	if(i % 2 == 0)
	goto aaa;
	printf("%d", i)
}
aaa:
printf("\n")
``` 

4. return 

- return 문을 만나면 함수를 호출한 곳으로 되돌아간다.
```
int even()
{
	int i, sum=0;
	for(i = 0; i <=10; i++)
	{
		if(i % 2 == 0)
		{
			sum += i
		} 
		else
		{
			continue;
		}
	}
	return sum; 
}
int main()
{
	int i, res;
	res = even();
	printf("1~10사이의 짝수의 합 :%d")
	printf("프로그램을 종료합니다.\n")
	return 0;
}
```

## 키워드

while  : while () 에 조건문을 넣어 참일 경우 거짓이 될때까지 문장을 반복한다.

for : () 안에 변수,조건,증감자 를 지정해 문장을 반복하게하는 문법.

do while : do {} while(); 의 형태로 do 의 문장을 먼저 한번 실행한 후 while 의 조건이 참이라면 do 를 다시 실행하고 거짓이면 넘어간다.    