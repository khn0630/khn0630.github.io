---
title: DateTime에서 Date로 변환하기
date: 2023-09-11 20:00:00 +0900
categories:
  - python
tags:
  - Python
  - DataTime
---

## Python에서의 변환 방법

Python에서 `datetime` 객체를 `date` 객체로 변환하려면 `date()` 메서드를 사용하면 됩니다. `datetime`은 날짜와 시간을 모두 포함하는 반면, `date`는 날짜만을 포함합니다. 예를 들어, `datetime` 객체가 `2023-10-04 12:34:56` 이라면, `date` 객체로 변환하면 `2023-10-04`가 됩니다.

### 코드 예시

```python
from datetime import datetime

# datetime 객체 생성
dt_object = datetime.now()

# date 객체로 변환
date_object = dt_object.date()

# 결과 출력
print("DateTime 객체:", dt_object)
print("Date 객체:", date_object)
```

이 코드를 실행하면, 현재의 `datetime` 객체를 먼저 출력한 다음, 그것을 `date` 객체로 변환하여 출력합니다.

## Java에서의 변환 방법

Java에서는 `LocalDateTime` 객체에서 `LocalDate` 객체로 변환할 수 있습니다. `toLocalDate()` 메서드를 사용하여 쉽게 변환할 수 있습니다.

### 코드 예시

```java
import java.time.LocalDateTime;
import java.time.LocalDate;

public class Main {
  public static void main(String[] args) {
    // LocalDateTime 객체 생성
    LocalDateTime dateTime = LocalDateTime.now();

    // LocalDate 객체로 변환
    LocalDate date = dateTime.toLocalDate();

    // 결과 출력
    System.out.println("LocalDateTime 객체: " + dateTime);
    System.out.println("LocalDate 객체: " + date);
  }
}
```

Java 코드도 Python과 유사하게, 먼저 `LocalDateTime` 객체를 생성하고 그 다음에 `LocalDate` 객체로 변환합니다.

## 요약

- Python: `date()` 메서드를 사용하여 `datetime`을 `date`로 변환
- Java: `toLocalDate()` 메서드를 사용하여 `LocalDateTime`을 `LocalDate`로 변환

이렇게 간단한 코드 몇 줄로 `datetime` 객체를 `date` 객체로 변환할 수 있습니다. 선택한 프로그래밍 언어에 따라 적절한 메서드를 사용하면 됩니다.