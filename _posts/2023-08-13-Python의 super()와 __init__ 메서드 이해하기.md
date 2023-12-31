---
title: Python의 super()와 __init__ 메서드 이해하기
date: 2023-08-13 20:00:00 +0900
categories:
  - python
tags:
  - Python
---

## 상속과 기본 개념

Python에서 `super()`는 상속에서 매우 중요한 역할을 합니다. 상속은 하나의 클래스가 다른 클래스의 기능을 물려받는 것을 의미합니다. `super()` 함수는 부모 클래스의 메서드를 호출할 때 주로 사용됩니다. 특히 `__init__` 메서드에서 이를 자주 볼 수 있습니다. 

## `__init__` 메서드란?

`__init__` 메서드는 클래스의 인스턴스가 생성될 때 자동으로 호출됩니다. 이 메서드는 객체 초기화에 사용되며, 필요한 매개변수를 받아 객체의 속성을 설정할 수 있습니다.

## `super()`의 작동 방식

`super()`는 부모 클래스의 메서드를 호출하는 데 사용됩니다. 예를 들어, 여러 클래스가 있고 이 클래스들이 상속 관계에 있을 때 `super()`를 사용하면 부모 클래스의 메서드를 자식 클래스에서 쉽게 호출할 수 있습니다.

```python
class Parent:
    def __init__(self, name):
        self.name = name

class Child(Parent):
    def __init__(self, name, age):
        super().__init__(name)
        self.age = age
```

위 예제에서 `Child` 클래스의 `__init__` 메서드는 `super().__init__(name)`을 통해 `Parent` 클래스의 `__init__` 메서드를 호출합니다. 이렇게 하면 `Child` 클래스는 `name`과 `age` 두 가지 속성을 가지게 됩니다.

## 왜 `super()`를 사용하는가?

1. **코드 재사용**: 부모 클래스의 메서드를 재사용할 수 있으므로 코드 중복을 줄일 수 있습니다.
2. **유지 보수**: 부모 클래스의 변경이 자식 클래스에 자동으로 반영됩니다. 따라서 유지 보수가 쉽습니다.
3. **확장성**: 새로운 자식 클래스를 쉽게 추가할 수 있으며, 기존 코드를 변경할 필요가 없습니다.

## 주의사항

- `super()`는 Python 3에서 사용 가능합니다. Python 2에서는 문법이 다르므로 주의가 필요합니다.
- 다중 상속을 다룰 때 `super()`는 MRO(Method Resolution Order)를 따릅니다. MRO는 메서드를 찾을 순서를 결정하는 규칙입니다.

## 정리

`super()`와 `__init__` 메서드는 Python에서 클래스와 객체 지향 프로그래밍을 이해하는 데 매우 중요한 요소입니다. 이들은 코드의 재사용성과 유지 보수성, 확장성을 높이는 데 큰 도움을 줍니다.