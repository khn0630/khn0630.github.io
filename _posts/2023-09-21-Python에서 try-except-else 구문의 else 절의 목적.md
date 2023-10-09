---
title: Python에서 try-except-else 구문의 else 절의 목적
date: 2023-09-21 20:00:00 +0900
categories:
  - python
tags:
  - Python구문
---

## 개요
Python의 try-except-else 구문은 코드에서 예외 처리를 돕습니다. 이 기능을 활용하면 프로그램 실행 중 발생할 수 있는 문제를 사전에 해결할 수 있습니다. 이 글에서는 try-except-else 구문에서 가장 이해하기 어려운 부분 중 하나인 'else 절'에 대해 상세히 설명합니다.

## try-except 구문 기본 구조
Python에서 try-except 구문은 기본적으로 다음과 같은 구조를 가집니다.

```python
try:
    # 예외가 발생할 가능성이 있는 코드
except [예외 이름]:
    # 예외 발생 시 실행할 코드
```

이 구조에서 `try` 블록 내의 코드는 실행 중에 문제가 생길 수 있습니다. 만약 문제가 생기면 `except` 블록의 코드가 실행되어 문제를 처리합니다.

## else 절의 목적
else 절은 try 블록의 코드가 예외 없이 성공적으로 실행된 경우에만 실행됩니다. 즉, try 블록에서 예외가 발생하지 않을 때 실행되는 코드를 작성하는 곳입니다.

```python
try:
    # 예외가 발생할 가능성이 있는 코드
except [예외 이름]:
    # 예외 발생 시 실행할 코드
else:
    # 예외가 발생하지 않았을 때 실행할 코드
```

## else 절 활용 예시
예를 들어, 파일을 열고 내용을 읽는 작업을 수행할 때 이 구문을 활용할 수 있습니다.

```python
try:
    file = open("example.txt", "r")
    data = file.read()
except FileNotFoundError:
    print("파일이 존재하지 않습니다.")
else:
    print(f"파일 내용: {data}")
    file.close()
```

여기서 else 절은 파일을 성공적으로 열고 읽은 후에 실행됩니다. 즉, 예외가 발생하지 않았을 때만 `file.close()`가 실행되어 파일을 닫습니다.

## 결론
else 절은 예외 처리의 일환으로, try 블록의 코드가 예외 없이 정상적으로 실행되었을 때만 동작하는 코드를 작성하는 공간입니다. 이를 통해 코드의 가독성을 높이고, 예외 처리를 더욱 명확하게 할 수 있습니다.