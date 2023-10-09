---
title: Python2에서 dict.items()와 dict.iteritems()의 차이점
date: 2023-09-26 20:00:00 +0900
categories:
  - python
tags:
  - Python2
---

## 정의와 작동 원리

Python2에서 `dict.items()`와 `dict.iteritems()`는 두 메소드 모두 딕셔너리의 항목을 반환하는 데 사용됩니다. 그러나 두 메소드의 작동 방식과 반환 형태가 다릅니다.

### dict.items()

`dict.items()` 메소드는 딕셔너리에서 모든 (키, 값) 쌍을 새로운 리스트로 복사하여 반환합니다. 이것은 메모리를 많이 사용할 수 있으므로 대용량 딕셔너리에서는 효율적이지 않을 수 있습니다.

```python
my_dict = {'a': 1, 'b': 2, 'c': 3}
items_list = my_dict.items()
print(items_list)  # [('a', 1), ('b', 2), ('c', 3)]
```

### dict.iteritems()

반면에 `dict.iteritems()`는 (키, 값) 쌍을 순회하는 iterator를 반환합니다. 이 메소드는 메모리를 절약하기 위해 원래의 딕셔너리 객체에서 항목을 순회합니다.

```python
my_dict = {'a': 1, 'b': 2, 'c': 3}
items_iterator = my_dict.iteritems()
for key, value in items_iterator:
    print(key, value)  # 'a' 1, 'b' 2, 'c' 3
```

## 성능 차이

- `dict.items()`는 딕셔너리의 모든 항목을 메모리에 저장하므로 큰 딕셔너리에서는 비효율적일 수 있습니다.
- `dict.iteritems()`는 필요한 만큼만 항목을 가져오기 때문에 메모리를 더 효율적으로 사용합니다.

## Python3에서의 변화

Python3에서는 `dict.items()`가 Python2의 `dict.iteritems()`처럼 작동하여 메모리를 효율적으로 사용합니다. Python2의 `dict.iteritems()`는 Python3에서는 사용할 수 없습니다.

## 에러 명칭

만약 Python3에서 `dict.iteritems()`을 사용하려고 시도하면, `AttributeError: 'dict' object has no attribute 'iteritems'`라는 에러 메시지가 발생합니다.

## 정리

Python2에서 `dict.items()`와 `dict.iteritems()`는 같은 목적을 가지지만 다른 방식으로 작동합니다. 따라서 사용 상황에 따라 적절한 메소드를 선택해야 합니다.