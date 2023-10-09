---
title: Matplotlib에서 그림 크기 조절하는 방법
date: 2023-08-15 20:00:00 +0900
categories:
  - python
tags:
  - Python
  - Matplotlib
---

## 개요

Matplotlib은 Python에서 데이터를 시각화하는 데 널리 사용되는 라이브러리입니다. 하지만 그림이나 차트의 크기가 원하는 대로 나오지 않을 때가 있습니다. 이 글에서는 Matplotlib를 사용하여 그림 크기를 어떻게 조절하는지 자세히 알아보겠습니다.

## figsize 속성을 사용한 크기 조절

`plt.figure()` 함수 내의 `figsize` 매개변수를 사용하여 그림의 크기를 설정할 수 있습니다. `figsize`는 `(가로 길이, 세로 길이)` 형태의 튜플입니다. 단위는 인치입니다.

```python
import matplotlib.pyplot as plt

plt.figure(figsize=(12, 8))
plt.plot([1, 2, 3], [1, 4, 9])
plt.show()
```

여기서 `figsize=(12, 8)`은 가로 12인치, 세로 8인치 크기의 그림을 생성합니다.

## subplot에서의 크기 조절

여러 개의 그림을 하나의 그래픽 창에 나타낼 때는 `plt.subplot()` 함수를 사용합니다. 이 경우에도 각 서브플롯의 크기를 `figsize` 매개변수를 통해 조절할 수 있습니다.

```python
plt.figure(figsize=(12, 8))
plt.subplot(2, 1, 1)
plt.plot([1, 2, 3], [1, 4, 9])
plt.subplot(2, 1, 2)
plt.plot([1, 2, 3], [1, 2, 3])
plt.show()
```

## 기존 Figure 크기 변경

이미 생성된 `Figure` 객체의 크기를 변경하려면 `set_size_inches` 메소드를 사용합니다.

```python
fig = plt.figure(figsize=(8, 6))
fig.set_size_inches(12, 8)
```

이 명령어로 기존에 8x6 크기였던 그림을 12x8 크기로 변경할 수 있습니다.

## 마무리

Matplotlib에서 그림 크기를 조절하는 방법은 여러 가지입니다. `figsize` 매개변수를 이용하거나, 이미 생성된 `Figure` 객체의 크기를 `set_size_inches` 메소드로 변경할 수 있습니다. 이 방법들을 활용하여 데이터를 더 명확하고 알기 쉽게 시각화하세요.