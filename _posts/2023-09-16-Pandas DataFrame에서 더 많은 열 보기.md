---
title: Pandas DataFrame에서 더 많은 열 보기
date: 2023-09-16 20:00:00 +0900
categories:
  - python
tags:
  - pandas
  - DataFrame
---

## 문제 상황: `max_columns` 설정

Python의 Pandas 라이브러리를 사용하면서 DataFrame의 모든 열을 한 번에 볼 수 없다는 문제에 직면한 적이 있나요? 이것은 Pandas의 `max_columns` 설정 때문입니다. 기본적으로 Pandas는 화면에 표시할 수 있는 열의 수를 제한합니다. 이 문제를 해결하기 위해 여러 방법이 있습니다.

## 설정 변경을 통한 해결법

Pandas 설정을 변경하는 것은 이 문제를 해결하기 위한 가장 직접적인 방법입니다. `pd.set_option` 함수를 사용하여 `max_columns` 옵션을 변경할 수 있습니다.

```python
import pandas as pd

# max_columns 설정 변경
pd.set_option('display.max_columns', None)
```

이렇게 하면 Pandas는 DataFrame을 출력할 때 가능한 모든 열을 표시합니다.

## 일시적으로 설정 변경하기

모든 DataFrame에 대해 이 설정을 변경하고 싶지 않다면, `with` 문을 사용하여 일시적으로 설정을 변경할 수 있습니다.

```python
with pd.option_context('display.max_columns', None):
    print(df)
```

이렇게 하면 `with` 문 안에서만 설정이 변경되며, 블록을 벗어나면 원래대로 돌아갑니다.

## `head`와 `tail` 메서드 사용

DataFrame의 처음과 끝 일부만 보고 싶다면 `head`와 `tail` 메서드를 사용할 수 있습니다. 이 메서드는 DataFrame의 상위 n개 행과 하위 n개 행을 각각 출력합니다.

```python
# 상위 5개 행 출력
print(df.head())

# 하위 5개 행 출력
print(df.tail())
```

## 주의사항

`max_columns` 옵션을 `None`으로 설정하면, 열이 많은 DataFrame을 출력할 때 화면이 지저분해질 수 있습니다. 따라서 상황에 따라 적절한 방법을 선택해야 합니다.

이렇게 Pandas의 설정을 조절하는 것만으로도 DataFrame을 효과적으로 관리하고 원하는 정보를 더 쉽게 얻을 수 있습니다.