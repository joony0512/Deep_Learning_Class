## CH 01. 환경설정

파이썬 개발환경 설정

## CH 02. 데이터 타입과 컬렉션

list tuple dict set


//파이썬 개발환경 설정
# hello python
## hello
### hello
**python**
- 1
    - 1
        - 1
        
a=5
print(a)
> hihi

c= None
print(c)

a=1
b=1.1
print(a == b)


a = 9
#a = a-3
a-=3
print(a)

a **=3
print(a)

// 문자열 타입의 이해
c=""" Hello World 
It's nice day."""

print(c)

print('Hello World \n\n')


a='Hello World'
print(a[10])
print(a[-1])
print(a[11])
a[:5]

//문자열 함수
a.upper()
a.replace('H','j')

//format

temperature = 25.5
prob =80.0
a= '오늘 기온은 {}도 이고, 비올 확률은 {}% 입니다.'.format(temperature, prob)
print(a)

a= 'hello world what a nice day'
a.split()

a.split('w')

//list

a=[]
print(a)

a=[1,2,3,4,5]
print(a)

a='hello world'
b= list(a)
print(b)
c=(1,2,3)
d=list(b)
print(d)

a= [1,2,3,4,5]
print(a[2])
print(a[4])
print(a[-1])

a ='hello world'
print(a[0])

#a[0]='j' 안됨 불변이라
d= 'j'+a[1:]
print(d)

a = [1,2,3,4,5]
a[0]=100
print(a)

a=[1,2,3,4,5]
a.append(10)
print(a)

a=[1,2,3,4,5]
b=[6,7,8,9,10]
a.extend(b)
print(a)

a=[1,2,3,4,5]
b=[6,7,8,9,10]
a+=b
print(a)

a.insert(1,40)
print(a)

a = [1,2,3,4,5,6,10]
b=7
c= b in a #False
print(c)

a=[1,2,3,9]
a.index(9)

//sort

a.sort(reverse= False)
print(a)
b=sorted(a,reverse=True)
print(b)

//tuple

a=[1,2,3]
b=(1,2,3)
a[0]=100
b[0]=100
print(a,b)

a=(1,2,3)
type(a)

a,b= 100, 200
print(a, b)

a= 5
b=4
print(a,b)

#logic
temp=a
a=b
b=temp

print(a, b)

a= 5
b=4
print(a,b)

#logic
a, b = b, a

print(a, b)

//dictionary

a={"Korea":"Seoul","Canada":"ottawa"}
print(a["Korea"])
a["Japan"]="Tokyo"
print(a)

a= {'a':1, 'b':2, 'c':3}
b= {'a':4, 'd':5, 'e':7}
a.update(b)
print(a)

a= {'a':1, 'b':2, 'c':3}
a.pop('b')
print(a)

a= {'a':1, 'b':2, 'c':3}

del a['b']
print(a)

a= {'a':1, 'b':2, 'c':3}
print(a)
a.clear()
print(a)

a= {'a':1, 'b':2, 'c':3}
print(a)
'b' in a

print(a.get('d'))

print(a)

print(a.keys())

print(a.values())

print(list(a.keys()))

print(list(a.values()))

//set

a={1,2,3}
b={2,3,4}
print(type(a))
print(a.union(b))
print(a.intersection(b))
print(a.difference(b))
print(a.issubset(b))

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
