---
title: Python에서 mkdir -p 기능 구현하기
date: 2023-09-05 20:00:00 +0900
categories:
  - python
tags:
  - Python
  - mkdir-p
---

## 개요

파이썬에서 디렉터리를 생성할 때, 종종 `mkdir -p` 명령어의 유용성을 느낄 수 있습니다. 이 명령어는 리눅스와 유닉스에서 디렉터리를 생성하면서 부모 디렉터리가 없으면 자동으로 생성해주는 기능을 합니다. 본문에서는 파이썬에서 이와 같은 기능을 어떻게 구현할 수 있는지에 대해 상세하게 알아보겠습니다.

## os 모듈을 활용한 방법

파이썬에서는 `os` 모듈을 활용하여 디렉터리를 생성할 수 있습니다. `os.mkdir` 함수는 기본적으로 디렉터리를 하나만 생성하기 때문에, 부모 디렉터리가 없으면 에러(`FileNotFoundError`)를 발생시킵니다. 그러나 `os.makedirs` 함수를 사용하면 `mkdir -p`와 같은 작업을 수행할 수 있습니다.

```python
import os

os.makedirs("a/b/c", exist_ok=True)
```

`exist_ok=True` 옵션을 주면, 디렉터리가 이미 존재하는 경우에도 에러를 발생시키지 않습니다.

## pathlib 모듈을 이용한 방법

`pathlib` 모듈을 활용하면 더욱 객체지향적인 방법으로 디렉터리를 관리할 수 있습니다. `mkdir` 메서드를 사용하여 디렉터리를 생성하는데, `parents=True` 옵션을 주면 부모 디렉터리까지 자동으로 생성합니다.

```python
from pathlib import Path

Path("a/b/c").mkdir(parents=True, exist_ok=True)
```

이 방법도 `exist_ok=True` 옵션을 통해 이미 존재하는 디렉터리에 대해 에러를 발생시키지 않을 수 있습니다.

## 결론

파이썬에서 `mkdir -p`와 같은 기능을 구현하려면 `os.makedirs` 또는 `pathlib.Path.mkdir`을 사용하면 됩니다. 두 방법 모두 `exist_ok=True` 옵션을 통해 디렉터리가 이미 존재하는 경우에도 안전하게 코드를 실행할 수 있습니다. 이렇게 하면 복잡한 경로 구조에서도 쉽게 디렉터리를 생성할 수 있습니다.