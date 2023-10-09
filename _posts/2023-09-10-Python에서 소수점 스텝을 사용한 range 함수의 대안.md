---
title: Python에서 소수점 스텝을 사용한 range 함수의 대안
date: 2023-09-10 20:00:00 +0900
categories:
  - python
tags:
  - Python
  - range함수
  - numpy라이브러리
---

## `range` 함수와 소수점 문제

Python의 내장 함수 `range`는 정수만을 대상으로 하는 함수입니다. 그렇기 때문에, `range(1, 10, 0.1)`과 같이 소수점 스텝을 사용하려고 하면 `TypeError`라는 오류가 발생합니다. 이 문제를 해결하기 위한 몇 가지 방법을 살펴보겠습니다.

## `numpy` 라이브러리 활용하기

`numpy` 라이브러리의 `arange` 함수를 사용하면 소수점 스텝을 적용할 수 있습니다. 예를 들어, `numpy.arange(0, 1, 0.1)`을 실행하면 `[0, 0.1, 0.2, ..., 0.9]` 같은 결과를 얻을 수 있습니다. 

`numpy`는 'Numeric Python'의 줄임말로, 과학 계산을 위한 라이브러리입니다. `arange`는 'array range'의 줄임말이며, 배열을 쉽게 생성할 수 있게 해줍니다.

## `for` 루프와 `while` 루프 활용하기

만약 `numpy` 라이브러리를 사용하고 싶지 않다면, `for` 루프나 `while` 루프를 활용할 수 있습니다.

```python
start = 0
stop = 1
step = 0.1
current = start

while current < stop:
    print(current)
    current += step
```

이 코드는 `start`에서 `stop`까지 `step`만큼 증가시키면서 숫자를 출력합니다.

## `decimal` 모듈을 이용한 방법

파이썬에는 `decimal`이라는 모듈도 있습니다. 이 모듈은 소수점 아래의 숫자까지 정확하게 계산할 수 있게 해줍니다. `decimal.Decimal('0.1')`처럼 사용하면 됩니다.

## 결론

`range` 함수는 소수점 스텝을 지원하지 않지만, 다양한 방법으로 이 문제를 해결할 수 있습니다. `numpy`의 `arange` 함수를 사용하거나, `for` 루프나 `while` 루프를 이용하거나, `decimal` 모듈을 활용할 수 있습니다. 이러한 방법들은 각각의 상황에 따라 가장 적합한 해결책을 제공합니다.