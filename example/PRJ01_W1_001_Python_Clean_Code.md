# Python 클린 코드 

### **학습 목표:** Python 코드 컨벤션과 클린코드 원칙을 적용한다.

---

## 1단계: 파이썬 기초 개념

### 1.1 변수와 데이터 타입

- **변수**는 메모리 공간의 이름으로, 파이썬의 _동적 타이핑_ 특성상 타입 선언 없이 자유롭게 값 할당 가능

- 기본 데이터 타입은 **숫자형**, **문자열**, **불리언**, **리스트**, **튜플**, **딕셔너리**, **집합** 등이 있으며 각각 고유한 특성 보유

- `type()` 함수로 데이터 타입을 확인하고, **타입 변환 함수**(`int()`, `str()`, `float()`)를 통해 데이터 타입 변환 가능



```python
# 기본 데이터 타입 예제
number = 42          # 정수형(int)
decimal = 3.14       # 실수형(float)
text = "Hello"       # 문자열(str)
is_valid = True      # 불리언(bool)
```


```python
# 데이터 타입 확인하기
print(type(number))  # <class 'int'>
```

    <class 'int'>
    


```python
print(type(text))    # <class 'str'>
```

    <class 'str'>
    

### 1.2 기본 연산자

- **산술 연산자**(`+`, `-`, `*`, `/`, `%`, `**`)로 기본 수학 연산을 수행하며, _정수 나눗셈_은 `//` 연산자 사용

- **비교 연산자**(`==`, `!=`, `>`, `<`, `>=`, `<=`)와 **논리 연산자**(`and`, `or`, `not`)를 조합하여 조건문 구성 가능

- **할당 연산자**(`=`, `+=`, `-=`, `*=`, `/=`)를 통해 변수에 값을 할당하거나 연산과 할당을 동시 수행


```python
# 산술 연산자
result1 = 10 + 5    # 덧셈
result2 = 10 - 5    # 뺄셈
result3 = 10 * 5    # 곱셈
result4 = 10 / 5    # 나눗셈
result5 = 10 % 3    # 나머지
result6 = 10 ** 2   # 거듭제곱

# 결과 출력
print(result1)      # 15
print(result2)      # 5
print(result3)      # 50
print(result4)      # 2.0
print(result5)      # 1
print(result6)      # 100
```

    15
    5
    50
    2.0
    1
    100
    


```python
# 비교 연산자
is_equal = 10 == 5      # False
is_greater = 10 > 5     # True

# 결과 출력
print(is_equal)         # False
print(is_greater)       # True
```

    False
    True
    


```python
# 논리 연산자
result1 = True and False   # False
result2 = True or False    # True

# 결과 출력
print(result1)             # False
print(result2)             # True
```

    False
    True
    


```python
# 할당 연산자
number = 10
number += 5     # number = number + 5

print(number)   # 15
```

    15
    

--- 

## 2단계: 제어문

### 2.1 조건문

- **조건문**은 `if`, `elif`, `else`를 사용하며, 들여쓰기로 코드 블록을 구분

- **조건식**에서는 비교/논리 연산자 사용 가능하며, 빈 컨테이너(`[]`, `()`, `{}`), `0`, `None`은 거짓으로 평가

- **삼항 연산자**(`결과 = A if 조건 else B`)로 간단한 조건문을 한 줄로 표현 가능


```python
# 조건문 사용 - 점수에 따른 등급을 출력 
score = 85
    
if score >= 90:
    print("A")

elif score >= 80:
    print("B")

elif score >= 70:
    print("C")

else:
    print("F")
```

    B
    


```python
# 삼항 연산자
score = 85
result = "pass" if score >= 80 else "fail"

print(result)   # pass
```

    pass
    

### 2.2 반복문

- **반복문**은 `for`와 `while` 두 종류가 있으며, `for`는 시퀀스 순회에, `while`은 조건부 반복에 사용

- **제어 키워드** `break`, `continue`, `else`를 통해 반복문의 세밀한 흐름 제어 가능

- **내장 함수** `enumerate()`, `zip()` 등과 함께 사용하여 다양한 반복 패턴 구현 가능


```python
# for 반복문 - 5번 반복
for i in range(5):
    print(f"반복 {i+1}번째")
```

    반복 1번째
    반복 2번째
    반복 3번째
    반복 4번째
    반복 5번째
    


```python
# while 반복문 - 조건을 충족할 때까지 반복
count = 0
while count < 5:
    print(f"현재 카운트: {count}")
    count += 1
```

    현재 카운트: 0
    현재 카운트: 1
    현재 카운트: 2
    현재 카운트: 3
    현재 카운트: 4
    


```python
# break 키워드 사용 - 반복문 종료

for i in range(10):
    if i == 5:
        break
    print(i) # 0, 1, 2, 3, 4 출력
```

    0
    1
    2
    3
    4
    


```python
# continue 키워드 사용 - 반복문의 나머지 부분을 건너뛰고 다음 반복을 진행

for i in range(10):
    if i % 2 == 0:
        continue
    print(i) # 1, 3, 5, 7, 9 출력
```

    1
    3
    5
    7
    9
    


```python
# enumerate 함수 - 반복문에서 인덱스와 원소를 함께 사용
fruits = ["apple", "banana", "cherry"]

for index, fruit in enumerate(fruits):
    print(f"인덱스: {index}, 과일: {fruit}")
```

    인덱스: 0, 과일: apple
    인덱스: 1, 과일: banana
    인덱스: 2, 과일: cherry
    


```python
# zip 함수 - 여러 개의 리스트를 같은 인덱스끼리 묶어주는 함수

fruits = ["apple", "banana", "cherry"]
colors = ["red", "yellow", "pink"]

for fruit, color in zip(fruits, colors):
    print(f"과일: {fruit}, 색상: {color}")
```

    과일: apple, 색상: red
    과일: banana, 색상: yellow
    과일: cherry, 색상: pink
    

--- 

## 3단계: 자료구조

### 3.1 리스트 (List)

- **리스트**는 순서가 있고 변경 가능한 시퀀스로, `[]`로 생성하며 다양한 타입의 요소 저장 가능

- **주요 메서드**로 `append()`, `extend()`, `insert()`, `remove()`, `pop()`, `sort()`를 제공하여 **데이터 조작** 가능

- **리스트 컴프리헨션**을 통해 반복문과 조건문을 한 줄로 표현하여 새로운 리스트를 효율적으로 생성


```python
# 리스트 생성과 조작
numbers = [1, 2, 3, 4, 5]
fruits = ["사과", "바나나", "오렌지"]
```


```python
# 인덱싱 - 리스트의 특정 위치에 있는 원소를 가져오기

print(numbers[0])   # 1
print(fruits[1])    # 바나나
```

    1
    바나나
    


```python
# 슬라이싱 - 리스트의 일부분을 가져오기

print(numbers[1:3]) # [2, 3]
print(fruits[:2])   # ['사과', '바나나']
```

    [2, 3]
    ['사과', '바나나']
    


```python
# 요소 추가 (append) : 리스트 끝에 요소 추가
numbers.append(6)   

print(numbers)  # [1, 2, 3, 4, 5, 6]
```

    [1, 2, 3, 4, 5, 6]
    


```python
# 요소 추가 (insert) : 특정 위치에 요소 추가
fruits.insert(1, "배")

print(fruits)   # ['사과', '배', '바나나', '오렌지']
```

    ['사과', '배', '바나나', '오렌지']
    


```python
# 마지막 요소 제거 (pop)
numbers.pop()

print(numbers)  # [1, 2, 3, 4, 5]
```

    [1, 2, 3, 4, 5]
    


```python
# 리스트 컴프리헨션 - 리스트를 간단하게 생성
odd_numbers = [i for i in range(10) if i % 2 == 1]

print(odd_numbers)  # [1, 3, 5, 7, 9]
```

    [1, 3, 5, 7, 9]
    

### 3.2 딕셔너리(Dictionary)

- **딕셔너리**는 키-값 쌍을 저장하는 해시 테이블 구조로, `{}`로 생성하며 키는 반드시 **고유하고 변경 불가능**해야 함

- **핵심 메서드**로 `keys()`, `values()`, `items()`, `get()`, `update()`, `pop()`을 제공하여 데이터 관리

- **딕셔너리 컴프리헨션**으로 간결한 문법을 통해 새로운 딕셔너리를 효율적으로 생성 가능


```python
# 딕셔너리 생성과 활용
student = {
    "name": "김철수",
    "age": 20,
    "scores": {
        "국어": 85,
        "수학": 90,
        "영어": 88
    }
}

# 객체 출력
print(student)
```

    {'name': '김철수', 'age': 20, 'scores': {'국어': 85, '수학': 90, '영어': 88}}
    


```python
# 딕셔너리 데이터 접근
print(student["name"])          # 김철수
print(student["scores"]["수학"]) # 90
```

    김철수
    90
    


```python
# 딕셔너리 데이터 수정
student["age"] = 21
student["scores"]["국어"] = 90

print(student)
```

    {'name': '김철수', 'age': 21, 'scores': {'국어': 90, '수학': 90, '영어': 88}}
    


```python
# keys 메서드 - 키 값들을 리스트로 반환
keys = student.keys()

print(keys) 
```

    dict_keys(['name', 'age', 'scores'])
    


```python
# values 메서드 - 값들을 리스트로 반환

values = student.values()

print(values)
```

    dict_values(['김철수', 21, {'국어': 90, '수학': 90, '영어': 88}])
    


```python
# items 메서드 - 키와 값의 쌍을 튜플로 반환

items = student.items()

print(items)
```

    dict_items([('name', '김철수'), ('age', 21), ('scores', {'국어': 90, '수학': 90, '영어': 88})])
    


```python
# get 메서드 - 키로 값을 가져오기

name = student.get("name")
print(name) # 김철수

address = student.get("address", "주소 없음")
print(address)  
```

    김철수
    주소 없음
    

---

## 4단계: 함수와 모듈

### 4.1 함수 정의와 호출

- **함수**는 `def` 키워드로 정의하며, 코드의 **재사용성**과 **모듈화**를 위한 핵심 요소

- **매개변수** 설정이 유연하며, 기본값 설정과 `*args`, `**kwargs`를 통한 가변 인자 지원

- **다중 반환값**과 **중첩 함수**를 지원하여 복잡한 함수 로직 구현 가능


```python
# 가변인자 사용하기 - 함수의 매개변수 개수가 가변적일 때 사용
def calculate_average(*numbers):
    """
    여러 숫자의 평균을 계산하는 함수
    Args:
        *numbers: 가변 인자로 받는 숫자들 (숫자 여러 개 가능)
    Returns:
        float: 평균값
    """
    return sum(numbers) / len(numbers)
```


```python
# 숫자 여러 개를 인자로 받아 평균을 계산
avg = calculate_average(10, 20, 30, 40, 50)
print(f"평균: {avg}") 
```

    평균: 30.0
    


```python
# 키워드 인자 사용 - 함수의 인자를 이름으로 전달

def print_student_info(name, age, score):
    """
    학생 정보를 출력하는 함수
    Args:
        name (str): 학생 이름
        age (int): 학생 나이
        score (int): 학생 점수

    Returns:
        None
    """

    print(f"이름: {name}, 나이: {age}, 점수: {score}")


# 키워드 인자로 함수 호출하여 학생 정보를 출력 
print_student_info(name="김철수", age=20, score=90)
```

    이름: 김철수, 나이: 20, 점수: 90
    

### 4.2 모듈 사용

- **모듈**은 `import` 문으로 가져오며, 전체 모듈, 특정 요소, 별칭 사용 등 **다양한 임포트 방식** 지원
- **표준 라이브러리**에서 `math`, `random`, `datetime`, `os`, `sys` 등 **자주 사용되는 모듈** 제공
- **사용자 정의 모듈**은 작업 디렉토리나 `PYTHONPATH`에 위치해야 하며, **패키지**로 체계적 관리 가능


```python
# random 모듈 활용
import random

random_number = random.randint(1, 100)
print(f"랜덤 숫자: {random_number}")
```

    랜덤 숫자: 55
    


```python
# datetime 모듈 활용
import datetime

current_time = datetime.datetime.now()
print(f"현재 시간: {current_time}")
```

    현재 시간: 2025-09-05 16:07:03.483368
    


```python
# 특정 요소 가져오기
from datetime import datetime  # datetime 모듈에서 datetime 클래스만 가져오기

current_time = datetime.now()
print(f"현재 시간: {current_time}")
```

    현재 시간: 2025-09-05 16:07:03.499435
    


```python
# 모듈 별칭 사용
import random as rd

random_number = rd.randint(1, 100)
print(f"랜덤 숫자: {random_number}")
```

    랜덤 숫자: 46
    

* 사용자 정의 모듈:    
    - `.py` 파일로 생성
    - 재사용 가능한 함수/클래스 포함
    - `if __name__ == "__main__":` 로 직접 실행 시 동작 정의
    - `import`로 다른 파일에서 사용


```python
# calculator.py 파일을 만들어서 저장 
def add(a, b):
    return a + b

def subtract(a, b):
    return a - b

if __name__ == "__main__":
    print(add(10, 5))  
```

    15
    


```python
# 사용자 정의 모듈 불러오기
import calculator

result = calculator.add(10, 5)
print(result)  # 15
```

    15
    

# [실습] 가장 큰 수 찾기 

다음과 같은 함수를 작성하고 테스트 결과를 출력하세요. 

- 입력: 정수 배열 nums
- 출력: 배열에서 가장 큰 수와 그 위치 (인덱스)
- 제약조건: 배열 길이 1 이상, 중복 가능


```python
# 여기에 코드를 작성하세요.
def bigNum(nums):
    if len(nums) == 0:
        return print("리스트가 비어 있습니다.")
    else:
        max_num = nums[0]
        for num in nums:
            if num > max_num:
                max_num = num
        return print(f"가장 큰 수는 {max_num}입니다.")
    
bigNum([3, 1, 4, 1, 5, 9, 2, 6, 5, 3, 5])
```

    가장 큰 수는 9입니다.
    

---

# 파이썬 클린 코드 가이드

- 클린 코드는 **효율적인 팀 협업**과 **안정적인 프로젝트 관리**의 기반

- **가독성 향상**을 위해 일관된 코딩 스타일과 명확한 변수/함수 이름 사용
- **유지보수**와 **버그 예방**을 위한 적절한 문서화와 테스트 코드 작성
- **재사용성**을 높이기 위해 모듈화와 단일 책임 원칙 준수



## 1. 의미 있는 이름 짓기

- **의미 있는 변수명**은 snake_case로 작성하며, 데이터의 특성을 정확히 반영해야 합니다 (예: `user_age`, `total_price`)

- **불리언 변수**는 `is_`, `has_`, `can_` 접두사를 사용하여 의미를 명확히 합니다

- **함수명**은 동사로 시작하며 기능을 직관적으로 표현해야 합니다 (예: `get_user_info()`, `process_payment()`)

- 모호한 이름(`x`, `temp`, `data`)은 사용을 피해야 합니다


```python
### 나쁜 예제
def f(x, l):
    r = []
    for i in range(l):
        if x[i] > 0:
            r.append(x[i])
    return r

### 좋은 예제
# 1. 함수명을 명확하게 작성
# 2. 함수의 인자를 명확하게 작성
# 3. 함수의 반환값을 명확하게 작성
# 4. 타입 힌트를 사용하여 함수의 인자와 반환값의 타입을 명시
# 5. 변수명이 구체적인 의미를 가지도록 작성

def filter_positive_numbers(numbers: list, length: int) -> list:
    positive_numbers = []
    for index in range(length):
        if numbers[index] > 0:
            positive_numbers.append(numbers[index])
    return positive_numbers
```

## 2. 함수 작성 원칙

- **단일 책임 원칙**(Single Responsibility Principle)은 함수가 하나의 작업만 수행해야 하는 원칙입니다

- 각 함수는 **명확한 목적**을 가지며 다른 기능과 분리되어야 합니다

- 이 원칙 적용 시 **코드 유지보수**와 **재사용성**이 향상됩니다

- **테스트 용이성**과 **버그 감소** 효과가 있습니다


```python
### 나쁜 예제 - 여러 책임이 혼재
def process_user_data(user_data):
    # 데이터 검증
    if not user_data.get('name') or not user_data.get('email'):
        raise ValueError("Invalid user data")
    
    # 데이터베이스 저장
    save_to_db(user_data)
    
    # 이메일 발송
    send_welcome_email(user_data['email'])

### 좋은 예제 - 책임 분리
def validate_user_data(user_data):
    if not user_data.get('name') or not user_data.get('email'):
        raise ValueError("Invalid user data")

def save_user_data(user_data):
    return save_to_db(user_data)

def send_user_welcome_email(email):
    send_welcome_email(email)

def process_user_registration(user_data):
    """
    사용자 등록 처리 함수 (책임 분리)
    """
    validate_user_data(user_data)
    save_user_data(user_data)
    send_user_welcome_email(user_data['email'])
```

## 3. 주석 작성 원칙

- 주석은 `#`(한 줄) 또는 `"""`/`'''`(여러 줄)을 사용하여 코드의 **목적**과 **동작 원리**를 설명

- **독스트링(docstring)** 은 함수와 클래스에 필수이며 매개변수, 반환값, 예외를 명확히 기술

- 코드는 **자체 문서화(self-documenting)** 원칙을 따르고, 불필요한 주석은 제거


```python
# 나쁜 예제 - 불필요한 주석
# 사용자의 나이를 계산한다
def calculate_age(birth_year):
    # 현재 연도에서 출생연도를 뺀다
    return 2024 - birth_year

# 좋은 예제 - 필요한 설명만 포함
def calculate_age(birth_year: int) -> int:
    """
    주어진 출생연도로부터 현재 나이를 계산합니다.
    
    Args:
        birth_year: 출생연도 (4자리 숫자)
        
    Returns:
        현재 나이
        
    Raises:
        ValueError: 출생연도가 올바르지 않은 경우
    """
    if birth_year < 1900 or birth_year > 2024:
        raise ValueError("올바르지 않은 출생연도입니다")
    return 2024 - birth_year
```

## 4. 예외 처리

- **예외 처리**는 `try-except` 구문을 사용해 프로그램 실행 중 발생하는 오류를 체계적으로 관리

- 파이썬은 `TypeError`, `ValueError`, `FileNotFoundError` 등 다양한 **내장 예외 클래스** 제공

- **예외 처리 구조**는 `try`, `except`, `else`, `finally` 블록으로 구성되며 각각 특정 상황에서 실행

- `raise`문과 커스텀 예외 클래스를 활용해 상황에 맞는 예외 처리를 구현할 수 있음 


```python
# 나쁜 예제 - 모든 예외를 동일하게 처리
def process_file(filename):
    try:
        with open(filename) as f:
            data = f.read()
            process_data(data)
    except Exception as e:
        print(f"Error: {e}")

# 좋은 예제 - 구체적인 예외 처리
def process_file(filename: str) -> None:
    try:
        with open(filename) as f:
            data = f.read()
            process_data(data)
    except FileNotFoundError:
        print(f"파일을 찾을 수 없습니다: {filename}")
        raise
    except PermissionError:
        print(f"파일 접근 권한이 없습니다: {filename}")
        raise
    except Exception as e:
        print(f"예상치 못한 에러 발생: {str(e)}")
        raise
```

## 5. 컬렉션 다루기

- **리스트**는 `[]`로 생성하는 수정 가능한 순서형 컬렉션으로, `append()`, `remove()` 등 다양한 메서드 제공

- **튜플**은 `()`로 생성하는 **불변(immutable)** 컬렉션으로, 데이터 무결성이 필요한 경우 사용

- **딕셔너리**는 `{}`로 생성하는 키-값 쌍 컬렉션으로, 고유한 키를 통해 데이터 접근

- **집합**은 중복을 허용하지 않는 컬렉션으로, 집합 연산(`union`, `intersection` 등) 지원


```python
# 나쁜 예제 - 복잡한 리스트 컴프리헨션
numbers = [x for x in [y for y in range(100) if y % 2 == 0] if x % 3 == 0]

# 좋은 예제 - 명확한 단계 분리
def get_numbers_divisible_by_six(max_number: int) -> list:
    even_numbers = [num for num in range(max_number) if num % 2 == 0]
    return [num for num in even_numbers if num % 3 == 0]
```

**[예제 해설]** 

- 코드 가독성을 위해 복잡한 **리스트 컴프리헨션**과 중첩된 연산은 지양

- **함수 분리**를 통해 코드의 각 단계를 명확히 구분하여 작성

- 의도가 명확한 **함수명**(`get_numbers_divisible_by_six()`)을 사용

## 6. 상수 관리

- 파이썬에서 상수는 모듈 레벨의 **대문자 변수**로 정의하며, `constants.py`와 같이 별도의 파일에서 함께 관리

- **매직 넘버** 제거를 위해 상수를 사용하여 코드의 의미를 명확히 하고 유지보수성 향상

- 환경별 설정값은 **환경변수**나 설정 파일과 연동하여 유연하게 관리

- 관련 상수는 **Enum 클래스**로 그룹화하여 체계적으로 관리


```python
# 나쁜 예제 - 매직 넘버 사용
def calculate_price(quantity, price):
    if quantity > 100:
        return quantity * price * 0.9
    return quantity * price

# 좋은 예제 - 상수 정의
BULK_ORDER_THRESHOLD = 100
BULK_ORDER_DISCOUNT = 0.9

def calculate_price(quantity: int, price: float) -> float:
    if quantity > BULK_ORDER_THRESHOLD:
        return quantity * price * BULK_ORDER_DISCOUNT
    return quantity * price
```


```python
# enum 사용
from enum import Enum

class Color(Enum):
    RED = 1
    GREEN = 2
    BLUE = 3

# 사용 예
print(Color.RED)  # Color.RED
print(Color.RED.name)  # "RED"
print(Color.RED.value)  # 1 
```

    Color.RED
    RED
    1
    

## 7. 타입 힌트(Type Hints)

- **타입 힌트**는 코드의 가독성을 높이고 타입 관련 버그를 조기 발견하는 기능

- `typing` 모듈로 `List`, `Dict`, `Callable` 등 **복잡한 타입**을 명시 가능

- `@dataclass` 데코레이터를 사용해 클래스 속성의 타입을 명확하게 문서화

- Python 3.5부터 도입된 기능으로 코드의 안정성과 가독성을 향상

- VS Code에서 Python 타입 오류를 체크하는 방법

    1. VS Code에 필요한 확장 프로그램 설치:
        - Python extension (Microsoft)
        - Pylance (Microsoft) - Python의 언어 서버로, 타입 체킹 기능 제공

    2. Pylance 설정:
        - VS Code 설정(Settings)에서 "Python Type Checking Mode" 검색
        - 다음 중 하나의 모드 선택:
            - off: 타입 체킹 비활성화
            - basic: 기본적인 타입 체킹
            - strict: 엄격한 타입 체킹


```python
from typing import List, Dict, Optional

def process_user_list(
    users: List[Dict[str, str]],             # 사용자 정보가 담긴 딕셔너리 리스트 : List[Dict[str, str]]
    department: Optional[str] = None         # 필터링할 부서명 (선택사항) : Optional[str]
) -> List[str]:                              # 이메일 주소 리스트 : List[str]
    """
    사용자 목록을 처리하여 이메일 주소 리스트를 반환합니다.
    
    Args:
        users: 사용자 정보가 담긴 딕셔너리 리스트
        department: 필터링할 부서명 (선택사항)
        
    Returns:
        이메일 주소 리스트
    """
    if department:
        filtered_users = [
            user for user in users 
            if user.get('department') == department
        ]
    else:
        filtered_users = users
    
    return [user['email'] for user in filtered_users]


# 함수 호출 - 사용자 목록에서 마케팅팀 이메일 주소만 가져오기
users = [
    {"name": "김철수", "email": "dev777@test.com", "department": "개발팀"},
    {"name": "박영희", "email": "marketing99@test.com", "department": "마케팅팀"},
    {"name": "이민수", "email": "marketing2@test.com", "department": "마케팅팀"},
]

emails = process_user_list(users, department="마케팅팀")
print(emails)  
```

    ['marketing99@test.com', 'marketing2@test.com']
    

# [실습] 리스트에서 중복 숫자 찾기 

다음과 같은 함수를 작성하고 테스트 결과를 출력하세요. 

요구사항:
- 주어진 정수 리스트에서 중복되는 숫자 찾기
- 결과는 오름차순으로 정렬된 리스트로 반환
- 중복이 없으면 빈 리스트 반환

제약조건:
- 입력 리스트 길이: 1 이상 100 이하
- 각 정수 범위: -100 이상 100 이하


```python
# 여기에 코드를 작성하세요.
```
