# 키보드 입출력 함수

- 키보드로 부터 한 문자(1byte) or 한 문자열(26byte)을 입력받고, 이를 출력하는 함수들

 

1. getchar( 인자값 필요없음 ) EX a = getchar();

	: 키보드로 부터 하나의 문자를 입력받는 함수

 

2. putchar (변수 or 문자) EX putchar(a);

	: 화면에 하나의 문자를 출력하는 함수

 

3. gets (문자열을 저장할 변수 // 배열) EX gets(array); // char array[100]

	: 키보드로 부터 하나의 문자열을 입력받는 함수

 

4. puts ("문자열" or 문자를 저장한 변수) EX puts(array); or puts("adcd")

	: 화면에 하나의 문자열을 출력 하기위한 변수 

 

 

```

#include<stdio.h> // getchar , putchar 예문

 

void main()

{

	char ch;

	printf("문자를 입력하세요 : \n");

	ch = getchar();

	printf("입력받은 문자 = ");

	putchar(ch);

	printf("\n");

}

 

```

 

```

#include<stdio.h> // gets , puts 예문

 

void main()

{

	char string[100];

	printf("문자열을 입력하세요 : \n");

	gets(string);

	printf("입력받은 문자열 = ");

	putchar(string);

	printf("\n");

}

```