
# 지역변수와 전역변수

## 지역변수

- 함수안에서 만들어지고, 함수 안에서만 사용되는 변수

* 지역변수는 함수가 리턴 될 때 같이 소멸된다.
* 지역변수는 선언된 블록 안에서만 사용이 가능하다.
* 지역변수는 따로 초기화 하지 않을시 쓰리게 값을 같는다.

```
int main (void)
{
	printf("data = %d\n", data); // 오류발생

}

void test(int num)
{
	int data;
	printf("data = %d\n", data);
}

//위와 같이 data 변수가 test 함수의 지역변수 임으로 main 에서는 사용할수 없다.
```
## 전역변수

- 프로그램 전체에서 사용할 수 있는 변수

* 전역변수는 자동으로 0 으로 초기화 한다.
* 전역변수는 프로그램이 시작될 떄 미리 생성되어 프로그램이 수행되는 동안 사용되다가 프로그램이 종료될 때 해제 된다.
* 전역변수는 소스파일의 시작 부분에 넣어준다.

```
int num; // 전역변수

int main(void)
{
	num = 10;

	TestGlobal();
	TestGlobal();

	printf("num = %d\n", num)
	return 0;
}

void TestGlobal(void)
{
	printf("num = %d\n", num++);
}

* 위의 모든 함수가 전역변수의 범위이다.
```

## 매개변수/인자

### 값에 의한 전달
- 함수를 호출할 때 넘겨주는 인자의 값을 함수의 정의에 있는 매개변수로 복사해서 전달하는 방식
- 복사에 의한 전달
- 함수 안에서 매개변수의 값을 변경해도 초기에 지정한 매개변수는 바뀌지 않는다.

```
int GetFactorial (int num);

int main(void)
{
	...
	result = GetFactorial(5);
	...
	return 0;
}

int GetFactorial(int num) // 매개변수 5
{
	...
	return fact;
}
```

