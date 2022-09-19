## CH 01. 환경설정

파이썬 개발환경 설정

## CH 02. 데이터 타입과 컬렉션

list tuple dict set

## CH 03. 조건문과 반복문

- if elif else
- while
- for

## CH 04. 함수 이해 및 활용

- def 이해 , 간단한 함수 만들기
- return 이해
- 

## CH 05. 파이썬 모듈

- 모듈의 이해 및 사용과 import 방법

## CH 06. 클래스와 인스턴스

1. 클래스 & 오브젝트 이해하기
    - class : 인간이라는 타입
        - 속성(attribute) : 이름, 국적, 나이
        - 행동(method) : 먹다, 자다, 일어나다
    - object : 홍길동, 임꺽정 등 실제로 존재하는 객체
    - class : ‘List’ 라는 타입 — 틀
        - 속성(attribute) : Items
        - 행동(method) : append, extend
    - object : [1, 2, 3] [’Hello World’, ‘World’] — 틀에 저장되어있는 내용
2. 클래스 정의 및 사용하기
    - 실세계의 것을 모델링하여 속성(attribute)와 동작(method)를 갖는 데이터 타입
    - python에서의 string, int, list, dict 모두가 다 클래스로 존재
    - 학생이라는는 클래스를 만들때, 학생을 나타내는 속성과 학생이 행하는 행동을 함께
    - 정의 할 수 있음
    - 따라서, 다루고자 하는 데이터(변수)와 다루는 연산(함수)를 하나로 캡슐화(encapsulation)하여 클래스로 표현
    - 모델링에서 중요시 하는 속성에 따라 클래스의 속성과 행동이 각각 달라짐
    
    ```python
    class test:
        pass
    class test2:
        pass
    
    class Person:
        pass
    bob = Person()
    cathy = Person()
    
    a = list()
    b = list()
    
    print(type(bob), type(cathy))
    print(type(a), type(b))
    
    //결과
    <class '__main__.Person'> <class '__main__.Person'>
    <class 'list'> <class 'list'>
    ```
    
3. 생성자(**init**)이해 및 사용하기
    
    ```python
    class Person:
        def __init__(self, name, age):
    #         print(self, 'is generated')
            self.name = name
            self.age = age
    # self뒤에있는것이 속성명이되고, (self, name, age)부분은 값만전달해주는 parameter임
    #(self, name, age)에서 name 과 age를 이름을 다르게 바꿔도 됨
    
    #     def __init__(self, n, a):
    #         print(self, 'is generated')
    #         self.name = n
    #         self.age = a
    p1 = Person('Bob', 30)
    p2 = Person('Kate', 20)
    
    print(p1.name, p1.age)
    print(p2.name ,p2.age)
    ```
    
4. self  키워드의 이해 및 사용하기
    
    ```python
    # self : 그 객체 스스로 자신을 말하는것
    # a라는 객체에 Person 이라는 클래스를 부여하고 그 클래스 안에 method 두가지를 만든것
    # a.sleep을 하면 self에 a라는 객체가 스스로 들어간다.
    
    class Person :
        def __init__(self, name, age):
            print('self:', self)
            self.name = name
            self.age = age
        def sleep(self):
            print('self:', self)
            print(self.name,'은 잠을 잡니다.')
    a = Person('Aron', 12)
    b = Person('Bob', 30)
    print(a)
    print(b)
    a.sleep()
    b.sleep()
    
    //결과
    self: <__main__.Person object at 0x0000013812962588>
    self: <__main__.Person object at 0x0000013812962648>
    <__main__.Person object at 0x0000013812962588>
    <__main__.Person object at 0x0000013812962648>
    self: <__main__.Person object at 0x0000013812962588>
    Aron 은 잠을 잡니다.
    self: <__main__.Person object at 0x0000013812962648>
    Bob 은 잠을 잡니다.
    
    ```
    
5. method, static method 정의 및 사용하기
    
    ```python
    
    ```
    
6. 클래스 상속의 이해 ( 코드를 재사용하기 2)
7. 클래스 연산자 재정의 이해 및 사용
8. 클래스 연습문제 풀이
