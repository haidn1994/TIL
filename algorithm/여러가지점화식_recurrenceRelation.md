## 점화식?

알고리즘 문제풀이를 열심히 공부하다 보면 문제를 풀기 위해 여러가지 점화식이 필요하다는 것을 알 수 있을 것이다.(특히 동적 프로그래밍 문제를 풀 떄!)


여기서 가장 매우 중요한 4가지 점화식을 구하는 재귀함수를 C/C++, Python, Javascript로 구현하여 보이려고 한다. 이 4가지 점화식은 **꼭 외우기** 바란다.

* 구현할 점화식의 종류는 다음과 같다.
  * 팩토리얼(Factorial)
  * 피보나치 수(Fibonacci number)
  * 조합, 이항계수(Combination, Binomial coefficient)
  * 두 수의 최대공약수(Greatest common divisor)를 구하는 유클리드 호제법(Euclidean algorithm)

## C/C++

#### 팩토리얼(Factorial)

```{.c}
int factorial(int n)
{
  return (n <= 1) ? 1 : n*factorial(n - 1);
}
```

#### 피보나치 수(Fibonacci number)

```{.c}
int fibo(int n)
{
  return (n <= 0) ? 0 :
         (n == 1) ? 1 : fibo(n - 1) + fibo(n - 2);
}
```

#### 조합(Combination)

```{.c}
int comb(int n, int r)
{
  if(r > n) {
    printf("r은 n보다 클 수 없다.\n")
    return -1;
  }

  // 왜 이런 조건식을 평가하는지 궁금하다면, 조합의 정의에 대해서 잘 생각해 볼것.
  return (n == r || r == 0) ? 1 : comb(n - 1, r - 1) + comb(n - 1, r);
}
```

#### 유클리드 호제법(Euclidean algorithm)

```{.c}
int gcd(int b, int s)
{
  return (s == 0) b : gcd(s, b%s);
}
```

## Python

추후 추가 예정

#### 팩토리얼(Factorial)

```{.python}
```

#### 피보나치 수(Fibonacci number)

```{.python}
```

#### 조합(Combination)

```{.python}
```

#### 유클리드 호제법(Euclidean algorithm)

```{.python}
```


## Javascript

추후 추가 예정

#### 팩토리얼(Factorial)

```{.javascript}
```

#### 피보나치 수(Fibonacci number)

```{.javascript}
```

#### 조합(Combination)

```{.javascript}
```

#### 유클리드 호제법(Euclidean algorithm)

```{.javascript}
```
