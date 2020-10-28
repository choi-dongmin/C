# 제어문 

제어문은 실질적으로 코드를 제어하는 문법이다, 조건문, 반복문, 분기문이있다.


## 조건문

조건에 따라 문장이 수행 또는 수행하지 않도록 제어하는 문장.

## 종류

1. if (조건식) : 가장 기본적인 형태의 조건문

```
if (num < 0)
	printf ("음수입니다."); // 조건문이 참일때 실행, 거짓이면 실행하지 않는다.

```

알고리즘의 형태로 설명한다면
```
statement 1 -> if(조건) -> 참 : statement 2 -> statement 3
					   -> 거짓 : statement 3

거짓이라면 statement 2 를 건너 뛴다.
```
만약 if 문의 문장이 복합문이라면 중괄호를 사용해야 한다.

```
if (a > b)
{
	max = a;
	min = b;
}

if 문에 해당되는 문장이 하나 이상이면 중괄호를 사용해야 한다.
```

2. if else 
	- if else 는 조건을 만족하면 if 문장을 만족하면 수행하지 않는것이 아닌 else 문장을 실행해야 한다.

```
if(num < 0)
	printf("음수입니다\n");
else
	printf("양수입니다.");

```
알고리즘의 형태로 설명한다면
```
statement 1 -> if(조건) -> 참 : statement 2 -> statement 4
					   -> 거짓 : statement 3 -> statement 4

거짓이라면 statement 2 를 건너 뛴다.
```

3. 다중 if

else if 를 통해 문법을 사용하는 다중 조건문이다.

```
if(num == a)
	printf("a");
else if (num == b)
	printf("b");
else if (num == c)
	printf("c");
	.
	.
	.

```  
위의 예문과 같이 조건문을 연속적으로 사용하는것이 다중 조건문이다.

알고리즘의 형태로 설명한다면
```
statement 1 -> if(조건) -> 참 : statement 2 
		    		   -> 거짓 : if(조건) -> 참 : statement 3
		    		   					-> 거짓 : if(조건) -> 참 : statement 4
		    		   									 -> 거짓 : else -> ..
```

위 같은 형식으로 진행이 된다.

4. switch 
- 정수식의 값에 따라 여러 가지 중 하나로 분기하는 다중분기

```
switch (정수식)
{
	case 정수값:
		문장 1
		break;
	case 정수값:
		문장 2
		break;
	...

}

* 즉 정수식의 값을 평가하고 값은 값인 case 문을 찾아서 해당 case 문 다음에 나열된 문장을 수행
	그러다 break 를 만나면 해당 switch 를 빠져 나간다.
```

## 키워드

- if : if문은 ()안에 조건식을 넣어 참일 경우 실행하고 거짓일 경우 실행하지 않는 제어문이다.

- if else : if 와 마찬가지 이지만 if() 조건문이 거짓이면 else 를 출력한다 이떄, 만약 다른 조건을 추가 하고 싶으면 if 를 중첩하여 사용 할 수있다.

- switch : ()안의 정수값에 따라 분기하는 다중 분기로 해당 case : 의 문장을 실행한다.
 